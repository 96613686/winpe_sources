# NlNetlogonMain(ulong,ushort * *)

- ea: `0x180077610`
- end: `0x180077ca8`
- name: `?NlNetlogonMain@@YAHKPEAPEAG@Z`
- size: `1688`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007518`
- `0x18000f3e4`
- `0x180016db8`
- `0x18001a1d4`
- `0x180025a74`
- `0x180029c68`
- `0x180029d5c`
- `0x180040aa8`
- `0x180041fbc`
- `0x180050de4`
- `0x180052d98`
- `0x1800747cc`
- `0x180075b60`
- `0x180077610`
- `0x18008646c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007794b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007794b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800778c3`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800778c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b20`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180077841`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007785a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180077c1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180077841`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007785a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180077c1c`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180077636`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180077636`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180077abf`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180077abf`
- `LSASRV!LsaIInitializeNetlogonFuncPtrs` at `0x180077c79`
- `LSASRV!LsaIInitializeNetlogonFuncPtrs` at `0x180077c79`
- `ntdll!RtlLeaveCriticalSection` at `0x180077c2b`
- `ntdll!RtlLeaveCriticalSection` at `0x180077c2b`
- `ntdll!RtlInitializeResource` at `0x180077a30`
- `ntdll!RtlInitializeResource` at `0x180077a43`
- `ntdll!RtlInitializeResource` at `0x180077a56`
- `ntdll!RtlInitializeResource` at `0x180077a69`
- `ntdll!RtlInitializeResource` at `0x180077a7c`
- `ntdll!RtlInitializeResource` at `0x180077a8f`
- `ntdll!RtlInitializeResource` at `0x180077a30`
- `ntdll!RtlInitializeResource` at `0x180077a43`
- `ntdll!RtlInitializeResource` at `0x180077a56`
- `ntdll!RtlInitializeResource` at `0x180077a69`
- `ntdll!RtlInitializeResource` at `0x180077a7c`
- `ntdll!RtlInitializeResource` at `0x180077a8f`
- `ntdll!RtlInitializeCriticalSection` at `0x1800776bc`
- `ntdll!RtlInitializeCriticalSection` at `0x180077995`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779a8`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779be`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779d1`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779e4`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779f7`
- `ntdll!RtlInitializeCriticalSection` at `0x180077a0a`
- `ntdll!RtlInitializeCriticalSection` at `0x180077a1d`
- `ntdll!RtlInitializeCriticalSection` at `0x180077aac`
- `ntdll!RtlInitializeCriticalSection` at `0x1800776bc`
- `ntdll!RtlInitializeCriticalSection` at `0x180077995`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779a8`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779be`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779d1`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779e4`
- `ntdll!RtlInitializeCriticalSection` at `0x1800779f7`
- `ntdll!RtlInitializeCriticalSection` at `0x180077a0a`
- `ntdll!RtlInitializeCriticalSection` at `0x180077a1d`
- `ntdll!RtlInitializeCriticalSection` at `0x180077aac`
- `ntdll!RtlEnterCriticalSection` at `0x180077bf9`
- `ntdll!RtlEnterCriticalSection` at `0x180077bf9`
- `ntdll!RtlInitUnicodeString` at `0x180077759`
- `ntdll!RtlInitUnicodeString` at `0x180077759`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180077b04`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180077b04`
- `SAMSRV!SamIQueryCapabilities` at `0x180077be2`
- `SAMSRV!SamIQueryCapabilities` at `0x180077be2`

## string_xrefs

- `0x18007796f`: `Cannot create termination Event %lu\n`
- `0x180077ad2`: `Cannot open the LSA policy handle 0x%08x\n`
- `0x180077ae8`: `Calling RegisterServiceCtrlHandler\n`
- `0x180077b2c`: `RegisterServiceCtrlHandler failed %lu\n`
- `0x180077bb4`: `Command line parsed successfully ...\n`
- `0x180077bca`: `Netlogon.dll has been unloaded (recover from it).\n`

## pseudocode

