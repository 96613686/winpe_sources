# Initialize

- ea: `0x180025144`
- end: `0x180026585`
- name: `Initialize`
- size: `5185`
- prototype: `HRESULT __cdecl()`
- caller_count: `1`
- callee_count: `54`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180024e18`

## callees

- `0x180002318`
- `0x18000282c`
- `0x180003228`
- `0x1800038f0`
- `0x18000601c`
- `0x18000d644`
- `0x18000eb90`
- `0x18001089c`
- `0x180012c90`
- `0x180013f20`
- `0x180016a74`
- `0x18001bf88`
- `0x18001c860`
- `0x18001cd4c`
- `0x18001cdc8`
- `0x18001dfc8`
- `0x18001e5fc`
- `0x18001ea70`
- `0x18002153c`
- `0x180021a98`
- `0x180024de8`
- `0x180025144`
- `0x18002658c`
- `0x1800266c4`
- `0x1800268c4`
- `0x180026d78`
- `0x180027dcc`
- `0x18003070c`
- `0x180034480`
- `0x180045b6c`
- `0x18004700c`
- `0x18005546c`
- `0x1800626dc`
- `0x180062c84`
- `0x180063b1c`
- `0x180067d7c`
- `0x180079404`
- `0x18007bf3c`
- `0x18007d47c`
- `0x180084600`
- `0x18008f0b4`
- `0x18008f1c0`
- `0x18009078c`
- `0x18009c650`
- `0x1800a0058`
- `0x1800a0ce8`
- `0x1800b62ac`
- `0x1800ba6b8`
- `0x1800ba71c`
- `0x1800ba924`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180025a05`
- `ntdll!RtlNtStatusToDosError` at `0x180025a05`
- `ADVAPI32!RegSetValueExW` at `0x180025ddb`
- `ADVAPI32!RegSetValueExW` at `0x180025ddb`
- `ADVAPI32!CryptAcquireContextW` at `0x1800262d2`
- `ADVAPI32!CryptAcquireContextW` at `0x1800262d2`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x1800251bc`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x1800251bc`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18002545c`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18002545c`
- `WS2_32!__imp_inet_ntoa` at `0x180025bef`
- `WS2_32!__imp_inet_ntoa` at `0x180025c6b`
- `WS2_32!__imp_inet_ntoa` at `0x180025bef`
- `WS2_32!__imp_inet_ntoa` at `0x180025c6b`
- `WS2_32!__imp_WSAStartup` at `0x18002593e`
- `WS2_32!__imp_WSAStartup` at `0x18002593e`
- `DSAUTH!DhcpDsInitDS` at `0x1800259e9`
- `DSAUTH!DhcpDsInitDS` at `0x1800259e9`
- `KERNEL32!CreateEventW` at `0x180025600`
- `KERNEL32!CreateEventW` at `0x1800257fc`
- `KERNEL32!CreateEventW` at `0x180025857`
- `KERNEL32!CreateEventW` at `0x180026371`
- `KERNEL32!CreateEventW` at `0x180025600`
- `KERNEL32!CreateEventW` at `0x1800257fc`
- `KERNEL32!CreateEventW` at `0x180025857`
- `KERNEL32!CreateEventW` at `0x180026371`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002547e`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800254a2`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800254c6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800254ea`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002552c`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025550`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025574`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002547e`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800254a2`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800254c6`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800254ea`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002552c`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025550`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025574`
- `KERNEL32!HeapAlloc` at `0x180025b66`
- `KERNEL32!HeapAlloc` at `0x180025b66`
- `KERNEL32!GetProcessHeap` at `0x180025b4f`
- `KERNEL32!GetProcessHeap` at `0x180025b4f`
- `KERNEL32!DeleteCriticalSection` at `0x180025f64`
- `KERNEL32!DeleteCriticalSection` at `0x180025f64`
- `KERNEL32!GetLastError` at `0x1800251d4`
- `KERNEL32!GetLastError` at `0x18002561c`
- `KERNEL32!GetLastError` at `0x180025652`
- `KERNEL32!GetLastError` at `0x18002569e`
- `KERNEL32!GetLastError` at `0x1800256d4`
- `KERNEL32!GetLastError` at `0x18002570d`
- `KERNEL32!GetLastError` at `0x180025746`
- `KERNEL32!GetLastError` at `0x18002577f`
- `KERNEL32!GetLastError` at `0x1800257b8`
- `KERNEL32!GetLastError` at `0x180025814`
- `KERNEL32!GetLastError` at `0x18002586f`
- `KERNEL32!GetLastError` at `0x180026389`
- `KERNEL32!GetLastError` at `0x1800251d4`
- `KERNEL32!GetLastError` at `0x18002561c`
- `KERNEL32!GetLastError` at `0x180025652`
- `KERNEL32!GetLastError` at `0x18002569e`
- `KERNEL32!GetLastError` at `0x1800256d4`
- `KERNEL32!GetLastError` at `0x18002570d`
- `KERNEL32!GetLastError` at `0x180025746`
- `KERNEL32!GetLastError` at `0x18002577f`
- `KERNEL32!GetLastError` at `0x1800257b8`
- `KERNEL32!GetLastError` at `0x180025814`
- `KERNEL32!GetLastError` at `0x18002586f`
- `KERNEL32!GetLastError` at `0x180026389`

## pseudocode

```c
HRESULT __cdecl Initialize()
{
  char v0; // dl
  char v1; // cl
  char v2; // r15
  char v3; // r12
  unsigned int v4; // r13d
  DWORD LastError; // eax
  DWORD Strings; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  ULONG64 *v9; // rbx
  const GUID **v10; // rdi
  const GUID *v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD v14; // eax
  unsigned int v15; // eax
  DWORD v16; // eax
  NTSTATUS WellKnownSids; // eax
  unsigned int v18; // r12d
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 AlternateDnsServerList; // rax
  int v23; // r15d
  __int64 v24; // r13
  unsigned int v25; // r8d
  unsigned int v26; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v28; // rax
  _DWORD *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  int v33; // ecx
  unsigned int v34; // r15d
  int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // r15d
  __int64 v39; // r12
  __int64 v40; // rcx
  DWORD v41; // eax
  DWORD v42; // eax
  DWORD v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // ebx
  DWORD v46; // eax
  DWORD v47; // eax
  DWORD v48; // eax
  JET_DBID v49; // r12d
  JET_SESID v50; // r15
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  DWORD v54; // eax
  DWORD v55; // eax
  __int64 v57; // [rsp+48h] [rbp-C0h] BYREF
  char *v58; // [rsp+50h] [rbp-B8h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v60[8]; // [rsp+68h] [rbp-A0h] BYREF
  int v61; // [rsp+ACh] [rbp-5Ch]
  WSAData WSAData; // [rsp+B8h] [rbp-50h] BYREF

  v2 = v0;
  v3 = v1;
  memset_0(&WSAData, 0, sizeof(WSAData));
  v58 = 0;
  v4 = 0;
  v57 = 0;
  gHAlgorithm = 0;
  DhcpGlobalServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"DhcpServer", ServiceControlHandler, 0);
  if ( !DhcpGlobalServiceStatusHandle )
  {
    LastError = GetLastError();
    Strings = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, LastError);
    v7 = 1001;
    goto LABEL_6;
  }
  DhcpGlobalServiceStatus.dwServiceType = 16;
  DhcpGlobalServiceStatus.dwCheckPoint = 1;
  *(_QWORD *)&DhcpGlobalServiceStatus.dwCurrentState = 2;
  DhcpGlobalServiceStatus.dwWaitHint = 18000000;
  *(_QWORD *)&DhcpGlobalServiceStatus.dwWin32ExitCode = 0;
  UpdateStatus();
  if ( !v2 )
  {
    DhcpGlobalOkToService = 0;
    *(_DWORD *)&DhcpGlobalServerPort = 67;
    DhcpGlobalClientPort = 68;
  }
  if ( v3 )
  {
    DhcpGlobalServiceStopping = 0;
    DhcpGlobalScavengeIpAddressInterval = 3600000;
    DhcpGlobalScavengeStatelessInterval = 3600000;
    DhcpLeaseExtension = 0;
    DhcpGlobalCleanupInterval = 10800000;
    DhcpGlobalRpcProtocols = 0;
    DhcpGlobalScavengeIpAddress = 0;
    DhcpGlobalIsStatelessTestEnv = 0;
    DhcpGlobalDetectConflictRetries = 0;
    DhcpGlobalBackupInterval = 900000;
    DhcpGlobalDatabaseLoggingFlag = 1;
    *(_DWORD *)&DhcpGlobalRestoreFlag = 0;
    DhcpGlobalAuditLogFlag = 1;
    DhcpGlobalRegQuarantineOn = 0;
    DhcpGlobalFirstTimeInitIAS = 1;
    DhcpGlobalQuarUserClassOnly = 1;
    DhcpGlobalQuarContextHandle = 0;
    DhcpComInitialized = 0;
    DhcpComNeedCleanUp = 0;
    DhcpGlobalIasDelay = 2000;
    DhcpGlobalRecomputeTimerEvent = 0;
    DhcpGlobalRpcStarted = 0;
    DhcpGlobalOemDatabasePath = 0;
    DhcpGlobalOemBackupPath = 0;
    DhcpGlobalOemRestorePath = 0;
    DhcpGlobalOemJetBackupPath = 0;
    DhcpGlobalOemJetRestorePath = 0;
    DhcpGlobalOemDatabaseName = 0;
    DhcpGlobalBackupConfigFileName = 0;
    DhcpGlobalRegRoot = 0;
    DhcpGlobalRegParam = 0;
    DhcpGlobalServicePrivateData = 0;
    DhcpGlobalDSDomainAnsi = 0;
    DhcpGlobalJetServerSession = 0;
    DhcpGlobalDatabaseHandle = 0;
    DhcpGlobalClientTableHandle = 0;
    DhcpGlobalClientTable = 0;
    DhcpGlobalScavengerTimeout = 0;
    DhcpGlobalProcessTerminationEvent = 0;
    DhcpGlobalRogueWaitEvent = 0;
    DhcpGlobalNumberOfNetsActive = 0;
    DhcpGlobalBindingsAware = 1;
    DhcpGlobalImpersonated = 0;
    DhcpGlobalDirSecurityDescriptor = 0;
    DhcpSid = 0;
    DhcpGlobalWellKnownSIDsMade = 0;
    DhcpGlobalRestoreStatus = 0;
    DhcpGlobalAlternateDnsServers = 0;
    DhcpGlobalAlternateDnsServerFlag = 0;
    DhcpGlobalAlternateDnsServerCount = 0;
    qword_1801570B0 = 0;
    v9 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_DhcpServerTrace;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    v10 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_MAIN_CB = 0;
    qword_1801570B8 = 1;
    do
    {
      v11 = *v10;
      TraceGuidReg.Guid = v11;
      ++v10;
      TraceGuidReg.RegHandle = 0;
      v9[4] = (ULONG64)v11;
      RegisterTraceGuidsW(WppControlCallback, v9, v11, 1u, &TraceGuidReg, 0, 0, v9 + 1);
      v9 = (ULONG64 *)*v9;
    }
    while ( v9 );
    if ( InitializeCriticalSectionAndSpinCount(&DhcpGlobalJetDatabaseCritSect, 0x80000000) )
    {
      fJetDatabaseCritSectInit = 1;
      if ( InitializeCriticalSectionAndSpinCount(&DhcpGlobalRegCritSect, 0x80000000) )
      {
        fRegCritSectInit = 1;
        if ( InitializeCriticalSectionAndSpinCount(&DhcpGlobalQuarCritSect, 0x80000000) )
        {
          fQuarCritSectInit = 1;
          if ( InitializeCriticalSectionAndSpinCount(&DhcpGlobalStatelessCritSect, 0x80000000) )
          {
            fStatelessCritSectInit = 1;
            DhcpGlobalServerStartTime = 0;
            DhcpGlobalUseNoDns = 1;
            DhcpGlobalThisServer = 0;
            goto LABEL_18;
          }
          Strings = GetLastError();
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          {
            goto LABEL_7;
          }
          v13 = 38;
        }
        else
        {
          Strings = GetLastError();
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          {
            goto LABEL_7;
          }
          v13 = 37;
        }
      }
      else
      {
        Strings = GetLastError();
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_7;
        v13 = 36;
      }
    }
    else
    {
      Strings = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_7;
      v13 = 35;
    }
LABEL_31:
    WPP_SF_D(v12[2], v13, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, Strings);
    goto LABEL_7;
  }
