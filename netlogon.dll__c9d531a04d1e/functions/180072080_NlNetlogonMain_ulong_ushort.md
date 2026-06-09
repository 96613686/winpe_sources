# NlNetlogonMain(ulong,ushort * *)

- ea: `0x180072080`
- end: `0x180072657`
- name: `?NlNetlogonMain@@YAHKPEAPEAG@Z`
- size: `1495`
- prototype: `unsigned int __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007278`
- `0x18000ed34`
- `0x18001636c`
- `0x180019618`
- `0x180024adc`
- `0x180028750`
- `0x180028834`
- `0x18003e350`
- `0x18003f684`
- `0x18004d810`
- `0x18004f688`
- `0x18006f490`
- `0x18007070c`
- `0x180072080`
- `0x180080598`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072391`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072391`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007230f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007230f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800720b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800723a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800720b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800723a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800724f4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072299`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800722ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800725de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072299`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800722ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800725de`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1800720a6`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x1800720a6`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18007249f`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18007249f`
- `LSASRV!LsaIInitializeNetlogonFuncPtrs` at `0x18007262f`
- `LSASRV!LsaIInitializeNetlogonFuncPtrs` at `0x18007262f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800725e7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800725e7`
- `ntdll!RtlInitializeResource` at `0x18007243a`
- `ntdll!RtlInitializeResource` at `0x180072447`
- `ntdll!RtlInitializeResource` at `0x180072454`
- `ntdll!RtlInitializeResource` at `0x180072461`
- `ntdll!RtlInitializeResource` at `0x18007246e`
- `ntdll!RtlInitializeResource` at `0x18007247b`
- `ntdll!RtlInitializeResource` at `0x18007243a`
- `ntdll!RtlInitializeResource` at `0x180072447`
- `ntdll!RtlInitializeResource` at `0x180072454`
- `ntdll!RtlInitializeResource` at `0x180072461`
- `ntdll!RtlInitializeResource` at `0x18007246e`
- `ntdll!RtlInitializeResource` at `0x18007247b`
- `ntdll!RtlInitializeCriticalSection` at `0x180072120`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723cf`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723dc`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723ec`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723f9`
- `ntdll!RtlInitializeCriticalSection` at `0x180072406`
- `ntdll!RtlInitializeCriticalSection` at `0x180072413`
- `ntdll!RtlInitializeCriticalSection` at `0x180072420`
- `ntdll!RtlInitializeCriticalSection` at `0x18007242d`
- `ntdll!RtlInitializeCriticalSection` at `0x180072492`
- `ntdll!RtlInitializeCriticalSection` at `0x180072120`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723cf`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723dc`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723ec`
- `ntdll!RtlInitializeCriticalSection` at `0x1800723f9`
- `ntdll!RtlInitializeCriticalSection` at `0x180072406`
- `ntdll!RtlInitializeCriticalSection` at `0x180072413`
- `ntdll!RtlInitializeCriticalSection` at `0x180072420`
- `ntdll!RtlInitializeCriticalSection` at `0x18007242d`
- `ntdll!RtlInitializeCriticalSection` at `0x180072492`
- `ntdll!RtlEnterCriticalSection` at `0x1800725c1`
- `ntdll!RtlEnterCriticalSection` at `0x1800725c1`
- `ntdll!RtlInitUnicodeString` at `0x1800721b7`
- `ntdll!RtlInitUnicodeString` at `0x1800721b7`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800724de`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x1800724de`
- `SAMSRV!SamIQueryCapabilities` at `0x1800725b0`
- `SAMSRV!SamIQueryCapabilities` at `0x1800725b0`

## string_xrefs

- `0x1800723a9`: `Cannot create termination Event %lu\n`
- `0x1800724ac`: `Cannot open the LSA policy handle 0x%08x\n`
- `0x1800724c2`: `Calling RegisterServiceCtrlHandler\n`
- `0x1800724fa`: `RegisterServiceCtrlHandler failed %lu\n`
- `0x180072582`: `Command line parsed successfully ...\n`
- `0x180072598`: `Netlogon.dll has been unloaded (recover from it).\n`

## pseudocode

