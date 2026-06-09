# NlCleanup(void)

- ea: `0x180029d5c`
- end: `0x18002a6eb`
- name: `?NlCleanup@@YAKXZ`
- size: `2447`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180077610`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x180008170`
- `0x18000dd00`
- `0x18000dd78`
- `0x18000ddec`
- `0x18000f3e4`
- `0x18001abcc`
- `0x180023a64`
- `0x18002520c`
- `0x180025a74`
- `0x180028dbc`
- `0x180029d5c`
- `0x18002edcc`
- `0x18003bfcc`
- `0x18003e0fc`
- `0x180044b14`
- `0x180049dac`
- `0x180050ea4`
- `0x180053344`
- `0x180058ecc`
- `0x18005c1ac`
- `0x180068d04`
- `0x180070a08`
- `0x1800865f4`
- `0x180087968`
- `0x18008dd38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029ea2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a517`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180029ea2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a517`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a266`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002a266`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a234`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a234`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029d82`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180029d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a46c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a46c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180029ede`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180029ede`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180029f37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180029f37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180029ef1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180029ef1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029f24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029eb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a3ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a45c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a52a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a582`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029eb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a3ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a45c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a4f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a52a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a582`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a24c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a24c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5c0`
- `RPCRT4!RpcServerUnregisterIf` at `0x180029e22`
- `RPCRT4!RpcServerUnregisterIf` at `0x180029e22`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18002a675`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18002a675`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18002a6b7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18002a6b7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002a4d6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002a4d6`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x180029f54`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x180029f54`
- `LSASRV!LsarClose` at `0x18002a499`
- `LSASRV!LsarClose` at `0x18002a499`
- `ntdll!RtlDeleteResource` at `0x18002a2bc`
- `ntdll!RtlDeleteResource` at `0x18002a312`
- `ntdll!RtlDeleteResource` at `0x18002a325`
- `ntdll!RtlDeleteResource` at `0x18002a338`
- `ntdll!RtlDeleteResource` at `0x18002a34b`
- `ntdll!RtlDeleteResource` at `0x18002a35e`
- `ntdll!RtlDeleteResource` at `0x18002a2bc`
- `ntdll!RtlDeleteResource` at `0x18002a312`
- `ntdll!RtlDeleteResource` at `0x18002a325`
- `ntdll!RtlDeleteResource` at `0x18002a338`
- `ntdll!RtlDeleteResource` at `0x18002a34b`
- `ntdll!RtlDeleteResource` at `0x18002a35e`
- `ntdll!EtwUnregisterTraceGuids` at `0x18002a3df`
- `ntdll!EtwUnregisterTraceGuids` at `0x18002a3df`
- `ntdll!RtlLeaveCriticalSection` at `0x180029e83`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a08d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a16f`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a1df`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a5da`
- `ntdll!RtlLeaveCriticalSection` at `0x180029e83`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a08d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a16f`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a1df`
- `ntdll!RtlLeaveCriticalSection` at `0x18002a5da`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a27f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a2d5`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a27f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002a2d5`
- `ntdll!RtlDeleteSecurityObject` at `0x18002a1fb`
- `ntdll!RtlDeleteSecurityObject` at `0x18002a1fb`
- `ntdll!RtlDeleteCriticalSection` at `0x180029fbe`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a01c`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a034`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a047`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a09c`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a125`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a17e`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a380`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a393`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a605`
- `ntdll!RtlDeleteCriticalSection` at `0x180029fbe`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a01c`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a034`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a047`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a09c`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a125`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a17e`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a380`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a393`
- `ntdll!RtlDeleteCriticalSection` at `0x18002a605`
- `ntdll!RtlEnterCriticalSection` at `0x180029e54`
- `ntdll!RtlEnterCriticalSection` at `0x18002a066`
- `ntdll!RtlEnterCriticalSection` at `0x18002a13b`
- `ntdll!RtlEnterCriticalSection` at `0x18002a191`
- `ntdll!RtlEnterCriticalSection` at `0x18002a56a`
- `ntdll!RtlEnterCriticalSection` at `0x180029e54`
- `ntdll!RtlEnterCriticalSection` at `0x18002a066`
- `ntdll!RtlEnterCriticalSection` at `0x18002a13b`
- `ntdll!RtlEnterCriticalSection` at `0x18002a191`
- `ntdll!RtlEnterCriticalSection` at `0x18002a56a`
- `ntdll!RtlReleaseResource` at `0x18002a2ad`
- `ntdll!RtlReleaseResource` at `0x18002a303`
- `ntdll!RtlReleaseResource` at `0x18002a2ad`
- `ntdll!RtlReleaseResource` at `0x18002a303`
- `gmsaclient!GMSACleanup` at `0x180029f64`
- `gmsaclient!GMSACleanup` at `0x180029f64`
- `netutils!NetApiBufferFree` at `0x18002a21a`
- `netutils!NetApiBufferFree` at `0x18002a21a`
- `WS2_32!__imp_WSACleanup` at `0x18002a3c7`
- `WS2_32!__imp_WSACleanup` at `0x18002a3c7`
- `AUTHZ!AuthzShutdownRemoteAccessCheck` at `0x180029db0`
- `AUTHZ!AuthzShutdownRemoteAccessCheck` at `0x180029db0`
- `AUTHZ!AuthzFreeResourceManager` at `0x180029dce`
- `AUTHZ!AuthzFreeResourceManager` at `0x180029ded`
- `AUTHZ!AuthzFreeResourceManager` at `0x18002a410`
- `AUTHZ!AuthzFreeResourceManager` at `0x180029dce`
- `AUTHZ!AuthzFreeResourceManager` at `0x180029ded`
- `AUTHZ!AuthzFreeResourceManager` at `0x18002a410`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002a62c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002a62c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180029fd6`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180029fd6`
- `CRYPTSP!CryptReleaseContext` at `0x18002a54b`
- `CRYPTSP!CryptReleaseContext` at `0x18002a54b`

