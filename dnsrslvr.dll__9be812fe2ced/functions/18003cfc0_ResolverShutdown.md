# ResolverShutdown

- ea: `0x18003cfc0`
- end: `0x18003d4aa`
- name: `ResolverShutdown`
- size: `1258`
- prototype: ``
- caller_count: `2`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003cf9c`
- `0x18004a080`

## callees

- `0x180005270`
- `0x180005370`
- `0x18000b130`
- `0x180012338`
- `0x18002d4c0`
- `0x18002d6f8`
- `0x18002e178`
- `0x18003cfc0`
- `0x18003d5e0`
- `0x18003db54`
- `0x180040be0`
- `0x180040c8c`
- `0x180041398`
- `0x180043048`
- `0x18004899c`
- `0x18004a150`
- `0x18004a1b0`
- `0x18004b78c`
- `0x18004c5dc`
- `0x18004c73c`
- `0x18004c884`
- `0x18004ca3c`
- `0x18004cef0`
- `0x1800505e8`
- `0x180050898`
- `0x180051224`
- `0x180051d1c`
- `0x180052260`
- `0x180052890`
- `0x180055538`
- `0x18005ed2c`
- `0x18007848c`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003d0d7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18003d0d7`
- `RPCRT4!RpcServerUnregisterIf` at `0x18003d153`
- `RPCRT4!RpcServerUnregisterIf` at `0x18003d153`
- `DNSAPI!Dns_CacheServiceStopIssued` at `0x18003d031`
- `DNSAPI!Dns_CacheServiceStopIssued` at `0x18003d031`
- `DNSAPI!Dns_CacheServiceCleanup` at `0x18003d346`
- `DNSAPI!Dns_CacheServiceCleanup` at `0x18003d346`
- `DNSAPI!NetInfo_Free` at `0x18003d334`
- `DNSAPI!NetInfo_Free` at `0x18003d334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d082`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d18b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d37b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d41f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d37b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d41f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d46d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d46d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d47b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d47b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003d2b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003d2b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003d2c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003d2c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d06f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d178`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d06f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003d178`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d12f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003d12f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d11b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d1af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d11b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d1af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d108`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d166`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d108`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d166`
- `WS2_32!__imp_WSACleanup` at `0x18003d300`
- `WS2_32!__imp_WSACleanup` at `0x18003d300`

## pseudocode