```c
__int64 __fastcall NlNetlogonMain(__int64 a1, unsigned __int16 **a2)
{
  DWORD LastError; // eax
  int v4; // eax
  DWORD v5; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v6; // [rsp+78h] [rbp+38h] BYREF

  v5 = 0;
  LODWORD(v6) = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &v6, 4) )
  {
    LastError = GetLastError();
    NlPrintRoutine(0x100u, L"ERROR:Failed to set EnforceRedirectionTrust with error %d\n", LastError);
  }
  memset_0(&NlGlobalParameters, 0, 0x220u);
  NlGlobalMailslotHandle = 0;
  NlGlobalRpcServerStarted = 0;
  NlGlobalRemoteAccessCheckStarted = 0;
  NlGlobalServerSupportsAuthRpc = 1;
  NlGlobalResourceManagerNoCAP = 0;
  NlGlobalResourceManagerWithCAP = 0;
  NlGlobalUnicodeComputerName = 0;
  NlGlobalNetlogonSecurityDescriptor = 0;
  NlGlobalServerSupportsKerberosAuthRpc = 0;
  RtlInitializeCriticalSection(&NlGlobalChallengeCritSect);
  NlGlobalChallengeCount = 0;
  qword_1800F8918 = (__int64)&NlGlobalChallengeList;
  NlGlobalChallengeList = &NlGlobalChallengeList;
  NlGlobalServiceAccountInitialized = 0;
  qword_1800F7C78 = (__int64)&NlGlobalServiceAccountList;
  NlGlobalServiceAccountList = &NlGlobalServiceAccountList;
  qword_1800F88A8 = (__int64)&NlGlobalTransportList;
  NlGlobalTransportList = &NlGlobalTransportList;
  qword_1800F7B78 = (__int64)&NlGlobalDnsList;
  NlGlobalDnsList = &NlGlobalDnsList;
  qword_1800F7B58 = (__int64)&NlGlobalDnsUpdateRequestList;
  NlGlobalDnsUpdateRequestList = &NlGlobalDnsUpdateRequestList;
  NlGlobalWinSockInitialized = 0;
  NlGlobalIpTransportCount = 0;
  NlGlobalUnicodeDnsForestName = 0;
  RtlInitUnicodeString(&NlGlobalUnicodeDnsForestNameString, 0);
  NlGlobalUtf8DnsForestName = 0;
  NlGlobalWinsockPnpSocket = -1;
  NlGlobalV6WinsockPnpSocket = -1;
  NlGlobalUtf8DnsForestNameAlias = 0;
  NlGlobalWinsockPnpEvent = 0;
  NlGlobalWinsockPnpAddresses = 0;
  NlGlobalWinsockPnpAddressSize = 0;
  NlGlobalV6WinsockPnpEvent = 0;
  NlGlobalV6WinsockPnpAddresses = 0;
  NlGlobalV6WinsockPnpAddressSize = 0;
  NlGlobalTerminateEvent = 0;
  NlGlobalStartedEvent = 0;
  NlGlobalTimerEvent = 0;
  NlGlobalServiceHandle = 0;
  NlGlobalServiceStatus.dwServiceType = 48;
  *(_QWORD *)&NlGlobalServiceStatus.dwCurrentState = 2;
  NlGlobalServiceStatus.dwCheckPoint = 1;
  NlGlobalServiceStatus.dwWaitHint = 60000;
  *(_QWORD *)&NlGlobalServiceStatus.dwWin32ExitCode = 0;
  NlGlobalDomainInfo = 0;
  NlGlobalServicedDomainCount = 0;
  NlGlobalTrustedDomainList = 0;
  qword_1800F81F0 = 0;
  NlGlobalTrustedDomainCount = 0;
  NlGlobalTrustedDomainListTime = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
  {
    NlGlobalSiteNameSetTime = 0;
    NlGlobalNoClientSiteCount = 0;
    GetSystemTimeAsFileTime(&NlGlobalNoClientSiteEventTime);
    NlGlobalPartialClientSiteMappingCount = 0;
    GetSystemTimeAsFileTime(&NlGlobalPartialClientSiteMappingEventTime);
  }
  NlGlobalNetlogonUnloaded = NlGlobalChangeLogDllUnloaded;
  NlGlobalBindingHandleCount = 0;
  dword_1800F8BD8 = -1;
  dword_1800F7B68 = -1;
  NlGlobalDsRunningUnknown = 1;
  NlGlobalJoinLogicDone = 0;
  NlGlobalCDC = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
    NlGlobalNextClosestSiteRetrieved = 0;
  NlGlobalVulnerableChannelAllowList = 0;
  InitializeSRWLock(&stru_1800F7F58);
  NlGlobalScavengerTimer = 0;
  NlGlobalParameters = 0;
  NlGlobalLogFile = (HANDLE)-1LL;
  NlGlobalDebugSharePath = 0;
  dword_1800F8BA8 = 1000 * dword_1800F8138;
  qword_1800F8C20 = (__int64)NlDcScavenger;
  NlGlobalPartialDisable = 0;
  NlGlobalDsPaused = 1;
  NlGlobalDsPausedEvent = 0;
  NlGlobalDsPausedWaitHandle = 0;
  NlGlobalDcDemotionInProgress = 0;
  NlGlobalDcScavengerIsRunning = 0;
  qword_1800F8C28 = 0;
  byte_1800F8C30 = 0;
  NlGlobalTerminate = 0;
  NlGlobalTerminateEvent = CreateEventW(0, 1, 0, 0);
  if ( !NlGlobalTerminateEvent )
  {
    v5 = GetLastError();
    NlPrintRoutine(0x100u, L"Cannot create termination Event %lu\n", v5);
    return v5;
  }
  RtlInitializeCriticalSection(&NlGlobalDcDiscoveryCritSect);
  RtlInitializeCriticalSection(&NlGlobalScavengerCritSect);
  RtlInitializeCriticalSection(&NlGlobalEventLoggerCritSect);
  RtlInitializeCriticalSection(&NlGlobalTransportCritSect);
  RtlInitializeCriticalSection(&NlGlobalDnsCritSect);
  RtlInitializeCriticalSection(&NlGlobalDnsUpdateRequestCritSect);
  RtlInitializeCriticalSection(&NlGlobalDnsForestNameCritSect);
  RtlInitializeCriticalSection(&NlGlobalServiceAccountCritSect);
  RtlInitializeResource(&NlGlobalRpcSecurityDescriptorLock);
  RtlInitializeResource(&NlGlobalRemoteAccessCheckSecurityDescriptorLock);
  RtlInitializeResource(&NlGlobalNtlmAllowedServersLock);
  RtlInitializeResource(&NlGlobalCompoundIdLock);
  RtlInitializeResource(&NlPcGlobalLock);
  RtlInitializeResource(&NlGlobalGMSADPAPILock);
  dword_1800F7D10 = -1;
  RtlInitializeCriticalSection(&NlGlobalParametersCritSect);
  v4 = LsaIOpenPolicyTrusted(&NlGlobalLsaPolicyHandle);
  if ( v4 >= 0 )
  {
    NlPrintRoutine(1u, L"Calling RegisterServiceCtrlHandler\n");
    NlGlobalServiceHandle = RegisterServiceCtrlHandlerW(L"NETLOGON", NlControlHandler);
    if ( !NlGlobalServiceHandle )
    {
      v6 = 0;
      v5 = GetLastError();
      NlPrintRoutine(0x100u, L"RegisterServiceCtrlHandler failed %lu\n", v5);
      v6 = (unsigned __int16 *)v5;
      NlpWriteEventlogEx(0x1648u, 1u, 0x40000000u, 0xFFFFFFFF, &v6, 1u, (unsigned __int8 *)&v5, 4u);
      return v5;
    }
    if ( (unsigned int)GiveInstallHints(0) )
    {
      NlOpenDebugFile(0);
      NlLoadStrings();
      if ( NlparseAllSections((struct _NETLOGON_PARAMETERS *)&NlGlobalParameters, 0) )
      {
        NlPrintRoutine(1u, L"Command line parsed successfully ...\n");
        if ( NlGlobalNetlogonUnloaded )
          NlPrintRoutine(1u, L"Netlogon.dll has been unloaded (recover from it).\n");
        NlInitializeLocatorConnectionCache();
        NlInitializeDomainNameMapper();
        NlGlobalCDC = SamIQueryCapabilities() & 1;
        RtlEnterCriticalSection(&NlGlobalEventLoggerCritSect);
        dword_1800F8BC0 = 1000 * dword_1800F813C;
        GetSystemTimeAsFileTime(&NlGlobalEventLoggerTimer);
        RtlLeaveCriticalSection(&NlGlobalEventLoggerCritSect);
        qword_1800F8C50 = 0;
        qword_1800F8C48 = (__int64)NlDcUserValReqEventsLogger;
        byte_1800F8C58 = 0;
        if ( (int)NlInitChangeLogServiceStart() >= 0
          && (unsigned int)NlInit()
          && (int)LsaIInitializeNetlogonFuncPtrs(I_NetLogonGetAuthDataEx, I_NetLogonFree, NetpGetGroupMSAPassword) >= 0 )
        {
          NlGlobalNetlogonUnloaded = 0;
          NlMainLoop();
        }
      }
    }
  }
  else
  {
    NlPrintRoutine(0x100u, L"Cannot open the LSA policy handle 0x%08x\n", (unsigned int)v4);
  }
  return NlCleanup();
}

```