## string_xrefs

- `0x180029e0d`: `onecore\ds\netapi\svcdlls\logonsrv\server\error.cxx`
- `0x180029f8b`: `IsListEmpty( &NlGlobalServiceAccountList )`
- `0x180029fa8`: `!NlGlobalServiceAccountInitialized`
- `0x18002a0f2`: `IsListEmpty( &NlGlobalChallengeList )`
- `0x18002a68e`: `NlCleanup: Delete successful.\n`
- `0x18002a69f`: `NlCleanup: Could not delete old perf instance: Status = %d\n`

## pseudocode

```c
__int64 NlCleanup(void)
{
  char *v0; // r9
  bool v1; // bl
  HANDLE v2; // rcx
  char *v3; // r9
  DWORD v4; // eax
  char *v5; // r9
  struct _LIST_ENTRY *Flink; // rax
  DWORD LastError; // eax
  DWORD v8; // eax
  int v9; // eax
  unsigned __int16 *InstanceName; // rax
  __int64 v11; // rcx
  ULONG v12; // eax
  __int64 result; // rax

  NlGlobalChangeLogNetlogonState = 0;
  NlGlobalTerminate = 1;
  if ( NlGlobalStartedEvent )
  {
    ResetEvent(NlGlobalStartedEvent);
    CloseHandle(NlGlobalStartedEvent);
    NlGlobalStartedEvent = 0;
  }
  if ( NlGlobalRemoteAccessCheckStarted )
  {
    AuthzShutdownRemoteAccessCheck();
    NlGlobalRemoteAccessCheckStarted = 0;
  }
  if ( NlGlobalResourceManagerNoCAP )
  {
    AuthzFreeResourceManager(NlGlobalResourceManagerNoCAP);
    NlGlobalResourceManagerNoCAP = 0;
  }
  if ( NlGlobalResourceManagerWithCAP )
  {
    AuthzFreeResourceManager(NlGlobalResourceManagerWithCAP);
    NlGlobalResourceManagerWithCAP = 0;
  }
  NlDnsRemoteScavenge(0);
  if ( NlGlobalRpcServerStarted )
  {
    if ( RpcServerUnregisterIf(qword_180099E80, 0, 1u) )
      NlAssertFailed("Status == RPC_S_OK", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx", 0x78u, v0);
    NlGlobalRpcServerStarted = 0;
  }
  RtlEnterCriticalSection(&NlGlobalMsvCritSect);
  if ( NlGlobalMsvEnabled )
  {
    NlGlobalMsvEnabled = 0;
    v1 = NlGlobalMsvThreadCount != 0;
  }
  else
  {
    v1 = 0;
  }
  RtlLeaveCriticalSection(&NlGlobalMsvCritSect);
  v2 = NlGlobalMsvTerminateEvent;
  if ( NlGlobalMsvTerminateEvent )
  {
    if ( v1 )
    {
      WaitForSingleObject(NlGlobalMsvTerminateEvent, 0xFFFFFFFF);
      v2 = NlGlobalMsvTerminateEvent;
    }
    CloseHandle(v2);
    NlGlobalMsvTerminateEvent = 0;
  }
  NlWorkerTermination();
  if ( NlGlobalThreadpoolCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(NlGlobalThreadpoolCleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(NlGlobalThreadpoolCleanupGroup);
    NlGlobalThreadpoolCleanupGroup = 0;
    memset_0(&NlGlobalThreadpoolEnvironment, 0, sizeof(NlGlobalThreadpoolEnvironment));
  }
  if ( gInboundFilterEventsTimer )
  {
    WaitForThreadpoolTimerCallbacks(gInboundFilterEventsTimer, 1);
    CloseThreadpoolTimer(gInboundFilterEventsTimer);
    gInboundFilterEventsTimer = 0;
    NlpLogFilterInboundNamespaceSummaryEventsIfNecessary();
  }
  NlCleanupServiceAccounts();
  if ( !(unsigned __int8)LsaIIsInEmulatedDomainJoinMode() )
    GMSACleanup();
  NlUninitializeDomains();
  if ( NlGlobalServiceAccountList != &NlGlobalServiceAccountList )
    NlAssertFailed(
      "IsListEmpty( &NlGlobalServiceAccountList )",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx",
      0xCAu,
      v3);
  if ( NlGlobalServiceAccountInitialized )
    NlAssertFailed(
      "!NlGlobalServiceAccountInitialized",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx",
      0xCBu,
      v3);
  RtlDeleteCriticalSection(&NlGlobalServiceAccountCritSect);
  if ( g_hNqmNotification )
  {
    v4 = PowerSettingUnregisterNotification(g_hNqmNotification);
    g_hNqmNotification = 0;
    NlPrintRoutine(1u, L"NlRegisterNQMNotifications: PowerSettingUnregisterNotification returned 0x%x\n", v4);
  }
  g_LowPowerNQMState = 0;
  NlBrowserClose();
  NlUninitializeDomainNameMapper();
  NlUninitializeLocatorConnectionCache();
  NlTransportClose();
  RtlDeleteCriticalSection(&NlGlobalTransportCritSect);
  NlDnsShutdown();
  RtlDeleteCriticalSection(&NlGlobalDnsCritSect);
  RtlDeleteCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
  NlSetDnsForestName(0, 0);
  RtlEnterCriticalSection(&NlGlobalDnsForestNameCritSect);
  if ( NlGlobalUtf8DnsForestNameAlias )
  {
    NetpMemoryFree();
    NlGlobalUtf8DnsForestNameAlias = 0;
  }
  RtlLeaveCriticalSection(&NlGlobalDnsForestNameCritSect);
  RtlDeleteCriticalSection(&NlGlobalDnsForestNameCritSect);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
    NlSiteTerminate();
  else
    NlSiteTerminate_Old();
  NlParseFree((struct _NETLOGON_PARAMETERS *)&NlGlobalParameters);
  NlRemoveChallengeForClient(0, 0, 0);
  if ( NlGlobalChallengeList != &NlGlobalChallengeList )
    NlAssertFailed(
      "IsListEmpty( &NlGlobalChallengeList )",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx",
      0x117u,
      v5);
  if ( NlGlobalChallengeCount )
    NlAssertFailed(
      "NlGlobalChallengeCount == 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx",
      0x118u,
      v5);
  RtlDeleteCriticalSection(&NlGlobalChallengeCritSect);
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  if ( NlGlobalTrustedDomainList )
  {
    NetpMemoryFree();
    NlGlobalTrustedDomainList = 0;
    NlGlobalTrustedDomainCount = 0;
    NlGlobalTrustedDomainListTime = 0;
  }
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  RtlDeleteCriticalSection(&NlGlobalDcDiscoveryCritSect);
  RtlEnterCriticalSection(&NlGlobalChangeLogCritSect);
  while ( NlGlobalChangeLogNotifications.Flink != &NlGlobalChangeLogNotifications )
  {
    if ( NlGlobalChangeLogNotifications.Flink->Blink != &NlGlobalChangeLogNotifications
      || (Flink = NlGlobalChangeLogNotifications.Flink->Flink,
          NlGlobalChangeLogNotifications.Flink->Flink->Blink != NlGlobalChangeLogNotifications.Flink) )
    {
      __fastfail(3u);
    }
    NlGlobalChangeLogNotifications.Flink = NlGlobalChangeLogNotifications.Flink->Flink;
    Flink->Blink = &NlGlobalChangeLogNotifications;
    NetpMemoryFree();
  }
  RtlLeaveCriticalSection(&NlGlobalChangeLogCritSect);
  if ( NlGlobalNetlogonSecurityDescriptor )
  {
    RtlDeleteSecurityObject(&NlGlobalNetlogonSecurityDescriptor);
    NlGlobalNetlogonSecurityDescriptor = 0;
  }
  if ( NlGlobalUnicodeComputerName )
  {
    NetApiBufferFree(NlGlobalUnicodeComputerName);
    NlGlobalUnicodeComputerName = 0;
  }
  AcquireSRWLockExclusive(&stru_1800F7F58);
  if ( NlGlobalVulnerableChannelAllowList )
  {
    LocalFree(NlGlobalVulnerableChannelAllowList);
    NlGlobalVulnerableChannelAllowList = 0;
  }
  ReleaseSRWLockExclusive(&stru_1800F7F58);
  RtlAcquireResourceExclusive(&NlGlobalRpcSecurityDescriptorLock, 1u);
  if ( NlGlobalRpcSecurityDescriptor )
  {
    LocalFree(NlGlobalRpcSecurityDescriptor);
    NlGlobalRpcSecurityDescriptor = 0;
  }
  RtlReleaseResource(&NlGlobalRpcSecurityDescriptorLock);
  RtlDeleteResource(&NlGlobalRpcSecurityDescriptorLock);
  RtlAcquireResourceExclusive(&NlGlobalRemoteAccessCheckSecurityDescriptorLock, 1u);
  if ( NlGlobalRemoteAccessCheckSecurityDescriptor )
  {
    LocalFree(NlGlobalRemoteAccessCheckSecurityDescriptor);
    NlGlobalRemoteAccessCheckSecurityDescriptor = 0;
  }
  RtlReleaseResource(&NlGlobalRemoteAccessCheckSecurityDescriptorLock);
  RtlDeleteResource(&NlGlobalRemoteAccessCheckSecurityDescriptorLock);
  RtlDeleteResource(&NlGlobalNtlmAllowedServersLock);
  RtlDeleteResource(&NlGlobalCompoundIdLock);
  RtlDeleteResource(&NlPcGlobalLock);
  RtlDeleteResource(&NlGlobalGMSADPAPILock);
  dword_1800F7D10 = -1;
  NetpFreeWellKnownSids();
  RtlDeleteCriticalSection(&NlGlobalScavengerCritSect);
  RtlDeleteCriticalSection(&NlGlobalEventLoggerCritSect);
  if ( NlGlobalTimerEvent )
  {
    CloseHandle(NlGlobalTimerEvent);
    NlGlobalTimerEvent = 0;
  }
  if ( NlGlobalWinSockInitialized )
    WSACleanup();
  if ( NlpTraceRegistrationHandle )
  {
    EtwUnregisterTraceGuids();
    NlpEventTraceFlag = 0;
    NlpTraceRegistrationHandle = 0;
    NlpTraceLoggerHandle = 0;
  }
  if ( NlAuthzRM )
  {
    if ( AuthzFreeResourceManager(NlAuthzRM) )
    {
      NlAuthzRM = 0;
    }
    else
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"AuthzFreeResourceManager failed 0x%lx\n", LastError);
    }
  }
  LODWORD(NlGlobalEventlogHandle[1].OwningThread) = 0;
  NetpEventlogClearList();
  if ( !CloseHandle(NlGlobalTerminateEvent) )
  {
    v8 = GetLastError();
    NlPrintRoutine(0x100u, L"CloseHandle NlGlobalTerminateEvent error: %lu\n", v8);
  }
  if ( NlGlobalLsaPolicyHandle )
  {
    v9 = LsarClose(&NlGlobalLsaPolicyHandle);
    if ( v9 >= 0 )
      NlGlobalLsaPolicyHandle = 0;
    else
      NlPrintRoutine(0x100u, L"Failed to close the LSA policy handle 0x%08X\n", (unsigned int)v9);
  }
  if ( NlGlobalDsPausedWaitHandle )
  {
    UnregisterWaitEx(NlGlobalDsPausedWaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    NlGlobalDsPausedWaitHandle = 0;
  }
  if ( NlGlobalDsPausedEvent )
  {
    CloseHandle(NlGlobalDsPausedEvent);
    NlGlobalDsPausedEvent = 0;
  }
  if ( NlCacheJoinDCPingThread )
  {
    WaitForSingleObject(NlCacheJoinDCPingThread, 0xFFFFFFFF);
    CloseHandle(NlCacheJoinDCPingThread);
    NlCacheJoinDCPingThread = 0;
  }
  if ( NlGlobalCryptProvider )
  {
    CryptReleaseContext(NlGlobalCryptProvider, 0);
    NlGlobalCryptProvider = 0;
  }
  NlCleanupCNG();
  RtlEnterCriticalSection(&NlGlobalLogFileCritSect);
  if ( NlGlobalLogFile != (HANDLE)-1LL )
  {
    CloseHandle(NlGlobalLogFile);
    NlGlobalLogFile = (HANDLE)-1LL;
  }
  if ( NlGlobalLogFileOutputBuffer )
  {
    LocalFree((HLOCAL)NlGlobalLogFileOutputBuffer);
    NlGlobalLogFileOutputBuffer = 0;
  }
  if ( NlGlobalLogFileUtf8Buffer )
  {
    LocalFree(NlGlobalLogFileUtf8Buffer);
    NlGlobalLogFileUtf8Buffer = 0;
  }
  RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
  if ( NlGlobalDebugSharePath )
  {
    NetpMemoryFree();
    NlGlobalDebugSharePath = 0;
  }
  RtlDeleteCriticalSection(&NlGlobalParametersCritSect);
  NlGlobalServiceStatus.dwCurrentState = 1;
  *(_QWORD *)&NlGlobalServiceStatus.dwCheckPoint = 0;
  SetServiceStatus(NlGlobalServiceHandle, &NlGlobalServiceStatus);
  NlDCLocUninitializeGlobalPerformanceCounters();
  if ( NlPcGlobalTotalInstance )
  {
    InstanceName = NlPcGetInstanceName(NlPcGlobalTotalInstance);
    NlPrintRoutine(0x8000u, L"NlCleanup: Shutting down NlPcGlobalTotalInstance (%p): \"%ws\"\n", v11, InstanceName);
    v12 = PerfDeleteInstance(hDataSource_PerfCntr_1, NlPcGlobalTotalInstance);
    NlPcGlobalTotalInstance = 0;
    if ( v12 )
      NlPrintRoutine(0x8000u, L"NlCleanup: Could not delete old perf instance: Status = %d\n", v12);
    else
      NlPrintRoutine(0x8000u, L"NlCleanup: Delete successful.\n");
  }
  if ( hDataSource_PerfCntr_1 )
  {
    PerfStopProvider(hDataSource_PerfCntr_1);
    hDataSource_PerfCntr_1 = 0;
  }
  NlCleanupFallbackHandleScratchPad();
  result = NlGlobalServiceStatus.dwWin32ExitCode;
  if ( NlGlobalServiceStatus.dwWin32ExitCode == 1066 )
    return NlGlobalServiceStatus.dwServiceSpecificExitCode;
  return result;
}

```

