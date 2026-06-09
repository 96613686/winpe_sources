# RouterManagerCleanup

- ea: `0x18000c054`
- end: `0x18000c700`
- name: `RouterManagerCleanup`
- size: `1708`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a4f0`
- `0x18002a9b0`
- `0x18002aef4`
- `0x18002b4b8`
- `0x180050e40`

## callees

- `0x1800017a0`
- `0x180002040`
- `0x1800020d0`
- `0x180002f14`
- `0x18000ac60`
- `0x18000bc0c`
- `0x18000bcec`
- `0x18000bdbc`
- `0x18000be58`
- `0x18000bee8`
- `0x18000c054`
- `0x18000c708`
- `0x18000e9a0`
- `0x180021220`
- `0x18002f168`
- `0x180052594`
- `0x1800553dc`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c5dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c5dd`
- `ntdll!RtlDeleteResource` at `0x18000c598`
- `ntdll!RtlDeleteResource` at `0x18000c5be`
- `ntdll!RtlDeleteResource` at `0x18000c598`
- `ntdll!RtlDeleteResource` at `0x18000c5be`
- `KERNEL32!HeapDestroy` at `0x18000c64c`
- `KERNEL32!HeapDestroy` at `0x18000c64c`
- `KERNEL32!CloseHandle` at `0x18000c33d`
- `KERNEL32!CloseHandle` at `0x18000c365`
- `KERNEL32!CloseHandle` at `0x18000c37e`
- `KERNEL32!CloseHandle` at `0x18000c397`
- `KERNEL32!CloseHandle` at `0x18000c3b0`
- `KERNEL32!CloseHandle` at `0x18000c3c9`
- `KERNEL32!CloseHandle` at `0x18000c3e2`
- `KERNEL32!CloseHandle` at `0x18000c3fb`
- `KERNEL32!CloseHandle` at `0x18000c414`
- `KERNEL32!CloseHandle` at `0x18000c42d`
- `KERNEL32!CloseHandle` at `0x18000c446`
- `KERNEL32!CloseHandle` at `0x18000c45f`
- `KERNEL32!CloseHandle` at `0x18000c478`
- `KERNEL32!CloseHandle` at `0x18000c491`
- `KERNEL32!CloseHandle` at `0x18000c4aa`
- `KERNEL32!CloseHandle` at `0x18000c4c3`
- `KERNEL32!CloseHandle` at `0x18000c4dc`
- `KERNEL32!CloseHandle` at `0x18000c33d`
- `KERNEL32!CloseHandle` at `0x18000c365`
- `KERNEL32!CloseHandle` at `0x18000c37e`
- `KERNEL32!CloseHandle` at `0x18000c397`
- `KERNEL32!CloseHandle` at `0x18000c3b0`
- `KERNEL32!CloseHandle` at `0x18000c3c9`
- `KERNEL32!CloseHandle` at `0x18000c3e2`
- `KERNEL32!CloseHandle` at `0x18000c3fb`
- `KERNEL32!CloseHandle` at `0x18000c414`
- `KERNEL32!CloseHandle` at `0x18000c42d`
- `KERNEL32!CloseHandle` at `0x18000c446`
- `KERNEL32!CloseHandle` at `0x18000c45f`
- `KERNEL32!CloseHandle` at `0x18000c478`
- `KERNEL32!CloseHandle` at `0x18000c491`
- `KERNEL32!CloseHandle` at `0x18000c4aa`
- `KERNEL32!CloseHandle` at `0x18000c4c3`
- `KERNEL32!CloseHandle` at `0x18000c4dc`
- `KERNEL32!WaitForSingleObject` at `0x18000c330`
- `KERNEL32!WaitForSingleObject` at `0x18000c358`
- `KERNEL32!WaitForSingleObject` at `0x18000c330`
- `KERNEL32!WaitForSingleObject` at `0x18000c358`
- `KERNEL32!SetEvent` at `0x18000c2e6`
- `KERNEL32!SetEvent` at `0x18000c2e6`
- `rtutils!TraceDeregisterA` at `0x18000c6b8`
- `rtutils!TraceDeregisterA` at `0x18000c6b8`
- `rtutils!RouterLogDeregisterA` at `0x18000c6ac`
- `rtutils!RouterLogDeregisterA` at `0x18000c6ac`
- `WS2_32!__imp_closesocket` at `0x18000c4f9`
- `WS2_32!__imp_closesocket` at `0x18000c512`
- `WS2_32!__imp_closesocket` at `0x18000c4f9`
- `WS2_32!__imp_closesocket` at `0x18000c512`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c550`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c550`
- `WS2_32!__imp_WSACleanup` at `0x18000c538`
- `WS2_32!__imp_WSACleanup` at `0x18000c538`
- `WINNSI!NsiDisconnectFromServer` at `0x18000c52b`
- `WINNSI!NsiDisconnectFromServer` at `0x18000c52b`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18000c195`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18000c195`
- `rtm!RtmCleanupInstances` at `0x18000c665`
- `rtm!RtmCleanupInstances` at `0x18000c665`
- `rtm!MgmDeInitialize` at `0x18000c16f`
- `rtm!MgmDeInitialize` at `0x18000c16f`
- `iprtprio!CleanUpIpPriority` at `0x18000c65f`
- `iprtprio!CleanUpIpPriority` at `0x18000c65f`

