# Dns_CacheServiceCleanup

- ea: `0x18009f000`
- end: `0x18009f17b`
- name: `Dns_CacheServiceCleanup`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000edd0`
- `0x180041ac0`
- `0x1800533bc`
- `0x18006353c`
- `0x180067d3c`
- `0x1800830f4`
- `0x1800834a0`
- `0x180083954`
- `0x180084c4c`
- `0x18008bf98`
- `0x180093f1c`
- `0x18009f000`
- `0x18009f740`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009f160`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f121`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009f121`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f148`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009f148`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18009f0ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18009f0ac`
- `WS2_32!__imp_WSACleanup` at `0x18009f102`
- `WS2_32!__imp_WSACleanup` at `0x18009f102`

## pseudocode

```c
__int64 Dns_CacheServiceCleanup()
{
  __int64 v0; // rcx
  PTP_WORK v2; // rcx
  LPCSTR retaddr; // [rsp+28h] [rbp+0h]

  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 20, WPP_91e50558be533056065562a944b5a4a4_Traceguids);
  if ( !g_fVelocitySuppressInternalExports || g_DnsIsCache || (unsigned int)Dns_IsCallerDns(retaddr) )
  {
    DnsCleanupDdr();
    if ( g_spUdpSocketsMap )
    {
      UdpSocketsMap::Release(g_spUdpSocketsMap);
      g_spUdpSocketsMap = 0;
    }
    DnsDestroySocketClosingWork();
    if ( !g_fVelocityDisableInternalExports )
      DnsShutdownWinsock();
    DnsCleanupDnsWinhttpSessionsMap();
    if ( qword_180111F70 )
    {
      DotConnectionMap::Release(qword_180111F70);
      qword_180111F70 = 0;
    }
    v2 = pwk;
    if ( pwk )
    {
      WaitForThreadpoolWorkCallbacks(pwk, 0);
      ThreadPool_CloseWork(pwk);
      pwk = 0;
    }
    if ( (_UNKNOWN *)g_DotCleanupWork != &g_DotCleanupWork )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2);
    if ( g_fVelocityDisableInternalExports )
      CleanUpDnsStatistics();
    CleanUpDnsApiStatistics();
    if ( g_fVelocityDisableInternalExports && g_fWinsockStarted )
    {
      WSACleanup();
      g_fWinsockStarted = 0;
    }
    g_DnsCacheServiceStopPending = 0;
    AcquireSRWLockExclusive(&g_rwResolverDataLock);
    memset_0(&g_ResolverData, 0, 0x90u);
    ReleaseSRWLockExclusive(&g_rwResolverDataLock);
    if ( g_hSettingsSemaphore )
      CloseHandle(g_hSettingsSemaphore);
    g_DnsIsCache = 0;
    return 0;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v0);
    return 120;
  }
}