## disassembly

```asm
0x180029d5c  push    rbx
0x180029d5e  push    rbp
0x180029d5f  push    rsi
0x180029d60  push    rdi
0x180029d61  sub     rsp, 28h
0x180029d65  mov     rcx, cs:?NlGlobalStartedEvent@@3PEAXEA; hEvent
0x180029d6c  xor     edi, edi
0x180029d6e  mov     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, edi; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x180029d74  lea     ebp, [rdi+1]
0x180029d77  mov     cs:?NlGlobalTerminate@@3HA, ebp; int NlGlobalTerminate
0x180029d7d  test    rcx, rcx
0x180029d80  jz      short loc_180029DA8
0x180029d82  call    cs:__imp_ResetEvent
0x180029d89  nop     dword ptr [rax+rax+00h]
0x180029d8e  mov     rcx, cs:?NlGlobalStartedEvent@@3PEAXEA; hObject
0x180029d95  call    cs:__imp_CloseHandle
0x180029d9c  nop     dword ptr [rax+rax+00h]
0x180029da1  mov     cs:?NlGlobalStartedEvent@@3PEAXEA, rdi; void * NlGlobalStartedEvent
0x180029da8  cmp     cs:?NlGlobalRemoteAccessCheckStarted@@3HA, edi; int NlGlobalRemoteAccessCheckStarted
0x180029dae  jz      short loc_180029DC2
0x180029db0  call    cs:__imp_AuthzShutdownRemoteAccessCheck
0x180029db7  nop     dword ptr [rax+rax+00h]
0x180029dbc  mov     cs:?NlGlobalRemoteAccessCheckStarted@@3HA, edi; int NlGlobalRemoteAccessCheckStarted
0x180029dc2  mov     rcx, cs:?NlGlobalResourceManagerNoCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x180029dc9  test    rcx, rcx
0x180029dcc  jz      short loc_180029DE1
0x180029dce  call    cs:__imp_AuthzFreeResourceManager
0x180029dd5  nop     dword ptr [rax+rax+00h]
0x180029dda  mov     cs:?NlGlobalResourceManagerNoCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rdi; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerNoCAP
0x180029de1  mov     rcx, cs:?NlGlobalResourceManagerWithCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x180029de8  test    rcx, rcx
0x180029deb  jz      short loc_180029E00
0x180029ded  call    cs:__imp_AuthzFreeResourceManager
0x180029df4  nop     dword ptr [rax+rax+00h]
0x180029df9  mov     cs:?NlGlobalResourceManagerWithCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rdi; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerWithCAP
0x180029e00  xor     ecx, ecx; unsigned int
0x180029e02  call    ?NlDnsRemoteScavenge@@YAXK@Z; NlDnsRemoteScavenge(ulong)
0x180029e07  cmp     cs:?NlGlobalRpcServerStarted@@3HA, edi; int NlGlobalRpcServerStarted
0x180029e0d  lea     rsi, aOnecoreDsNetap_3; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180029e14  jz      short loc_180029E4D
0x180029e16  mov     r8d, ebp; WaitForCallsToComplete
0x180029e19  lea     rcx, qword_180099E80; IfSpec
0x180029e20  xor     edx, edx; MgrTypeUuid
0x180029e22  call    cs:__imp_RpcServerUnregisterIf
0x180029e29  nop     dword ptr [rax+rax+00h]
0x180029e2e  test    eax, eax
0x180029e30  jz      short loc_180029E47
0x180029e32  mov     r8d, 78h ; 'x'; unsigned int
0x180029e38  lea     rcx, aStatusRpcSOk; "Status == RPC_S_OK"
0x180029e3f  mov     rdx, rsi; void *
0x180029e42  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180029e47  mov     cs:?NlGlobalRpcServerStarted@@3HA, edi; int NlGlobalRpcServerStarted
0x180029e4d  lea     rcx, ?NlGlobalMsvCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180029e54  call    cs:__imp_RtlEnterCriticalSection
0x180029e5b  nop     dword ptr [rax+rax+00h]
0x180029e60  cmp     cs:?NlGlobalMsvEnabled@@3HA, edi; int NlGlobalMsvEnabled
0x180029e66  jz      short loc_180029E79
0x180029e68  cmp     cs:?NlGlobalMsvThreadCount@@3KA, edi; ulong NlGlobalMsvThreadCount
0x180029e6e  mov     cs:?NlGlobalMsvEnabled@@3HA, edi; int NlGlobalMsvEnabled
0x180029e74  setnbe  bl
0x180029e77  jmp     short loc_180029E7C
0x180029e79  mov     bl, dil
0x180029e7c  lea     rcx, ?NlGlobalMsvCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180029e83  call    cs:__imp_RtlLeaveCriticalSection
0x180029e8a  nop     dword ptr [rax+rax+00h]
0x180029e8f  mov     rcx, cs:?NlGlobalMsvTerminateEvent@@3PEAXEA; hHandle
0x180029e96  test    rcx, rcx
0x180029e99  jz      short loc_180029EC8
0x180029e9b  test    bl, bl
0x180029e9d  jz      short loc_180029EB5
0x180029e9f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180029ea2  call    cs:__imp_WaitForSingleObject
0x180029ea9  nop     dword ptr [rax+rax+00h]
0x180029eae  mov     rcx, cs:?NlGlobalMsvTerminateEvent@@3PEAXEA; hObject
0x180029eb5  call    cs:__imp_CloseHandle
0x180029ebc  nop     dword ptr [rax+rax+00h]
0x180029ec1  mov     cs:?NlGlobalMsvTerminateEvent@@3PEAXEA, rdi; void * NlGlobalMsvTerminateEvent
0x180029ec8  call    ?NlWorkerTermination@@YAXXZ; NlWorkerTermination(void)
0x180029ecd  mov     rcx, cs:?NlGlobalThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180029ed4  test    rcx, rcx
0x180029ed7  jz      short loc_180029F16
0x180029ed9  xor     r8d, r8d; pvCleanupContext
0x180029edc  mov     edx, ebp; fCancelPendingCallbacks
0x180029ede  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180029ee5  nop     dword ptr [rax+rax+00h]
0x180029eea  mov     rcx, cs:?NlGlobalThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180029ef1  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180029ef8  nop     dword ptr [rax+rax+00h]
0x180029efd  xor     edx, edx; Val
0x180029eff  mov     cs:?NlGlobalThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rdi; _TP_CLEANUP_GROUP * NlGlobalThreadpoolCleanupGroup
0x180029f06  lea     rcx, ?NlGlobalThreadpoolEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; void *
0x180029f0d  lea     r8d, [rdx+48h]; Size
0x180029f11  call    memset_0
0x180029f16  mov     rcx, cs:?gInboundFilterEventsTimer@@3PEAU_TP_TIMER@@EA; pti
0x180029f1d  test    rcx, rcx
0x180029f20  jz      short loc_180029F4F
0x180029f22  mov     edx, ebp; fCancelPendingCallbacks
0x180029f24  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180029f2b  nop     dword ptr [rax+rax+00h]
0x180029f30  mov     rcx, cs:?gInboundFilterEventsTimer@@3PEAU_TP_TIMER@@EA; pti
0x180029f37  call    cs:__imp_CloseThreadpoolTimer
0x180029f3e  nop     dword ptr [rax+rax+00h]
0x180029f43  mov     cs:?gInboundFilterEventsTimer@@3PEAU_TP_TIMER@@EA, rdi; _TP_TIMER * gInboundFilterEventsTimer
0x180029f4a  call    ?NlpLogFilterInboundNamespaceSummaryEventsIfNecessary@@YAXXZ; NlpLogFilterInboundNamespaceSummaryEventsIfNecessary(void)
0x180029f4f  call    ?NlCleanupServiceAccounts@@YAXXZ; NlCleanupServiceAccounts(void)
0x180029f54  call    cs:__imp_LsaIIsInEmulatedDomainJoinMode
0x180029f5b  nop     dword ptr [rax+rax+00h]
0x180029f60  test    al, al
0x180029f62  jnz     short loc_180029F70
0x180029f64  call    cs:__imp_GMSACleanup
0x180029f6b  nop     dword ptr [rax+rax+00h]
0x180029f70  call    ?NlUninitializeDomains@@YAXXZ; NlUninitializeDomains(void)
0x180029f75  lea     rax, ?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServiceAccountList
0x180029f7c  cmp     cs:?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServiceAccountList
0x180029f83  jz      short loc_180029F9A
0x180029f85  mov     r8d, 0CAh; unsigned int
0x180029f8b  lea     rcx, aIslistemptyNlg_0; "IsListEmpty( &NlGlobalServiceAccountLis"...
0x180029f92  mov     rdx, rsi; void *
0x180029f95  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180029f9a  cmp     cs:?NlGlobalServiceAccountInitialized@@3KA, edi; ulong NlGlobalServiceAccountInitialized
0x180029fa0  jz      short loc_180029FB7
0x180029fa2  mov     r8d, 0CBh; unsigned int
0x180029fa8  lea     rcx, aNlglobalservic; "!NlGlobalServiceAccountInitialized"
0x180029faf  mov     rdx, rsi; void *
0x180029fb2  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180029fb7  lea     rcx, ?NlGlobalServiceAccountCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180029fbe  call    cs:__imp_RtlDeleteCriticalSection
0x180029fc5  nop     dword ptr [rax+rax+00h]
0x180029fca  mov     rcx, cs:?g_hNqmNotification@@3PEAXEA; RegistrationHandle
0x180029fd1  test    rcx, rcx
0x180029fd4  jz      short loc_180029FFA
0x180029fd6  call    cs:__imp_PowerSettingUnregisterNotification
0x180029fdd  nop     dword ptr [rax+rax+00h]
0x180029fe2  lea     rdx, aNlregisternqmn_0; "NlRegisterNQMNotifications: PowerSettin"...
0x180029fe9  mov     cs:?g_hNqmNotification@@3PEAXEA, rdi; void * g_hNqmNotification
0x180029ff0  mov     r8d, eax
0x180029ff3  mov     ecx, ebp; unsigned int
0x180029ff5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180029ffa  mov     cs:?g_LowPowerNQMState@@3EA, dil; uchar g_LowPowerNQMState
0x18002a001  call    ?NlBrowserClose@@YAXXZ; NlBrowserClose(void)
0x18002a006  call    ?NlUninitializeDomainNameMapper@@YAXXZ; NlUninitializeDomainNameMapper(void)
0x18002a00b  call    ?NlUninitializeLocatorConnectionCache@@YAXXZ; NlUninitializeLocatorConnectionCache(void)
0x18002a010  call    ?NlTransportClose@@YAXXZ; NlTransportClose(void)
0x18002a015  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002a01c  call    cs:__imp_RtlDeleteCriticalSection
0x18002a023  nop     dword ptr [rax+rax+00h]
0x18002a028  call    ?NlDnsShutdown@@YAXXZ; NlDnsShutdown(void)
0x18002a02d  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002a034  call    cs:__imp_RtlDeleteCriticalSection
0x18002a03b  nop     dword ptr [rax+rax+00h]
0x18002a040  lea     rcx, ?NlGlobalDnsUpdateRequestCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002a047  call    cs:__imp_RtlDeleteCriticalSection
0x18002a04e  nop     dword ptr [rax+rax+00h]
0x18002a053  xor     edx, edx; unsigned __int8 *
0x18002a055  xor     ecx, ecx; struct _UNICODE_STRING *
0x18002a057  call    ?NlSetDnsForestName@@YAKPEAU_UNICODE_STRING@@PEAE@Z; NlSetDnsForestName(_UNICODE_STRING *,uchar *)
0x18002a05c  lea     rbx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDnsForestNameCritSect
0x18002a063  mov     rcx, rbx; CriticalSection
0x18002a066  call    cs:__imp_RtlEnterCriticalSection
0x18002a06d  nop     dword ptr [rax+rax+00h]
0x18002a072  mov     rcx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x18002a079  test    rcx, rcx
0x18002a07c  jz      short loc_18002A08A
0x18002a07e  call    NetpMemoryFree
0x18002a083  mov     cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA, rdi; char * NlGlobalUtf8DnsForestNameAlias
0x18002a08a  mov     rcx, rbx; CriticalSection
0x18002a08d  call    cs:__imp_RtlLeaveCriticalSection
0x18002a094  nop     dword ptr [rax+rax+00h]
0x18002a099  mov     rcx, rbx; CriticalSection
0x18002a09c  call    cs:__imp_RtlDeleteCriticalSection
0x18002a0a3  nop     dword ptr [rax+rax+00h]
0x18002a0a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x18002a0af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x18002a0b4  test    al, al
0x18002a0b6  jz      short loc_18002A0BF
0x18002a0b8  call    ?NlSiteTerminate@@YAXXZ; NlSiteTerminate(void)
0x18002a0bd  jmp     short loc_18002A0C4
0x18002a0bf  call    ?NlSiteTerminate_Old@@YAXXZ; NlSiteTerminate_Old(void)
0x18002a0c4  lea     rcx, ?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A; struct _NETLOGON_PARAMETERS *
0x18002a0cb  call    ?NlParseFree@@YAXPEAU_NETLOGON_PARAMETERS@@@Z; NlParseFree(_NETLOGON_PARAMETERS *)
0x18002a0d0  xor     r8d, r8d; int
0x18002a0d3  xor     edx, edx; unsigned __int16 *
0x18002a0d5  xor     ecx, ecx; unsigned __int16 *
0x18002a0d7  call    ?NlRemoveChallengeForClient@@YAXPEAG0H@Z; NlRemoveChallengeForClient(ushort *,ushort *,int)
0x18002a0dc  lea     rax, ?NlGlobalChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChallengeList
0x18002a0e3  cmp     cs:?NlGlobalChallengeList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChallengeList
0x18002a0ea  jz      short loc_18002A101
0x18002a0ec  mov     r8d, 117h; unsigned int
0x18002a0f2  lea     rcx, aIslistemptyNlg_2; "IsListEmpty( &NlGlobalChallengeList )"
0x18002a0f9  mov     rdx, rsi; void *
0x18002a0fc  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002a101  cmp     cs:?NlGlobalChallengeCount@@3KA, edi; ulong NlGlobalChallengeCount
0x18002a107  jz      short loc_18002A11E
0x18002a109  mov     r8d, 118h; unsigned int
0x18002a10f  lea     rcx, aNlglobalchalle; "NlGlobalChallengeCount == 0"
0x18002a116  mov     rdx, rsi; void *
0x18002a119  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002a11e  lea     rcx, ?NlGlobalChallengeCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002a125  call    cs:__imp_RtlDeleteCriticalSection
0x18002a12c  nop     dword ptr [rax+rax+00h]
0x18002a131  lea     rbx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDcDiscoveryCritSect
0x18002a138  mov     rcx, rbx; CriticalSection
0x18002a13b  call    cs:__imp_RtlEnterCriticalSection
0x18002a142  nop     dword ptr [rax+rax+00h]
0x18002a147  mov     rcx, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18002a14e  test    rcx, rcx
0x18002a151  jz      short loc_18002A16C
0x18002a153  call    NetpMemoryFree
0x18002a158  mov     cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA, rdi; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x18002a15f  mov     cs:?NlGlobalTrustedDomainCount@@3KA, edi; ulong NlGlobalTrustedDomainCount
0x18002a165  mov     qword ptr cs:?NlGlobalTrustedDomainListTime@@3T_LARGE_INTEGER@@A.dwLowDateTime, rdi; _LARGE_INTEGER NlGlobalTrustedDomainListTime ...
0x18002a16c  mov     rcx, rbx; CriticalSection
0x18002a16f  call    cs:__imp_RtlLeaveCriticalSection
0x18002a176  nop     dword ptr [rax+rax+00h]
0x18002a17b  mov     rcx, rbx; CriticalSection
0x18002a17e  call    cs:__imp_RtlDeleteCriticalSection
0x18002a185  nop     dword ptr [rax+rax+00h]
0x18002a18a  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002a191  call    cs:__imp_RtlEnterCriticalSection
0x18002a198  nop     dword ptr [rax+rax+00h]
0x18002a19d  lea     rbx, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18002a1a4  mov     rcx, cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18002a1ab  cmp     rcx, rbx
0x18002a1ae  jz      short loc_18002A1D8
0x18002a1b0  cmp     [rcx+8], rbx
0x18002a1b4  jnz     short loc_18002A1D1
0x18002a1b6  mov     rax, [rcx]
0x18002a1b9  cmp     [rax+8], rcx
0x18002a1bd  jnz     short loc_18002A1D1
0x18002a1bf  mov     cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChangeLogNotifications
0x18002a1c6  mov     [rax+8], rbx
0x18002a1ca  call    NetpMemoryFree
0x18002a1cf  jmp     short loc_18002A1A4
0x18002a1d1  mov     ecx, 3
0x18002a1d6  int     29h; Win8: RtlFailFast(ecx)
0x18002a1d8  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002a1df  call    cs:__imp_RtlLeaveCriticalSection
0x18002a1e6  nop     dword ptr [rax+rax+00h]
0x18002a1eb  cmp     cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalNetlogonSecurityDescriptor
0x18002a1f2  jz      short loc_18002A20E
0x18002a1f4  lea     rcx, ?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; ObjectDescriptor
0x18002a1fb  call    cs:__imp_RtlDeleteSecurityObject
0x18002a202  nop     dword ptr [rax+rax+00h]
0x18002a207  mov     cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalNetlogonSecurityDescriptor
0x18002a20e  mov     rcx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; Buffer
0x18002a215  test    rcx, rcx
0x18002a218  jz      short loc_18002A22D
0x18002a21a  call    cs:__imp_NetApiBufferFree
0x18002a221  nop     dword ptr [rax+rax+00h]
0x18002a226  mov     cs:?NlGlobalUnicodeComputerName@@3PEAGEA, rdi; ushort * NlGlobalUnicodeComputerName
0x18002a22d  lea     rcx, stru_1800F7F58; SRWLock
0x18002a234  call    cs:__imp_AcquireSRWLockExclusive
0x18002a23b  nop     dword ptr [rax+rax+00h]
0x18002a240  mov     rcx, cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A; hMem
0x18002a247  test    rcx, rcx
0x18002a24a  jz      short loc_18002A25F
0x18002a24c  call    cs:__imp_LocalFree
0x18002a253  nop     dword ptr [rax+rax+00h]
0x18002a258  mov     cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A, rdi; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x18002a25f  lea     rcx, stru_1800F7F58; SRWLock
0x18002a266  call    cs:__imp_ReleaseSRWLockExclusive
0x18002a26d  nop     dword ptr [rax+rax+00h]
0x18002a272  lea     rbx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE NlGlobalRpcSecurityDescriptorLock
0x18002a279  mov     dl, bpl; Wait
0x18002a27c  mov     rcx, rbx; Resource
0x18002a27f  call    cs:__imp_RtlAcquireResourceExclusive
0x18002a286  nop     dword ptr [rax+rax+00h]
0x18002a28b  mov     rcx, cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA; hMem
0x18002a292  test    rcx, rcx
0x18002a295  jz      short loc_18002A2AA
0x18002a297  call    cs:__imp_LocalFree
0x18002a29e  nop     dword ptr [rax+rax+00h]
0x18002a2a3  mov     cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalRpcSecurityDescriptor
0x18002a2aa  mov     rcx, rbx; Resource
0x18002a2ad  call    cs:__imp_RtlReleaseResource
0x18002a2b4  nop     dword ptr [rax+rax+00h]
0x18002a2b9  mov     rcx, rbx; Resource
0x18002a2bc  call    cs:__imp_RtlDeleteResource
0x18002a2c3  nop     dword ptr [rax+rax+00h]
0x18002a2c8  lea     rbx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE NlGlobalRemoteAccessCheckSecurityDescriptorLock
0x18002a2cf  mov     dl, bpl; Wait
0x18002a2d2  mov     rcx, rbx; Resource
0x18002a2d5  call    cs:__imp_RtlAcquireResourceExclusive
0x18002a2dc  nop     dword ptr [rax+rax+00h]
0x18002a2e1  mov     rcx, cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA; hMem
0x18002a2e8  test    rcx, rcx
0x18002a2eb  jz      short loc_18002A300
0x18002a2ed  call    cs:__imp_LocalFree
0x18002a2f4  nop     dword ptr [rax+rax+00h]
0x18002a2f9  mov     cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalRemoteAccessCheckSecurityDescriptor
0x18002a300  mov     rcx, rbx; Resource
0x18002a303  call    cs:__imp_RtlReleaseResource
0x18002a30a  nop     dword ptr [rax+rax+00h]
0x18002a30f  mov     rcx, rbx; Resource
0x18002a312  call    cs:__imp_RtlDeleteResource
0x18002a319  nop     dword ptr [rax+rax+00h]
0x18002a31e  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x18002a325  call    cs:__imp_RtlDeleteResource
0x18002a32c  nop     dword ptr [rax+rax+00h]
0x18002a331  lea     rcx, ?NlGlobalCompoundIdLock@@3U_RTL_RESOURCE@@A; Resource
  ... truncated ...
```
