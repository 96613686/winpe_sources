# ResolverInitialize

- ea: `0x1800495c0`
- end: `0x180049fa3`
- name: `ResolverInitialize`
- size: `2531`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `44`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a000`

## callees

- `0x180005270`
- `0x180005370`
- `0x180008b00`
- `0x18002d4c0`
- `0x18002d6f8`
- `0x180030c2c`
- `0x1800319e0`
- `0x1800332a4`
- `0x18003546c`
- `0x1800355bc`
- `0x180035a34`
- `0x180035b6c`
- `0x18003621c`
- `0x18003cf9c`
- `0x18003d4b0`
- `0x18003db54`
- `0x18003db8c`
- `0x18003f95c`
- `0x18003fa20`
- `0x18003fa78`
- `0x18004016c`
- `0x180040280`
- `0x18004050c`
- `0x180040570`
- `0x18004067c`
- `0x18004076c`
- `0x180040858`
- `0x1800409d0`
- `0x180040a60`
- `0x180040d7c`
- `0x180046ec0`
- `0x180047818`
- `0x180048b44`
- `0x180049070`
- `0x180049214`
- `0x1800494f8`
- `0x1800495c0`
- `0x180055ac4`
- `0x18007863c`
- `0x180086700`
- `0x1800868b8`
- `0x180086b1c`
- `0x180086f24`
- `0x18008841c`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180049c65`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180049c65`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180049791`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180049791`
- `ntdll!RtlNtStatusToDosError` at `0x180049bf9`
- `ntdll!RtlNtStatusToDosError` at `0x180049c71`
- `ntdll!RtlNtStatusToDosError` at `0x180049bf9`
- `ntdll!RtlNtStatusToDosError` at `0x180049c71`
- `DNSAPI!Reg_ReadGlobalsEx` at `0x180049af1`
- `DNSAPI!Reg_ReadGlobalsEx` at `0x180049af1`
- `DNSAPI!DnsGlobals` at `0x180049af7`
- `DNSAPI!DnsTraceServerConfig` at `0x180049f38`
- `DNSAPI!DnsTraceServerConfig` at `0x180049f38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049a25`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004963f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800499d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049a04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049ec0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004963f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800499d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049a04`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049ec0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180049aab`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180049b58`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180049aab`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180049b58`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049f2a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049f2a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180049f08`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180049f08`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049f21`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049f21`
- `WS2_32!__imp_WSAStartup` at `0x180049962`
- `WS2_32!__imp_WSAStartup` at `0x180049962`
- `IPHLPAPI!GetDefaultCompartmentId` at `0x18004994c`
- `IPHLPAPI!GetDefaultCompartmentId` at `0x18004994c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180049727`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180049727`

## string_xrefs

- `0x1800496fe`: `dnscache`
- `0x180049657`: `CreateEvent for g_hStopServiceEvent failed`
- `0x18004973f`: `Call to RegisterServiceCtrlHandlerW failed!`
- `0x1800498e0`: `Cache_GCTimerInit failed`
- `0x1800499ed`: `CreateEvent() failed`
- `0x180049a2b`: `CreateEvent() failed`
- `0x180049ddf`: `Register Stop Service failed`

## pseudocode

```c
__int64 __fastcall ResolverInitialize(__int64 a1, char a2)
{
  CWxGlobalCounters *v4; // rcx
  DWORD LastError; // eax
  const char *v6; // r9
  DWORD v7; // ebx
  __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  DWORD v12; // eax
  __int64 v13; // r8
  __int64 *v14; // rdx
  DWORD v15; // eax
  int v16; // eax
  CRpcWatchDog *v17; // rcx
  unsigned int v18; // ebx
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rcx
  DWORD inited; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  DWORD v33; // eax
  unsigned int v34; // eax
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v36; // rbx
  CRpcWatchDog *v37; // rcx
  _DWORD v39[4]; // [rsp+40h] [rbp-208h] BYREF
  struct WSAData WSAData; // [rsp+50h] [rbp-1F8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  g_ResolverStatus = 213909504;
  v39[0] = 0;
  g_InitState = 0;
  g_fStopFlag = 0;
  g_hStopEvent = 0;
  g_fServiceControlHandled = 0;
  g_BackgroundThreadCount = 0;
  _InterlockedExchange(&g_dwServiceControlFlags, 0);
  g_hStopServiceEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hStopServiceEvent )
  {
    LastError = GetLastError();
    v6 = "CreateEvent for g_hStopServiceEvent failed";
LABEL_3:
    v7 = LastError;
    v8 = LastError;
LABEL_111:
    v13 = 0;
    v14 = 0;
    goto LABEL_112;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 39, WPP_baf6623f38bf314eb96485734268b87e_Traceguids);
  v9 = CWxGlobalCounters::InitializeForWrite(v4);
  v10 = v9;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 10, WPP_ae2cdafdc45d36790eff36519d0aacfd_Traceguids, v9);
  v11 = WX_WIN32_FROM_HR(v10);
  if ( v11 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 40, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v11);
  IncrementGlobalCountersProxyCacheVersion();
  ServiceStatusHandle = 0;
  ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwCheckPoint = 0;
  ServiceStatus.dwWaitHint = 5000;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"dnscache", ResolverControlHandler, 0);
  if ( !ServiceStatusHandle )
  {
    v12 = GetLastError();
    v6 = "Call to RegisterServiceCtrlHandlerW failed!";
    v13 = 728261459;
    v7 = v12;
    v14 = DNS_CACHE_START_FAILURE_LOW_MEMORY;
    v8 = v12;
LABEL_112:
    ResolverInitFailure(v8, v14, v13, v6);
    return v7;
  }
  g_ResolverStatus = 213909516;
  ResolverUpdateStatus();
  if ( !g_fVelocityLockGeneralCleanup )
  {
    g_IpNotifyThread = 0;
    g_IpNotifyThreadId = 0;
    g_IpNotifyEvent = 0;
  }
  g_ResolverStatus = 213909505;
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 41, WPP_baf6623f38bf314eb96485734268b87e_Traceguids);
    g_IsArgon = 1;
  }
  if ( !g_fVelocityDisableInternalExports )
    GetXboxProductType();
  v15 = OpenRegistryPaths();
  v7 = v15;
  if ( v15 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 42, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v15);
    goto LABEL_109;
  }
  v16 = CRpcWatchDog::Start();
  v18 = v16;
  if ( v16 < 0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 43, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, (unsigned int)v16);
    LastError = WX_WIN32_FROM_HR(v18);
    v6 = "RpcWatchDogInitialize failed";
    goto LABEL_3;
  }
  g_ServiceInitializeWDEntry = ResolverInitialize;
  CRpcWatchDog::AddEntry(v17, (struct _WatchDogEntry *)&g_ServiceInitializeWDEntry, 0);
  LogEventInMemory(726877001, 0);
  if ( !(unsigned int)InitializeFirewallState() )
    g_InitState |= 0x200000u;
  if ( a2 )
    _InterlockedOr(&g_InitState, 0x400000u);
  LogEventInMemory(760431433, 0);
  v19 = PriorityCache_Initialize();
  v7 = v19;
  if ( v19 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 44, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v19);
