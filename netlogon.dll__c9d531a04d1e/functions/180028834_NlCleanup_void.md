# NlCleanup(void)

- ea: `0x180028834`
- end: `0x180029018`
- name: `?NlCleanup@@YAKXZ`
- size: `2020`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180072080`

## callees

- `0x180003670`
- `0x180007278`
- `0x180007e20`
- `0x18000d710`
- `0x18000d77c`
- `0x18000d7e0`
- `0x18000ed34`
- `0x180019f28`
- `0x18002291c`
- `0x180024158`
- `0x180024adc`
- `0x180027990`
- `0x180028834`
- `0x18002d2bc`
- `0x180039c7c`
- `0x18003bbb0`
- `0x180041e84`
- `0x180046cb8`
- `0x18004d8b4`
- `0x18004fc18`
- `0x1800552b0`
- `0x18005826c`
- `0x180064308`
- `0x18006b948`
- `0x180080710`
- `0x180081928`
- `0x180087870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002894a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028e8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002894a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028e8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028c72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028c72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028c4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028c4c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002885a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002885a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dfa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002897a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002897a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800289c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800289c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180028987`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180028987`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800289b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800289b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ee0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028df0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028cd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ef9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028c97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028cd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ef9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f12`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800288dc`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800288dc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180028faf`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180028faf`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180028feb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180028feb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180028e58`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180028e58`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x1800289d8`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x1800289d8`
- `LSASRV!LsarClose` at `0x180028e21`
- `LSASRV!LsarClose` at `0x180028e21`
- `ntdll!RtlDeleteResource` at `0x180028cb0`
- `ntdll!RtlDeleteResource` at `0x180028cee`
- `ntdll!RtlDeleteResource` at `0x180028cfb`
- `ntdll!RtlDeleteResource` at `0x180028d08`
- `ntdll!RtlDeleteResource` at `0x180028d15`
- `ntdll!RtlDeleteResource` at `0x180028d22`
- `ntdll!RtlDeleteResource` at `0x180028cb0`
- `ntdll!RtlDeleteResource` at `0x180028cee`
- `ntdll!RtlDeleteResource` at `0x180028cfb`
- `ntdll!RtlDeleteResource` at `0x180028d08`
- `ntdll!RtlDeleteResource` at `0x180028d15`
- `ntdll!RtlDeleteResource` at `0x180028d22`
- `ntdll!EtwUnregisterTraceGuids` at `0x180028d85`
- `ntdll!EtwUnregisterTraceGuids` at `0x180028d85`
- `ntdll!RtlLeaveCriticalSection` at `0x180028931`
- `ntdll!RtlLeaveCriticalSection` at `0x180028ae1`
- `ntdll!RtlLeaveCriticalSection` at `0x180028bab`
- `ntdll!RtlLeaveCriticalSection` at `0x180028c09`
- `ntdll!RtlLeaveCriticalSection` at `0x180028f26`
- `ntdll!RtlLeaveCriticalSection` at `0x180028931`
- `ntdll!RtlLeaveCriticalSection` at `0x180028ae1`
- `ntdll!RtlLeaveCriticalSection` at `0x180028bab`
- `ntdll!RtlLeaveCriticalSection` at `0x180028c09`
- `ntdll!RtlLeaveCriticalSection` at `0x180028f26`
- `ntdll!RtlAcquireResourceExclusive` at `0x180028c85`
- `ntdll!RtlAcquireResourceExclusive` at `0x180028cc3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180028c85`
- `ntdll!RtlAcquireResourceExclusive` at `0x180028cc3`
- `ntdll!RtlDeleteSecurityObject` at `0x180028c1f`
- `ntdll!RtlDeleteSecurityObject` at `0x180028c1f`
- `ntdll!RtlDeleteCriticalSection` at `0x180028a36`
- `ntdll!RtlDeleteCriticalSection` at `0x180028a88`
- `ntdll!RtlDeleteCriticalSection` at `0x180028a9a`
- `ntdll!RtlDeleteCriticalSection` at `0x180028aa7`
- `ntdll!RtlDeleteCriticalSection` at `0x180028aea`
- `ntdll!RtlDeleteCriticalSection` at `0x180028b6d`
- `ntdll!RtlDeleteCriticalSection` at `0x180028bb4`
- `ntdll!RtlDeleteCriticalSection` at `0x180028d3e`
- `ntdll!RtlDeleteCriticalSection` at `0x180028d4b`
- `ntdll!RtlDeleteCriticalSection` at `0x180028f4b`
- `ntdll!RtlDeleteCriticalSection` at `0x180028a36`
- `ntdll!RtlDeleteCriticalSection` at `0x180028a88`
- `ntdll!RtlDeleteCriticalSection` at `0x180028a9a`
- `ntdll!RtlDeleteCriticalSection` at `0x180028aa7`
- `ntdll!RtlDeleteCriticalSection` at `0x180028aea`
- `ntdll!RtlDeleteCriticalSection` at `0x180028b6d`
- `ntdll!RtlDeleteCriticalSection` at `0x180028bb4`
- `ntdll!RtlDeleteCriticalSection` at `0x180028d3e`
- `ntdll!RtlDeleteCriticalSection` at `0x180028d4b`
- `ntdll!RtlDeleteCriticalSection` at `0x180028f4b`
- `ntdll!RtlEnterCriticalSection` at `0x180028908`
- `ntdll!RtlEnterCriticalSection` at `0x180028ac0`
- `ntdll!RtlEnterCriticalSection` at `0x180028b7d`
- `ntdll!RtlEnterCriticalSection` at `0x180028bc1`
- `ntdll!RtlEnterCriticalSection` at `0x180028ece`
- `ntdll!RtlEnterCriticalSection` at `0x180028908`
- `ntdll!RtlEnterCriticalSection` at `0x180028ac0`
- `ntdll!RtlEnterCriticalSection` at `0x180028b7d`
- `ntdll!RtlEnterCriticalSection` at `0x180028bc1`
- `ntdll!RtlEnterCriticalSection` at `0x180028ece`
- `ntdll!RtlReleaseResource` at `0x180028ca7`
- `ntdll!RtlReleaseResource` at `0x180028ce5`
- `ntdll!RtlReleaseResource` at `0x180028ca7`
- `ntdll!RtlReleaseResource` at `0x180028ce5`
- `gmsaclient!GMSACleanup` at `0x1800289e2`
- `gmsaclient!GMSACleanup` at `0x1800289e2`
- `netutils!NetApiBufferFree` at `0x180028c38`
- `netutils!NetApiBufferFree` at `0x180028c38`
- `WS2_32!__imp_WSACleanup` at `0x180028d73`
- `WS2_32!__imp_WSACleanup` at `0x180028d73`
- `AUTHZ!AuthzShutdownRemoteAccessCheck` at `0x18002887c`
- `AUTHZ!AuthzShutdownRemoteAccessCheck` at `0x18002887c`
- `AUTHZ!AuthzFreeResourceManager` at `0x180028894`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800288ad`
- `AUTHZ!AuthzFreeResourceManager` at `0x180028db0`
- `AUTHZ!AuthzFreeResourceManager` at `0x180028894`
- `AUTHZ!AuthzFreeResourceManager` at `0x1800288ad`
- `AUTHZ!AuthzFreeResourceManager` at `0x180028db0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180028f6c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180028f6c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180028a48`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x180028a48`
- `CRYPTSP!CryptReleaseContext` at `0x180028eb5`
- `CRYPTSP!CryptReleaseContext` at `0x180028eb5`

