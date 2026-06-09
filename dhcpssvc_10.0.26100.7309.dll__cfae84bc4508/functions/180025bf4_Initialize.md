# Initialize

- ea: `0x180025bf4`
- end: `0x18002701e`
- name: `Initialize`
- size: `5162`
- prototype: `HRESULT __cdecl()`
- caller_count: `1`
- callee_count: `54`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800258dc`

## callees

- `0x180002324`
- `0x180002854`
- `0x18000323c`
- `0x1800038fc`
- `0x180006038`
- `0x18000df98`
- `0x18000f4b8`
- `0x18001119c`
- `0x180013550`
- `0x1800147a8`
- `0x1800174c0`
- `0x18001c9dc`
- `0x18001d2bc`
- `0x18001d7a8`
- `0x18001d818`
- `0x18001ea10`
- `0x18001f040`
- `0x18001f4b0`
- `0x180022060`
- `0x1800225f0`
- `0x1800258ac`
- `0x180025bf4`
- `0x180027024`
- `0x180027154`
- `0x18002734c`
- `0x1800277f8`
- `0x180028844`
- `0x18003116c`
- `0x180034e40`
- `0x180046060`
- `0x1800473f4`
- `0x180055758`
- `0x180062964`
- `0x180062f0c`
- `0x180063d7c`
- `0x180067fd0`
- `0x1800794ec`
- `0x18007c0e4`
- `0x18007d5bc`
- `0x18008474c`
- `0x18008ef3c`
- `0x18008f044`
- `0x1800905e0`
- `0x18009b9a8`
- `0x18009f3a0`
- `0x1800a001c`
- `0x1800b5408`
- `0x1800b97b0`
- `0x1800b9814`
- `0x1800b9a0c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800264b1`
- `ntdll!RtlNtStatusToDosError` at `0x1800264b1`
- `ADVAPI32!RegSetValueExW` at `0x18002687a`
- `ADVAPI32!RegSetValueExW` at `0x18002687a`
- `ADVAPI32!CryptAcquireContextW` at `0x180026d71`
- `ADVAPI32!CryptAcquireContextW` at `0x180026d71`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180025c68`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180025c68`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180025f08`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180025f08`
- `WS2_32!__imp_inet_ntoa` at `0x18002669c`
- `WS2_32!__imp_inet_ntoa` at `0x18002671b`
- `WS2_32!__imp_inet_ntoa` at `0x18002669c`
- `WS2_32!__imp_inet_ntoa` at `0x18002671b`
- `WS2_32!__imp_WSAStartup` at `0x1800263ea`
- `WS2_32!__imp_WSAStartup` at `0x1800263ea`
- `DSAUTH!DhcpDsInitDS` at `0x180026495`
- `DSAUTH!DhcpDsInitDS` at `0x180026495`
- `KERNEL32!CreateEventW` at `0x1800260ac`
- `KERNEL32!CreateEventW` at `0x1800262a8`
- `KERNEL32!CreateEventW` at `0x180026303`
- `KERNEL32!CreateEventW` at `0x180026e10`
- `KERNEL32!CreateEventW` at `0x1800260ac`
- `KERNEL32!CreateEventW` at `0x1800262a8`
- `KERNEL32!CreateEventW` at `0x180026303`
- `KERNEL32!CreateEventW` at `0x180026e10`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f2a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f4e`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f72`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f96`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025fd8`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025ffc`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180026020`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f2a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f4e`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f72`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025f96`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025fd8`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180025ffc`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180026020`
- `KERNEL32!HeapAlloc` at `0x180026612`
- `KERNEL32!HeapAlloc` at `0x180026612`
- `KERNEL32!GetProcessHeap` at `0x1800265fb`
- `KERNEL32!GetProcessHeap` at `0x1800265fb`
- `KERNEL32!DeleteCriticalSection` at `0x180026a03`
- `KERNEL32!DeleteCriticalSection` at `0x180026a03`
- `KERNEL32!GetLastError` at `0x180025c80`
- `KERNEL32!GetLastError` at `0x1800260c8`
- `KERNEL32!GetLastError` at `0x1800260fe`
- `KERNEL32!GetLastError` at `0x18002614a`
- `KERNEL32!GetLastError` at `0x180026180`
- `KERNEL32!GetLastError` at `0x1800261b9`
- `KERNEL32!GetLastError` at `0x1800261f2`
- `KERNEL32!GetLastError` at `0x18002622b`
- `KERNEL32!GetLastError` at `0x180026264`
- `KERNEL32!GetLastError` at `0x1800262c0`
- `KERNEL32!GetLastError` at `0x18002631b`
- `KERNEL32!GetLastError` at `0x180026e28`
- `KERNEL32!GetLastError` at `0x180025c80`
- `KERNEL32!GetLastError` at `0x1800260c8`
- `KERNEL32!GetLastError` at `0x1800260fe`
- `KERNEL32!GetLastError` at `0x18002614a`
- `KERNEL32!GetLastError` at `0x180026180`
- `KERNEL32!GetLastError` at `0x1800261b9`
- `KERNEL32!GetLastError` at `0x1800261f2`
- `KERNEL32!GetLastError` at `0x18002622b`
- `KERNEL32!GetLastError` at `0x180026264`
- `KERNEL32!GetLastError` at `0x1800262c0`
- `KERNEL32!GetLastError` at `0x18002631b`
- `KERNEL32!GetLastError` at `0x180026e28`

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
  __int64 v19; // rdx
  unsigned __int64 v20; // r8
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned __int64 v23; // rcx
  unsigned int v24; // eax
  _DWORD *AlternateDnsServerList; // rax
  int v26; // r15d
  _DWORD *v27; // r13
  unsigned int v28; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v30; // rax
  _DWORD *v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rcx
  unsigned int i; // r15d
  __int64 v35; // rcx
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  unsigned int v40; // r15d
  __int64 v41; // r12
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  DWORD v46; // eax
  DWORD v47; // eax
  void *v48; // rcx
  DWORD v49; // eax
  __int64 v50; // rdx
  __int64 v51; // r8
  void *v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // r8
  void *v55; // rcx
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  unsigned int v59; // ebx
  DWORD v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  DWORD v67; // eax
  void *v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // r8
  DWORD v87; // eax
  __int64 v88; // rdx
  __int64 v89; // r8
  void *v90; // rcx
  JET_DBID v91; // r12d
  JET_SESID v92; // r15
  __int64 v93; // rdx
  __int64 v94; // rcx
  __int64 v95; // r8
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // r8
  unsigned int v99; // eax
  unsigned int v100; // eax
  __int64 v101; // rdx
  void *v102; // rcx
  __int64 v103; // r8
  unsigned int v104; // eax
  DWORD v105; // eax
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // r8
  __int64 v109; // r9
  DWORD v110; // eax
  __int64 v112; // [rsp+48h] [rbp-C0h] BYREF
  char *v113; // [rsp+50h] [rbp-B8h]
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v115[8]; // [rsp+68h] [rbp-A0h] BYREF
  int v116; // [rsp+ACh] [rbp-5Ch]
  WSAData WSAData; // [rsp+B8h] [rbp-50h] BYREF

  v2 = v0;
  v3 = v1;
  memset_0(&WSAData, 0, sizeof(WSAData));
  HIDWORD(v112) = 0;
  v113 = 0;
  v4 = 0;
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
    qword_180155110 = 0;
    v9 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_DhcpServerTrace;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    v10 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_MAIN_CB = 0;
    qword_180155118 = 1;
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
  qword_180154A58 = (__int64)&DhcpGlobalFreeRecvList;
  DhcpGlobalFreeRecvList = (__int64)&DhcpGlobalFreeRecvList;
  qword_180154A68 = (__int64)&DhcpGlobalActiveRecvList;
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
    xmmword_180154910 = 0;
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
      goto LABEL_271;
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
    Strings = ((__int64 (*)(void))DhcpInitializeRegistry)();
    if ( Strings )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_96;
      v22 = 52;
LABEL_95:
      WPP_SF_D(v21[2], v22, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, Strings);
LABEL_96:
      v7 = 1003;
      goto LABEL_6;
    }
    LastIasInitTime = 0;
    v23 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    if ( DhcpGlobalDebugFlag )
    {
      if ( (DhcpGlobalDebugFlag & 0x800000) != 0 )
        v24 = DhcpGlobalDebugFlag | 0x80000000;
      else
        v24 = DhcpGlobalDebugFlag | 0x8000FFFF;
      DhcpGlobalDebugFlag = v24;
      DhcpOpenDebugFile();
    }
    if ( DhcpGlobalAlternateDnsServerFlag )
    {
      AlternateDnsServerList = GetAlternateDnsServerList((unsigned int *)&v112 + 1);
      v26 = HIDWORD(v112);
      v27 = AlternateDnsServerList;
      if ( HIDWORD(v112) )
      {
        v20 = 40LL * HIDWORD(v112);
        if ( v20 <= 0xFFFFFFFF && (int)v20 + 12 >= (unsigned int)v20 )
        {
          v28 = v20 + 12;
          ProcessHeap = GetProcessHeap();
          v30 = HeapAlloc(ProcessHeap, 8u, v28);
          v31 = v30;
          if ( v30 )
          {
            v30[1] = v26;
            *v30 = v26;
            if ( v26 )
            {
              do
              {
                v32 = v18++;
                v33 = 5 * v32;
                LOWORD(v31[2 * v33 + 3]) = 2;
                v31[2 * v33 + 4] = v27[v32];
                v31[2 * v33 + 11] = 16;
              }
              while ( v18 < v31[1] );
            }
            v4 = 0;
            if ( (unsigned int)DhcpValidateDnsServers(v31) )
            {
              v40 = 0;
              if ( v31[1] )
              {
                v41 = 5LL * v18;
                do
                {
                  v113 = inet_ntoa((struct in_addr)v31[2 * v41 + 4]);
                  DhcpReportEventA(v42, 1344, 2);
                  ++v40;
                }
                while ( v40 < v31[1] );
              }
              goto LABEL_119;
            }
            for ( i = 0; i < v31[1]; ++i )
            {
              v19 = 5LL * i;
              v23 = (unsigned int)v31[10 * i + 12];
              if ( (unsigned int)(v23 - 1) <= 3 || (unsigned int)v23 >= 7 )
              {
                v113 = inet_ntoa((struct in_addr)v31[10 * i + 4]);
                DhcpReportEventA(v35, 1344, 2);
              }
            }
          }
        }
      }
      v4 = 0;
    }
LABEL_119:
    if ( DhcpGlobalOemJetRestorePath )
    {
      v36 = PerformRestore(v23, v19, v20);
      if ( v36 )
      {
LABEL_121:
        v8 = v36;
        return ClearDhcpError(v8);
      }
      v4 = 1;
      DhcpCleanupRegistry(v38, v37, v39);
      Strings = DhcpInitializeRegistry(v44, v43, v45);
      if ( Strings )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_96;
        v22 = 55;
        goto LABEL_95;
      }
    }
    if ( *(_DWORD *)&DhcpGlobalRestoreFlag )
    {
      v46 = DhcpRestoreConfiguration(DhcpGlobalBackupConfigFileName);
      Strings = v46;
      if ( v46 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v46);
        v7 = 1019;
        goto LABEL_6;
      }
      v47 = DhcpRestoreDatabase(DhcpGlobalOemJetBackupPath);
      Strings = v47;
      if ( v47 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v47);
        v7 = 1018;
        goto LABEL_6;
      }
      v4 = 1;
      DhcpServerEventLog(1040, 4, 0);
      *(_DWORD *)&DhcpGlobalRestoreFlag = 0;
      RegSetValueExW(DhcpGlobalRegParam, L"RestoreFlag", 0, 4u, &DhcpGlobalRestoreFlag, 4u);
    }
    v48 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    v49 = DhcpAuditLogInit(v48, v19, v20);
    Strings = v49;
    if ( v49 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v49);
      goto LABEL_7;
    }
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    DhcpUALStart(v52, v50, v51);
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    DhcpInitializeCom(v55, v53, v54);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    v56 = DhcpInitializeDatabaseEx(0);
    v59 = v56;
    if ( v56 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v56);
      DhcpServerEventLog(1004, 1, v59);
      v60 = DhcpRestoreDatabase(DhcpGlobalOemJetBackupPath);
      Strings = v60;
      if ( v60 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v60);
        DhcpServerEventLog(1018, 1, Strings);
        if ( fJetDatabaseCritSectInit )
        {
          DeleteCriticalSection(&DhcpGlobalJetDatabaseCritSect);
          fJetDatabaseCritSectInit = 0;
        }
        DhcpCleanupDnsMemory(v62, v61, v63);
        Dhcpv6CleanupDnsMemory(v65, v64, v66);
        goto LABEL_7;
      }
      DhcpServerEventLog(1040, 4, 0);
      v67 = DhcpInitializeDatabaseEx(0);
      Strings = v67;
      if ( v67 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v67);
        v7 = 1004;
        goto LABEL_6;
      }
      v4 = 1;
    }
    v68 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    Strings = DhcpOpenPolicyTables(v68, v57, v58);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 69;
      goto LABEL_31;
    }
    Strings = DhcpReadConfigInfo(&DhcpGlobalThisServer);
    if ( Strings || (Strings = ReadServerBitmasks(v70, v69, v71)) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, Strings);
      v7 = 1058;
      goto LABEL_6;
    }
    Strings = DhcpPolicyConfigInit(v73, v72, v74);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 71;
      goto LABEL_31;
    }
    Strings = DhcpPolicyCriteriaListInit(v76, v75, v77);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 72;
      goto LABEL_31;
    }
    Strings = DhcpPolicyCriteriaFeatureListInit(v79, v78, v80);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 73;
      goto LABEL_31;
    }
    Strings = DhcpPolicyWildCardLenListInit(v82, v81, v83);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 74;
      goto LABEL_31;
    }
    v87 = DhcpConfigV6Init(v85, v84, v86);
    Strings = v87;
    if ( v87 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v87);
      DhcpV6ServerEventLog(10019, 1, Strings);
      goto LABEL_7;
    }
    v90 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    Strings = DhcpInitV6LeaseTable(v90, v88, v89);
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 77;
      goto LABEL_31;
    }
    v91 = DhcpGlobalDatabaseHandle;
    v92 = DhcpGlobalJetServerSession;
    memset_0(v115, 0, 0x48u);
    v116 = 4;
    v115[0] = "StatelessClients";
    v115[1] = &StatelessClientsTableHandle;
    v115[2] = &StatelessClientsTable;
    Strings = DhcpDALOpenDbTable(v92, v91, v115);
    if ( Strings == 2 )
    {
      Strings = DhcpDALCreateDbTable(v92, v91, v115);
      if ( !Strings )
        Strings = CreateStatelessIndexes(v92, v115);
    }
    if ( Strings )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_7;
      v13 = 78;
      goto LABEL_31;
    }
    if ( (unsigned int)DhcpCheckIfSystemUpgraded(v94, v93, v95) == 1 )
    {
      v99 = DhcpV6ReservationEntryToLeaseTable(v97, v96, v98);
      if ( v99 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v99);
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
    v100 = SetDefaultConfigInfo();
    if ( v100 )
    {
      v102 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v100);
    }
    v104 = SetDefaultConfigInfoV6((__int64)v102, v101, v103);
    if ( v104
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v104);
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
      v36 = DynamicDnsInit();
      if ( v36 )
        goto LABEL_121;
    }
    CalloutInit();
    v105 = DhcpInitializeClientToServer();
    Strings = v105;
    if ( v105 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v105);
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
    DhcpGlobalServiceStatus.dwCheckPoint = 0;
    DhcpGlobalServiceStatus.dwCurrentState = 4;
    DhcpGlobalServiceStatus.dwControlsAccepted = 279;
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
    DhcpGlobalServerStartTime = DhcpGetDateTime(v107, v106, v108, v109);
    v110 = InitializeRpc();
    Strings = v110;
    if ( v110 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v110);
      v7 = 1006;
      goto LABEL_6;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids);
    Dhcpv4DnsDhcidEnabled = 0;
    Dhcpv4DnsDhcidEnabled = DhcpIsDhcidEnabled();
LABEL_271:
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
0x180025bf4  mov     rax, rsp
0x180025bf7  mov     [rax+8], rbx
0x180025bfb  mov     [rax+10h], rsi
0x180025bff  mov     [rax+18h], rdi
0x180025c03  push    rbp
0x180025c04  push    r12
0x180025c06  push    r13
0x180025c08  push    r14
0x180025c0a  push    r15
0x180025c0c  lea     rbp, [rax-188h]
0x180025c13  sub     rsp, 260h
0x180025c1a  mov     rax, cs:__security_cookie
0x180025c21  xor     rax, rsp
0x180025c24  mov     [rbp+180h+var_30], rax
0x180025c2b  mov     r15b, dl
0x180025c2e  mov     r12b, cl
0x180025c31  xor     edx, edx; Val
0x180025c33  lea     rcx, [rbp+180h+WSAData]; void *
0x180025c37  mov     r8d, 198h; Size
0x180025c3d  call    memset_0
0x180025c42  xor     esi, esi
0x180025c44  lea     rdx, ServiceControlHandler; lpHandlerProc
0x180025c4b  xor     r8d, r8d; lpContext
0x180025c4e  mov     dword ptr [rsp+280h+var_240+4], esi
0x180025c52  lea     rcx, SourceName; "DhcpServer"
0x180025c59  mov     [rsp+280h+var_238], rsi
0x180025c5e  mov     r13d, esi
0x180025c61  mov     cs:gHAlgorithm, rsi
0x180025c68  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180025c6f  nop     dword ptr [rax+rax+00h]
0x180025c74  mov     cs:DhcpGlobalServiceStatusHandle, rax
0x180025c7b  test    rax, rax
0x180025c7e  jnz     short loc_180025CD6
0x180025c80  call    cs:__imp_GetLastError
0x180025c87  nop     dword ptr [rax+rax+00h]
0x180025c8c  mov     ebx, eax
0x180025c8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025c95  lea     rdi, WPP_GLOBAL_Control
0x180025c9c  cmp     rcx, rdi
0x180025c9f  jz      short loc_180025CBD
0x180025ca1  test    byte ptr [rcx+1Ch], 40h
0x180025ca5  jz      short loc_180025CBD
0x180025ca7  mov     rcx, [rcx+10h]
0x180025cab  lea     edx, [rsi+22h]
0x180025cae  mov     r9d, eax
0x180025cb1  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180025cb8  call    WPP_SF_D
0x180025cbd  mov     edx, 1
0x180025cc2  mov     ecx, 3E9h
0x180025cc7  mov     r8d, ebx
0x180025cca  call    DhcpServerEventLog
0x180025ccf  mov     ecx, ebx
0x180025cd1  jmp     loc_180026FE8
0x180025cd6  mov     r14d, 1
0x180025cdc  mov     cs:DhcpGlobalServiceStatus.dwServiceType, 10h
0x180025ce6  mov     cs:DhcpGlobalServiceStatus.dwCheckPoint, r14d
0x180025ced  mov     qword ptr cs:DhcpGlobalServiceStatus.dwCurrentState, 2
0x180025cf8  mov     cs:DhcpGlobalServiceStatus.dwWaitHint, 112A880h
0x180025d02  mov     qword ptr cs:DhcpGlobalServiceStatus.dwWin32ExitCode, rsi
0x180025d09  call    UpdateStatus
0x180025d0e  test    r15b, r15b
0x180025d11  jnz     short loc_180025D2D
0x180025d13  mov     cs:DhcpGlobalOkToService, esi
0x180025d19  mov     cs:DhcpGlobalServerPort, 43h ; 'C'
0x180025d23  mov     cs:DhcpGlobalClientPort, 44h ; 'D'
0x180025d2d  mov     ebx, 80000000h
0x180025d32  test    r12b, r12b
0x180025d35  jz      loc_180025FC6
0x180025d3b  mov     eax, 36EE80h
0x180025d40  mov     cs:DhcpGlobalServiceStopping, esi
0x180025d46  mov     cs:DhcpGlobalScavengeIpAddressInterval, eax
0x180025d4c  mov     cs:DhcpGlobalScavengeStatelessInterval, eax
0x180025d52  mov     cs:DhcpLeaseExtension, esi
0x180025d58  mov     cs:DhcpGlobalCleanupInterval, 0A4CB80h
0x180025d62  mov     cs:DhcpGlobalRpcProtocols, esi
0x180025d68  mov     cs:DhcpGlobalScavengeIpAddress, esi
0x180025d6e  mov     cs:DhcpGlobalIsStatelessTestEnv, esi
0x180025d74  mov     cs:DhcpGlobalDetectConflictRetries, esi
0x180025d7a  mov     cs:DhcpGlobalBackupInterval, 0DBBA0h
0x180025d84  mov     cs:DhcpGlobalDatabaseLoggingFlag, r14d
0x180025d8b  mov     cs:DhcpGlobalRestoreFlag, esi
0x180025d91  mov     cs:DhcpGlobalAuditLogFlag, r14d
0x180025d98  mov     cs:DhcpGlobalRegQuarantineOn, esi
0x180025d9e  mov     cs:DhcpGlobalFirstTimeInitIAS, r14d
0x180025da5  mov     cs:DhcpGlobalQuarUserClassOnly, r14d
0x180025dac  mov     cs:DhcpGlobalQuarContextHandle, esi
0x180025db2  mov     cs:DhcpComInitialized, esi
0x180025db8  mov     cs:DhcpComNeedCleanUp, esi
0x180025dbe  mov     cs:DhcpGlobalIasDelay, 7D0h
0x180025dc8  mov     cs:DhcpGlobalRecomputeTimerEvent, rsi
0x180025dcf  mov     cs:DhcpGlobalRpcStarted, esi
0x180025dd5  mov     cs:DhcpGlobalOemDatabasePath, rsi
0x180025ddc  mov     cs:DhcpGlobalOemBackupPath, rsi
0x180025de3  mov     cs:DhcpGlobalOemRestorePath, rsi
0x180025dea  mov     cs:DhcpGlobalOemJetBackupPath, rsi
0x180025df1  mov     cs:DhcpGlobalOemJetRestorePath, rsi
0x180025df8  mov     cs:DhcpGlobalOemDatabaseName, rsi
0x180025dff  mov     cs:DhcpGlobalBackupConfigFileName, rsi
0x180025e06  mov     cs:DhcpGlobalRegRoot, rsi
0x180025e0d  mov     cs:DhcpGlobalRegParam, rsi
0x180025e14  mov     cs:DhcpGlobalServicePrivateData, rsi
0x180025e1b  mov     cs:DhcpGlobalDSDomainAnsi, rsi
0x180025e22  mov     cs:DhcpGlobalJetServerSession, rsi
0x180025e29  mov     cs:DhcpGlobalDatabaseHandle, esi
0x180025e2f  mov     cs:DhcpGlobalClientTableHandle, rsi
0x180025e36  mov     cs:DhcpGlobalClientTable, rsi
0x180025e3d  mov     cs:DhcpGlobalScavengerTimeout, esi
0x180025e43  mov     cs:DhcpGlobalProcessTerminationEvent, rsi
0x180025e4a  mov     cs:DhcpGlobalRogueWaitEvent, rsi
0x180025e51  mov     cs:DhcpGlobalNumberOfNetsActive, esi
0x180025e57  mov     cs:DhcpGlobalBindingsAware, r14d
0x180025e5e  mov     cs:DhcpGlobalImpersonated, esi
0x180025e64  mov     cs:DhcpGlobalDirSecurityDescriptor, rsi
0x180025e6b  mov     cs:DhcpSid, rsi
0x180025e72  mov     cs:DhcpGlobalWellKnownSIDsMade, esi
0x180025e78  mov     cs:DhcpGlobalRestoreStatus, esi
0x180025e7e  mov     cs:DhcpGlobalAlternateDnsServers, rsi
0x180025e85  mov     cs:DhcpGlobalAlternateDnsServerFlag, esi
0x180025e8b  mov     cs:DhcpGlobalAlternateDnsServerCount, esi
0x180025e91  lea     rax, WPP_ThisDir_CTLGUID_DhcpServerTrace
0x180025e98  mov     cs:qword_180155110, rsi
0x180025e9f  lea     rbx, WPP_MAIN_CB
0x180025ea6  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180025ead  mov     cs:WPP_GLOBAL_Control, rbx
0x180025eb4  lea     rdi, WPP_REGISTRATION_GUIDS
0x180025ebb  mov     cs:WPP_MAIN_CB, rsi
0x180025ec2  mov     cs:qword_180155118, r14
0x180025ec9  mov     r8, [rdi]; ControlGuid
0x180025ecc  lea     rax, [rbx+8]
0x180025ed0  mov     [rsp+280h+RegistrationHandle], rax; RegistrationHandle
0x180025ed5  lea     rcx, WppControlCallback; RequestAddress
0x180025edc  mov     [rsp+280h+MofResourceName], rsi; MofResourceName
0x180025ee1  lea     rax, [rsp+280h+var_230]
0x180025ee6  mov     [rsp+280h+var_230.Guid], r8
0x180025eeb  lea     rdi, [rdi+8]
0x180025eef  mov     [rsp+280h+var_230.RegHandle], rsi
0x180025ef4  mov     r9d, r14d; GuidCount
0x180025ef7  mov     [rsp+280h+MofImagePath], rsi; MofImagePath
0x180025efc  mov     rdx, rbx; RequestContext
0x180025eff  mov     [rsp+280h+TraceGuidReg], rax; TraceGuidReg
0x180025f04  mov     [rbx+20h], r8
0x180025f08  call    cs:__imp_RegisterTraceGuidsW
0x180025f0f  nop     dword ptr [rax+rax+00h]
0x180025f14  mov     rbx, [rbx]
0x180025f17  test    rbx, rbx
0x180025f1a  jnz     short loc_180025EC9
0x180025f1c  mov     ebx, 80000000h
0x180025f21  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180025f28  mov     edx, ebx; dwSpinCount
0x180025f2a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025f31  nop     dword ptr [rax+rax+00h]
0x180025f36  test    eax, eax
0x180025f38  jz      loc_1800261B9
0x180025f3e  mov     edx, ebx; dwSpinCount
0x180025f40  mov     cs:fJetDatabaseCritSectInit, r14d
0x180025f47  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x180025f4e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025f55  nop     dword ptr [rax+rax+00h]
0x180025f5a  test    eax, eax
0x180025f5c  jz      loc_180026180
0x180025f62  mov     edx, ebx; dwSpinCount
0x180025f64  mov     cs:fRegCritSectInit, r14d
0x180025f6b  lea     rcx, DhcpGlobalQuarCritSect; lpCriticalSection
0x180025f72  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025f79  nop     dword ptr [rax+rax+00h]
0x180025f7e  test    eax, eax
0x180025f80  jz      loc_18002614A
0x180025f86  mov     edx, ebx; dwSpinCount
0x180025f88  mov     cs:fQuarCritSectInit, r14d
0x180025f8f  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x180025f96  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025f9d  nop     dword ptr [rax+rax+00h]
0x180025fa2  test    eax, eax
0x180025fa4  jz      loc_1800260FE
0x180025faa  mov     cs:fStatelessCritSectInit, r14d
0x180025fb1  mov     cs:DhcpGlobalServerStartTime, rsi
0x180025fb8  mov     cs:DhcpGlobalUseNoDns, r14d
0x180025fbf  mov     cs:DhcpGlobalThisServer, rsi
0x180025fc6  test    r15b, r15b
0x180025fc9  jnz     loc_18002607D
0x180025fcf  mov     edx, ebx; dwSpinCount
0x180025fd1  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x180025fd8  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180025fdf  nop     dword ptr [rax+rax+00h]
0x180025fe4  test    eax, eax
0x180025fe6  jz      loc_180026264
0x180025fec  mov     edx, ebx; dwSpinCount
0x180025fee  mov     cs:fInProgressCritSectInit, r14d
0x180025ff5  lea     rcx, DhcpGlobalMemoryCritSect; lpCriticalSection
0x180025ffc  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180026003  nop     dword ptr [rax+rax+00h]
0x180026008  test    eax, eax
0x18002600a  jz      loc_18002622B
0x180026010  mov     edx, ebx; dwSpinCount
0x180026012  mov     cs:fMemoryCritSectInit, r14d
0x180026019  lea     rcx, g_ProcessMessageCritSect; lpCriticalSection
0x180026020  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180026027  nop     dword ptr [rax+rax+00h]
0x18002602c  test    eax, eax
0x18002602e  jz      loc_1800261F2
0x180026034  lea     rax, DhcpGlobalFreeRecvList
0x18002603b  mov     cs:fProcessMessageCritSectInit, r14d
0x180026042  mov     cs:qword_180154A58, rax
0x180026049  mov     cs:DhcpGlobalFreeRecvList, rax
0x180026050  lea     rax, DhcpGlobalActiveRecvList
0x180026057  mov     cs:qword_180154A68, rax
0x18002605e  mov     cs:DhcpGlobalActiveRecvList, rax
0x180026065  mov     cs:DhcpGlobalMessageQueueLength, 32h ; '2'
0x18002606f  mov     cs:DhcpGlobalDebugFileHandle, rsi
0x180026076  mov     cs:DhcpGlobalDebugSharePath, rsi
0x18002607d  test    r12b, r12b
0x180026080  jz      loc_180026367
0x180026086  call    DhcpInitDnsMemory
0x18002608b  call    Dhcpv6InitDnsMemory
0x180026090  xorps   xmm0, xmm0
0x180026093  xor     r9d, r9d; lpName
0x180026096  xor     r8d, r8d; bInitialState
0x180026099  mov     edx, r14d; bManualReset
0x18002609c  xor     ecx, ecx; lpEventAttributes
0x18002609e  movups  cs:MadcapGlobalMibCounters, xmm0
0x1800260a5  movups  cs:xmmword_180154910, xmm0
0x1800260ac  call    cs:__imp_CreateEventW
0x1800260b3  nop     dword ptr [rax+rax+00h]
0x1800260b8  mov     cs:DhcpGlobalProcessTerminationEvent, rax
0x1800260bf  test    rax, rax
0x1800260c2  jnz     loc_18002629D
0x1800260c8  call    cs:__imp_GetLastError
0x1800260cf  nop     dword ptr [rax+rax+00h]
0x1800260d4  mov     ebx, eax
0x1800260d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260dd  lea     rdi, WPP_GLOBAL_Control
0x1800260e4  cmp     rcx, rdi
0x1800260e7  jz      loc_180025CCF
0x1800260ed  test    byte ptr [rcx+1Ch], 40h
0x1800260f1  jz      loc_180025CCF
0x1800260f7  mov     edx, 2Ah ; '*'
0x1800260fc  jmp     short loc_180026132
0x1800260fe  call    cs:__imp_GetLastError
0x180026105  nop     dword ptr [rax+rax+00h]
0x18002610a  mov     ebx, eax
0x18002610c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026113  lea     rdi, WPP_GLOBAL_Control
0x18002611a  cmp     rcx, rdi
0x18002611d  jz      loc_180025CCF
0x180026123  test    byte ptr [rcx+1Ch], 40h
0x180026127  jz      loc_180025CCF
0x18002612d  mov     edx, 26h ; '&'
0x180026132  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180026139  mov     rcx, [rcx+10h]
0x18002613d  mov     r9d, ebx
0x180026140  call    WPP_SF_D
0x180026145  jmp     loc_180025CCF
0x18002614a  call    cs:__imp_GetLastError
0x180026151  nop     dword ptr [rax+rax+00h]
0x180026156  mov     ebx, eax
0x180026158  mov     rcx, cs:WPP_GLOBAL_Control
0x18002615f  lea     rdi, WPP_GLOBAL_Control
0x180026166  cmp     rcx, rdi
0x180026169  jz      loc_180025CCF
0x18002616f  test    byte ptr [rcx+1Ch], 40h
0x180026173  jz      loc_180025CCF
0x180026179  mov     edx, 25h ; '%'
0x18002617e  jmp     short loc_180026132
0x180026180  call    cs:__imp_GetLastError
0x180026187  nop     dword ptr [rax+rax+00h]
0x18002618c  mov     ebx, eax
0x18002618e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026195  lea     rdi, WPP_GLOBAL_Control
0x18002619c  cmp     rcx, rdi
0x18002619f  jz      loc_180025CCF
0x1800261a5  test    byte ptr [rcx+1Ch], 40h
0x1800261a9  jz      loc_180025CCF
0x1800261af  mov     edx, 24h ; '$'
0x1800261b4  jmp     loc_180026132
0x1800261b9  call    cs:__imp_GetLastError
0x1800261c0  nop     dword ptr [rax+rax+00h]
0x1800261c5  mov     ebx, eax
0x1800261c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261ce  lea     rdi, WPP_GLOBAL_Control
0x1800261d5  cmp     rcx, rdi
0x1800261d8  jz      loc_180025CCF
0x1800261de  test    byte ptr [rcx+1Ch], 40h
0x1800261e2  jz      loc_180025CCF
0x1800261e8  mov     edx, 23h ; '#'
0x1800261ed  jmp     loc_180026132
0x1800261f2  call    cs:__imp_GetLastError
0x1800261f9  nop     dword ptr [rax+rax+00h]
0x1800261fe  mov     ebx, eax
0x180026200  mov     rcx, cs:WPP_GLOBAL_Control
0x180026207  lea     rdi, WPP_GLOBAL_Control
0x18002620e  cmp     rcx, rdi
0x180026211  jz      loc_180025CCF
0x180026217  test    byte ptr [rcx+1Ch], 40h
0x18002621b  jz      loc_180025CCF
0x180026221  mov     edx, 29h ; ')'
0x180026226  jmp     loc_180026132
0x18002622b  call    cs:__imp_GetLastError
0x180026232  nop     dword ptr [rax+rax+00h]
0x180026237  mov     ebx, eax
0x180026239  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