LABEL_109:
    v6 = "ResolverInitialize failed";
    goto LABEL_110;
  }
  g_InitState |= 0x8000000u;
  UnreachableServerCache_Initialize();
  v20 = Cache_GCTimerInit();
  v7 = v20;
  if ( v20 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 45, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v20);
    v6 = "Cache_GCTimerInit failed";
    goto LABEL_110;
  }
  GetEnforceMitigationsRegValue(v39);
  v7 = EnableMitigations(v39[0]);
  if ( v7 )
    goto LABEL_109;
  v21 = Hijack_Initialize();
  v7 = v21;
  if ( v21 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 46, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v21);
    v6 = "Hijack Initialize failed";
    goto LABEL_110;
  }
  g_InitState |= 0x2000000u;
  g_DefaultCompartmentId = GetDefaultCompartmentId();
  v22 = WSAStartup(0x202u, &WSAData);
  v7 = v22;
  if ( v22 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 47, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v22);
    v6 = "Winsock Startup failed";
    goto LABEL_110;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Dd(v23, 48, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, WSAData.wHighVersion, WSAData.wVersion);
  g_InitState |= 0x10u;
  g_hStopEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hStopEvent )
  {
    LastError = GetLastError();
    v6 = "CreateEvent() failed";
    goto LABEL_3;
  }
  g_hBackgroundThreadWaitEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hBackgroundThreadWaitEvent )
  {
    v7 = GetLastError();
    CloseHandle(g_hStopEvent);
    v6 = "CreateEvent() failed";
    g_hStopEvent = 0;
LABEL_110:
    v8 = v7;
    goto LABEL_111;
  }
  g_ResolverStatus = 213909507;
  g_InitState |= 0x20u;
  inited = InitDnsApi();
  v7 = inited;
  if ( inited )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 49, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, inited);
    v6 = "DNSAPI Init failed";
    goto LABEL_110;
  }
  g_InitState |= 0x1000000u;
  ResolverUpdateStatus();
  InitializeResolverFastWppCallback();
  InitializeSRWLock(&SRWLock);
  qword_1800ABD58 = 0;
  dword_1800ABC2C = 0;
  dword_1800ABC28 = 0;
  dword_1800ABD64 = 0;
  dword_1800ABD60 = 0;
  dword_1800ABCE8 = 0;
  dword_1800ABCEC = 0;
  g_InitState |= 0x4000000u;
  Reg_ReadGlobalsEx(1, 0);
  DnsGlobals[2] = 1;
  v7 = InitZtdns();
  if ( v7 )
    goto LABEL_109;
  g_ResolverStatus = 213909519;
  g_InitState |= 0x40000000u;
  ResolverUpdateStatus();
  v7 = Cache_Alloc(0);
  if ( v7 )
    goto LABEL_109;
  g_InitState |= 0x100u;
  InitializeSRWLock(&stru_1800ABCA8);
  g_fVPNTriggerInitialized = 1;
  StartNotify();
  g_ResolverStatus = 213909510;
  g_InitState |= 0x1000u;
  ResolverUpdateStatus();
  g_ResolverStatus = 213909511;
  g_InitState |= 0x2000u;
  ResolverUpdateStatus();
  v7 = RpcConcurrentQueriesInitialize();
  if ( v7 )
    goto LABEL_109;
  g_InitState |= 0x80000000;
  LogEventInMemory(727937106, 0);
  if ( (unsigned int)RegReadContainerResolutionFlag() || (unsigned int)RegReadHvsiContainerOverideFlag() )
  {
    v29 = HvsiLRpcInitialize();
    if ( v29 < 0 )
    {
      LastError = RtlNtStatusToDosError(v29);
      v6 = "HvsiRpc init failed.";
      goto LABEL_3;
    }
    v28 = 1;
    g_fHvsiActive = 1;
  }
  else
  {
    v28 = (unsigned int)g_fHvsiActive;
  }
  if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    WPP_SF_d(1055, 51, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v28);
  if ( (unsigned int)RegReadContainerWaitForRestoreFlag(v26, v25, v27, v28) )
  {
    v30 = RtlSubscribeWnfStateChangeNotification(
            &qword_1800AB5B0,
            WNF_CONT_RESTORE_FROM_SNAPSHOT_COMPLETE,
            0,
            WaitForRestoreCallback,
            0,
            0,
            0,
            0);
    if ( v30 < 0 )
    {
      LastError = RtlNtStatusToDosError(v30);
      v6 = "Restore from snapshot WNF subscription failed";
      goto LABEL_3;
    }
  }
  v31 = MDns_Initialize();
  if ( v31 )
  {
    ResolverInitFailureNoShutdown(v31, 0, 0, "mDNS listen init failed");
  }
  else
  {
    g_ResolverStatus = 213909517;
    g_InitState |= 0x10000000u;
  }
  ResolverUpdateStatus();
  v7 = InitIpListAndNotification();
  if ( v7 )
  {
    v6 = "IP list init failed";
    goto LABEL_110;
  }
  g_ResolverStatus = 213909512;
  g_InitState |= 0x4000u;
  ResolverUpdateStatus();
  v32 = Mcast_Startup();
  if ( v32 )
  {
    ResolverInitFailureNoShutdown(v32, 0, 0, "Multicast listen init failed");
  }
  else
  {
    g_ResolverStatus = 213909513;
    g_InitState |= 0x8000u;
  }
  ResolverUpdateStatus();
  v33 = Rpc_Initialize();
  v7 = v33;
  if ( v33 )
  {
    LogEventInMemory(1952543827, v33);
    if ( v7 != 1712 && v7 != -1073610739 )
    {
      if ( SBYTE3(xmmword_1800AB5A0) < 0 )
        WPP_SF_DS(1055, 53, (unsigned int)WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v7, (__int64)L"DNSResolver");
      v6 = "Call to StartRpcServer failed!";
      v13 = 0;
      v14 = DNS_CACHE_START_FAILURE_NO_RPC;
      v8 = v7;
      goto LABEL_112;
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 52, WPP_baf6623f38bf314eb96485734268b87e_Traceguids);
  }
  g_ResolverStatus = 213909514;
  g_InitState |= 0x100000u;
  ResolverUpdateStatus();
  v7 = RegisterStopService(a1);
  if ( v7 )
  {
    v6 = "Register Stop Service failed";
    goto LABEL_110;
  }
  g_ResolverStatus = 213909515;
  g_InitState |= 0x10000u;
  ResolverUpdateStatus();
  if ( !(unsigned int)Util_IsRunningOnXboxGameOS() )
  {
    v34 = NRP_Initialize();
    if ( v34 )
    {
      ResolverInitFailureNoShutdown(v34, 0, 0, "NRP Initialization Failed");
    }
    else
    {
      g_ResolverStatus = 213909518;
      g_InitState |= 0x20000000u;
    }
    ResolverUpdateStatus();
  }
  ServiceStatus.dwCurrentState = 4;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 88;
  ServiceStatus.dwWaitHint = 0;
  if ( g_fVelocityDynamicRegStartup )
    g_ResolverStatus = 213909760;
  ResolverUpdateStatus();
  if ( !g_fVelocityDynamicRegStartup )
    g_ResolverStatus = 213909760;
  LogEventInMemory(1918989395, 0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 54, WPP_baf6623f38bf314eb96485734268b87e_Traceguids);
  hObject = CreateEventW(0, 0, 0, 0);
  if ( hObject || !GetLastError() )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_q(1035, 15, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, 0);
    ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)InterceptionInit_Work, 0, 0);
    v36 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v36);
    }
    else
    {
      GetLastError();
    }
  }
  DnsTraceServerConfig(0, 1, 1);
  CRpcWatchDog::RemoveEntry(v37, (struct _WatchDogEntry *)&g_ServiceInitializeWDEntry);
  return 0;
}