## string_xrefs

- `0x1800288c7`: `onecore\ds\netapi\svcdlls\logonsrv\server\error.cxx`
- `0x180028a03`: `IsListEmpty( &NlGlobalServiceAccountList )`
- `0x180028a20`: `!NlGlobalServiceAccountInitialized`
- `0x180028b3a`: `IsListEmpty( &NlGlobalChallengeList )`
- `0x180028fc2`: `NlCleanup: Delete successful.\n`
- `0x180028fd3`: `NlCleanup: Could not delete old perf instance: Status = %d\n`

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
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v7; // rax
  DWORD LastError; // eax
  DWORD v9; // eax
  int v10; // eax
  unsigned __int16 *InstanceName; // rax
  __int64 v12; // rcx
  ULONG v13; // eax
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
    if ( RpcServerUnregisterIf(qword_180092E80, 0, 1u) )
      NlAssertFailed("Status == RPC_S_OK", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx", 119, v0);
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
      201,
      v3);
  if ( NlGlobalServiceAccountInitialized )
    NlAssertFailed(
      "!NlGlobalServiceAccountInitialized",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx",
      202,
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
    NetpMemoryFree(NlGlobalUtf8DnsForestNameAlias);
    NlGlobalUtf8DnsForestNameAlias = 0;
  }
  RtlLeaveCriticalSection(&NlGlobalDnsForestNameCritSect);
  RtlDeleteCriticalSection(&NlGlobalDnsForestNameCritSect);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
    NlSiteTerminate();
  else
    NlSiteTerminate_Old();
  NlParseFree((struct _NETLOGON_PARAMETERS *)&NlGlobalParameters);
  NlRemoveChallengeForClient(0, 0, 0);
  if ( NlGlobalChallengeList != &NlGlobalChallengeList )
    NlAssertFailed(
      "IsListEmpty( &NlGlobalChallengeList )",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx",
      278,
      v5);
  if ( NlGlobalChallengeCount )
    NlAssertFailed("NlGlobalChallengeCount == 0", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\error.cxx", 279, v5);
  RtlDeleteCriticalSection(&NlGlobalChallengeCritSect);
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  if ( NlGlobalTrustedDomainList )
  {
    NetpMemoryFree(NlGlobalTrustedDomainList);
    NlGlobalTrustedDomainList = 0;
    NlGlobalTrustedDomainCount = 0;
    NlGlobalTrustedDomainListTime = 0;
  }
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  RtlDeleteCriticalSection(&NlGlobalDcDiscoveryCritSect);
  RtlEnterCriticalSection(&NlGlobalChangeLogCritSect);
  while ( 1 )
  {
    Flink = NlGlobalChangeLogNotifications.Flink;
    if ( NlGlobalChangeLogNotifications.Flink == &NlGlobalChangeLogNotifications )
      break;
    if ( NlGlobalChangeLogNotifications.Flink->Blink != &NlGlobalChangeLogNotifications
      || (v7 = NlGlobalChangeLogNotifications.Flink->Flink,
          NlGlobalChangeLogNotifications.Flink->Flink->Blink != NlGlobalChangeLogNotifications.Flink) )
    {
      __fastfail(3u);
    }
    NlGlobalChangeLogNotifications.Flink = NlGlobalChangeLogNotifications.Flink->Flink;
    v7->Blink = &NlGlobalChangeLogNotifications;
    NetpMemoryFree(Flink);
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
  AcquireSRWLockExclusive(&stru_1800F0F58);
  if ( NlGlobalVulnerableChannelAllowList )
  {
    LocalFree(NlGlobalVulnerableChannelAllowList);
    NlGlobalVulnerableChannelAllowList = 0;
  }
  ReleaseSRWLockExclusive(&stru_1800F0F58);
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
  dword_1800F0D10 = -1;
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
    v9 = GetLastError();
    NlPrintRoutine(0x100u, L"CloseHandle NlGlobalTerminateEvent error: %lu\n", v9);
  }
  if ( NlGlobalLsaPolicyHandle )
  {
    v10 = LsarClose(&NlGlobalLsaPolicyHandle);
    if ( v10 >= 0 )
      NlGlobalLsaPolicyHandle = 0;
    else
      NlPrintRoutine(0x100u, L"Failed to close the LSA policy handle 0x%08X\n", (unsigned int)v10);
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
    NetpMemoryFree(NlGlobalDebugSharePath);
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
    NlPrintRoutine(0x8000u, L"NlCleanup: Shutting down NlPcGlobalTotalInstance (%p): \"%ws\"\n", v12, InstanceName);
    v13 = PerfDeleteInstance(hDataSource_PerfCntr_1, NlPcGlobalTotalInstance);
    NlPcGlobalTotalInstance = 0;
    if ( v13 )
      NlPrintRoutine(0x8000u, L"NlCleanup: Could not delete old perf instance: Status = %d\n", v13);
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
0x180028834  push    rbx
0x180028836  push    rbp
0x180028837  push    rsi
0x180028838  push    rdi
0x180028839  sub     rsp, 28h
0x18002883d  mov     rcx, cs:?NlGlobalStartedEvent@@3PEAXEA; hEvent
0x180028844  xor     edi, edi
0x180028846  mov     cs:?NlGlobalChangeLogNetlogonState@@3W4_CHANGELOG_NETLOGON_STATE@@A, edi; _CHANGELOG_NETLOGON_STATE NlGlobalChangeLogNetlogonState
0x18002884c  lea     ebp, [rdi+1]
0x18002884f  mov     cs:?NlGlobalTerminate@@3HA, ebp; int NlGlobalTerminate
0x180028855  test    rcx, rcx
0x180028858  jz      short loc_180028874
0x18002885a  call    cs:__imp_ResetEvent
0x180028860  mov     rcx, cs:?NlGlobalStartedEvent@@3PEAXEA; hObject
0x180028867  call    cs:__imp_CloseHandle
0x18002886d  mov     cs:?NlGlobalStartedEvent@@3PEAXEA, rdi; void * NlGlobalStartedEvent
0x180028874  cmp     cs:?NlGlobalRemoteAccessCheckStarted@@3HA, edi; int NlGlobalRemoteAccessCheckStarted
0x18002887a  jz      short loc_180028888
0x18002887c  call    cs:__imp_AuthzShutdownRemoteAccessCheck
0x180028882  mov     cs:?NlGlobalRemoteAccessCheckStarted@@3HA, edi; int NlGlobalRemoteAccessCheckStarted
0x180028888  mov     rcx, cs:?NlGlobalResourceManagerNoCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x18002888f  test    rcx, rcx
0x180028892  jz      short loc_1800288A1
0x180028894  call    cs:__imp_AuthzFreeResourceManager
0x18002889a  mov     cs:?NlGlobalResourceManagerNoCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rdi; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerNoCAP
0x1800288a1  mov     rcx, cs:?NlGlobalResourceManagerWithCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x1800288a8  test    rcx, rcx
0x1800288ab  jz      short loc_1800288BA
0x1800288ad  call    cs:__imp_AuthzFreeResourceManager
0x1800288b3  mov     cs:?NlGlobalResourceManagerWithCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rdi; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerWithCAP
0x1800288ba  xor     ecx, ecx; unsigned int
0x1800288bc  call    ?NlDnsRemoteScavenge@@YAXK@Z; NlDnsRemoteScavenge(ulong)
0x1800288c1  cmp     cs:?NlGlobalRpcServerStarted@@3HA, edi; int NlGlobalRpcServerStarted
0x1800288c7  lea     rsi, aOnecoreDsNetap_3; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800288ce  jz      short loc_180028901
0x1800288d0  mov     r8d, ebp; WaitForCallsToComplete
0x1800288d3  lea     rcx, qword_180092E80; IfSpec
0x1800288da  xor     edx, edx; MgrTypeUuid
0x1800288dc  call    cs:__imp_RpcServerUnregisterIf
0x1800288e2  test    eax, eax
0x1800288e4  jz      short loc_1800288FB
0x1800288e6  mov     r8d, 77h ; 'w'; unsigned int
0x1800288ec  lea     rcx, aStatusRpcSOk; "Status == RPC_S_OK"
0x1800288f3  mov     rdx, rsi; void *
0x1800288f6  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800288fb  mov     cs:?NlGlobalRpcServerStarted@@3HA, edi; int NlGlobalRpcServerStarted
0x180028901  lea     rcx, ?NlGlobalMsvCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028908  call    cs:__imp_RtlEnterCriticalSection
0x18002890e  cmp     cs:?NlGlobalMsvEnabled@@3HA, edi; int NlGlobalMsvEnabled
0x180028914  jz      short loc_180028927
0x180028916  cmp     cs:?NlGlobalMsvThreadCount@@3KA, edi; ulong NlGlobalMsvThreadCount
0x18002891c  mov     cs:?NlGlobalMsvEnabled@@3HA, edi; int NlGlobalMsvEnabled
0x180028922  setnbe  bl
0x180028925  jmp     short loc_18002892A
0x180028927  mov     bl, dil
0x18002892a  lea     rcx, ?NlGlobalMsvCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028931  call    cs:__imp_RtlLeaveCriticalSection
0x180028937  mov     rcx, cs:?NlGlobalMsvTerminateEvent@@3PEAXEA; hHandle
0x18002893e  test    rcx, rcx
0x180028941  jz      short loc_180028964
0x180028943  test    bl, bl
0x180028945  jz      short loc_180028957
0x180028947  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002894a  call    cs:__imp_WaitForSingleObject
0x180028950  mov     rcx, cs:?NlGlobalMsvTerminateEvent@@3PEAXEA; hObject
0x180028957  call    cs:__imp_CloseHandle
0x18002895d  mov     cs:?NlGlobalMsvTerminateEvent@@3PEAXEA, rdi; void * NlGlobalMsvTerminateEvent
0x180028964  call    ?NlWorkerTermination@@YAXXZ; NlWorkerTermination(void)
0x180028969  mov     rcx, cs:?NlGlobalThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180028970  test    rcx, rcx
0x180028973  jz      short loc_1800289A6
0x180028975  xor     r8d, r8d; pvCleanupContext
0x180028978  mov     edx, ebp; fCancelPendingCallbacks
0x18002897a  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180028980  mov     rcx, cs:?NlGlobalThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180028987  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002898d  xor     edx, edx; Val
0x18002898f  mov     cs:?NlGlobalThreadpoolCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rdi; _TP_CLEANUP_GROUP * NlGlobalThreadpoolCleanupGroup
0x180028996  lea     rcx, ?NlGlobalThreadpoolEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; void *
0x18002899d  lea     r8d, [rdx+48h]; Size
0x1800289a1  call    memset_0
0x1800289a6  mov     rcx, cs:?gInboundFilterEventsTimer@@3PEAU_TP_TIMER@@EA; pti
0x1800289ad  test    rcx, rcx
0x1800289b0  jz      short loc_1800289D3
0x1800289b2  mov     edx, ebp; fCancelPendingCallbacks
0x1800289b4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800289ba  mov     rcx, cs:?gInboundFilterEventsTimer@@3PEAU_TP_TIMER@@EA; pti
0x1800289c1  call    cs:__imp_CloseThreadpoolTimer
0x1800289c7  mov     cs:?gInboundFilterEventsTimer@@3PEAU_TP_TIMER@@EA, rdi; _TP_TIMER * gInboundFilterEventsTimer
0x1800289ce  call    ?NlpLogFilterInboundNamespaceSummaryEventsIfNecessary@@YAXXZ; NlpLogFilterInboundNamespaceSummaryEventsIfNecessary(void)
0x1800289d3  call    ?NlCleanupServiceAccounts@@YAXXZ; NlCleanupServiceAccounts(void)
0x1800289d8  call    cs:__imp_LsaIIsInEmulatedDomainJoinMode
0x1800289de  test    al, al
0x1800289e0  jnz     short loc_1800289E8
0x1800289e2  call    cs:__imp_GMSACleanup
0x1800289e8  call    ?NlUninitializeDomains@@YAXXZ; NlUninitializeDomains(void)
0x1800289ed  lea     rax, ?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServiceAccountList
0x1800289f4  cmp     cs:?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServiceAccountList
0x1800289fb  jz      short loc_180028A12
0x1800289fd  mov     r8d, 0C9h; unsigned int
0x180028a03  lea     rcx, aIslistemptyNlg_0; "IsListEmpty( &NlGlobalServiceAccountLis"...
0x180028a0a  mov     rdx, rsi; void *
0x180028a0d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180028a12  cmp     cs:?NlGlobalServiceAccountInitialized@@3KA, edi; ulong NlGlobalServiceAccountInitialized
0x180028a18  jz      short loc_180028A2F
0x180028a1a  mov     r8d, 0CAh; unsigned int
0x180028a20  lea     rcx, aNlglobalservic; "!NlGlobalServiceAccountInitialized"
0x180028a27  mov     rdx, rsi; void *
0x180028a2a  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180028a2f  lea     rcx, ?NlGlobalServiceAccountCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028a36  call    cs:__imp_RtlDeleteCriticalSection
0x180028a3c  mov     rcx, cs:?g_hNqmNotification@@3PEAXEA; RegistrationHandle
0x180028a43  test    rcx, rcx
0x180028a46  jz      short loc_180028A66
0x180028a48  call    cs:__imp_PowerSettingUnregisterNotification
0x180028a4e  lea     rdx, aNlregisternqmn_0; "NlRegisterNQMNotifications: PowerSettin"...
0x180028a55  mov     cs:?g_hNqmNotification@@3PEAXEA, rdi; void * g_hNqmNotification
0x180028a5c  mov     r8d, eax
0x180028a5f  mov     ecx, ebp; unsigned int
0x180028a61  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180028a66  mov     cs:?g_LowPowerNQMState@@3EA, dil; uchar g_LowPowerNQMState
0x180028a6d  call    ?NlBrowserClose@@YAXXZ; NlBrowserClose(void)
0x180028a72  call    ?NlUninitializeDomainNameMapper@@YAXXZ; NlUninitializeDomainNameMapper(void)
0x180028a77  call    ?NlUninitializeLocatorConnectionCache@@YAXXZ; NlUninitializeLocatorConnectionCache(void)
0x180028a7c  call    ?NlTransportClose@@YAXXZ; NlTransportClose(void)
0x180028a81  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028a88  call    cs:__imp_RtlDeleteCriticalSection
0x180028a8e  call    ?NlDnsShutdown@@YAXXZ; NlDnsShutdown(void)
0x180028a93  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028a9a  call    cs:__imp_RtlDeleteCriticalSection
0x180028aa0  lea     rcx, ?NlGlobalDnsUpdateRequestCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028aa7  call    cs:__imp_RtlDeleteCriticalSection
0x180028aad  xor     edx, edx; unsigned __int8 *
0x180028aaf  xor     ecx, ecx; struct _UNICODE_STRING *
0x180028ab1  call    ?NlSetDnsForestName@@YAKPEAU_UNICODE_STRING@@PEAE@Z; NlSetDnsForestName(_UNICODE_STRING *,uchar *)
0x180028ab6  lea     rbx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDnsForestNameCritSect
0x180028abd  mov     rcx, rbx; CriticalSection
0x180028ac0  call    cs:__imp_RtlEnterCriticalSection
0x180028ac6  mov     rcx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char * NlGlobalUtf8DnsForestNameAlias
0x180028acd  test    rcx, rcx
0x180028ad0  jz      short loc_180028ADE
0x180028ad2  call    NetpMemoryFree
0x180028ad7  mov     cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA, rdi; char * NlGlobalUtf8DnsForestNameAlias
0x180028ade  mov     rcx, rbx; CriticalSection
0x180028ae1  call    cs:__imp_RtlLeaveCriticalSection
0x180028ae7  mov     rcx, rbx; CriticalSection
0x180028aea  call    cs:__imp_RtlDeleteCriticalSection
0x180028af0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x180028af7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x180028afc  test    al, al
0x180028afe  jz      short loc_180028B07
0x180028b00  call    ?NlSiteTerminate@@YAXXZ; NlSiteTerminate(void)
0x180028b05  jmp     short loc_180028B0C
0x180028b07  call    ?NlSiteTerminate_Old@@YAXXZ; NlSiteTerminate_Old(void)
0x180028b0c  lea     rcx, ?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A; struct _NETLOGON_PARAMETERS *
0x180028b13  call    ?NlParseFree@@YAXPEAU_NETLOGON_PARAMETERS@@@Z; NlParseFree(_NETLOGON_PARAMETERS *)
0x180028b18  xor     r8d, r8d; int
0x180028b1b  xor     edx, edx; unsigned __int16 *
0x180028b1d  xor     ecx, ecx; unsigned __int16 *
0x180028b1f  call    ?NlRemoveChallengeForClient@@YAXPEAG0H@Z; NlRemoveChallengeForClient(ushort *,ushort *,int)
0x180028b24  lea     rax, ?NlGlobalChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChallengeList
0x180028b2b  cmp     cs:?NlGlobalChallengeList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChallengeList
0x180028b32  jz      short loc_180028B49
0x180028b34  mov     r8d, 116h; unsigned int
0x180028b3a  lea     rcx, aIslistemptyNlg_2; "IsListEmpty( &NlGlobalChallengeList )"
0x180028b41  mov     rdx, rsi; void *
0x180028b44  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180028b49  cmp     cs:?NlGlobalChallengeCount@@3KA, edi; ulong NlGlobalChallengeCount
0x180028b4f  jz      short loc_180028B66
0x180028b51  mov     r8d, 117h; unsigned int
0x180028b57  lea     rcx, aNlglobalchalle; "NlGlobalChallengeCount == 0"
0x180028b5e  mov     rdx, rsi; void *
0x180028b61  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180028b66  lea     rcx, ?NlGlobalChallengeCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028b6d  call    cs:__imp_RtlDeleteCriticalSection
0x180028b73  lea     rbx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalDcDiscoveryCritSect
0x180028b7a  mov     rcx, rbx; CriticalSection
0x180028b7d  call    cs:__imp_RtlEnterCriticalSection
0x180028b83  mov     rcx, cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x180028b8a  test    rcx, rcx
0x180028b8d  jz      short loc_180028BA8
0x180028b8f  call    NetpMemoryFree
0x180028b94  mov     cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA, rdi; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x180028b9b  mov     cs:?NlGlobalTrustedDomainCount@@3KA, edi; ulong NlGlobalTrustedDomainCount
0x180028ba1  mov     qword ptr cs:?NlGlobalTrustedDomainListTime@@3T_LARGE_INTEGER@@A.dwLowDateTime, rdi; _LARGE_INTEGER NlGlobalTrustedDomainListTime ...
0x180028ba8  mov     rcx, rbx; CriticalSection
0x180028bab  call    cs:__imp_RtlLeaveCriticalSection
0x180028bb1  mov     rcx, rbx; CriticalSection
0x180028bb4  call    cs:__imp_RtlDeleteCriticalSection
0x180028bba  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028bc1  call    cs:__imp_RtlEnterCriticalSection
0x180028bc7  lea     rbx, ?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x180028bce  mov     rcx, cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChangeLogNotifications
0x180028bd5  cmp     rcx, rbx
0x180028bd8  jz      short loc_180028C02
0x180028bda  cmp     [rcx+8], rbx
0x180028bde  jnz     short loc_180028BFB
0x180028be0  mov     rax, [rcx]
0x180028be3  cmp     [rax+8], rcx
0x180028be7  jnz     short loc_180028BFB
0x180028be9  mov     cs:?NlGlobalChangeLogNotifications@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChangeLogNotifications
0x180028bf0  mov     [rax+8], rbx
0x180028bf4  call    NetpMemoryFree
0x180028bf9  jmp     short loc_180028BCE
0x180028bfb  mov     ecx, 3
0x180028c00  int     29h; Win8: RtlFailFast(ecx)
0x180028c02  lea     rcx, ?NlGlobalChangeLogCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028c09  call    cs:__imp_RtlLeaveCriticalSection
0x180028c0f  cmp     cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalNetlogonSecurityDescriptor
0x180028c16  jz      short loc_180028C2C
0x180028c18  lea     rcx, ?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA; ObjectDescriptor
0x180028c1f  call    cs:__imp_RtlDeleteSecurityObject
0x180028c25  mov     cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalNetlogonSecurityDescriptor
0x180028c2c  mov     rcx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; Buffer
0x180028c33  test    rcx, rcx
0x180028c36  jz      short loc_180028C45
0x180028c38  call    cs:__imp_NetApiBufferFree
0x180028c3e  mov     cs:?NlGlobalUnicodeComputerName@@3PEAGEA, rdi; ushort * NlGlobalUnicodeComputerName
0x180028c45  lea     rcx, stru_1800F0F58; SRWLock
0x180028c4c  call    cs:__imp_AcquireSRWLockExclusive
0x180028c52  mov     rcx, cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A; hMem
0x180028c59  test    rcx, rcx
0x180028c5c  jz      short loc_180028C6B
0x180028c5e  call    cs:__imp_LocalFree
0x180028c64  mov     cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A, rdi; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x180028c6b  lea     rcx, stru_1800F0F58; SRWLock
0x180028c72  call    cs:__imp_ReleaseSRWLockExclusive
0x180028c78  lea     rbx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE NlGlobalRpcSecurityDescriptorLock
0x180028c7f  mov     dl, bpl; Wait
0x180028c82  mov     rcx, rbx; Resource
0x180028c85  call    cs:__imp_RtlAcquireResourceExclusive
0x180028c8b  mov     rcx, cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA; hMem
0x180028c92  test    rcx, rcx
0x180028c95  jz      short loc_180028CA4
0x180028c97  call    cs:__imp_LocalFree
0x180028c9d  mov     cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalRpcSecurityDescriptor
0x180028ca4  mov     rcx, rbx; Resource
0x180028ca7  call    cs:__imp_RtlReleaseResource
0x180028cad  mov     rcx, rbx; Resource
0x180028cb0  call    cs:__imp_RtlDeleteResource
0x180028cb6  lea     rbx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE NlGlobalRemoteAccessCheckSecurityDescriptorLock
0x180028cbd  mov     dl, bpl; Wait
0x180028cc0  mov     rcx, rbx; Resource
0x180028cc3  call    cs:__imp_RtlAcquireResourceExclusive
0x180028cc9  mov     rcx, cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA; hMem
0x180028cd0  test    rcx, rcx
0x180028cd3  jz      short loc_180028CE2
0x180028cd5  call    cs:__imp_LocalFree
0x180028cdb  mov     cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA, rdi; void * NlGlobalRemoteAccessCheckSecurityDescriptor
0x180028ce2  mov     rcx, rbx; Resource
0x180028ce5  call    cs:__imp_RtlReleaseResource
0x180028ceb  mov     rcx, rbx; Resource
0x180028cee  call    cs:__imp_RtlDeleteResource
0x180028cf4  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x180028cfb  call    cs:__imp_RtlDeleteResource
0x180028d01  lea     rcx, ?NlGlobalCompoundIdLock@@3U_RTL_RESOURCE@@A; Resource
0x180028d08  call    cs:__imp_RtlDeleteResource
0x180028d0e  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180028d15  call    cs:__imp_RtlDeleteResource
0x180028d1b  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x180028d22  call    cs:__imp_RtlDeleteResource
0x180028d28  mov     cs:dword_1800F0D10, 0FFFFFFFFh
0x180028d32  call    NetpFreeWellKnownSids
0x180028d37  lea     rcx, ?NlGlobalScavengerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028d3e  call    cs:__imp_RtlDeleteCriticalSection
0x180028d44  lea     rcx, ?NlGlobalEventLoggerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180028d4b  call    cs:__imp_RtlDeleteCriticalSection
0x180028d51  mov     rcx, cs:?NlGlobalTimerEvent@@3PEAXEA; hObject
0x180028d58  test    rcx, rcx
0x180028d5b  jz      short loc_180028D6A
0x180028d5d  call    cs:__imp_CloseHandle
0x180028d63  mov     cs:?NlGlobalTimerEvent@@3PEAXEA, rdi; void * NlGlobalTimerEvent
0x180028d6a  cmp     cs:?NlGlobalWinSockInitialized@@3EA, dil; uchar NlGlobalWinSockInitialized
0x180028d71  jz      short loc_180028D79
0x180028d73  call    cs:__imp_WSACleanup
0x180028d79  mov     rcx, cs:?NlpTraceRegistrationHandle@@3_KA; unsigned __int64 NlpTraceRegistrationHandle
0x180028d80  test    rcx, rcx
0x180028d83  jz      short loc_180028D9F
0x180028d85  call    cs:__imp_EtwUnregisterTraceGuids
0x180028d8b  mov     cs:?NlpEventTraceFlag@@3KA, edi; ulong NlpEventTraceFlag
0x180028d91  mov     cs:?NlpTraceRegistrationHandle@@3_KA, rdi; unsigned __int64 NlpTraceRegistrationHandle
0x180028d98  mov     cs:?NlpTraceLoggerHandle@@3_KA, rdi; unsigned __int64 NlpTraceLoggerHandle
0x180028d9f  mov     rcx, cs:?NlAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x180028da6  mov     ebx, 100h
0x180028dab  test    rcx, rcx
0x180028dae  jz      short loc_180028DDA
0x180028db0  call    cs:__imp_AuthzFreeResourceManager
0x180028db6  test    eax, eax
0x180028db8  jnz     short loc_180028DD3
0x180028dba  call    cs:__imp_GetLastError
0x180028dc0  lea     rdx, aAuthzfreeresou_0; "AuthzFreeResourceManager failed 0x%lx\n"
0x180028dc7  mov     ecx, ebx; unsigned int
0x180028dc9  mov     r8d, eax
0x180028dcc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180028dd1  jmp     short loc_180028DDA
0x180028dd3  mov     cs:?NlAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rdi; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlAuthzRM
0x180028dda  mov     rcx, cs:?NlGlobalEventlogHandle@@3PEAXEA; void * NlGlobalEventlogHandle
0x180028de1  mov     [rcx+38h], edi
0x180028de4  call    NetpEventlogClearList
0x180028de9  mov     rcx, cs:?NlGlobalTerminateEvent@@3PEAXEA; hObject
  ... truncated ...
```