LABEL_18:
  if ( v2 )
    goto LABEL_23;
  if ( !InitializeCriticalSectionAndSpinCount(&DhcpGlobalInProgressCritSect, 0x80000000) )
  {
    Strings = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_7;
    v13 = 39;
    goto LABEL_31;
  }
  fInProgressCritSectInit = 1;
  if ( !InitializeCriticalSectionAndSpinCount(&DhcpGlobalMemoryCritSect, 0x80000000) )
  {
    Strings = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_7;
    v13 = 40;
    goto LABEL_31;
  }
  fMemoryCritSectInit = 1;
  if ( !InitializeCriticalSectionAndSpinCount(&g_ProcessMessageCritSect, 0x80000000) )
  {
    Strings = GetLastError();
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_7;
    v13 = 41;
    goto LABEL_31;
  }
  fProcessMessageCritSectInit = 1;
  qword_1801569F8 = (__int64)&DhcpGlobalFreeRecvList;
  DhcpGlobalFreeRecvList = (__int64)&DhcpGlobalFreeRecvList;
  qword_180156A08 = (__int64)&DhcpGlobalActiveRecvList;
  DhcpGlobalActiveRecvList = (__int64)&DhcpGlobalActiveRecvList;
  DhcpGlobalMessageQueueLength = 50;
  DhcpGlobalDebugFileHandle = 0;
  DhcpGlobalDebugSharePath = 0;