```

## disassembly

```asm
0x1800495c0  push    rbx
0x1800495c2  push    rbp
0x1800495c3  push    rsi
0x1800495c4  push    rdi
0x1800495c5  push    r12
0x1800495c7  push    r13
0x1800495c9  push    r14
0x1800495cb  push    r15
0x1800495cd  sub     rsp, 208h
0x1800495d4  mov     rax, cs:__security_cookie
0x1800495db  xor     rax, rsp
0x1800495de  mov     [rsp+248h+var_58], rax
0x1800495e6  mov     dil, dl
0x1800495e9  mov     rsi, rcx
0x1800495ec  xor     edx, edx; Val
0x1800495ee  lea     rcx, [rsp+248h+WSAData]; void *
0x1800495f3  mov     r8d, 198h; Size
0x1800495f9  call    memset_0
0x1800495fe  xor     ebp, ebp
0x180049600  mov     cs:g_ResolverStatus, 0CC00000h
0x18004960a  mov     [rsp+248h+var_208], ebp
0x18004960e  mov     eax, ebp
0x180049610  mov     cs:g_InitState, ebp
0x180049616  xor     r9d, r9d; lpName
0x180049619  mov     cs:g_fStopFlag, ebp
0x18004961f  xor     r8d, r8d; bInitialState
0x180049622  mov     cs:g_hStopEvent, rbp
0x180049629  xor     edx, edx; bManualReset
0x18004962b  mov     cs:g_fServiceControlHandled, ebp
0x180049631  xor     ecx, ecx; lpEventAttributes
0x180049633  mov     cs:g_BackgroundThreadCount, ebp
0x180049639  xchg    eax, cs:g_dwServiceControlFlags
0x18004963f  call    cs:__imp_CreateEventW
0x180049645  mov     cs:g_hStopServiceEvent, rax
0x18004964c  test    rax, rax
0x18004964f  jnz     short loc_180049667
0x180049651  call    cs:__imp_GetLastError
0x180049657  lea     r9, aCreateeventFor; "CreateEvent for g_hStopServiceEvent fai"...
0x18004965e  mov     ebx, eax
0x180049660  mov     ecx, eax
0x180049662  jmp     loc_180049F73
0x180049667  mov     r14b, 8
0x18004966a  lea     r15, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x180049671  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x180049678  mov     r12d, 40Bh
0x18004967e  jz      short loc_180049690
0x180049680  mov     edx, 27h ; '''
0x180049685  mov     ecx, r12d
0x180049688  mov     r8, r15
0x18004968b  call    WPP_SF_
0x180049690  call    ?InitializeForWrite@CWxGlobalCounters@@QEAAJXZ; CWxGlobalCounters::InitializeForWrite(void)
0x180049695  mov     ebx, eax
0x180049697  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x18004969e  jz      short loc_1800496B7
0x1800496a0  mov     edx, 0Ah
0x1800496a5  lea     r8, WPP_ae2cdafdc45d36790eff36519d0aacfd_Traceguids
0x1800496ac  mov     ecx, r12d
0x1800496af  mov     r9d, eax
0x1800496b2  call    WPP_SF_d
0x1800496b7  mov     ecx, ebx
0x1800496b9  call    WX_WIN32_FROM_HR
0x1800496be  test    eax, eax
0x1800496c0  jz      short loc_1800496DE
0x1800496c2  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x1800496c9  jz      short loc_1800496DE
0x1800496cb  mov     edx, 28h ; '('
0x1800496d0  mov     ecx, r12d
0x1800496d3  mov     r9d, eax
0x1800496d6  mov     r8, r15
0x1800496d9  call    WPP_SF_d
0x1800496de  call    IncrementGlobalCountersProxyCacheVersion
0x1800496e3  xor     r8d, r8d; lpContext
0x1800496e6  mov     cs:ServiceStatusHandle, rbp
0x1800496ed  lea     rdx, ResolverControlHandler; lpHandlerProc
0x1800496f4  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x1800496fe  lea     rcx, ServiceName; "dnscache"
0x180049705  mov     qword ptr cs:ServiceStatus.dwCurrentState, 2
0x180049710  mov     cs:ServiceStatus.dwCheckPoint, ebp
0x180049716  mov     cs:ServiceStatus.dwWaitHint, 1388h
0x180049720  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, rbp
0x180049727  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18004972d  mov     cs:ServiceStatusHandle, rax
0x180049734  test    rax, rax
0x180049737  jnz     short loc_18004975C
0x180049739  call    cs:__imp_GetLastError
0x18004973f  lea     r9, aCallToRegister; "Call to RegisterServiceCtrlHandlerW fai"...
0x180049746  mov     r8d, 2B686353h
0x18004974c  mov     ebx, eax
0x18004974e  lea     rdx, DNS_CACHE_START_FAILURE_LOW_MEMORY
0x180049755  mov     ecx, eax
0x180049757  jmp     loc_180049F78
0x18004975c  mov     cs:g_ResolverStatus, 0CC0000Ch
0x180049766  call    ResolverUpdateStatus
0x18004976b  cmp     cs:g_fVelocityLockGeneralCleanup, ebp
0x180049771  jnz     short loc_180049787
0x180049773  mov     cs:g_IpNotifyThread, rbp
0x18004977a  mov     cs:g_IpNotifyThreadId, ebp
0x180049780  mov     cs:g_IpNotifyEvent, rbp
0x180049787  mov     cs:g_ResolverStatus, 0CC00001h
0x180049791  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180049797  mov     r13d, 1
0x18004979d  test    eax, eax
0x18004979f  jz      short loc_1800497C0
0x1800497a1  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x1800497a8  jz      short loc_1800497B9
0x1800497aa  lea     edx, [r13+28h]
0x1800497ae  mov     ecx, r12d
0x1800497b1  mov     r8, r15
0x1800497b4  call    WPP_SF_
0x1800497b9  mov     cs:g_IsArgon, r13d
0x1800497c0  cmp     cs:g_fVelocityDisableInternalExports, ebp
0x1800497c6  jnz     short loc_1800497CD
0x1800497c8  call    GetXboxProductType
0x1800497cd  call    OpenRegistryPaths
0x1800497d2  mov     ebx, eax
0x1800497d4  test    eax, eax
0x1800497d6  jnz     loc_180049F4E
0x1800497dc  call    ?Start@CRpcWatchDog@@QEAAJW4_WatchDogReportType@@@Z; CRpcWatchDog::Start(_WatchDogReportType)
0x1800497e1  mov     ebx, eax
0x1800497e3  test    eax, eax
0x1800497e5  jns     short loc_180049816
0x1800497e7  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x1800497ee  jz      short loc_180049803
0x1800497f0  mov     edx, 2Bh ; '+'
0x1800497f5  mov     ecx, r12d
0x1800497f8  mov     r9d, eax
0x1800497fb  mov     r8, r15
0x1800497fe  call    WPP_SF_d
0x180049803  mov     ecx, ebx
0x180049805  call    WX_WIN32_FROM_HR
0x18004980a  lea     r9, aRpcwatchdogini; "RpcWatchDogInitialize failed"
0x180049811  jmp     loc_18004965E
0x180049816  lea     rax, ResolverInitialize
0x18004981d  xor     r8d, r8d; int
0x180049820  lea     rdx, g_ServiceInitializeWDEntry; struct _WatchDogEntry *
0x180049827  mov     cs:g_ServiceInitializeWDEntry, rax
0x18004982e  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x180049833  xor     edx, edx
0x180049835  mov     ecx, 2B534349h
0x18004983a  call    LogEventInMemory
0x18004983f  call    InitializeFirewallState
0x180049844  test    eax, eax
0x180049846  jnz     short loc_180049858
0x180049848  mov     eax, cs:g_InitState
0x18004984e  bts     eax, 15h
0x180049852  mov     cs:g_InitState, eax
0x180049858  test    dil, dil
0x18004985b  jz      short loc_180049868
0x18004985d  lock or cs:g_InitState, 400000h
0x180049868  xor     edx, edx
0x18004986a  mov     ecx, 2D534349h
0x18004986f  call    LogEventInMemory
0x180049874  call    PriorityCache_Initialize
0x180049879  mov     ebx, eax
0x18004987b  test    eax, eax
0x18004987d  jz      short loc_1800498A4
0x18004987f  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x180049886  jz      loc_180049F6A
0x18004988c  mov     edx, 2Ch ; ','
0x180049891  mov     ecx, r12d
0x180049894  mov     r9d, eax
0x180049897  mov     r8, r15
0x18004989a  call    WPP_SF_d
0x18004989f  jmp     loc_180049F6A
0x1800498a4  mov     eax, cs:g_InitState
0x1800498aa  bts     eax, 1Bh
0x1800498ae  mov     cs:g_InitState, eax
0x1800498b4  call    UnreachableServerCache_Initialize
0x1800498b9  call    Cache_GCTimerInit
0x1800498be  mov     ebx, eax
0x1800498c0  test    eax, eax
0x1800498c2  jz      short loc_1800498EC
0x1800498c4  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x1800498cb  jz      short loc_1800498E0
0x1800498cd  mov     edx, 2Dh ; '-'
0x1800498d2  mov     ecx, r12d
0x1800498d5  mov     r9d, eax
0x1800498d8  mov     r8, r15
0x1800498db  call    WPP_SF_d
0x1800498e0  lea     r9, aCacheGctimerin; "Cache_GCTimerInit failed"
0x1800498e7  jmp     loc_180049F71
0x1800498ec  lea     rcx, [rsp+248h+var_208]
0x1800498f1  call    GetEnforceMitigationsRegValue
0x1800498f6  mov     ecx, [rsp+248h+var_208]
0x1800498fa  call    EnableMitigations
0x1800498ff  mov     ebx, eax
0x180049901  test    eax, eax
0x180049903  jnz     loc_180049F6A
0x180049909  call    Hijack_Initialize
0x18004990e  mov     ebx, eax
0x180049910  test    eax, eax
0x180049912  jz      short loc_18004993C
0x180049914  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x18004991b  jz      short loc_180049930
0x18004991d  mov     edx, 2Eh ; '.'
0x180049922  mov     ecx, r12d
0x180049925  mov     r9d, eax
0x180049928  mov     r8, r15
0x18004992b  call    WPP_SF_d
0x180049930  lea     r9, aHijackInitiali; "Hijack Initialize failed"
0x180049937  jmp     loc_180049F71
0x18004993c  mov     eax, cs:g_InitState
0x180049942  bts     eax, 19h
0x180049946  mov     cs:g_InitState, eax
0x18004994c  call    cs:__imp_GetDefaultCompartmentId
0x180049952  mov     ecx, 202h; wVersionRequested
0x180049957  lea     rdx, [rsp+248h+WSAData]; lpWSAData
0x18004995c  mov     cs:g_DefaultCompartmentId, eax
0x180049962  call    cs:__imp_WSAStartup
0x180049968  mov     ebx, eax
0x18004996a  test    eax, eax
0x18004996c  jz      short loc_180049996
0x18004996e  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x180049975  jz      short loc_18004998A
0x180049977  mov     edx, 2Fh ; '/'
0x18004997c  mov     ecx, r12d
0x18004997f  mov     r9d, eax
0x180049982  mov     r8, r15
0x180049985  call    WPP_SF_d
0x18004998a  lea     r9, aWinsockStartup; "Winsock Startup failed"
0x180049991  jmp     loc_180049F71
0x180049996  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x18004999d  jz      short loc_1800499BB
0x18004999f  movzx   eax, [rsp+248h+WSAData.wVersion]
0x1800499a4  mov     edx, 30h ; '0'
0x1800499a9  movzx   r9d, [rsp+248h+WSAData.wHighVersion]
0x1800499af  mov     r8, r15
0x1800499b2  mov     dword ptr [rsp+248h+var_228], eax
0x1800499b6  call    WPP_SF_Dd
0x1800499bb  mov     eax, cs:g_InitState
0x1800499c1  xor     r9d, r9d; lpName
0x1800499c4  or      eax, 10h
0x1800499c7  xor     r8d, r8d; bInitialState
0x1800499ca  mov     edx, r13d; bManualReset
0x1800499cd  mov     cs:g_InitState, eax
0x1800499d3  xor     ecx, ecx; lpEventAttributes
0x1800499d5  call    cs:__imp_CreateEventW
0x1800499db  mov     cs:g_hStopEvent, rax
0x1800499e2  test    rax, rax
0x1800499e5  jnz     short loc_1800499F9
0x1800499e7  call    cs:__imp_GetLastError
0x1800499ed  lea     r9, aCreateeventFai; "CreateEvent() failed"
0x1800499f4  jmp     loc_18004965E
0x1800499f9  xor     r9d, r9d; lpName
0x1800499fc  xor     r8d, r8d; bInitialState
0x1800499ff  mov     edx, r13d; bManualReset
0x180049a02  xor     ecx, ecx; lpEventAttributes
0x180049a04  call    cs:__imp_CreateEventW
0x180049a0a  mov     cs:g_hBackgroundThreadWaitEvent, rax
0x180049a11  test    rax, rax
0x180049a14  jnz     short loc_180049A3E
0x180049a16  call    cs:__imp_GetLastError
0x180049a1c  mov     rcx, cs:g_hStopEvent; hObject
0x180049a23  mov     ebx, eax
0x180049a25  call    cs:__imp_CloseHandle
0x180049a2b  lea     r9, aCreateeventFai; "CreateEvent() failed"
0x180049a32  mov     cs:g_hStopEvent, rbp
0x180049a39  jmp     loc_180049F71
0x180049a3e  mov     eax, cs:g_InitState
0x180049a44  or      eax, 20h
0x180049a47  mov     cs:g_ResolverStatus, 0CC00003h
0x180049a51  mov     cs:g_InitState, eax
0x180049a57  call    InitDnsApi
0x180049a5c  mov     ebx, eax
0x180049a5e  test    eax, eax
0x180049a60  jz      short loc_180049A8A
0x180049a62  test    byte ptr cs:xmmword_1800AB5A0+1, r14b
0x180049a69  jz      short loc_180049A7E
0x180049a6b  mov     edx, 31h ; '1'
0x180049a70  mov     ecx, r12d
0x180049a73  mov     r9d, eax
0x180049a76  mov     r8, r15
0x180049a79  call    WPP_SF_d
0x180049a7e  lea     r9, aDnsapiInitFail; "DNSAPI Init failed"
0x180049a85  jmp     loc_180049F71
0x180049a8a  mov     eax, cs:g_InitState
0x180049a90  bts     eax, 18h
0x180049a94  mov     cs:g_InitState, eax
0x180049a9a  call    ResolverUpdateStatus
0x180049a9f  call    InitializeResolverFastWppCallback
0x180049aa4  lea     rcx, SRWLock; SRWLock
0x180049aab  call    cs:__imp_InitializeSRWLock
0x180049ab1  mov     eax, cs:g_InitState
0x180049ab7  xor     edx, edx
0x180049ab9  bts     eax, 1Ah
0x180049abd  mov     cs:qword_1800ABD58, rbp
0x180049ac4  mov     cs:dword_1800ABC2C, ebp
0x180049aca  mov     ecx, r13d
0x180049acd  mov     cs:dword_1800ABC28, ebp
0x180049ad3  mov     cs:dword_1800ABD64, ebp
0x180049ad9  mov     cs:dword_1800ABD60, ebp
0x180049adf  mov     cs:dword_1800ABCE8, ebp
0x180049ae5  mov     cs:dword_1800ABCEC, ebp
0x180049aeb  mov     cs:g_InitState, eax
0x180049af1  call    cs:__imp_Reg_ReadGlobalsEx
0x180049af7  mov     rax, cs:__imp_DnsGlobals
0x180049afe  mov     [rax+8], r13d
0x180049b02  call    InitZtdns
0x180049b07  mov     ebx, eax
0x180049b09  test    eax, eax
  ... truncated ...
```