```c
unsigned int __fastcall NlNetlogonMain(__int64 a1, unsigned __int16 **a2)
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
  qword_1800F1918 = (__int64)&NlGlobalChallengeList;
  NlGlobalChallengeList = &NlGlobalChallengeList;
  NlGlobalServiceAccountInitialized = 0;
  qword_1800F0C78 = (__int64)&NlGlobalServiceAccountList;
  NlGlobalServiceAccountList = &NlGlobalServiceAccountList;
  qword_1800F18A8 = (__int64)&NlGlobalTransportList;
  NlGlobalTransportList = &NlGlobalTransportList;
  qword_1800F0B78 = (__int64)&NlGlobalDnsList;
  NlGlobalDnsList = &NlGlobalDnsList;
  qword_1800F0B58 = (__int64)&NlGlobalDnsUpdateRequestList;
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
  qword_1800F11F0 = 0;
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
  dword_1800F1C08 = -1;
  dword_1800F0B68 = -1;
  NlGlobalDsRunningUnknown = 1;
  NlGlobalJoinLogicDone = 0;
  NlGlobalCDC = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
    NlGlobalNextClosestSiteRetrieved = 0;
  NlGlobalVulnerableChannelAllowList = 0;
  InitializeSRWLock(&stru_1800F0F58);
  NlGlobalScavengerTimer = 0;
  NlGlobalParameters = 0;
  NlGlobalLogFile = (HANDLE)-1LL;
  NlGlobalDebugSharePath = 0;
  dword_1800F1BC8 = 1000 * dword_1800F1138;
  qword_1800F1C50 = (__int64)NlDcScavenger;
  NlGlobalPartialDisable = 0;
  NlGlobalDsPaused = 1;
  NlGlobalDsPausedEvent = 0;
  NlGlobalDsPausedWaitHandle = 0;
  NlGlobalDcDemotionInProgress = 0;
  NlGlobalDcScavengerIsRunning = 0;
  qword_1800F1C58 = 0;
  byte_1800F1C60 = 0;
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
  dword_1800F0D10 = -1;
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
        dword_1800F1BF0 = 1000 * dword_1800F113C;
        GetSystemTimeAsFileTime(&NlGlobalEventLoggerTimer);
        RtlLeaveCriticalSection(&NlGlobalEventLoggerCritSect);
        qword_1800F1C88 = 0;
        qword_1800F1C80 = (__int64)NlDcUserValReqEventsLogger;
        byte_1800F1C90 = 0;
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
0x180072080  mov     [rsp-18h+arg_0], rbx
0x180072085  push    rbp
0x180072086  push    rdi
0x180072087  push    r15
0x180072089  mov     rbp, rsp
0x18007208c  sub     rsp, 40h
0x180072090  xor     ebx, ebx
0x180072092  lea     rdx, [rbp+arg_18]
0x180072096  mov     [rbp+arg_10], ebx
0x180072099  lea     edi, [rbx+1]
0x18007209c  lea     r8d, [rbx+4]
0x1800720a0  mov     dword ptr [rbp+arg_18], edi
0x1800720a3  lea     ecx, [rbx+10h]
0x1800720a6  call    cs:__imp_SetProcessMitigationPolicy
0x1800720ac  test    eax, eax
0x1800720ae  jnz     short loc_1800720CA
0x1800720b0  call    cs:__imp_GetLastError
0x1800720b6  lea     rdx, aErrorFailedToS; "ERROR:Failed to set EnforceRedirectionT"...
0x1800720bd  mov     ecx, 100h; unsigned int
0x1800720c2  mov     r8d, eax
0x1800720c5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800720ca  xor     edx, edx; Val
0x1800720cc  lea     rcx, ?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A; void *
0x1800720d3  mov     r8d, 220h; Size
0x1800720d9  call    memset_0
0x1800720de  lea     rcx, ?NlGlobalChallengeCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800720e5  mov     cs:?NlGlobalMailslotHandle@@3PEAXEA, rbx; void * NlGlobalMailslotHandle
0x1800720ec  mov     cs:?NlGlobalRpcServerStarted@@3HA, ebx; int NlGlobalRpcServerStarted
0x1800720f2  mov     cs:?NlGlobalRemoteAccessCheckStarted@@3HA, ebx; int NlGlobalRemoteAccessCheckStarted
0x1800720f8  mov     cs:?NlGlobalServerSupportsAuthRpc@@3HA, edi; int NlGlobalServerSupportsAuthRpc
0x1800720fe  mov     cs:?NlGlobalResourceManagerNoCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rbx; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerNoCAP
0x180072105  mov     cs:?NlGlobalResourceManagerWithCAP@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rbx; AUTHZ_RESOURCE_MANAGER_HANDLE__ * NlGlobalResourceManagerWithCAP
0x18007210c  mov     cs:?NlGlobalUnicodeComputerName@@3PEAGEA, rbx; ushort * NlGlobalUnicodeComputerName
0x180072113  mov     cs:?NlGlobalNetlogonSecurityDescriptor@@3PEAXEA, rbx; void * NlGlobalNetlogonSecurityDescriptor
0x18007211a  mov     cs:?NlGlobalServerSupportsKerberosAuthRpc@@3HA, ebx; int NlGlobalServerSupportsKerberosAuthRpc
0x180072120  call    cs:__imp_RtlInitializeCriticalSection
0x180072126  lea     rax, ?NlGlobalChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalChallengeList
0x18007212d  mov     cs:?NlGlobalChallengeCount@@3KA, ebx; ulong NlGlobalChallengeCount
0x180072133  mov     cs:qword_1800F1918, rax
0x18007213a  lea     rcx, ?NlGlobalUnicodeDnsForestNameString@@3U_UNICODE_STRING@@A; DestinationString
0x180072141  mov     cs:?NlGlobalChallengeList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalChallengeList
0x180072148  xor     edx, edx; SourceString
0x18007214a  lea     rax, ?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServiceAccountList
0x180072151  mov     cs:?NlGlobalServiceAccountInitialized@@3KA, ebx; ulong NlGlobalServiceAccountInitialized
0x180072157  mov     cs:qword_1800F0C78, rax
0x18007215e  mov     cs:?NlGlobalServiceAccountList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServiceAccountList
0x180072165  lea     rax, ?NlGlobalTransportList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalTransportList
0x18007216c  mov     cs:qword_1800F18A8, rax
0x180072173  mov     cs:?NlGlobalTransportList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalTransportList
0x18007217a  lea     rax, ?NlGlobalDnsList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsList
0x180072181  mov     cs:qword_1800F0B78, rax
0x180072188  mov     cs:?NlGlobalDnsList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalDnsList
0x18007218f  lea     rax, ?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x180072196  mov     cs:qword_1800F0B58, rax
0x18007219d  mov     cs:?NlGlobalDnsUpdateRequestList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalDnsUpdateRequestList
0x1800721a4  mov     cs:?NlGlobalWinSockInitialized@@3EA, bl; uchar NlGlobalWinSockInitialized
0x1800721aa  mov     cs:?NlGlobalIpTransportCount@@3KA, ebx; ulong NlGlobalIpTransportCount
0x1800721b0  mov     cs:?NlGlobalUnicodeDnsForestName@@3PEAGEA, rbx; ushort * NlGlobalUnicodeDnsForestName
0x1800721b7  call    cs:__imp_RtlInitUnicodeString
0x1800721bd  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800721c1  mov     cs:?NlGlobalUtf8DnsForestName@@3PEADEA, rbx; char * NlGlobalUtf8DnsForestName
0x1800721c8  mov     cs:?NlGlobalWinsockPnpSocket@@3_KA, r15; unsigned __int64 NlGlobalWinsockPnpSocket
0x1800721cf  mov     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, r15; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x1800721d6  mov     cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA, rbx; char * NlGlobalUtf8DnsForestNameAlias
0x1800721dd  mov     cs:?NlGlobalWinsockPnpEvent@@3PEAXEA, rbx; void * NlGlobalWinsockPnpEvent
0x1800721e4  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x1800721eb  mov     cs:?NlGlobalWinsockPnpAddressSize@@3KA, ebx; ulong NlGlobalWinsockPnpAddressSize
0x1800721f1  mov     cs:?NlGlobalV6WinsockPnpEvent@@3PEAXEA, rbx; void * NlGlobalV6WinsockPnpEvent
0x1800721f8  mov     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x1800721ff  mov     cs:?NlGlobalV6WinsockPnpAddressSize@@3KA, ebx; ulong NlGlobalV6WinsockPnpAddressSize
0x180072205  mov     cs:?NlGlobalTerminateEvent@@3PEAXEA, rbx; void * NlGlobalTerminateEvent
0x18007220c  mov     cs:?NlGlobalStartedEvent@@3PEAXEA, rbx; void * NlGlobalStartedEvent
0x180072213  mov     cs:?NlGlobalTimerEvent@@3PEAXEA, rbx; void * NlGlobalTimerEvent
0x18007221a  mov     cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rbx; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x180072221  mov     cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 30h ; '0'; _SERVICE_STATUS NlGlobalServiceStatus ...
0x18007222b  mov     qword ptr cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS NlGlobalServiceStatus ...
0x180072236  mov     cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS NlGlobalServiceStatus ...
0x18007223c  mov     cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS NlGlobalServiceStatus ...
0x180072246  mov     qword ptr cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rbx; _SERVICE_STATUS NlGlobalServiceStatus ...
0x18007224d  mov     cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA, rbx; _DOMAIN_INFO * NlGlobalDomainInfo
0x180072254  mov     cs:?NlGlobalServicedDomainCount@@3KA, ebx; ulong NlGlobalServicedDomainCount
0x18007225a  mov     cs:?NlGlobalTrustedDomainList@@3PEAUTRUSTED_DOMAIN@@EA, rbx; TRUSTED_DOMAIN * NlGlobalTrustedDomainList
0x180072261  mov     cs:qword_1800F11F0, rbx
0x180072268  mov     cs:?NlGlobalTrustedDomainCount@@3KA, ebx; ulong NlGlobalTrustedDomainCount
0x18007226e  mov     qword ptr cs:?NlGlobalTrustedDomainListTime@@3T_LARGE_INTEGER@@A.dwLowDateTime, rbx; _LARGE_INTEGER NlGlobalTrustedDomainListTime ...
0x180072275  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x18007227c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x180072281  test    al, al
0x180072283  jnz     short loc_1800722B2
0x180072285  lea     rcx, ?NlGlobalNoClientSiteEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x18007228c  mov     qword ptr cs:?NlGlobalSiteNameSetTime@@3T_LARGE_INTEGER@@A.dwLowDateTime, rbx; _LARGE_INTEGER NlGlobalSiteNameSetTime ...
0x180072293  mov     cs:?NlGlobalNoClientSiteCount@@3KA, ebx; ulong NlGlobalNoClientSiteCount
0x180072299  call    cs:__imp_GetSystemTimeAsFileTime
0x18007229f  lea     rcx, ?NlGlobalPartialClientSiteMappingEventTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x1800722a6  mov     cs:?NlGlobalPartialClientSiteMappingCount@@3KA, ebx; ulong NlGlobalPartialClientSiteMappingCount
0x1800722ac  call    cs:__imp_GetSystemTimeAsFileTime
0x1800722b2  mov     eax, cs:?NlGlobalChangeLogDllUnloaded@@3HA; int NlGlobalChangeLogDllUnloaded
0x1800722b8  mov     cs:?NlGlobalNetlogonUnloaded@@3HA, eax; int NlGlobalNetlogonUnloaded
0x1800722be  mov     cs:?NlGlobalBindingHandleCount@@3KA, ebx; ulong NlGlobalBindingHandleCount
0x1800722c4  mov     cs:dword_1800F1C08, 0FFFFFFFFh
0x1800722ce  mov     cs:dword_1800F0B68, 0FFFFFFFFh
0x1800722d8  mov     cs:?NlGlobalDsRunningUnknown@@3EA, dil; uchar NlGlobalDsRunningUnknown
0x1800722df  mov     cs:?NlGlobalJoinLogicDone@@3HA, ebx; int NlGlobalJoinLogicDone
0x1800722e5  mov     cs:?NlGlobalCDC@@3HA, ebx; int NlGlobalCDC
0x1800722eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x1800722f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x1800722f7  test    al, al
0x1800722f9  jnz     short loc_180072301
0x1800722fb  mov     cs:?NlGlobalNextClosestSiteRetrieved@@3HA, ebx; int NlGlobalNextClosestSiteRetrieved
0x180072301  lea     rcx, stru_1800F0F58; SRWLock
0x180072308  mov     cs:?NlGlobalVulnerableChannelAllowList@@3U_SafeSecurityDescriptor@@A, rbx; _SafeSecurityDescriptor NlGlobalVulnerableChannelAllowList
0x18007230f  call    cs:__imp_InitializeSRWLock
0x180072315  imul    eax, cs:dword_1800F1138, 3E8h
0x18007231f  xor     r9d, r9d; lpName
0x180072322  xor     r8d, r8d; bInitialState
0x180072325  mov     qword ptr cs:?NlGlobalScavengerTimer@@3U_TIMER@@A.dwLowDateTime, rbx; _TIMER NlGlobalScavengerTimer ...
0x18007232c  mov     edx, edi; bManualReset
0x18007232e  mov     cs:?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A, ebx; _NETLOGON_PARAMETERS NlGlobalParameters
0x180072334  xor     ecx, ecx; lpEventAttributes
0x180072336  mov     cs:?NlGlobalLogFile@@3PEAXEA, r15; void * NlGlobalLogFile
0x18007233d  mov     cs:?NlGlobalDebugSharePath@@3PEAGEA, rbx; ushort * NlGlobalDebugSharePath
0x180072344  mov     cs:dword_1800F1BC8, eax
0x18007234a  lea     rax, ?NlDcScavenger@@YAXPEAX@Z; NlDcScavenger(void *)
0x180072351  mov     cs:qword_1800F1C50, rax
0x180072358  mov     cs:?NlGlobalPartialDisable@@3HA, ebx; int NlGlobalPartialDisable
0x18007235e  mov     cs:?NlGlobalDsPaused@@3HA, edi; int NlGlobalDsPaused
0x180072364  mov     cs:?NlGlobalDsPausedEvent@@3PEAXEA, rbx; void * NlGlobalDsPausedEvent
0x18007236b  mov     cs:?NlGlobalDsPausedWaitHandle@@3PEAXEA, rbx; void * NlGlobalDsPausedWaitHandle
0x180072372  mov     cs:?NlGlobalDcDemotionInProgress@@3EA, bl; uchar NlGlobalDcDemotionInProgress
0x180072378  mov     cs:?NlGlobalDcScavengerIsRunning@@3HA, ebx; int NlGlobalDcScavengerIsRunning
0x18007237e  mov     cs:qword_1800F1C58, rbx
0x180072385  mov     cs:byte_1800F1C60, bl
0x18007238b  mov     cs:?NlGlobalTerminate@@3HA, ebx; int NlGlobalTerminate
0x180072391  call    cs:__imp_CreateEventW
0x180072397  mov     cs:?NlGlobalTerminateEvent@@3PEAXEA, rax; void * NlGlobalTerminateEvent
0x18007239e  test    rax, rax
0x1800723a1  jnz     short loc_1800723C8
0x1800723a3  call    cs:__imp_GetLastError
0x1800723a9  lea     rdx, aCannotCreateTe; "Cannot create termination Event %lu\n"
0x1800723b0  mov     ecx, 100h; unsigned int
0x1800723b5  mov     r8d, eax
0x1800723b8  mov     [rbp+arg_10], eax
0x1800723bb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800723c0  mov     eax, [rbp+arg_10]
0x1800723c3  jmp     loc_180072649
0x1800723c8  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800723cf  call    cs:__imp_RtlInitializeCriticalSection
0x1800723d5  lea     rcx, ?NlGlobalScavengerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800723dc  call    cs:__imp_RtlInitializeCriticalSection
0x1800723e2  lea     r15, ?NlGlobalEventLoggerCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalEventLoggerCritSect
0x1800723e9  mov     rcx, r15; CriticalSection
0x1800723ec  call    cs:__imp_RtlInitializeCriticalSection
0x1800723f2  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800723f9  call    cs:__imp_RtlInitializeCriticalSection
0x1800723ff  lea     rcx, ?NlGlobalDnsCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180072406  call    cs:__imp_RtlInitializeCriticalSection
0x18007240c  lea     rcx, ?NlGlobalDnsUpdateRequestCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180072413  call    cs:__imp_RtlInitializeCriticalSection
0x180072419  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180072420  call    cs:__imp_RtlInitializeCriticalSection
0x180072426  lea     rcx, ?NlGlobalServiceAccountCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18007242d  call    cs:__imp_RtlInitializeCriticalSection
0x180072433  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x18007243a  call    cs:__imp_RtlInitializeResource
0x180072440  lea     rcx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180072447  call    cs:__imp_RtlInitializeResource
0x18007244d  lea     rcx, ?NlGlobalNtlmAllowedServersLock@@3U_RTL_RESOURCE@@A; Resource
0x180072454  call    cs:__imp_RtlInitializeResource
0x18007245a  lea     rcx, ?NlGlobalCompoundIdLock@@3U_RTL_RESOURCE@@A; Resource
0x180072461  call    cs:__imp_RtlInitializeResource
0x180072467  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x18007246e  call    cs:__imp_RtlInitializeResource
0x180072474  lea     rcx, ?NlGlobalGMSADPAPILock@@3U_tagGMsaDPAPILock@@A; Resource
0x18007247b  call    cs:__imp_RtlInitializeResource
0x180072481  lea     rcx, ?NlGlobalParametersCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180072488  mov     cs:dword_1800F0D10, 0FFFFFFFFh
0x180072492  call    cs:__imp_RtlInitializeCriticalSection
0x180072498  lea     rcx, ?NlGlobalLsaPolicyHandle@@3PEAXEA; void * NlGlobalLsaPolicyHandle
0x18007249f  call    cs:__imp_LsaIOpenPolicyTrusted
0x1800724a5  test    eax, eax
0x1800724a7  jns     short loc_1800724C2
0x1800724a9  mov     r8d, eax
0x1800724ac  lea     rdx, aCannotOpenTheL; "Cannot open the LSA policy handle 0x%08"...
0x1800724b3  mov     ecx, 100h; unsigned int
0x1800724b8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800724bd  jmp     loc_180072644
0x1800724c2  lea     rdx, aCallingRegiste; "Calling RegisterServiceCtrlHandler\n"
0x1800724c9  mov     ecx, edi; unsigned int
0x1800724cb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800724d0  lea     rdx, ?NlControlHandler@@YAXK@Z; lpHandlerProc
0x1800724d7  lea     rcx, aNetlogon_0; "NETLOGON"
0x1800724de  call    cs:__imp_RegisterServiceCtrlHandlerW
0x1800724e4  mov     cs:?NlGlobalServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * NlGlobalServiceHandle
0x1800724eb  test    rax, rax
0x1800724ee  jnz     short loc_180072551
0x1800724f0  mov     [rbp+arg_18], rbx
0x1800724f4  call    cs:__imp_GetLastError
0x1800724fa  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandler failed %lu\n"
0x180072501  mov     ecx, 100h; unsigned int
0x180072506  mov     r8d, eax
0x180072509  mov     [rbp+arg_10], eax
0x18007250c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180072511  mov     eax, [rbp+arg_10]
0x180072514  or      r9d, 0FFFFFFFFh; unsigned int
0x180072518  mov     [rbp+arg_18], rax
0x18007251c  mov     r8d, 40000000h; unsigned int
0x180072522  mov     [rsp+40h+var_8], 4; unsigned int
0x18007252a  lea     rax, [rbp+arg_10]
0x18007252e  mov     [rsp+40h+var_10], rax; unsigned __int8 *
0x180072533  mov     edx, edi; unsigned int
0x180072535  lea     rax, [rbp+arg_18]
0x180072539  mov     [rsp+40h+var_18], edi; unsigned int
0x18007253d  mov     ecx, 1648h; unsigned int
0x180072542  mov     [rsp+40h+var_20], rax; unsigned __int16 **
0x180072547  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18007254c  jmp     loc_1800723C0
0x180072551  xor     ecx, ecx; int
0x180072553  call    ?GiveInstallHints@@YAHH@Z; GiveInstallHints(int)
0x180072558  test    eax, eax
0x18007255a  jz      loc_180072644
0x180072560  xor     ecx, ecx; int
0x180072562  call    ?NlOpenDebugFile@@YAXH@Z; NlOpenDebugFile(int)
0x180072567  call    ?NlLoadStrings@@YAHXZ; NlLoadStrings(void)
0x18007256c  xor     edx, edx; unsigned __int8
0x18007256e  lea     rcx, ?NlGlobalParameters@@3U_NETLOGON_PARAMETERS@@A; struct _NETLOGON_PARAMETERS *
0x180072575  call    ?NlparseAllSections@@YAHPEAU_NETLOGON_PARAMETERS@@E@Z; NlparseAllSections(_NETLOGON_PARAMETERS *,uchar)
0x18007257a  test    eax, eax
0x18007257c  jz      loc_180072644
0x180072582  lea     rdx, aCommandLinePar; "Command line parsed successfully ...\n"
0x180072589  mov     ecx, edi; unsigned int
0x18007258b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180072590  cmp     cs:?NlGlobalNetlogonUnloaded@@3HA, ebx; int NlGlobalNetlogonUnloaded
0x180072596  jz      short loc_1800725A6
0x180072598  lea     rdx, aNetlogonDllHas; "Netlogon.dll has been unloaded (recover"...
0x18007259f  mov     ecx, edi; unsigned int
0x1800725a1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800725a6  call    ?NlInitializeLocatorConnectionCache@@YAXXZ; NlInitializeLocatorConnectionCache(void)
0x1800725ab  call    ?NlInitializeDomainNameMapper@@YAXXZ; NlInitializeDomainNameMapper(void)
0x1800725b0  call    cs:__imp_SamIQueryCapabilities
0x1800725b6  and     eax, edi
0x1800725b8  mov     rcx, r15; CriticalSection
0x1800725bb  mov     cs:?NlGlobalCDC@@3HA, eax; int NlGlobalCDC
0x1800725c1  call    cs:__imp_RtlEnterCriticalSection
0x1800725c7  imul    eax, cs:dword_1800F113C, 3E8h
0x1800725d1  lea     rcx, ?NlGlobalEventLoggerTimer@@3U_TIMER@@A; lpSystemTimeAsFileTime
0x1800725d8  mov     cs:dword_1800F1BF0, eax
0x1800725de  call    cs:__imp_GetSystemTimeAsFileTime
0x1800725e4  mov     rcx, r15; CriticalSection
0x1800725e7  call    cs:__imp_RtlLeaveCriticalSection
0x1800725ed  lea     rax, ?NlDcUserValReqEventsLogger@@YAXPEAX@Z; NlDcUserValReqEventsLogger(void *)
0x1800725f4  mov     cs:qword_1800F1C88, rbx
0x1800725fb  mov     cs:qword_1800F1C80, rax
0x180072602  mov     cs:byte_1800F1C90, bl
0x180072608  call    ?NlInitChangeLogServiceStart@@YAJXZ; NlInitChangeLogServiceStart(void)
0x18007260d  test    eax, eax
0x18007260f  js      short loc_180072644
0x180072611  call    ?NlInit@@YAHXZ; NlInit(void)
0x180072616  test    eax, eax
0x180072618  jz      short loc_180072644
0x18007261a  lea     r8, ?NetpGetGroupMSAPassword@@YAJPEAU_UNICODE_STRING@@0W4_CRED_FETCH@@PEAU_FILETIME@@002@Z; NetpGetGroupMSAPassword(_UNICODE_STRING *,_UNICODE_STRING *,_CRED_FETCH,_FILETIME *,_UNICODE_STRING *,_UNICODE_STRING *,_FILETIME *)
0x180072621  lea     rdx, I_NetLogonFree
0x180072628  lea     rcx, I_NetLogonGetAuthDataEx
0x18007262f  call    cs:__imp_LsaIInitializeNetlogonFuncPtrs
0x180072635  test    eax, eax
0x180072637  js      short loc_180072644
0x180072639  mov     cs:?NlGlobalNetlogonUnloaded@@3HA, ebx; int NlGlobalNetlogonUnloaded
0x18007263f  call    ?NlMainLoop@@YAXXZ; NlMainLoop(void)
0x180072644  call    ?NlCleanup@@YAKXZ; NlCleanup(void)
0x180072649  mov     rbx, [rsp+40h+arg_0]
0x18007264e  add     rsp, 40h
0x180072652  pop     r15
0x180072654  pop     rdi
0x180072655  pop     rbp
0x180072656  retn
```