LABEL_23:
  if ( v3 )
  {
    DhcpInitDnsMemory();
    Dhcpv6InitDnsMemory();
    MadcapGlobalMibCounters = 0;
    xmmword_1801568B0 = 0;
    DhcpGlobalProcessTerminationEvent = CreateEventW(0, 1, 0, 0);
    if ( !DhcpGlobalProcessTerminationEvent )
    {
      Strings = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_7;
      v13 = 42;
      goto LABEL_31;
    }
    DhcpGlobalRogueWaitEvent = CreateEventW(0, 1, 0, 0);
    if ( !DhcpGlobalRogueWaitEvent )
    {
      Strings = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_7;
      v13 = 43;
      goto LABEL_31;
    }
    g_hevtProcessMessageComplete = (__int64)CreateEventW(0, 0, 0, 0);
    if ( !g_hevtProcessMessageComplete )
    {
      v14 = GetLastError();
      Strings = v14;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v14);
      goto LABEL_7;
    }
  }
  if ( v2 )
    goto LABEL_67;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
  Strings = LoadStrings();
  if ( !Strings )
  {
LABEL_67:
    if ( v3 )
    {
      v15 = WSAStartup(0x101u, &WSAData);
      Strings = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v15);
        v7 = 1005;
        goto LABEL_6;
      }
      v16 = InitializeData();
      Strings = v16;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v16);
        goto LABEL_66;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    }
    if ( !v2 )
      DhcpDsInitDS(0, 0);
    if ( !v3 )
      goto LABEL_273;
    WellKnownSids = NetpCreateWellKnownSids();
    v18 = 0;
    Strings = RtlNtStatusToDosError(WellKnownSids);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 50;
      goto LABEL_31;
    }
    DhcpGlobalWellKnownSIDsMade = 1;
    Strings = DhcpCreateSecurityObjects();
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 51;
      goto LABEL_31;
    }
    Strings = DhcpInitializeRegistry();
    if ( Strings )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_96;
      v20 = 52;
LABEL_95:
      WPP_SF_D(v19[2], v20, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, Strings);