```

## disassembly

```asm
0x18009f000  push    rbx
0x18009f002  sub     rsp, 20h
0x18009f006  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009f00d  jz      short loc_18009F025
0x18009f00f  mov     edx, 14h
0x18009f014  lea     r8, WPP_91e50558be533056065562a944b5a4a4_Traceguids
0x18009f01b  mov     ecx, 40Bh
0x18009f020  call    WPP_SF_
0x18009f025  xor     ebx, ebx
0x18009f027  cmp     cs:g_fVelocitySuppressInternalExports, ebx
0x18009f02d  jz      short loc_18009F052
0x18009f02f  cmp     cs:g_DnsIsCache, ebx
0x18009f035  jnz     short loc_18009F052
0x18009f037  mov     rcx, [rsp+28h]; lpModuleName
0x18009f03c  call    Dns_IsCallerDns
0x18009f041  test    eax, eax
0x18009f043  jnz     short loc_18009F052
0x18009f045  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009f04a  lea     eax, [rbx+78h]
0x18009f04d  jmp     loc_18009F174
0x18009f052  call    DnsCleanupDdr
0x18009f057  mov     rcx, cs:?g_spUdpSocketsMap@@3V?$AutoInterface@VUdpSocketsMap@@@@A; this
0x18009f05e  test    rcx, rcx
0x18009f061  jz      short loc_18009F06F
0x18009f063  call    ?Release@UdpSocketsMap@@QEAAKXZ; UdpSocketsMap::Release(void)
0x18009f068  mov     cs:?g_spUdpSocketsMap@@3V?$AutoInterface@VUdpSocketsMap@@@@A, rbx; AutoInterface<UdpSocketsMap> g_spUdpSocketsMap
0x18009f06f  call    DnsDestroySocketClosingWork
0x18009f074  cmp     cs:g_fVelocityDisableInternalExports, ebx
0x18009f07a  jnz     short loc_18009F081
0x18009f07c  call    DnsShutdownWinsock
0x18009f081  call    DnsCleanupDnsWinhttpSessionsMap
0x18009f086  mov     rcx, cs:qword_180111F70; this
0x18009f08d  test    rcx, rcx
0x18009f090  jz      short loc_18009F09E
0x18009f092  call    ?Release@DotConnectionMap@@QEAAKXZ; DotConnectionMap::Release(void)
0x18009f097  mov     cs:qword_180111F70, rbx
0x18009f09e  mov     rcx, cs:pwk; pwk
0x18009f0a5  test    rcx, rcx
0x18009f0a8  jz      short loc_18009F0CB
0x18009f0aa  xor     edx, edx; fCancelPendingCallbacks
0x18009f0ac  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18009f0b3  nop     dword ptr [rax+rax+00h]
0x18009f0b8  mov     rcx, cs:pwk
0x18009f0bf  call    ThreadPool_CloseWork
0x18009f0c4  mov     cs:pwk, rbx
0x18009f0cb  lea     rax, ?g_DotCleanupWork@@3VDotCleanupWork@@A; DotCleanupWork g_DotCleanupWork
0x18009f0d2  cmp     cs:?g_DotCleanupWork@@3VDotCleanupWork@@A, rax; DotCleanupWork g_DotCleanupWork
0x18009f0d9  jz      short loc_18009F0E0
0x18009f0db  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009f0e0  cmp     cs:g_fVelocityDisableInternalExports, ebx
0x18009f0e6  jz      short loc_18009F0ED
0x18009f0e8  call    CleanUpDnsStatistics
0x18009f0ed  call    CleanUpDnsApiStatistics
0x18009f0f2  cmp     cs:g_fVelocityDisableInternalExports, ebx
0x18009f0f8  jz      short loc_18009F114
0x18009f0fa  cmp     cs:g_fWinsockStarted, ebx
0x18009f100  jz      short loc_18009F114
0x18009f102  call    cs:__imp_WSACleanup
0x18009f109  nop     dword ptr [rax+rax+00h]
0x18009f10e  mov     cs:g_fWinsockStarted, ebx
0x18009f114  lea     rcx, g_rwResolverDataLock; SRWLock
0x18009f11b  mov     cs:g_DnsCacheServiceStopPending, ebx
0x18009f121  call    cs:__imp_AcquireSRWLockExclusive
0x18009f128  nop     dword ptr [rax+rax+00h]
0x18009f12d  xor     edx, edx; Val
0x18009f12f  lea     rcx, g_ResolverData; void *
0x18009f136  mov     r8d, 90h; Size
0x18009f13c  call    memset_0
0x18009f141  lea     rcx, g_rwResolverDataLock; SRWLock
0x18009f148  call    cs:__imp_ReleaseSRWLockExclusive
0x18009f14f  nop     dword ptr [rax+rax+00h]
0x18009f154  mov     rcx, cs:g_hSettingsSemaphore; hObject
0x18009f15b  test    rcx, rcx
0x18009f15e  jz      short loc_18009F16C
0x18009f160  call    cs:__imp_CloseHandle
0x18009f167  nop     dword ptr [rax+rax+00h]
0x18009f16c  mov     cs:g_DnsIsCache, ebx
0x18009f172  xor     eax, eax
0x18009f174  add     rsp, 20h
0x18009f178  pop     rbx
0x18009f179  retn
```