## string_xrefs

- `0x18000c288`: `Common cleanup start`
- `0x18000c6c4`: `Common clean-up terminated: One or more routers running`
- `0x18000c559`: `RouterManagerCleanup: WSACleanup returned %d`
- `0x18000c676`: `IP Router Manager Common cleanup done`
- `0x18000c5ff`: `InitializeThreadPool`
- `0x18000c627`: `Leaving: UninitializeThreadPool`

## pseudocode

```c
DWORD __fastcall RouterManagerCleanup(int a1)
{
  DWORD result; // eax
  __int64 v3; // rcx
  const wchar_t *v4; // r8
  __int64 v5; // rcx
  unsigned int Error; // eax
  __int64 i; // rbx
  struct RtMgrRdConfigStore *Instance; // rbx
  RtMgrRdConfigStore *v9; // rbx
  void *v10; // rbx
  int v11; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v12[2044]; // [rsp+34h] [rbp-824h] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  result = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v11) = 0;
    FormatRRASErrorString(&v11, L"Entered: %ws", L"RouterManagerCleanup");
    result = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v11);
      result = Microsoft_Windows_RRASEnableBits;
    }
  }
  switch ( a1 )
  {
    case 33:
      if ( (g_dwLoadedTransports & 1) != 0 )
      {
        if ( (result & 0x80u) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"IPv4 Router Manager cleanup start");
        DeleteAllInterfaces(0x21u);
        UnloadRoutingProtocols(33);
        CloseIPDriver();
        CloseMcastDriver();
        MIBCleanup();
        DoCleanupForAllRoutingDomains(0x21u);
        g_hLocalRoute = 0;
        g_hAutoStaticRoute = 0;
        g_hRouteChangeNotificationV4 = 0;
        memset_0(g_rgRtmHandlesV4, 0, 0x50u);
        MgmDeInitialize();
        if ( g_hMcastNotification )
        {
          NsiRpcDeregisterChangeNotification(g_hNsiRPCHandle, &NPI_MS_IPV4_MODULEID, 23);
          g_hMcastNotification = 0;
        }
        if ( !RouterRoleLanOnly )
          IPv4DemandDialCleanupRequired = 1;
        result = DeleteRTRMgrOwnedRoutesToDestFromStackForAllRoutingDomains(v3, 1);
        g_dwLoadedTransports &= ~1u;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v4 = L"IPv4 Router Manager cleanup done";
          return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v4);
        }
      }
      break;
    case 87:
      if ( (g_dwLoadedTransports & 2) != 0 )
      {
        if ( (result & 0x80u) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"IPv6 Router Manager cleanup start");
        DeleteAllInterfaces(0x57u);
        UnloadRoutingProtocols(87);
        DoCleanupForAllRoutingDomains(0x57u);
        g_hLocalRouteV6 = 0;
        g_hRouteChangeNotificationV6 = 0;
        memset_0(&g_rgRtmHandlesV6, 0, 0x50u);
        if ( !RouterRoleLanOnly )
          IPv6DemandDialCleanupRequired = 1;
        result = DeleteRTRMgrOwnedRoutesToDestFromStackForAllRoutingDomains(v5, 0);
        g_dwLoadedTransports &= ~2u;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v4 = L"IPv6 Router Manager cleanup done";
          return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v4);
        }
      }
      break;
    case -1:
      if ( (result & 0x80u) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Common cleanup start");
        result = Microsoft_Windows_RRASEnableBits;
      }
      if ( (g_dwLoadedTransports & 3) != 0 )
      {
        if ( (result & 0x80u) == 0 )
          return result;
        v4 = L"Common clean-up terminated: One or more routers running";
        return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v4);
      }
      UnInitHashTables();
      if ( !RouterRoleLanOnly && g_bEnableNetbtBcastFrowarding )
      {
        RestoreNetbtBcastForwardingMode();
        g_bEnableNetbtBcastFrowarding = 0;
      }
      InterfaceContainer::UnInitInterfaceContainer((InterfaceContainer *)&icContainer);
      if ( g_hStopRouterEvent )
        SetEvent(g_hStopRouterEvent);
      if ( IPv4DemandDialCleanupRequired )
      {
        CloseDemandDial(1);
        IPv4DemandDialCleanupRequired = 0;
      }
      if ( IPv6DemandDialCleanupRequired )
      {
        CloseDemandDial(0);
        IPv6DemandDialCleanupRequired = 0;
      }
      if ( g_hDemandDialEvent )
      {
        WaitForSingleObject(g_hDemandDialEvent, 0x3E8u);
        CloseHandle(g_hDemandDialEvent);
        g_hDemandDialEvent = 0;
      }
      if ( g_hDemandDialEventV6 )
      {
        WaitForSingleObject(g_hDemandDialEventV6, 0x3E8u);
        CloseHandle(g_hDemandDialEventV6);
        g_hDemandDialEventV6 = 0;
      }
      if ( g_hSetForwardingEventV4 )
      {
        CloseHandle(g_hSetForwardingEventV4);
        g_hSetForwardingEventV4 = 0;
      }
      if ( g_hSetForwardingEventV6 )
      {
        CloseHandle(g_hSetForwardingEventV6);
        g_hSetForwardingEventV6 = 0;
      }
      if ( g_hForwardingChangeEvent )
      {
        CloseHandle(g_hForwardingChangeEvent);
        g_hForwardingChangeEvent = 0;
      }
      if ( g_hStackChangeEvent )
      {
        CloseHandle(g_hStackChangeEvent);
        g_hStackChangeEvent = 0;
      }
      if ( g_hStopRouterEvent )
      {
        CloseHandle(g_hStopRouterEvent);
        g_hStopRouterEvent = 0;
      }
      if ( g_hStopRouterEventV6 )
      {
        CloseHandle(g_hStopRouterEventV6);
        g_hStopRouterEventV6 = 0;
      }
      if ( g_hRoutingProtocolEvent )
      {
        CloseHandle(g_hRoutingProtocolEvent);
        g_hRoutingProtocolEvent = 0;
      }
      if ( g_hRoutingProtocolEventV6 )
      {
        CloseHandle(g_hRoutingProtocolEventV6);
        g_hRoutingProtocolEventV6 = 0;
      }
      if ( g_hRtrDiscSocketEvent )
      {
        CloseHandle(g_hRtrDiscSocketEvent);
        g_hRtrDiscSocketEvent = 0;
      }
      if ( g_hMcMiscSocketEvent )
      {
        CloseHandle(g_hMcMiscSocketEvent);
        g_hMcMiscSocketEvent = 0;
      }
      if ( g_hRtrDiscTimer )
      {
        CloseHandle(g_hRtrDiscTimer);
        g_hRtrDiscTimer = 0;
      }
      if ( g_hRasAdvTimer )
      {
        CloseHandle(g_hRasAdvTimer);
        g_hRasAdvTimer = 0;
      }
      if ( g_hMzapTimer )
      {
        CloseHandle(g_hMzapTimer);
        g_hMzapTimer = 0;
      }
      if ( g_hMHbeatSocketEvent )
      {
        CloseHandle(g_hMHbeatSocketEvent);
        g_hMHbeatSocketEvent = 0;
      }
      if ( g_hMzapSocketEvent )
      {
        CloseHandle(g_hMzapSocketEvent);
        g_hMzapSocketEvent = 0;
      }
      if ( g_AddrChangeSocketV4 != -1 )
      {
        closesocket(g_AddrChangeSocketV4);
        g_AddrChangeSocketV4 = -1;
      }
      if ( g_AddrChangeSocketV6 != -1 )
      {
        closesocket(g_AddrChangeSocketV6);
        g_AddrChangeSocketV6 = -1;
      }
      if ( g_hNsiRPCHandle )
      {
        NsiDisconnectFromServer();
        g_hNsiRPCHandle = 0;
      }
      if ( WSACleanup() )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v11) = 0;
          Error = WSAGetLastError();
          FormatRRASErrorString(&v11, L"RouterManagerCleanup: WSACleanup returned %d", Error);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v11);
        }
      }
      for ( i = 0; i != 15; ++i )
        RtlDeleteResource(&g_LockTable + i);
      Instance = RtMgrRdConfigStore::GetInstance();
      RtMgrRdConfigStore::CleanUpStore(Instance);
      RtlDeleteResource((PRTL_RESOURCE)((char *)Instance + 184));
      *(_DWORD *)Instance = 0;
      v9 = RtMgrRdConfigStore::pInstance;
      if ( RtMgrRdConfigStore::pInstance )
      {
        RtMgrRdConfigStore::~RtMgrRdConfigStore(RtMgrRdConfigStore::pInstance);
        operator delete(v9);
        RtMgrRdConfigStore::pInstance = 0;
      }
      v10 = g_hDDEventThreadPool;
      if ( g_hDDEventThreadPool )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"InitializeThreadPool");
        if ( v10 )
          DestroyThreadPoolInternal(v10);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: UninitializeThreadPool");
        g_hDDEventThreadPool = 0;
      }
      if ( IPRouterHeap )
      {
        HeapDestroy(IPRouterHeap);
        IPRouterHeap = 0;
      }
      g_fRouterManagerInitialized = 0;
      CleanUpIpPriority();
      RtmCleanupInstances();
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"IP Router Manager Common cleanup done");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: RouterManagerCleanup");
      }
      RouterLogDeregisterA(g_hLogHandle);
      return TraceDeregisterA(TraceHandle);
    default:
      return result;
  }
  return result;
}

```