LABEL_96:
      v7 = 1003;
      goto LABEL_6;
    }
    LastIasInitTime = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    if ( DhcpGlobalDebugFlag )
    {
      if ( (DhcpGlobalDebugFlag & 0x800000) != 0 )
        v21 = DhcpGlobalDebugFlag | 0x80000000;
      else
        v21 = DhcpGlobalDebugFlag | 0x8000FFFF;
      DhcpGlobalDebugFlag = v21;
      DhcpOpenDebugFile();
    }
    if ( DhcpGlobalAlternateDnsServerFlag )
    {
      AlternateDnsServerList = GetAlternateDnsServerList((char *)&v57 + 4);
      v23 = HIDWORD(v57);
      v24 = AlternateDnsServerList;
      if ( HIDWORD(v57) )
      {
        v25 = 40 * HIDWORD(v57);
        if ( 40 * (unsigned __int64)HIDWORD(v57) <= 0xFFFFFFFF && v25 + 12 >= v25 )
        {
          v26 = v25 + 12;
          ProcessHeap = GetProcessHeap();
          v28 = HeapAlloc(ProcessHeap, 8u, v26);
          v29 = v28;
          if ( v28 )
          {
            v28[1] = v23;
            *v28 = v23;
            if ( v23 )
            {
              do
              {
                v30 = v18++;
                v31 = 5 * v30;
                LOWORD(v29[2 * v31 + 3]) = 2;
                v29[2 * v31 + 4] = *(_DWORD *)(v24 + 4 * v30);
                v29[2 * v31 + 11] = 16;
              }
              while ( v18 < v29[1] );
            }
            v32 = DhcpValidateDnsServers(v29);
            v33 = v29[1];
            if ( v32 )
            {
              v38 = 0;
              if ( v33 )
              {
                v39 = 5LL * v18;
                do
                {
                  v58 = inet_ntoa((struct in_addr)v29[2 * v39 + 4]);
                  DhcpReportEventA(v40, 1344, 2, 1, 0, &v58, 0);
                  ++v38;
                }
                while ( v38 < v29[1] );
                v4 = v57;
              }
              else
              {
                v4 = 0;
              }
              goto LABEL_120;
            }
            v34 = 0;
            if ( v33 )
            {
              do
              {
                v35 = v29[10 * v34 + 12];
                if ( v35 != 5 && v35 && v35 != 6 )
                {
                  v58 = inet_ntoa((struct in_addr)v29[10 * v34 + 4]);
                  DhcpReportEventA(v36, 1344, 2, 1, 0, &v58, 0);
                }
                ++v34;
              }
              while ( v34 < v29[1] );
            }
          }
        }
      }
      v4 = 0;
    }