```c
__int32 __fastcall ResolverShutdown(CRpcWatchDog *a1)
{
  DWORD v1; // edi
  __int32 result; // eax
  DWORD LastError; // eax
  int v4; // ebx
  DWORD v5; // eax
  int v6; // ebx
  CRpcWatchDog *v7; // rcx
  CRpcWatchDog *v8; // rcx
  void *v9; // rbx
  HANDLE ProcessHeap; // rax

  v1 = (unsigned int)a1;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 55, WPP_baf6623f38bf314eb96485734268b87e_Traceguids);
  g_ResolverStatus = 213910272;
  result = _InterlockedExchange(&g_fStopFlag, 1);
  if ( !result )
  {
    g_ServiceShutdownWDEntry = ResolverShutdown;
    CRpcWatchDog::AddEntry(a1, (struct _WatchDogEntry *)&g_ServiceShutdownWDEntry, 0);
    Dns_CacheServiceStopIssued();
    ServiceStatus.dwCurrentState = 3;
    ServiceStatus.dwCheckPoint = 1;
    ServiceStatus.dwWaitHint = 60000;
    ResolverUpdateStatus();
    LogEventInMemory(1886352467, 0);
    if ( g_hStopEvent && !SetEvent(g_hStopEvent) && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(1035, 56, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, LastError);
    }
    g_ResolverStatus = 213910273;
    if ( !(unsigned int)Util_IsRunningOnXboxGameOS() )
    {
      if ( (g_InitState & 0x20000000) != 0 )
        NrpStopRpcServer();
      g_ResolverStatus = 213910287;
    }
    if ( qword_1800AB5B0 )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      qword_1800AB5B0 = 0;
    }
    if ( (g_InitState & 0x100000) != 0 )
    {
      LogEventInMemory(761491538, 0);
      Rpc_Shutdown();
      EnterCriticalSection(&g_csCache);
      v4 = g_BackgroundThreadCount;
      LeaveCriticalSection(&g_csCache);
      if ( v4 )
        WaitForSingleObject(g_hBackgroundThreadWaitEvent, 0xFFFFFFFF);
    }
    g_ResolverStatus = 213910274;
    if ( g_fHvsiActive )
    {
      RpcServerUnregisterIf(qword_180091D50, 0, 1u);
      g_fHvsiActive = 0;
    }
    EnterCriticalSection(&g_csCache);
    if ( g_hStopEvent && !SetEvent(g_hStopEvent) && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v5 = GetLastError();
      WPP_SF_d(1035, 57, WPP_baf6623f38bf314eb96485734268b87e_Traceguids, v5);
    }
    LeaveCriticalSection(&g_csCache);
    if ( g_InitState < 0 )
      RpcConcurrentQueriesShutdown();
    if ( (g_InitState & 0x1000) != 0 )
      ShutdownNotify();
    g_ResolverStatus = 213910275;
    if ( g_fVPNTriggerInitialized )
    {
      VPNTriggerCleanup();
      g_fVPNTriggerInitialized = 0;
    }
    if ( (g_InitState & 0x8000) != 0 )
      Mcast_Shutdown();
    g_ResolverStatus = 213910276;
    if ( (g_InitState & 0x4000) != 0 )
      ShutdownIpListAndNotify();
    g_ResolverStatus = 213910278;
    if ( (g_InitState & 0x10000000) != 0 )
      MDns_Shutdown();
    g_ResolverStatus = 213910277;
    if ( (g_InitState & 0x2000) != 0 )
      HostReg_Shutdown();
    g_ResolverStatus = 213910279;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 13, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids);
    Cache_Flush(1);
    if ( (g_InitState & 0x100) != 0 )
      Cache_Free();
    g_ResolverStatus = 213910280;
    if ( (g_InitState & 0x40000000) != 0 )
    {
      AcquireSRWLockShared(&g_rwZtSettingsLock);
      v6 = g_fZtDriverRunning;
      ReleaseSRWLockShared(&g_rwZtSettingsLock);
      if ( v6 )
      {
        DnsZtStop();
        DnsFwCleanup();
        g_ResolverStatus = 213910288;
      }
    }
    CleanupZtdns();
    CleanupNetworkInfo();
    g_ResolverStatus = 213910281;
    if ( (g_InitState & 0x10) != 0 )
      WSACleanup();
    Cache_GCTimerDestroy();
    CloseRegistryPaths();
    if ( (g_InitState & 0x2000000) != 0 )
      Hijack_Cleanup();
    if ( (g_InitState & 0x4000000) != 0 )
      NetInfo_Free(qword_1800ABD58);
    if ( (g_InitState & 0x1000000) != 0 )
      Dns_CacheServiceCleanup();
    if ( (g_InitState & 0x20) != 0 )
    {
      if ( g_hStopEvent )
      {
        CloseHandle(g_hStopEvent);
        g_hStopEvent = 0;
      }
      if ( g_hBackgroundThreadWaitEvent )
      {
        CloseHandle(g_hBackgroundThreadWaitEvent);
        g_hBackgroundThreadWaitEvent = 0;
      }
    }
    g_ResolverStatus = 213910284;
    if ( (g_InitState & 0x8000000) != 0 )
    {
      PriorityCache_CleanupEntries();
      MIDL_user_free(g_pPriorityCache);
      g_pPriorityCache = 0;
    }
    UnreachableServerCache_Cleanup();
    if ( (g_InitState & 0x200000) != 0 )
      CleanupFirewallState();
    InterceptionShutdown();
    v7 = g_spDnsWellKnownAddrMap;
    if ( g_spDnsWellKnownAddrMap )
    {
      DnsWellKnownAddrMap::Release(g_spDnsWellKnownAddrMap);
      g_spDnsWellKnownAddrMap = 0;
    }
    CRpcWatchDog::RemoveEntry(v7, (struct _WatchDogEntry *)&g_ServiceShutdownWDEntry);
    CRpcWatchDog::Stop(v8);
    g_ResolverStatus = 213910285;
    UnregisterStopService();
    g_ResolverStatus = 213910286;
    if ( g_hStopServiceEvent )
    {
      CloseHandle(g_hStopServiceEvent);
      g_hStopServiceEvent = 0;
    }
    *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwWin32ExitCode = v1;
    *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
    ServiceStatus.dwWaitHint = 0;
    result = ResolverUpdateStatus();
    g_ResolverStatus = 213910528;
    if ( g_pEventArray )
    {
      v9 = (void *)_InterlockedExchange64(&g_pEventArray, 0);
      if ( v9 )
      {
        ProcessHeap = GetProcessHeap();
        result = HeapFree(ProcessHeap, 0, v9);
      }
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      return WPP_SF_(1035, 58, WPP_baf6623f38bf314eb96485734268b87e_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x18003cfc0  push    rbx
0x18003cfc2  push    rsi
0x18003cfc3  push    rdi
0x18003cfc4  push    r12
0x18003cfc6  push    r15
0x18003cfc8  sub     rsp, 20h
0x18003cfcc  mov     edi, ecx
0x18003cfce  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003cfd5  mov     r12d, 40Bh
0x18003cfdb  jz      short loc_18003CFF1
0x18003cfdd  mov     edx, 37h ; '7'
0x18003cfe2  lea     r8, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x18003cfe9  mov     ecx, r12d
0x18003cfec  call    WPP_SF_
0x18003cff1  mov     r15d, 1
0x18003cff7  mov     cs:g_ResolverStatus, 0CC00300h
0x18003d001  mov     eax, r15d
0x18003d004  xor     esi, esi
0x18003d006  xchg    eax, cs:g_fStopFlag
0x18003d00c  test    eax, eax
0x18003d00e  jnz     loc_18003D49E
0x18003d014  lea     rax, ResolverShutdown
0x18003d01b  xor     r8d, r8d; int
0x18003d01e  lea     rdx, g_ServiceShutdownWDEntry; struct _WatchDogEntry *
0x18003d025  mov     cs:g_ServiceShutdownWDEntry, rax
0x18003d02c  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18003d031  call    cs:__imp_Dns_CacheServiceStopIssued
0x18003d037  mov     cs:ServiceStatus.dwCurrentState, 3
0x18003d041  mov     cs:ServiceStatus.dwCheckPoint, r15d
0x18003d048  mov     cs:ServiceStatus.dwWaitHint, 0EA60h
0x18003d052  call    ResolverUpdateStatus
0x18003d057  xor     edx, edx
0x18003d059  mov     ecx, 706F7453h
0x18003d05e  call    LogEventInMemory
0x18003d063  mov     rcx, cs:g_hStopEvent; hEvent
0x18003d06a  test    rcx, rcx
0x18003d06d  jz      short loc_18003D09D
0x18003d06f  call    cs:__imp_SetEvent
0x18003d075  test    eax, eax
0x18003d077  jnz     short loc_18003D09D
0x18003d079  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003d080  jz      short loc_18003D09D
0x18003d082  call    cs:__imp_GetLastError
0x18003d088  lea     edx, [rsi+38h]
0x18003d08b  mov     ecx, r12d
0x18003d08e  mov     r9d, eax
0x18003d091  lea     r8, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x18003d098  call    WPP_SF_d
0x18003d09d  mov     cs:g_ResolverStatus, 0CC00301h
0x18003d0a7  call    Util_IsRunningOnXboxGameOS
0x18003d0ac  test    eax, eax
0x18003d0ae  jnz     short loc_18003D0CB
0x18003d0b0  mov     eax, cs:g_InitState
0x18003d0b6  bt      eax, 1Dh
0x18003d0ba  jnb     short loc_18003D0C1
0x18003d0bc  call    NrpStopRpcServer
0x18003d0c1  mov     cs:g_ResolverStatus, 0CC0030Fh
0x18003d0cb  mov     rcx, cs:qword_1800AB5B0
0x18003d0d2  test    rcx, rcx
0x18003d0d5  jz      short loc_18003D0E4
0x18003d0d7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18003d0dd  mov     cs:qword_1800AB5B0, rsi
0x18003d0e4  mov     eax, cs:g_InitState
0x18003d0ea  bt      eax, 14h
0x18003d0ee  jnb     short loc_18003D135
0x18003d0f0  xor     edx, edx
0x18003d0f2  mov     ecx, 2D637052h
0x18003d0f7  call    LogEventInMemory
0x18003d0fc  call    Rpc_Shutdown
0x18003d101  lea     rcx, g_csCache; lpCriticalSection
0x18003d108  call    cs:__imp_EnterCriticalSection
0x18003d10e  mov     ebx, cs:g_BackgroundThreadCount
0x18003d114  lea     rcx, g_csCache; lpCriticalSection
0x18003d11b  call    cs:__imp_LeaveCriticalSection
0x18003d121  test    ebx, ebx
0x18003d123  jz      short loc_18003D135
0x18003d125  mov     rcx, cs:g_hBackgroundThreadWaitEvent; hHandle
0x18003d12c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003d12f  call    cs:__imp_WaitForSingleObject
0x18003d135  cmp     cs:g_fHvsiActive, esi
0x18003d13b  mov     cs:g_ResolverStatus, 0CC00302h
0x18003d145  jz      short loc_18003D15F
0x18003d147  mov     r8d, r15d; WaitForCallsToComplete
0x18003d14a  lea     rcx, qword_180091D50; IfSpec
0x18003d151  xor     edx, edx; MgrTypeUuid
0x18003d153  call    cs:__imp_RpcServerUnregisterIf
0x18003d159  mov     cs:g_fHvsiActive, esi
0x18003d15f  lea     rcx, g_csCache; lpCriticalSection
0x18003d166  call    cs:__imp_EnterCriticalSection
0x18003d16c  mov     rcx, cs:g_hStopEvent; hEvent
0x18003d173  test    rcx, rcx
0x18003d176  jz      short loc_18003D1A8
0x18003d178  call    cs:__imp_SetEvent
0x18003d17e  test    eax, eax
0x18003d180  jnz     short loc_18003D1A8
0x18003d182  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003d189  jz      short loc_18003D1A8
0x18003d18b  call    cs:__imp_GetLastError
0x18003d191  mov     edx, 39h ; '9'
0x18003d196  lea     r8, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x18003d19d  mov     r9d, eax
0x18003d1a0  mov     ecx, r12d
0x18003d1a3  call    WPP_SF_d
0x18003d1a8  lea     rcx, g_csCache; lpCriticalSection
0x18003d1af  call    cs:__imp_LeaveCriticalSection
0x18003d1b5  mov     eax, cs:g_InitState
0x18003d1bb  test    eax, eax
0x18003d1bd  jns     short loc_18003D1C4
0x18003d1bf  call    RpcConcurrentQueriesShutdown
0x18003d1c4  mov     eax, cs:g_InitState
0x18003d1ca  bt      eax, 0Ch
0x18003d1ce  jnb     short loc_18003D1D5
0x18003d1d0  call    ShutdownNotify
0x18003d1d5  cmp     cs:g_fVPNTriggerInitialized, esi
0x18003d1db  mov     cs:g_ResolverStatus, 0CC00303h
0x18003d1e5  jz      short loc_18003D1F2
0x18003d1e7  call    VPNTriggerCleanup
0x18003d1ec  mov     cs:g_fVPNTriggerInitialized, esi
0x18003d1f2  mov     eax, cs:g_InitState
0x18003d1f8  bt      eax, 0Fh
0x18003d1fc  jnb     short loc_18003D203
0x18003d1fe  call    Mcast_Shutdown
0x18003d203  mov     eax, cs:g_InitState
0x18003d209  mov     cs:g_ResolverStatus, 0CC00304h
0x18003d213  bt      eax, 0Eh
0x18003d217  jnb     short loc_18003D21E
0x18003d219  call    ShutdownIpListAndNotify
0x18003d21e  mov     eax, cs:g_InitState
0x18003d224  mov     cs:g_ResolverStatus, 0CC00306h
0x18003d22e  bt      eax, 1Ch
0x18003d232  jnb     short loc_18003D239
0x18003d234  call    MDns_Shutdown
0x18003d239  mov     eax, cs:g_InitState
0x18003d23f  mov     cs:g_ResolverStatus, 0CC00305h
0x18003d249  bt      eax, 0Dh
0x18003d24d  jnb     short loc_18003D254
0x18003d24f  call    HostReg_Shutdown
0x18003d254  mov     cs:g_ResolverStatus, 0CC00307h
0x18003d25e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003d265  jz      short loc_18003D27B
0x18003d267  mov     edx, 0Dh
0x18003d26c  lea     r8, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids
0x18003d273  mov     ecx, r12d
0x18003d276  call    WPP_SF_
0x18003d27b  mov     ecx, r15d
0x18003d27e  call    Cache_Flush
0x18003d283  mov     eax, cs:g_InitState
0x18003d289  bt      eax, 8
0x18003d28d  jnb     short loc_18003D294
0x18003d28f  call    Cache_Free
0x18003d294  mov     eax, cs:g_InitState
0x18003d29a  mov     cs:g_ResolverStatus, 0CC00308h
0x18003d2a4  bt      eax, 1Eh
0x18003d2a8  jnb     short loc_18003D2E2
0x18003d2aa  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18003d2b1  call    cs:__imp_AcquireSRWLockShared
0x18003d2b7  mov     ebx, cs:g_fZtDriverRunning
0x18003d2bd  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18003d2c4  call    cs:__imp_ReleaseSRWLockShared
0x18003d2ca  test    ebx, ebx
0x18003d2cc  jz      short loc_18003D2E2
0x18003d2ce  call    DnsZtStop
0x18003d2d3  call    DnsFwCleanup
0x18003d2d8  mov     cs:g_ResolverStatus, 0CC00310h
0x18003d2e2  call    CleanupZtdns
0x18003d2e7  call    CleanupNetworkInfo
0x18003d2ec  mov     eax, cs:g_InitState
0x18003d2f2  mov     cs:g_ResolverStatus, 0CC00309h
0x18003d2fc  test    al, 10h
0x18003d2fe  jz      short loc_18003D306
0x18003d300  call    cs:__imp_WSACleanup
0x18003d306  call    Cache_GCTimerDestroy
0x18003d30b  call    CloseRegistryPaths
0x18003d310  mov     eax, cs:g_InitState
0x18003d316  bt      eax, 19h
0x18003d31a  jnb     short loc_18003D321
0x18003d31c  call    Hijack_Cleanup
0x18003d321  mov     eax, cs:g_InitState
0x18003d327  bt      eax, 1Ah
0x18003d32b  jnb     short loc_18003D33A
0x18003d32d  mov     rcx, cs:qword_1800ABD58
0x18003d334  call    cs:__imp_NetInfo_Free
0x18003d33a  mov     eax, cs:g_InitState
0x18003d340  bt      eax, 18h
0x18003d344  jnb     short loc_18003D34C
0x18003d346  call    cs:__imp_Dns_CacheServiceCleanup
0x18003d34c  mov     eax, cs:g_InitState
0x18003d352  test    al, 20h
0x18003d354  jz      short loc_18003D388
0x18003d356  mov     rcx, cs:g_hStopEvent; hObject
0x18003d35d  test    rcx, rcx
0x18003d360  jz      short loc_18003D36F
0x18003d362  call    cs:__imp_CloseHandle
0x18003d368  mov     cs:g_hStopEvent, rsi
0x18003d36f  mov     rcx, cs:g_hBackgroundThreadWaitEvent; hObject
0x18003d376  test    rcx, rcx
0x18003d379  jz      short loc_18003D388
0x18003d37b  call    cs:__imp_CloseHandle
0x18003d381  mov     cs:g_hBackgroundThreadWaitEvent, rsi
0x18003d388  mov     eax, cs:g_InitState
0x18003d38e  mov     cs:g_ResolverStatus, 0CC0030Ch
0x18003d398  bt      eax, 1Bh
0x18003d39c  jnb     short loc_18003D3B6
0x18003d39e  call    PriorityCache_CleanupEntries
0x18003d3a3  mov     rcx, cs:g_pPriorityCache; void *
0x18003d3aa  call    MIDL_user_free
0x18003d3af  mov     cs:g_pPriorityCache, rsi
0x18003d3b6  call    UnreachableServerCache_Cleanup
0x18003d3bb  mov     eax, cs:g_InitState
0x18003d3c1  bt      eax, 15h
0x18003d3c5  jnb     short loc_18003D3CC
0x18003d3c7  call    CleanupFirewallState
0x18003d3cc  call    InterceptionShutdown
0x18003d3d1  mov     rcx, cs:?g_spDnsWellKnownAddrMap@@3V?$AutoInterface@VDnsWellKnownAddrMap@@@@A; this
0x18003d3d8  test    rcx, rcx
0x18003d3db  jz      short loc_18003D3E9
0x18003d3dd  call    ?Release@DnsWellKnownAddrMap@@QEAAKXZ; DnsWellKnownAddrMap::Release(void)
0x18003d3e2  mov     cs:?g_spDnsWellKnownAddrMap@@3V?$AutoInterface@VDnsWellKnownAddrMap@@@@A, rsi; AutoInterface<DnsWellKnownAddrMap> g_spDnsWellKnownAddrMap
0x18003d3e9  lea     rdx, g_ServiceShutdownWDEntry; struct _WatchDogEntry *
0x18003d3f0  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18003d3f5  call    ?Stop@CRpcWatchDog@@QEAAXXZ; CRpcWatchDog::Stop(void)
0x18003d3fa  mov     cs:g_ResolverStatus, 0CC0030Dh
0x18003d404  call    UnregisterStopService
0x18003d409  mov     rcx, cs:g_hStopServiceEvent; hObject
0x18003d410  mov     cs:g_ResolverStatus, 0CC0030Eh
0x18003d41a  test    rcx, rcx
0x18003d41d  jz      short loc_18003D42C
0x18003d41f  call    cs:__imp_CloseHandle
0x18003d425  mov     cs:g_hStopServiceEvent, rsi
0x18003d42c  mov     qword ptr cs:ServiceStatus.dwCurrentState, r15
0x18003d433  mov     cs:ServiceStatus.dwWin32ExitCode, edi
0x18003d439  mov     qword ptr cs:ServiceStatus.dwServiceSpecificExitCode, rsi
0x18003d440  mov     cs:ServiceStatus.dwWaitHint, esi
0x18003d446  call    ResolverUpdateStatus
0x18003d44b  cmp     cs:g_pEventArray, rsi
0x18003d452  mov     cs:g_ResolverStatus, 0CC00400h
0x18003d45c  jz      short loc_18003D481
0x18003d45e  mov     rbx, rsi
0x18003d461  xchg    rbx, cs:g_pEventArray
0x18003d468  test    rbx, rbx
0x18003d46b  jz      short loc_18003D481
0x18003d46d  call    cs:__imp_GetProcessHeap
0x18003d473  mov     r8, rbx; lpMem
0x18003d476  xor     edx, edx; dwFlags
0x18003d478  mov     rcx, rax; hHeap
0x18003d47b  call    cs:__imp_HeapFree
0x18003d481  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003d488  jz      short loc_18003D49E
0x18003d48a  mov     edx, 3Ah ; ':'
0x18003d48f  lea     r8, WPP_baf6623f38bf314eb96485734268b87e_Traceguids
0x18003d496  mov     ecx, r12d
0x18003d499  call    WPP_SF_
0x18003d49e  add     rsp, 20h
0x18003d4a2  pop     r15
0x18003d4a4  pop     r12
0x18003d4a6  pop     rdi
0x18003d4a7  pop     rsi
0x18003d4a8  pop     rbx
0x18003d4a9  retn
```