## disassembly

```asm
0x18000c054  mov     [rsp+arg_8], rbx
0x18000c059  mov     [rsp+arg_10], rsi
0x18000c05e  push    r12
0x18000c060  push    r14
0x18000c062  push    r15
0x18000c064  sub     rsp, 840h
0x18000c06b  mov     rax, cs:__security_cookie
0x18000c072  xor     rax, rsp
0x18000c075  mov     [rsp+858h+var_28], rax
0x18000c07d  mov     ebx, ecx
0x18000c07f  xor     esi, esi
0x18000c081  lea     rcx, [rsp+858h+var_824]; void *
0x18000c086  mov     [rsp+858h+var_828], esi
0x18000c08a  xor     edx, edx; Val
0x18000c08c  mov     r8d, 7FCh; Size
0x18000c092  call    memset_0
0x18000c097  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000c09e  lea     r14, RasRtrmgrTraceInfo
0x18000c0a5  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000c0ac  test    al, al
0x18000c0ae  jns     short loc_18000C0EF
0x18000c0b0  lea     r8, aRoutermanagerc; "RouterManagerCleanup"
0x18000c0b7  mov     word ptr [rsp+858h+var_828], si
0x18000c0bc  lea     rdx, aEnteredWs; "Entered: %ws"
0x18000c0c3  lea     rcx, [rsp+858h+var_828]
0x18000c0c8  call    FormatRRASErrorString
0x18000c0cd  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000c0d4  test    al, al
0x18000c0d6  jns     short loc_18000C0EF
0x18000c0d8  lea     r8, [rsp+858h+var_828]
0x18000c0dd  mov     rdx, r14
0x18000c0e0  mov     rcx, r15
0x18000c0e3  call    McTemplateU0z_EventWriteTransfer
0x18000c0e8  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000c0ef  mov     r12d, 21h ; '!'
0x18000c0f5  cmp     ebx, r12d
0x18000c0f8  jnz     loc_18000C1DB
0x18000c0fe  test    byte ptr cs:g_dwLoadedTransports, 1
0x18000c105  jz      loc_18000C6D6
0x18000c10b  test    al, 80h
0x18000c10d  jz      short loc_18000C121
0x18000c10f  lea     r8, aIpv4RouterMana_0; "IPv4 Router Manager cleanup start"
0x18000c116  mov     rdx, r14
0x18000c119  mov     rcx, r15
0x18000c11c  call    McTemplateU0z_EventWriteTransfer
0x18000c121  mov     ecx, r12d; unsigned int
0x18000c124  call    DeleteAllInterfaces
0x18000c129  mov     ecx, r12d
0x18000c12c  call    UnloadRoutingProtocols
0x18000c131  call    CloseIPDriver
0x18000c136  call    CloseMcastDriver
0x18000c13b  call    MIBCleanup
0x18000c140  mov     ecx, r12d; unsigned int
0x18000c143  call    DoCleanupForAllRoutingDomains
0x18000c148  xor     edx, edx; Val
0x18000c14a  mov     cs:g_hLocalRoute, rsi
0x18000c151  lea     rcx, g_rgRtmHandlesV4; void *
0x18000c158  mov     cs:g_hAutoStaticRoute, rsi
0x18000c15f  mov     cs:g_hRouteChangeNotificationV4, rsi
0x18000c166  lea     r8d, [rdx+50h]; Size
0x18000c16a  call    memset_0
0x18000c16f  call    cs:__imp_MgmDeInitialize
0x18000c175  mov     r9, cs:g_hMcastNotification
0x18000c17c  test    r9, r9
0x18000c17f  jz      short loc_18000C1A2
0x18000c181  mov     rcx, cs:g_hNsiRPCHandle
0x18000c188  lea     rdx, NPI_MS_IPV4_MODULEID
0x18000c18f  mov     r8d, 17h
0x18000c195  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18000c19b  mov     cs:g_hMcastNotification, rsi
0x18000c1a2  cmp     cs:RouterRoleLanOnly, esi
0x18000c1a8  jnz     short loc_18000C1B1
0x18000c1aa  mov     cs:IPv4DemandDialCleanupRequired, 1
0x18000c1b1  mov     edx, 1
0x18000c1b6  call    DeleteRTRMgrOwnedRoutesToDestFromStackForAllRoutingDomains
0x18000c1bb  and     cs:g_dwLoadedTransports, 0FFFFFFFEh
0x18000c1c2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000c1c9  jz      loc_18000C6D6
0x18000c1cf  lea     r8, aIpv4RouterMana; "IPv4 Router Manager cleanup done"
0x18000c1d6  jmp     loc_18000C6CB
0x18000c1db  mov     r12d, 57h ; 'W'
0x18000c1e1  cmp     ebx, r12d
0x18000c1e4  jnz     loc_18000C27B
0x18000c1ea  test    byte ptr cs:g_dwLoadedTransports, 2
0x18000c1f1  jz      loc_18000C6D6
0x18000c1f7  test    al, 80h
0x18000c1f9  jz      short loc_18000C20D
0x18000c1fb  lea     r8, aIpv6RouterMana_0; "IPv6 Router Manager cleanup start"
0x18000c202  mov     rdx, r14
0x18000c205  mov     rcx, r15
0x18000c208  call    McTemplateU0z_EventWriteTransfer
0x18000c20d  mov     ecx, r12d; unsigned int
0x18000c210  call    DeleteAllInterfaces
0x18000c215  mov     ecx, r12d
0x18000c218  call    UnloadRoutingProtocols
0x18000c21d  mov     ecx, r12d; unsigned int
0x18000c220  call    DoCleanupForAllRoutingDomains
0x18000c225  xor     edx, edx; Val
0x18000c227  mov     cs:g_hLocalRouteV6, rsi
0x18000c22e  lea     rcx, g_rgRtmHandlesV6; void *
0x18000c235  mov     cs:g_hRouteChangeNotificationV6, rsi
0x18000c23c  lea     r8d, [rdx+50h]; Size
0x18000c240  call    memset_0
0x18000c245  cmp     cs:RouterRoleLanOnly, esi
0x18000c24b  jnz     short loc_18000C254
0x18000c24d  mov     cs:IPv6DemandDialCleanupRequired, 1
0x18000c254  xor     edx, edx
0x18000c256  call    DeleteRTRMgrOwnedRoutesToDestFromStackForAllRoutingDomains
0x18000c25b  and     cs:g_dwLoadedTransports, 0FFFFFFFDh
0x18000c262  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000c269  jz      loc_18000C6D6
0x18000c26f  lea     r8, aIpv6RouterMana; "IPv6 Router Manager cleanup done"
0x18000c276  jmp     loc_18000C6CB
0x18000c27b  cmp     ebx, 0FFFFFFFFh
0x18000c27e  jnz     loc_18000C6D6
0x18000c284  test    al, 80h
0x18000c286  jz      short loc_18000C2A1
0x18000c288  lea     r8, aCommonCleanupS; "Common cleanup start"
0x18000c28f  mov     rdx, r14
0x18000c292  mov     rcx, r15
0x18000c295  call    McTemplateU0z_EventWriteTransfer
0x18000c29a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000c2a1  test    byte ptr cs:g_dwLoadedTransports, 3
0x18000c2a8  jnz     loc_18000C6C0
0x18000c2ae  call    UnInitHashTables
0x18000c2b3  cmp     cs:RouterRoleLanOnly, esi
0x18000c2b9  jnz     short loc_18000C2CE
0x18000c2bb  cmp     cs:g_bEnableNetbtBcastFrowarding, esi
0x18000c2c1  jz      short loc_18000C2CE
0x18000c2c3  call    RestoreNetbtBcastForwardingMode
0x18000c2c8  mov     cs:g_bEnableNetbtBcastFrowarding, esi
0x18000c2ce  lea     rcx, ?icContainer@@3VInterfaceContainer@@A; this
0x18000c2d5  call    ?UnInitInterfaceContainer@InterfaceContainer@@QEAAXXZ; InterfaceContainer::UnInitInterfaceContainer(void)
0x18000c2da  mov     rcx, cs:g_hStopRouterEvent; hEvent
0x18000c2e1  test    rcx, rcx
0x18000c2e4  jz      short loc_18000C2EC
0x18000c2e6  call    cs:__imp_SetEvent
0x18000c2ec  cmp     cs:IPv4DemandDialCleanupRequired, sil
0x18000c2f3  jz      short loc_18000C306
0x18000c2f5  mov     ecx, 1
0x18000c2fa  call    CloseDemandDial
0x18000c2ff  mov     cs:IPv4DemandDialCleanupRequired, sil
0x18000c306  cmp     cs:IPv6DemandDialCleanupRequired, sil
0x18000c30d  jz      short loc_18000C31D
0x18000c30f  xor     ecx, ecx
0x18000c311  call    CloseDemandDial
0x18000c316  mov     cs:IPv6DemandDialCleanupRequired, sil
0x18000c31d  mov     rcx, cs:g_hDemandDialEvent; hHandle
0x18000c324  mov     ebx, 3E8h
0x18000c329  test    rcx, rcx
0x18000c32c  jz      short loc_18000C34A
0x18000c32e  mov     edx, ebx; dwMilliseconds
0x18000c330  call    cs:__imp_WaitForSingleObject
0x18000c336  mov     rcx, cs:g_hDemandDialEvent; hObject
0x18000c33d  call    cs:__imp_CloseHandle
0x18000c343  mov     cs:g_hDemandDialEvent, rsi
0x18000c34a  mov     rcx, cs:g_hDemandDialEventV6; hHandle
0x18000c351  test    rcx, rcx
0x18000c354  jz      short loc_18000C372
0x18000c356  mov     edx, ebx; dwMilliseconds
0x18000c358  call    cs:__imp_WaitForSingleObject
0x18000c35e  mov     rcx, cs:g_hDemandDialEventV6; hObject
0x18000c365  call    cs:__imp_CloseHandle
0x18000c36b  mov     cs:g_hDemandDialEventV6, rsi
0x18000c372  mov     rcx, cs:g_hSetForwardingEventV4; hObject
0x18000c379  test    rcx, rcx
0x18000c37c  jz      short loc_18000C38B
0x18000c37e  call    cs:__imp_CloseHandle
0x18000c384  mov     cs:g_hSetForwardingEventV4, rsi
0x18000c38b  mov     rcx, cs:g_hSetForwardingEventV6; hObject
0x18000c392  test    rcx, rcx
0x18000c395  jz      short loc_18000C3A4
0x18000c397  call    cs:__imp_CloseHandle
0x18000c39d  mov     cs:g_hSetForwardingEventV6, rsi
0x18000c3a4  mov     rcx, cs:g_hForwardingChangeEvent; hObject
0x18000c3ab  test    rcx, rcx
0x18000c3ae  jz      short loc_18000C3BD
0x18000c3b0  call    cs:__imp_CloseHandle
0x18000c3b6  mov     cs:g_hForwardingChangeEvent, rsi
0x18000c3bd  mov     rcx, cs:g_hStackChangeEvent; hObject
0x18000c3c4  test    rcx, rcx
0x18000c3c7  jz      short loc_18000C3D6
0x18000c3c9  call    cs:__imp_CloseHandle
0x18000c3cf  mov     cs:g_hStackChangeEvent, rsi
0x18000c3d6  mov     rcx, cs:g_hStopRouterEvent; hObject
0x18000c3dd  test    rcx, rcx
0x18000c3e0  jz      short loc_18000C3EF
0x18000c3e2  call    cs:__imp_CloseHandle
0x18000c3e8  mov     cs:g_hStopRouterEvent, rsi
0x18000c3ef  mov     rcx, cs:g_hStopRouterEventV6; hObject
0x18000c3f6  test    rcx, rcx
0x18000c3f9  jz      short loc_18000C408
0x18000c3fb  call    cs:__imp_CloseHandle
0x18000c401  mov     cs:g_hStopRouterEventV6, rsi
0x18000c408  mov     rcx, cs:g_hRoutingProtocolEvent; hObject
0x18000c40f  test    rcx, rcx
0x18000c412  jz      short loc_18000C421
0x18000c414  call    cs:__imp_CloseHandle
0x18000c41a  mov     cs:g_hRoutingProtocolEvent, rsi
0x18000c421  mov     rcx, cs:g_hRoutingProtocolEventV6; hObject
0x18000c428  test    rcx, rcx
0x18000c42b  jz      short loc_18000C43A
0x18000c42d  call    cs:__imp_CloseHandle
0x18000c433  mov     cs:g_hRoutingProtocolEventV6, rsi
0x18000c43a  mov     rcx, cs:g_hRtrDiscSocketEvent; hObject
0x18000c441  test    rcx, rcx
0x18000c444  jz      short loc_18000C453
0x18000c446  call    cs:__imp_CloseHandle
0x18000c44c  mov     cs:g_hRtrDiscSocketEvent, rsi
0x18000c453  mov     rcx, cs:g_hMcMiscSocketEvent; hObject
0x18000c45a  test    rcx, rcx
0x18000c45d  jz      short loc_18000C46C
0x18000c45f  call    cs:__imp_CloseHandle
0x18000c465  mov     cs:g_hMcMiscSocketEvent, rsi
0x18000c46c  mov     rcx, cs:g_hRtrDiscTimer; hObject
0x18000c473  test    rcx, rcx
0x18000c476  jz      short loc_18000C485
0x18000c478  call    cs:__imp_CloseHandle
0x18000c47e  mov     cs:g_hRtrDiscTimer, rsi
0x18000c485  mov     rcx, cs:g_hRasAdvTimer; hObject
0x18000c48c  test    rcx, rcx
0x18000c48f  jz      short loc_18000C49E
0x18000c491  call    cs:__imp_CloseHandle
0x18000c497  mov     cs:g_hRasAdvTimer, rsi
0x18000c49e  mov     rcx, cs:g_hMzapTimer; hObject
0x18000c4a5  test    rcx, rcx
0x18000c4a8  jz      short loc_18000C4B7
0x18000c4aa  call    cs:__imp_CloseHandle
0x18000c4b0  mov     cs:g_hMzapTimer, rsi
0x18000c4b7  mov     rcx, cs:g_hMHbeatSocketEvent; hObject
0x18000c4be  test    rcx, rcx
0x18000c4c1  jz      short loc_18000C4D0
0x18000c4c3  call    cs:__imp_CloseHandle
0x18000c4c9  mov     cs:g_hMHbeatSocketEvent, rsi
0x18000c4d0  mov     rcx, cs:g_hMzapSocketEvent; hObject
0x18000c4d7  test    rcx, rcx
0x18000c4da  jz      short loc_18000C4E9
0x18000c4dc  call    cs:__imp_CloseHandle
0x18000c4e2  mov     cs:g_hMzapSocketEvent, rsi
0x18000c4e9  mov     rcx, cs:g_AddrChangeSocketV4; s
0x18000c4f0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c4f4  cmp     rcx, rbx
0x18000c4f7  jz      short loc_18000C506
0x18000c4f9  call    cs:__imp_closesocket
0x18000c4ff  mov     cs:g_AddrChangeSocketV4, rbx
0x18000c506  mov     rcx, cs:g_AddrChangeSocketV6; s
0x18000c50d  cmp     rcx, rbx
0x18000c510  jz      short loc_18000C51F
0x18000c512  call    cs:__imp_closesocket
0x18000c518  mov     cs:g_AddrChangeSocketV6, rbx
0x18000c51f  mov     rcx, cs:g_hNsiRPCHandle
0x18000c526  test    rcx, rcx
0x18000c529  jz      short loc_18000C538
0x18000c52b  call    cs:__imp_NsiDisconnectFromServer
0x18000c531  mov     cs:g_hNsiRPCHandle, rsi
0x18000c538  call    cs:__imp_WSACleanup
0x18000c53e  test    eax, eax
0x18000c540  jz      short loc_18000C583
0x18000c542  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18000c549  jge     short loc_18000C583
0x18000c54b  mov     word ptr [rsp+858h+var_828], si
0x18000c550  call    cs:__imp_WSAGetLastError
0x18000c556  mov     r8d, eax
0x18000c559  lea     rdx, aRoutermanagerc_0; "RouterManagerCleanup: WSACleanup return"...
0x18000c560  lea     rcx, [rsp+858h+var_828]
0x18000c565  call    FormatRRASErrorString
0x18000c56a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18000c571  jge     short loc_18000C583
0x18000c573  lea     r8, [rsp+858h+var_828]
0x18000c578  mov     rdx, r14
0x18000c57b  mov     rcx, r15
0x18000c57e  call    McTemplateU0z_EventWriteTransfer
0x18000c583  mov     rbx, rsi
0x18000c586  lea     rax, g_LockTable
0x18000c58d  lea     rcx, [rbx+rbx*2]
0x18000c591  shl     rcx, 5
0x18000c595  add     rcx, rax; Resource
0x18000c598  call    cs:__imp_RtlDeleteResource
0x18000c59e  inc     rbx
0x18000c5a1  cmp     rbx, 0Fh
0x18000c5a5  jnz     short loc_18000C586
0x18000c5a7  call    ?GetInstance@RtMgrRdConfigStore@@SAPEAV1@XZ; RtMgrRdConfigStore::GetInstance(void)
0x18000c5ac  mov     rcx, rax; this
0x18000c5af  mov     rbx, rax
0x18000c5b2  call    ?CleanUpStore@RtMgrRdConfigStore@@AEAAXXZ; RtMgrRdConfigStore::CleanUpStore(void)
0x18000c5b7  lea     rcx, [rbx+0B8h]; Resource
0x18000c5be  call    cs:__imp_RtlDeleteResource
0x18000c5c4  mov     [rbx], esi
0x18000c5c6  mov     rbx, cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x18000c5cd  test    rbx, rbx
0x18000c5d0  jz      short loc_18000C5EA
0x18000c5d2  mov     rcx, rbx; this
0x18000c5d5  call    ??1RtMgrRdConfigStore@@QEAA@XZ; RtMgrRdConfigStore::~RtMgrRdConfigStore(void)
0x18000c5da  mov     rcx, rbx
0x18000c5dd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c5e3  mov     cs:?pInstance@RtMgrRdConfigStore@@0PEAV1@EA, rsi; RtMgrRdConfigStore * RtMgrRdConfigStore::pInstance
0x18000c5ea  mov     rbx, cs:g_hDDEventThreadPool
0x18000c5f1  test    rbx, rbx
0x18000c5f4  jz      short loc_18000C640
0x18000c5f6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
  ... truncated ...
```