LABEL_120:
    if ( DhcpGlobalOemJetRestorePath )
    {
      v37 = PerformRestore();
      if ( v37 )
      {
LABEL_122:
        v8 = v37;
        return ClearDhcpError(v8);
      }
      v4 = 1;
      DhcpCleanupRegistry();
      Strings = DhcpInitializeRegistry();
      if ( Strings )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_96;
        v20 = 55;
        goto LABEL_95;
      }
    }
    if ( *(_DWORD *)&DhcpGlobalRestoreFlag )
    {
      v41 = DhcpRestoreConfiguration(DhcpGlobalBackupConfigFileName);
      Strings = v41;
      if ( v41 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v41);
        v7 = 1019;
        goto LABEL_6;
      }
      v42 = DhcpRestoreDatabase(DhcpGlobalOemJetBackupPath);
      Strings = v42;
      if ( v42 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v42);
        v7 = 1018;
        goto LABEL_6;
      }
      v4 = 1;
      DhcpServerEventLog(1040, 4, 0);
      *(_DWORD *)&DhcpGlobalRestoreFlag = 0;
      RegSetValueExW(DhcpGlobalRegParam, L"RestoreFlag", 0, 4u, &DhcpGlobalRestoreFlag, 4u);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    v43 = DhcpAuditLogInit();
    Strings = v43;
    if ( v43 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v43);
      goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    DhcpUALStart();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    DhcpInitializeCom();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    v44 = DhcpInitializeDatabaseEx(0);
    v45 = v44;
    if ( v44 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v44);
      DhcpServerEventLog(1004, 1, v45);
      v46 = DhcpRestoreDatabase(DhcpGlobalOemJetBackupPath);
      Strings = v46;
      if ( v46 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v46);
        DhcpServerEventLog(1018, 1, Strings);
        if ( fJetDatabaseCritSectInit )
        {
          DeleteCriticalSection(&DhcpGlobalJetDatabaseCritSect);
          fJetDatabaseCritSectInit = 0;
        }
        DhcpCleanupDnsMemory();
        Dhcpv6CleanupDnsMemory();
        goto LABEL_7;
      }
      DhcpServerEventLog(1040, 4, 0);
      v47 = DhcpInitializeDatabaseEx(0);
      Strings = v47;
      if ( v47 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v47);
        v7 = 1004;
        goto LABEL_6;
      }
      v4 = 1;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    Strings = DhcpOpenPolicyTables();
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 69;
      goto LABEL_31;
    }
    Strings = DhcpReadConfigInfo(&DhcpGlobalThisServer);
    if ( Strings || (Strings = ReadServerBitmasks()) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, Strings);
      v7 = 1058;
      goto LABEL_6;
    }
    Strings = DhcpPolicyConfigInit();
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 71;
      goto LABEL_31;
    }
    Strings = DhcpPolicyCriteriaListInit();
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 72;
      goto LABEL_31;
    }
    Strings = DhcpPolicyCriteriaFeatureListInit();
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 73;
      goto LABEL_31;
    }
    Strings = DhcpPolicyWildCardLenListInit();
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 74;
      goto LABEL_31;
    }
    v48 = DhcpConfigV6Init();
    Strings = v48;
    if ( v48 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v48);
      DhcpV6ServerEventLog(10019, 1, Strings);
      goto LABEL_7;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    Strings = DhcpInitV6LeaseTable();
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 77;
      goto LABEL_31;
    }
    v49 = DhcpGlobalDatabaseHandle;
    v50 = DhcpGlobalJetServerSession;
    memset_0(v60, 0, 0x48u);
    v61 = 4;
    v60[0] = "StatelessClients";
    v60[1] = &StatelessClientsTableHandle;
    v60[2] = &StatelessClientsTable;
    Strings = DhcpDALOpenDbTable(v50, v49, v60);
    if ( Strings == 2 )
    {
      Strings = DhcpDALCreateDbTable(v50, v49, v60);
      if ( Strings )
        goto LABEL_222;
      Strings = CreateStatelessIndexes(v50, v60);
    }
    if ( Strings )
    {
LABEL_222:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 78;
      goto LABEL_31;
    }
    if ( (unsigned int)DhcpCheckIfSystemUpgraded() == 1 )
    {
      v51 = DhcpV6ReservationEntryToLeaseTable();
      if ( v51 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v51);
      }
    }
    if ( !CryptAcquireContextW(&hCryptProv, 0, 0, 0x18u, 0xF0000000) )
    {
      v12 = WPP_GLOBAL_Control;
      Strings = 1627;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 80;
      goto LABEL_31;
    }
    v52 = SetDefaultConfigInfo();
    if ( v52
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v52);
    }
    v53 = SetDefaultConfigInfoV6();
    if ( v53
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v53);
    }
    DhcpGlobalRecomputeTimerEvent = CreateEventW(0, 0, 0, 0);
    if ( !DhcpGlobalRecomputeTimerEvent )
    {
      Strings = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_7;
      v13 = 84;
      goto LABEL_31;
    }
    if ( DhcpGlobalUseNoDns == 1 )
    {
      v37 = DynamicDnsInit();
      if ( v37 )
        goto LABEL_122;
    }
    CalloutInit();
    v54 = DhcpInitializeClientToServer();
    Strings = v54;
    if ( v54 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v54);
      v7 = 1007;
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    Strings = DhcpInitializeFailoverConfiguration(v4);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 87;
      goto LABEL_31;
    }
    DhcpGlobalServiceStatus.dwCurrentState = 4;
    DhcpGlobalServiceStatus.dwControlsAccepted = 279;
    DhcpGlobalServiceStatus.dwCheckPoint = 0;
    UpdateStatus();
    Strings = DhcpRogueInit(0, DhcpGlobalRogueWaitEvent, DhcpGlobalProcessTerminationEvent);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_7;
      v13 = 88;
      goto LABEL_31;
    }
    DhcpGlobalServerStartTime = DhcpGetDateTime();
    v55 = InitializeRpc();
    Strings = v55;
    if ( v55 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v55);
      v7 = 1006;
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    Dhcpv4DnsDhcidEnabled = 0;
    Dhcpv4DnsDhcidEnabled = DhcpIsDhcidEnabled();
LABEL_273:
    v8 = 0;
    return ClearDhcpError(v8);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
LABEL_66:
  v7 = 1002;
LABEL_6:
  DhcpServerEventLog(v7, 1, Strings);
LABEL_7:
  v8 = Strings;
  return ClearDhcpError(v8);
}