## disassembly

```asm
0x180077610  mov     [rsp-18h+arg_0], rbx
0x180077615  push    rbp
0x180077616  push    rdi
0x180077617  push    r15
0x180077619  mov     rbp, rsp
0x18007761c  sub     rsp, 40h
0x180077620  xor     ebx, ebx
0x180077622  lea     rdx, [rbp+arg_18]
0x180077626  mov     [rbp+arg_10], ebx
0x180077629  lea     edi, [rbx+1]
0x18007762c  lea     r8d, [rbx+4]
0x180077630  mov     dword ptr [rbp+arg_18], edi
0x180077633  lea     ecx, [rbx+10h]
0x180077636  call    cs:__imp_SetProcessMitigationPolicy
0x18007763d  nop     dword ptr [rax+rax+00h]
0x180077642  test    eax, eax
0x180077644  jnz     short loc_180077666
0x180077646  call    cs:__imp_GetLastError
0x18007764d  nop     dword ptr [rax+rax+00h]
0x180077652  lea     rdx, aErrorFailedToS; "ERROR:Failed to set EnforceRedirectionT"...
0x180077659  mov     ecx, 100h; unsigned int
0x18007765e  mov     r8d, eax
0x180077661  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180077666  xor     edx, edx; Val
0x180077668  lea     rcx, ?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A; void *
0x18007766f  mov     r8d, 220h; Size
0x180077675  call    memset_0
0x18007767a  lea     rcx, ?NlGlobalChallengeCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180077681  mov     cs:?NlGlobalMailslotHandle@@3PEAXEA, rbx; void * NlGlobalMailslotHandle
0x180077688  mov     cs:?NlGlobalRpcServerStarted@@3HA, ebx; int NlGlobalRpcServerStarted
0x18007768e  mov     cs:?NlGlobalRemoteAccessCheckStarted@@3HA, ebx; int NlGlobalRemoteAccessCheckStarted
0x180077694  mov     cs:?NlGlobalServerSupportsAuthRpc@@3HA, edi; int NlGlobalServerSupportsAuthRpc
0x18007769a  mov     cs:?NlGlobalResourceManagerNoCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rbx; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerNoCAP
0x1800776a1  mov     cs:?NlGlobalResourceManagerWithCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rbx; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerWithCAP
0x1800776a8  mov     cs:?NlGlobalUnicodeComputerName@@3PEAGEA, rbx; ushort * NlGlobalUnicodeComputerName
0x1800776af  mov     cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA, rbx; void * NlGlobalNetlogonSecurityDescriptor
0x1800776b6  mov     cs:?NlGlobalServerSupportsKerberosAuthRpc@@3HA, ebx; int NlGlobalServerSupportsKerberosAuthRpc
0x1800776bc  call    cs:__imp_RtlInitializeCriticalSection
0x1800776c3  nop     dword ptr [rax+rax+00h]
0x1800776c8  lea     rax, ?NlGlobalChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChallengeList
0x1800776cf  mov     cs:?NlGlobalChallengeCount@@3KA, ebx; ulong NlGlobalChallengeCount
0x1800776d5  mov     cs:qword_1800F8918, rax
0x1800776dc  lea     rcx, ?NlGlobalUnicodeDnsForestNameString@@3U_UNICODE_STRING@@A; DestinationString
0x1800776e3  mov     cs:?NlGlobalChallengeList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChallengeList
0x1800776ea  xor     edx, edx; SourceString
0x1800776ec  lea     rax, ?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServiceAccountList
0x1800776f3  mov     cs:?NlGlobalServiceAccountInitialized@@3KA, ebx; ulong NlGlobalServiceAccountInitialized
0x1800776f9  mov     cs:qword_1800F7C78, rax
0x180077700  mov     cs:?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServiceAccountList
0x180077707  lea     rax, ?NlGlobalTransportList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalTransportList
0x18007770e  mov     cs:qword_1800F88A8, rax
0x180077715  mov     cs:?NlGlobalTransportList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalTransportList
0x18007771c  lea     rax, ?NlGlobalDnsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsList
0x180077723  mov     cs:qword_1800F7B78, rax
0x18007772a  mov     cs:?NlGlobalDnsList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalDnsList
0x180077731  lea     rax, ?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x180077738  mov     cs:qword_1800F7B58, rax
0x18007773f  mov     cs:?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x180077746  mov     cs:?NlGlobalWinSockInitialized@@3EA, bl; uchar NlGlobalWinSockInitialized
0x18007774c  mov     cs:?NlGlobalIpTransportCount@@3KA, ebx; ulong NlGlobalIpTransportCount
0x180077752  mov     cs:?NlGlobalUnicodeDnsForestName@@3PEAGEA, rbx; ushort * NlGlobalUnicodeDnsForestName
0x180077759  call    cs:__imp_RtlInitUnicodeString
0x180077760  nop     dword ptr [rax+rax+00h]
0x180077765  or      r15, 0FFFFFFFFFFFFFFFFh
0x180077769  mov     cs:?NlGlobalUtf8DnsForestName@@3PEADEA, rbx; char * NlGlobalUtf8DnsForestName
0x180077770  mov     cs:?NlGlobalWinsockPnpSocket@@3_KA, r15; unsigned __int64 NlGlobalWinsockPnpSocket
0x180077777  mov     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, r15; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x18007777e  mov     cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA, rbx; char * NlGlobalUtf8DnsForestNameAlias
0x180077785  mov     cs:?NlGlobalWinsockPnpEvent@@3PEAXEA, rbx; void * NlGlobalWinsockPnpEvent
0x18007778c  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180077793  mov     cs:?NlGlobalWinsockPnpAddressSize@@3KA, ebx; ulong NlGlobalWinsockPnpAddressSize
0x180077799  mov     cs:?NlGlobalV6WinsockPnpEvent@@3PEAXEA, rbx; void * NlGlobalV6WinsockPnpEvent
0x1800777a0  mov     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x1800777a7  mov     cs:?NlGlobalV6WinsockPnpAddressSize@@3KA, ebx; ulong NlGlobalV6WinsockPnpAddressSize
0x1800777ad  mov     cs:?NlGlobalTerminateEvent@@3PEAXEA, rbx; void * NlGlobalTerminateEvent
0x1800777b4  mov     cs:?NlGlobalStartedEvent@@3PEAXEA, rbx; void * NlGlobalStartedEvent
0x1800777bb  mov     cs:?NlGlobalTimerEvent@@3PEAXEA, rbx; void * NlGlobalTimerEvent
0x1800777c2  mov     cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rbx; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x1800777c9  mov     cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 30h ; '0'; _SERVICE_STATUS NlGlobalServiceStatus ...
0x1800777d3  mov     qword ptr cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS NlGlobalServiceStatus ...
0x1800777de  mov     cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS NlGlobalServiceStatus ...
0x1800777e4  mov     cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS NlGlobalServiceStatus ...
0x1800777ee  mov     qword ptr cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rbx; _SERVICE_STATUS NlGlobalServiceStatus ...
0x1800777f5  mov     cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA, rbx; _DOMAIN_INFO * NlGlobalDomainInfo
0x1800777fc  mov     cs:?NlGlobalServicedDomainCount@@3KA, ebx; ulong NlGlobalServicedDomainCount
0x180077802  mov     cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA, rbx; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x180077809  mov     cs:qword_1800F81F0, rbx
0x180077810  mov     cs:?NlGlobalTrustedDomainCount@@3KA, ebx; ulong NlGlobalTrustedDomainCount
0x180077816  mov     qword ptr cs:?NlGlobalTrustedDomainListTime@@3T_LARGE_INTEGER@@A.dwLowDateTime, rbx; _LARGE_INTEGER NlGlobalTrustedDomainListTime ...
0x18007781d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x180077824  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x180077829  test    al, al
0x18007782b  jnz     short loc_180077866
0x18007782d  lea     rcx, ?NlGlobalNoClientSiteEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180077834  mov     qword ptr cs:?NlGlobalSiteNameSetTime@@3T_LARGE_INTEGER@@A.dwLowDateTime, rbx; _LARGE_INTEGER NlGlobalSiteNameSetTime ...
0x18007783b  mov     cs:?NlGlobalNoClientSiteCount@@3KA, ebx; ulong NlGlobalNoClientSiteCount
0x180077841  call    cs:__imp_GetSystemTimeAsFileTime
0x180077848  nop     dword ptr [rax+rax+00h]
0x18007784d  lea     rcx, ?NlGlobalPartialClientSiteMappingEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180077854  mov     cs:?NlGlobalPartialClientSiteMappingCount@@3KA, ebx; ulong NlGlobalPartialClientSiteMappingCount
0x18007785a  call    cs:__imp_GetSystemTimeAsFileTime
0x180077861  nop     dword ptr [rax+rax+00h]
0x180077866  mov     eax, cs:?NlGlobalChangeLogDllUnloaded@@3HA; int NlGlobalChangeLogDllUnloaded
0x18007786c  mov     cs:?NlGlobalNetlogonUnloaded@@3HA, eax; int NlGlobalNetlogonUnloaded
0x180077872  mov     cs:?NlGlobalBindingHandleCount@@3KA, ebx; ulong NlGlobalBindingHandleCount
0x180077878  mov     cs:dword_1800F8BD8, 0FFFFFFFFh
0x180077882  mov     cs:dword_1800F7B68, 0FFFFFFFFh
0x18007788c  mov     cs:?NlGlobalDsRunningUnknown@@3EA, dil; uchar NlGlobalDsRunningUnknown
0x180077893  mov     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x180077899  mov     cs:?NlGlobalCDC@@3HA, ebx; int NlGlobalCDC
0x18007789f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x1800778a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x1800778ab  test    al, al
0x1800778ad  jnz     short loc_1800778B5
0x1800778af  mov     cs:?NlGlobalNextClosestSiteRetrieved@@3HA, ebx; int NlGlobalNextClosestSiteRetrieved
0x1800778b5  lea     rcx, stru_1800F7F58; SRWLock
0x1800778bc  mov     cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A, rbx; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x1800778c3  call    cs:__imp_InitializeSRWLock
0x1800778ca  nop     dword ptr [rax+rax+00h]
0x1800778cf  imul    eax, cs:dword_1800F8138, 3E8h
0x1800778d9  xor     r9d, r9d; lpName
0x1800778dc  xor     r8d, r8d; bInitialState
0x1800778df  mov     qword ptr cs:?NlGlobalScavengerTimer@@3U_TIMER@@A.dwLowDateTime, rbx; _TIMER NlGlobalScavengerTimer ...
0x1800778e6  mov     edx, edi; bManualReset
0x1800778e8  mov     cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, ebx; _NETLOGON_PARAMETERS NlGlobalParameters
0x1800778ee  xor     ecx, ecx; lpEventAttributes
0x1800778f0  mov     cs:?NlGlobalLogFile@@3PEAXEA, r15; void * NlGlobalLogFile
0x1800778f7  mov     cs:?NlGlobalDebugSharePath@@3PEAGEA, rbx; ushort * NlGlobalDebugSharePath
0x1800778fe  mov     cs:dword_1800F8BA8, eax
0x180077904  lea     rax, ?NlDcScavenger@@YAXPEAX@Z; NlDcScavenger(void *)
0x18007790b  mov     cs:qword_1800F8C20, rax
0x180077912  mov     cs:?NlGlobalPartialDisable@@3HA, ebx; int NlGlobalPartialDisable
0x180077918  mov     cs:?NlGlobalDsPaused@@3HA, edi; int NlGlobalDsPaused
0x18007791e  mov     cs:?NlGlobalDsPausedEvent@@3PEAXEA, rbx; void * NlGlobalDsPausedEvent
0x180077925  mov     cs:?NlGlobalDsPausedWaitHandle@@3PEAXEA, rbx; void * NlGlobalDsPausedWaitHandle
0x18007792c  mov     cs:?NlGlobalDcDemotionInProgress@@3EA, bl; uchar NlGlobalDcDemotionInProgress
0x180077932  mov     cs:?NlGlobalDcScavengerIsRunning@@3HA, ebx; int NlGlobalDcScavengerIsRunning
0x180077938  mov     cs:qword_1800F8C28, rbx
0x18007793f  mov     cs:byte_1800F8C30, bl
0x180077945  mov     cs:?NlGlobalTerminate@@3HA, ebx; int NlGlobalTerminate
0x18007794b  call    cs:__imp_CreateEventW
0x180077952  nop     dword ptr [rax+rax+00h]
0x180077957  mov     cs:?NlGlobalTerminateEvent@@3PEAXEA, rax; void * NlGlobalTerminateEvent
0x18007795e  test    rax, rax
0x180077961  jnz     short loc_18007798E
0x180077963  call    cs:__imp_GetLastError
0x18007796a  nop     dword ptr [rax+rax+00h]
0x18007796f  lea     rdx, aCannotCreateTe; "Cannot create termination Event %lu\n"
0x180077976  mov     ecx, 100h; unsigned int
0x18007797b  mov     r8d, eax
0x18007797e  mov     [rbp+arg_10], eax
0x180077981  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180077986  mov     eax, [rbp+arg_10]
0x180077989  jmp     loc_180077C99
0x18007798e  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180077995  call    cs:__imp_RtlInitializeCriticalSection
0x18007799c  nop     dword ptr [rax+rax+00h]
0x1800779a1  lea     rcx, ?NlGlobalScavengerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800779a8  call    cs:__imp_RtlInitializeCriticalSection
0x1800779af  nop     dword ptr [rax+rax+00h]
0x1800779b4  lea     r15, ?NlGlobalEventLoggerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalEventLoggerCritSect
0x1800779bb  mov     rcx, r15; CriticalSection
0x1800779be  call    cs:__imp_RtlInitializeCriticalSection
0x1800779c5  nop     dword ptr [rax+rax+00h]
0x1800779ca  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800779d1  call    cs:__imp_RtlInitializeCriticalSection
0x1800779d8  nop     dword ptr [rax+rax+00h]
0x1800779dd  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800779e4  call    cs:__imp_RtlInitializeCriticalSection
0x1800779eb  nop     dword ptr [rax+rax+00h]
0x1800779f0  lea     rcx, ?NlGlobalDnsUpdateRequestCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800779f7  call    cs:__imp_RtlInitializeCriticalSection
0x1800779fe  nop     dword ptr [rax+rax+00h]
0x180077a03  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180077a0a  call    cs:__imp_RtlInitializeCriticalSection
0x180077a11  nop     dword ptr [rax+rax+00h]
0x180077a16  lea     rcx, ?NlGlobalServiceAccountCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180077a1d  call    cs:__imp_RtlInitializeCriticalSection
0x180077a24  nop     dword ptr [rax+rax+00h]
0x180077a29  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180077a30  call    cs:__imp_RtlInitializeResource
0x180077a37  nop     dword ptr [rax+rax+00h]
0x180077a3c  lea     rcx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180077a43  call    cs:__imp_RtlInitializeResource
0x180077a4a  nop     dword ptr [rax+rax+00h]
0x180077a4f  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x180077a56  call    cs:__imp_RtlInitializeResource
0x180077a5d  nop     dword ptr [rax+rax+00h]
0x180077a62  lea     rcx, ?NlGlobalCompoundIdLock@@3U_RTL_RESOURCE@@A; Resource
0x180077a69  call    cs:__imp_RtlInitializeResource
0x180077a70  nop     dword ptr [rax+rax+00h]
0x180077a75  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180077a7c  call    cs:__imp_RtlInitializeResource
0x180077a83  nop     dword ptr [rax+rax+00h]
0x180077a88  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x180077a8f  call    cs:__imp_RtlInitializeResource
0x180077a96  nop     dword ptr [rax+rax+00h]
0x180077a9b  lea     rcx, ?NlGlobalParametersCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180077aa2  mov     cs:dword_1800F7D10, 0FFFFFFFFh
0x180077aac  call    cs:__imp_RtlInitializeCriticalSection
0x180077ab3  nop     dword ptr [rax+rax+00h]
0x180077ab8  lea     rcx, ?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x180077abf  call    cs:__imp_LsaIOpenPolicyTrusted
0x180077ac6  nop     dword ptr [rax+rax+00h]
0x180077acb  test    eax, eax
0x180077acd  jns     short loc_180077AE8
0x180077acf  mov     r8d, eax
0x180077ad2  lea     rdx, aCannotOpenTheL; "Cannot open the LSA policy handle 0x%08"...
0x180077ad9  mov     ecx, 100h; unsigned int
0x180077ade  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180077ae3  jmp     loc_180077C94
0x180077ae8  lea     rdx, aCallingRegiste; "Calling RegisterServiceCtrlHandler\n"
0x180077aef  mov     ecx, edi; unsigned int
0x180077af1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180077af6  lea     rdx, ?NlControlHandler@@YAXK@Z; lpHandlerProc
0x180077afd  lea     rcx, aNetlogon_0; "NETLOGON"
0x180077b04  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180077b0b  nop     dword ptr [rax+rax+00h]
0x180077b10  mov     cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x180077b17  test    rax, rax
0x180077b1a  jnz     short loc_180077B83
0x180077b1c  mov     [rbp+arg_18], rbx
0x180077b20  call    cs:__imp_GetLastError
0x180077b27  nop     dword ptr [rax+rax+00h]
0x180077b2c  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandler failed %lu\n"
0x180077b33  mov     ecx, 100h; unsigned int
0x180077b38  mov     r8d, eax
0x180077b3b  mov     [rbp+arg_10], eax
0x180077b3e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180077b43  mov     eax, [rbp+arg_10]
0x180077b46  or      r9d, 0FFFFFFFFh; unsigned int
0x180077b4a  mov     [rbp+arg_18], rax
0x180077b4e  mov     r8d, 40000000h; unsigned int
0x180077b54  mov     [rsp+40h+var_8], 4; unsigned int
0x180077b5c  lea     rax, [rbp+arg_10]
0x180077b60  mov     [rsp+40h+var_10], rax; unsigned __int8 *
0x180077b65  mov     edx, edi; unsigned int
0x180077b67  lea     rax, [rbp+arg_18]
0x180077b6b  mov     [rsp+40h+var_18], edi; unsigned int
0x180077b6f  mov     ecx, 1648h; unsigned int
0x180077b74  mov     [rsp+40h+var_20], rax; unsigned __int16 **
0x180077b79  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180077b7e  jmp     loc_180077986
0x180077b83  xor     ecx, ecx; int
0x180077b85  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x180077b8a  test    eax, eax
0x180077b8c  jz      loc_180077C94
0x180077b92  xor     ecx, ecx; int
0x180077b94  call    ?NlOpenDebugFile@@YAXH@Z; NlOpenDebugFile(int)
0x180077b99  call    ?NlLoadStrings@@YAHXZ; NlLoadStrings(void)
0x180077b9e  xor     edx, edx; unsigned __int8
0x180077ba0  lea     rcx, ?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A; struct _NETLOGON_PARAMETERS *
0x180077ba7  call    ?NlparseAllSections@@YAHPEAU_NETLOGON_PARAMETERS@@E@Z; NlparseAllSections(_NETLOGON_PARAMETERS *,uchar)
0x180077bac  test    eax, eax
0x180077bae  jz      loc_180077C94
0x180077bb4  lea     rdx, aCommandLinePar; "Command line parsed successfully ...\n"
0x180077bbb  mov     ecx, edi; unsigned int
0x180077bbd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180077bc2  cmp     cs:?NlGlobalNetlogonUnloaded@@3HA, ebx; int NlGlobalNetlogonUnloaded
0x180077bc8  jz      short loc_180077BD8
0x180077bca  lea     rdx, aNetlogonDllHas; "Netlogon.dll has been unloaded (recover"...
0x180077bd1  mov     ecx, edi; unsigned int
0x180077bd3  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180077bd8  call    ?NlInitializeLocatorConnectionCache@@YAXXZ; NlInitializeLocatorConnectionCache(void)
0x180077bdd  call    ?NlInitializeDomainNameMapper@@YAXXZ; NlInitializeDomainNameMapper(void)
0x180077be2  call    cs:__imp_SamIQueryCapabilities
0x180077be9  nop     dword ptr [rax+rax+00h]
0x180077bee  and     eax, edi
0x180077bf0  mov     rcx, r15; CriticalSection
0x180077bf3  mov     cs:?NlGlobalCDC@@3HA, eax; int NlGlobalCDC
0x180077bf9  call    cs:__imp_RtlEnterCriticalSection
0x180077c00  nop     dword ptr [rax+rax+00h]
0x180077c05  imul    eax, cs:dword_1800F813C, 3E8h
0x180077c0f  lea     rcx, ?NlGlobalEventLoggerTimer@@3U_TIMER@@A; lpSystemTimeAsFileTime
0x180077c16  mov     cs:dword_1800F8BC0, eax
0x180077c1c  call    cs:__imp_GetSystemTimeAsFileTime
0x180077c23  nop     dword ptr [rax+rax+00h]
0x180077c28  mov     rcx, r15; CriticalSection
0x180077c2b  call    cs:__imp_RtlLeaveCriticalSection
0x180077c32  nop     dword ptr [rax+rax+00h]
0x180077c37  lea     rax, ?NlDcUserValReqEventsLogger@@YAXPEAX@Z; NlDcUserValReqEventsLogger(void *)
0x180077c3e  mov     cs:qword_1800F8C50, rbx
0x180077c45  mov     cs:qword_1800F8C48, rax
0x180077c4c  mov     cs:byte_1800F8C58, bl
0x180077c52  call    ?NlInitChangeLogServiceStart@@YAJXZ; NlInitChangeLogServiceStart(void)
0x180077c57  test    eax, eax
0x180077c59  js      short loc_180077C94
0x180077c5b  call    ?NlInit@@YAHXZ; NlInit(void)
0x180077c60  test    eax, eax
0x180077c62  jz      short loc_180077C94
0x180077c64  lea     r8, ?NetpGetGroupMSAPassword@@YAJPEAU_UNICODE_STRING@@0W4_CRED_FETCH@@PEAU_FILETIME@@002@Z; NetpGetGroupMSAPassword(_UNICODE_STRING *,_UNICODE_STRING *,_CRED_FETCH,_FILETIME *,_UNICODE_STRING *,_UNICODE_STRING *,_FILETIME *)
0x180077c6b  lea     rdx, I_NetLogonFree
0x180077c72  lea     rcx, I_NetLogonGetAuthDataEx
0x180077c79  call    cs:__imp_LsaIInitializeNetlogonFuncPtrs
0x180077c80  nop     dword ptr [rax+rax+00h]
0x180077c85  test    eax, eax
0x180077c87  js      short loc_180077C94
0x180077c89  mov     cs:?NlGlobalNetlogonUnloaded@@3HA, ebx; int NlGlobalNetlogonUnloaded
0x180077c8f  call    ?NlMainLoop@@YAXXZ; NlMainLoop(void)
0x180077c94  call    ?NlCleanup@@YAKXZ; NlCleanup(void)
  ... truncated ...
```