```

## disassembly

```asm
0x180025144  mov     rax, rsp
0x180025147  mov     [rax+8], rbx
0x18002514b  mov     [rax+10h], rsi
0x18002514f  mov     [rax+18h], rdi
0x180025153  push    rbp
0x180025154  push    r12
0x180025156  push    r13
0x180025158  push    r14
0x18002515a  push    r15
0x18002515c  lea     rbp, [rax-188h]
0x180025163  sub     rsp, 260h
0x18002516a  mov     rax, cs:__security_cookie
0x180025171  xor     rax, rsp
0x180025174  mov     [rbp+180h+var_30], rax
0x18002517b  mov     r15b, dl
0x18002517e  mov     r12b, cl
0x180025181  xor     edx, edx; Val
0x180025183  lea     rcx, [rbp+180h+WSAData]; void *
0x180025187  mov     r8d, 198h; Size
0x18002518d  call    memset_0
0x180025192  xor     esi, esi
0x180025194  lea     rdx, ServiceControlHandler; lpHandlerProc
0x18002519b  xor     r8d, r8d; lpContext
0x18002519e  mov     dword ptr [rsp+280h+var_240+4], esi
0x1800251a2  lea     rcx, SourceName; "DhcpServer"
0x1800251a9  mov     [rsp+280h+var_238], rsi
0x1800251ae  mov     r13d, esi
0x1800251b1  mov     dword ptr [rsp+280h+var_240], esi
0x1800251b5  mov     cs:gHAlgorithm, rsi
0x1800251bc  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800251c3  nop     dword ptr [rax+rax+00h]
0x1800251c8  mov     cs:DhcpGlobalServiceStatusHandle, rax
0x1800251cf  test    rax, rax
0x1800251d2  jnz     short loc_18002522A
0x1800251d4  call    cs:__imp_GetLastError
0x1800251db  nop     dword ptr [rax+rax+00h]
0x1800251e0  mov     ebx, eax
0x1800251e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251e9  lea     rdi, WPP_GLOBAL_Control
0x1800251f0  cmp     rcx, rdi
0x1800251f3  jz      short loc_180025211
0x1800251f5  test    byte ptr [rcx+1Ch], 40h
0x1800251f9  jz      short loc_180025211
0x1800251fb  mov     rcx, [rcx+10h]
0x1800251ff  lea     edx, [rsi+22h]
0x180025202  mov     r9d, eax
0x180025205  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x18002520c  call    WPP_SF_D
0x180025211  mov     edx, 1
0x180025216  mov     ecx, 3E9h
0x18002521b  mov     r8d, ebx
0x18002521e  call    DhcpServerEventLog
0x180025223  mov     ecx, ebx
0x180025225  jmp     loc_18002654F
0x18002522a  mov     r14d, 1
0x180025230  mov     cs:DhcpGlobalServiceStatus.dwServiceType, 10h
0x18002523a  mov     cs:DhcpGlobalServiceStatus.dwCheckPoint, r14d
0x180025241  mov     qword ptr cs:DhcpGlobalServiceStatus.dwCurrentState, 2
0x18002524c  mov     cs:DhcpGlobalServiceStatus.dwWaitHint, 112A880h
0x180025256  mov     qword ptr cs:DhcpGlobalServiceStatus.dwWin32ExitCode, rsi
0x18002525d  call    UpdateStatus
0x180025262  test    r15b, r15b
0x180025265  jnz     short loc_180025281
0x180025267  mov     cs:DhcpGlobalOkToService, esi
0x18002526d  mov     cs:DhcpGlobalServerPort, 43h ; 'C'
0x180025277  mov     cs:DhcpGlobalClientPort, 44h ; 'D'
0x180025281  mov     ebx, 80000000h
0x180025286  test    r12b, r12b
0x180025289  jz      loc_18002551A
0x18002528f  mov     eax, 36EE80h
0x180025294  mov     cs:DhcpGlobalServiceStopping, esi
0x18002529a  mov     cs:DhcpGlobalScavengeIpAddressInterval, eax
0x1800252a0  mov     cs:DhcpGlobalScavengeStatelessInterval, eax
0x1800252a6  mov     cs:DhcpLeaseExtension, esi
0x1800252ac  mov     cs:DhcpGlobalCleanupInterval, 0A4CB80h
0x1800252b6  mov     cs:DhcpGlobalRpcProtocols, esi
0x1800252bc  mov     cs:DhcpGlobalScavengeIpAddress, esi
0x1800252c2  mov     cs:DhcpGlobalIsStatelessTestEnv, esi
0x1800252c8  mov     cs:DhcpGlobalDetectConflictRetries, esi
0x1800252ce  mov     cs:DhcpGlobalBackupInterval, 0DBBA0h
0x1800252d8  mov     cs:DhcpGlobalDatabaseLoggingFlag, r14d
0x1800252df  mov     cs:DhcpGlobalRestoreFlag, esi
0x1800252e5  mov     cs:DhcpGlobalAuditLogFlag, r14d
0x1800252ec  mov     cs:DhcpGlobalRegQuarantineOn, esi
0x1800252f2  mov     cs:DhcpGlobalFirstTimeInitIAS, r14d
0x1800252f9  mov     cs:DhcpGlobalQuarUserClassOnly, r14d
0x180025300  mov     cs:DhcpGlobalQuarContextHandle, esi
0x180025306  mov     cs:DhcpComInitialized, esi
0x18002530c  mov     cs:DhcpComNeedCleanUp, esi
0x180025312  mov     cs:DhcpGlobalIasDelay, 7D0h
0x18002531c  mov     cs:DhcpGlobalRecomputeTimerEvent, rsi
0x180025323  mov     cs:DhcpGlobalRpcStarted, esi
0x180025329  mov     cs:DhcpGlobalOemDatabasePath, rsi
0x180025330  mov     cs:DhcpGlobalOemBackupPath, rsi
0x180025337  mov     cs:DhcpGlobalOemRestorePath, rsi
0x18002533e  mov     cs:DhcpGlobalOemJetBackupPath, rsi
0x180025345  mov     cs:DhcpGlobalOemJetRestorePath, rsi
0x18002534c  mov     cs:DhcpGlobalOemDatabaseName, rsi
0x180025353  mov     cs:DhcpGlobalBackupConfigFileName, rsi
0x18002535a  mov     cs:DhcpGlobalRegRoot, rsi
0x180025361  mov     cs:DhcpGlobalRegParam, rsi
0x180025368  mov     cs:DhcpGlobalServicePrivateData, rsi
0x18002536f  mov     cs:DhcpGlobalDSDomainAnsi, rsi
0x180025376  mov     cs:DhcpGlobalJetServerSession, rsi
0x18002537d  mov     cs:DhcpGlobalDatabaseHandle, esi
0x180025383  mov     cs:DhcpGlobalClientTableHandle, rsi
0x18002538a  mov     cs:DhcpGlobalClientTable, rsi
0x180025391  mov     cs:DhcpGlobalScavengerTimeout, esi
0x180025397  mov     cs:DhcpGlobalProcessTerminationEvent, rsi
0x18002539e  mov     cs:DhcpGlobalRogueWaitEvent, rsi
0x1800253a5  mov     cs:DhcpGlobalNumberOfNetsActive, esi
0x1800253ab  mov     cs:DhcpGlobalBindingsAware, r14d
0x1800253b2  mov     cs:DhcpGlobalImpersonated, esi
0x1800253b8  mov     cs:DhcpGlobalDirSecurityDescriptor, rsi
0x1800253bf  mov     cs:DhcpSid, rsi
0x1800253c6  mov     cs:DhcpGlobalWellKnownSIDsMade, esi
0x1800253cc  mov     cs:DhcpGlobalRestoreStatus, esi
0x1800253d2  mov     cs:DhcpGlobalAlternateDnsServers, rsi
0x1800253d9  mov     cs:DhcpGlobalAlternateDnsServerFlag, esi
0x1800253df  mov     cs:DhcpGlobalAlternateDnsServerCount, esi
0x1800253e5  lea     rax, WPP_ThisDir_CTLGUID_DhcpServerTrace
0x1800253ec  mov     cs:qword_1801570B0, rsi
0x1800253f3  lea     rbx, WPP_MAIN_CB
0x1800253fa  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180025401  mov     cs:WPP_GLOBAL_Control, rbx
0x180025408  lea     rdi, WPP_REGISTRATION_GUIDS
0x18002540f  mov     cs:WPP_MAIN_CB, rsi
0x180025416  mov     cs:qword_1801570B8, r14
0x18002541d  mov     r8, [rdi]; ControlGuid
0x180025420  lea     rax, [rbx+8]
0x180025424  mov     [rsp+280h+RegistrationHandle], rax; RegistrationHandle
0x180025429  lea     rcx, WppControlCallback; RequestAddress
0x180025430  mov     [rsp+280h+MofResourceName], rsi; MofResourceName
0x180025435  lea     rax, [rsp+280h+var_230]
0x18002543a  mov     [rsp+280h+var_230.Guid], r8
0x18002543f  lea     rdi, [rdi+8]
0x180025443  mov     [rsp+280h+var_230.RegHandle], rsi
0x180025448  mov     r9d, r14d; GuidCount
0x18002544b  mov     [rsp+280h+MofImagePath], rsi; MofImagePath
0x180025450  mov     rdx, rbx; RequestContext
0x180025453  mov     [rsp+280h+TraceGuidReg], rax; TraceGuidReg
0x180025458  mov     [rbx+20h], r8
0x18002545c  call    cs:__imp_RegisterTraceGuidsW
0x180025463  nop     dword ptr [rax+rax+00h]
0x180025468  mov     rbx, [rbx]
0x18002546b  test    rbx, rbx
0x18002546e  jnz     short loc_18002541D
0x180025470  mov     ebx, 80000000h
0x180025475  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002547c  mov     edx, ebx; dwSpinCount
0x18002547e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025485  nop     dword ptr [rax+rax+00h]
0x18002548a  test    eax, eax
0x18002548c  jz      loc_18002570D
0x180025492  mov     edx, ebx; dwSpinCount
0x180025494  mov     cs:fJetDatabaseCritSectInit, r14d
0x18002549b  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x1800254a2  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800254a9  nop     dword ptr [rax+rax+00h]
0x1800254ae  test    eax, eax
0x1800254b0  jz      loc_1800256D4
0x1800254b6  mov     edx, ebx; dwSpinCount
0x1800254b8  mov     cs:fRegCritSectInit, r14d
0x1800254bf  lea     rcx, DhcpGlobalQuarCritSect; lpCriticalSection
0x1800254c6  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800254cd  nop     dword ptr [rax+rax+00h]
0x1800254d2  test    eax, eax
0x1800254d4  jz      loc_18002569E
0x1800254da  mov     edx, ebx; dwSpinCount
0x1800254dc  mov     cs:fQuarCritSectInit, r14d
0x1800254e3  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x1800254ea  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800254f1  nop     dword ptr [rax+rax+00h]
0x1800254f6  test    eax, eax
0x1800254f8  jz      loc_180025652
0x1800254fe  mov     cs:fStatelessCritSectInit, r14d
0x180025505  mov     cs:DhcpGlobalServerStartTime, rsi
0x18002550c  mov     cs:DhcpGlobalUseNoDns, r14d
0x180025513  mov     cs:DhcpGlobalThisServer, rsi
0x18002551a  test    r15b, r15b
0x18002551d  jnz     loc_1800255D1
0x180025523  mov     edx, ebx; dwSpinCount
0x180025525  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x18002552c  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025533  nop     dword ptr [rax+rax+00h]
0x180025538  test    eax, eax
0x18002553a  jz      loc_1800257B8
0x180025540  mov     edx, ebx; dwSpinCount
0x180025542  mov     cs:fInProgressCritSectInit, r14d
0x180025549  lea     rcx, DhcpGlobalMemoryCritSect; lpCriticalSection
0x180025550  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025557  nop     dword ptr [rax+rax+00h]
0x18002555c  test    eax, eax
0x18002555e  jz      loc_18002577F
0x180025564  mov     edx, ebx; dwSpinCount
0x180025566  mov     cs:fMemoryCritSectInit, r14d
0x18002556d  lea     rcx, g_ProcessMessageCritSect; lpCriticalSection
0x180025574  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002557b  nop     dword ptr [rax+rax+00h]
0x180025580  test    eax, eax
0x180025582  jz      loc_180025746
0x180025588  lea     rax, DhcpGlobalFreeRecvList
0x18002558f  mov     cs:fProcessMessageCritSectInit, r14d
0x180025596  mov     cs:qword_1801569F8, rax
0x18002559d  mov     cs:DhcpGlobalFreeRecvList, rax
0x1800255a4  lea     rax, DhcpGlobalActiveRecvList
0x1800255ab  mov     cs:qword_180156A08, rax
0x1800255b2  mov     cs:DhcpGlobalActiveRecvList, rax
0x1800255b9  mov     cs:DhcpGlobalMessageQueueLength, 32h ; '2'
0x1800255c3  mov     cs:DhcpGlobalDebugFileHandle, rsi
0x1800255ca  mov     cs:DhcpGlobalDebugSharePath, rsi
0x1800255d1  test    r12b, r12b
0x1800255d4  jz      loc_1800258BB
0x1800255da  call    DhcpInitDnsMemory
0x1800255df  call    Dhcpv6InitDnsMemory
0x1800255e4  xorps   xmm0, xmm0
0x1800255e7  xor     r9d, r9d; lpName
0x1800255ea  xor     r8d, r8d; bInitialState
0x1800255ed  mov     edx, r14d; bManualReset
0x1800255f0  xor     ecx, ecx; lpEventAttributes
0x1800255f2  movups  cs:MadcapGlobalMibCounters, xmm0
0x1800255f9  movups  cs:xmmword_1801568B0, xmm0
0x180025600  call    cs:__imp_CreateEventW
0x180025607  nop     dword ptr [rax+rax+00h]
0x18002560c  mov     cs:DhcpGlobalProcessTerminationEvent, rax
0x180025613  test    rax, rax
0x180025616  jnz     loc_1800257F1
0x18002561c  call    cs:__imp_GetLastError
0x180025623  nop     dword ptr [rax+rax+00h]
0x180025628  mov     ebx, eax
0x18002562a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025631  lea     rdi, WPP_GLOBAL_Control
0x180025638  cmp     rcx, rdi
0x18002563b  jz      loc_180025223
0x180025641  test    byte ptr [rcx+1Ch], 40h
0x180025645  jz      loc_180025223
0x18002564b  mov     edx, 2Ah ; '*'
0x180025650  jmp     short loc_180025686
0x180025652  call    cs:__imp_GetLastError
0x180025659  nop     dword ptr [rax+rax+00h]
0x18002565e  mov     ebx, eax
0x180025660  mov     rcx, cs:WPP_GLOBAL_Control
0x180025667  lea     rdi, WPP_GLOBAL_Control
0x18002566e  cmp     rcx, rdi
0x180025671  jz      loc_180025223
0x180025677  test    byte ptr [rcx+1Ch], 40h
0x18002567b  jz      loc_180025223
0x180025681  mov     edx, 26h ; '&'
0x180025686  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x18002568d  mov     rcx, [rcx+10h]
0x180025691  mov     r9d, ebx
0x180025694  call    WPP_SF_D
0x180025699  jmp     loc_180025223
0x18002569e  call    cs:__imp_GetLastError
0x1800256a5  nop     dword ptr [rax+rax+00h]
0x1800256aa  mov     ebx, eax
0x1800256ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256b3  lea     rdi, WPP_GLOBAL_Control
0x1800256ba  cmp     rcx, rdi
0x1800256bd  jz      loc_180025223
0x1800256c3  test    byte ptr [rcx+1Ch], 40h
0x1800256c7  jz      loc_180025223
0x1800256cd  mov     edx, 25h ; '%'
0x1800256d2  jmp     short loc_180025686
0x1800256d4  call    cs:__imp_GetLastError
0x1800256db  nop     dword ptr [rax+rax+00h]
0x1800256e0  mov     ebx, eax
0x1800256e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256e9  lea     rdi, WPP_GLOBAL_Control
0x1800256f0  cmp     rcx, rdi
0x1800256f3  jz      loc_180025223
0x1800256f9  test    byte ptr [rcx+1Ch], 40h
0x1800256fd  jz      loc_180025223
0x180025703  mov     edx, 24h ; '$'
0x180025708  jmp     loc_180025686
0x18002570d  call    cs:__imp_GetLastError
0x180025714  nop     dword ptr [rax+rax+00h]
0x180025719  mov     ebx, eax
0x18002571b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025722  lea     rdi, WPP_GLOBAL_Control
0x180025729  cmp     rcx, rdi
0x18002572c  jz      loc_180025223
0x180025732  test    byte ptr [rcx+1Ch], 40h
0x180025736  jz      loc_180025223
0x18002573c  mov     edx, 23h ; '#'
0x180025741  jmp     loc_180025686
0x180025746  call    cs:__imp_GetLastError
0x18002574d  nop     dword ptr [rax+rax+00h]
0x180025752  mov     ebx, eax
0x180025754  mov     rcx, cs:WPP_GLOBAL_Control
0x18002575b  lea     rdi, WPP_GLOBAL_Control
0x180025762  cmp     rcx, rdi
0x180025765  jz      loc_180025223
0x18002576b  test    byte ptr [rcx+1Ch], 40h
0x18002576f  jz      loc_180025223
0x180025775  mov     edx, 29h ; ')'
0x18002577a  jmp     loc_180025686
0x18002577f  call    cs:__imp_GetLastError
0x180025786  nop     dword ptr [rax+rax+00h]
0x18002578b  mov     ebx, eax
  ... truncated ...
```
