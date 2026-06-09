# WorkerThread

- ea: `0x180050e40`
- end: `0x180051a0c`
- name: `WorkerThread`
- size: `3020`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ac60`
- `0x18000c054`
- `0x1800106a0`
- `0x18003225c`
- `0x1800325c0`
- `0x180038540`
- `0x180039e14`
- `0x18003be98`
- `0x18003bfb0`
- `0x18004edd8`
- `0x18004f084`
- `0x180050434`
- `0x180050b74`
- `0x180050d18`
- `0x180050e40`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18005170c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180051754`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005170c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180051754`
- `ntdll!RtlReleaseResource` at `0x1800517b7`
- `ntdll!RtlReleaseResource` at `0x1800517b7`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18005104b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x18005104b`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1800519ae`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1800519ae`
- `KERNEL32!GetLastError` at `0x180051852`
- `KERNEL32!GetLastError` at `0x180051852`
- `KERNEL32!LeaveCriticalSection` at `0x1800511a8`
- `KERNEL32!LeaveCriticalSection` at `0x18005135d`
- `KERNEL32!LeaveCriticalSection` at `0x180051466`
- `KERNEL32!LeaveCriticalSection` at `0x1800515f0`
- `KERNEL32!LeaveCriticalSection` at `0x18005164a`
- `KERNEL32!LeaveCriticalSection` at `0x180051682`
- `KERNEL32!LeaveCriticalSection` at `0x1800516b7`
- `KERNEL32!LeaveCriticalSection` at `0x1800516fc`
- `KERNEL32!LeaveCriticalSection` at `0x180051744`
- `KERNEL32!LeaveCriticalSection` at `0x1800511a8`
- `KERNEL32!LeaveCriticalSection` at `0x18005135d`
- `KERNEL32!LeaveCriticalSection` at `0x180051466`
- `KERNEL32!LeaveCriticalSection` at `0x1800515f0`
- `KERNEL32!LeaveCriticalSection` at `0x18005164a`
- `KERNEL32!LeaveCriticalSection` at `0x180051682`
- `KERNEL32!LeaveCriticalSection` at `0x1800516b7`
- `KERNEL32!LeaveCriticalSection` at `0x1800516fc`
- `KERNEL32!LeaveCriticalSection` at `0x180051744`
- `KERNEL32!EnterCriticalSection` at `0x1800510d7`
- `KERNEL32!EnterCriticalSection` at `0x18005118d`
- `KERNEL32!EnterCriticalSection` at `0x180051300`
- `KERNEL32!EnterCriticalSection` at `0x180051408`
- `KERNEL32!EnterCriticalSection` at `0x1800515b4`
- `KERNEL32!EnterCriticalSection` at `0x180051625`
- `KERNEL32!EnterCriticalSection` at `0x18005165d`
- `KERNEL32!EnterCriticalSection` at `0x180051695`
- `KERNEL32!EnterCriticalSection` at `0x1800516ca`
- `KERNEL32!EnterCriticalSection` at `0x18005171f`
- `KERNEL32!EnterCriticalSection` at `0x1800510d7`
- `KERNEL32!EnterCriticalSection` at `0x18005118d`
- `KERNEL32!EnterCriticalSection` at `0x180051300`
- `KERNEL32!EnterCriticalSection` at `0x180051408`
- `KERNEL32!EnterCriticalSection` at `0x1800515b4`
- `KERNEL32!EnterCriticalSection` at `0x180051625`
- `KERNEL32!EnterCriticalSection` at `0x18005165d`
- `KERNEL32!EnterCriticalSection` at `0x180051695`
- `KERNEL32!EnterCriticalSection` at `0x1800516ca`
- `KERNEL32!EnterCriticalSection` at `0x18005171f`

## string_xrefs

- `0x180050ec1`: `WorkerThread`
- `0x1800514df`: `WorkerThread: Demand Dial IPv4 event received`
- `0x1800514b9`: `WorkerThread: Demand Dial IPv6 event received`
- `0x1800513d3`: `WorkerThread: **--STOP Router for v4--**\n\n`
- `0x180051214`: `WorkerThread: **--Disabling IPv4 forwarding--**\n\n`
- `0x18005142a`: `WorkerThread: **--Disabling IPv4 forwarding--**\n\n`
- `0x1800512cc`: `WorkerThread: **--STOP Router for v6--**\n\n`
- `0x18005114d`: `WorkerThread: **--Disabling IPv6 forwarding--**\n\n`
- `0x180051322`: `WorkerThread: **--Disabling IPv6 forwarding--**\n\n`
- `0x1800511d3`: `WorkerThread: **--Enabling IPv4 forwarding--**\n\n`
- `0x180051277`: `WorkerThread: Error %d from call`
- `0x18005110f`: `WorkerThread: **--Enabling IPv6 forwarding--**\n\n`
- `0x1800510c1`: `WorkerThread: **--Forwarding change event--**\n\n`
- `0x18005150e`: `WorkerThread: Routing protocol notification for IPv4 received`
- `0x1800517d6`: `WorkerThread: Routing protocol notification for IPv6 received`
- `0x1800515d3`: `WorkerThread: Router discovery timer fired while shutting down. Ignoring`
- `0x180051606`: `WorkerThread: RasAdv Timer event received`
- `0x18005176c`: `WorkerThread: Router Discovery Timer event received`
- `0x18005179e`: `WorkerThread: Router Discovery Timer went off but no timer items`
- `0x1800516ed`: `WorkerThread: FD_READ while shutting down. Ignoring`
- `0x18005185b`: `WorkerThread: Wait failed with following error %d`
- `0x18005197d`: `WorkerThread: Worker thread stopping`
- `0x180058b84`: `WorkerThread: Worker thread stopping`
- `0x1800519be`: `WorkerThread: Exit`

## pseudocode

```c
__int64 __fastcall WorkerThread(PVOID Parameter)
{
  DWORD v1; // r14d
  DWORD v2; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  DWORD v7; // eax
  const wchar_t *v8; // r8
  __int64 *v9; // rdx
  unsigned int v10; // eax
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  bool v20; // zf
  const wchar_t *v21; // r8
  bool v22; // zf
  char v23; // al
  DWORD LastError; // eax
  int v25; // edi
  int v27; // [rsp+38h] [rbp-910h] BYREF
  int v28; // [rsp+3Ch] [rbp-90Ch]
  int v29; // [rsp+40h] [rbp-908h]
  int v30; // [rsp+44h] [rbp-904h]
  int v31; // [rsp+48h] [rbp-900h]
  int v32; // [rsp+4Ch] [rbp-8FCh]
  int v33; // [rsp+50h] [rbp-8F8h]
  int v34; // [rsp+54h] [rbp-8F4h]
  __int128 v35; // [rsp+58h] [rbp-8F0h] BYREF
  __int128 v36; // [rsp+68h] [rbp-8E0h]
  HANDLE Handles[16]; // [rsp+80h] [rbp-8C8h] BYREF
  int v38; // [rsp+100h] [rbp-848h] BYREF
  char v39[2044]; // [rsp+104h] [rbp-844h] BYREF

  memset_0(Handles, 0, sizeof(Handles));
  v27 = 0;
  v35 = 0;
  v36 = 0;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v38, L"Entered: %ws", L"WorkerThread");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v38);
  }
  Handles[0] = g_hDemandDialEvent;
  Handles[1] = g_hDemandDialEventV6;
  Handles[2] = g_hStopRouterEvent;
  Handles[3] = g_hStopRouterEventV6;
  Handles[4] = g_hSetForwardingEventV4;
  Handles[5] = g_hSetForwardingEventV6;
  Handles[6] = g_hForwardingChangeEvent;
  Handles[7] = g_hRoutingProtocolEvent;
  Handles[8] = g_hRoutingProtocolEventV6;
  Handles[9] = g_hRtrDiscTimer;
  Handles[10] = g_hRtrDiscSocketEvent;
  Handles[11] = g_hMcMiscSocketEvent;
  Handles[13] = g_hMzapTimer;
  Handles[14] = g_hMzapSocketEvent;
  Handles[15] = g_hRasAdvTimer;
  Handles[12] = g_hMHbeatSocketEvent;
  v1 = -1;
  g_AddrChangeSocketV4 = -1;
  g_AddrChangeSocketV6 = -1;
  v35 = 0;
  v36 = 0;
  do
  {
    while ( 1 )
    {
      do
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v2 = WaitForMultipleObjectsEx(0x10u, Handles, 0, v1, 1);
            if ( v2 > 0xC0 )
              break;
            if ( v2 != 192 )
            {
              if ( v2 > 7 )
              {
                v14 = v2 - 8;
                if ( v14 )
                {
                  v15 = v14 - 1;
                  if ( v15 )
                  {
                    v16 = v15 - 1;
                    if ( v16 )
                    {
                      v17 = v16 - 1;
                      if ( v17 )
                      {
                        v18 = v17 - 2;
                        if ( v18 )
                        {
                          v19 = v18 - 1;
                          if ( v19 )
                          {
                            if ( v19 != 1 )
                              goto LABEL_127;
                            EnterCriticalSection(&RouterStateLock);
                            if ( (_DWORD)RouterState )
                            {
                              v20 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
                              goto LABEL_88;
                            }
                            LeaveCriticalSection(&RouterStateLock);
                            if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                              McTemplateU0z_EventWriteTransfer(
                                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                RasRtrmgrTraceInfo,
                                L"WorkerThread: RasAdv Timer event received");
                            HandleRasAdvTimer();
                          }
                          else
                          {
                            EnterCriticalSection(&RouterStateLock);
                            if ( (_DWORD)RouterState )
                            {
                              v22 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
LABEL_106:
                              if ( v22 )
                                goto LABEL_91;
                              v21 = L"WorkerThread: FD_READ while shutting down. Ignoring";
                              goto LABEL_90;
                            }
                            LeaveCriticalSection(&RouterStateLock);
                            HandleMZAPMessages();
                          }
                        }
                        else
                        {
                          EnterCriticalSection(&RouterStateLock);
                          if ( (_DWORD)RouterState )
                          {
                            v20 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
                            goto LABEL_88;
                          }
                          LeaveCriticalSection(&RouterStateLock);
                          HandleMzapTimer();
                        }
                      }
                      else
                      {
                        EnterCriticalSection(&RouterStateLock);
                        if ( (_DWORD)RouterState )
                        {
                          v22 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
                          goto LABEL_106;
                        }
                        LeaveCriticalSection(&RouterStateLock);
                        HandleMcMiscMessages();
                      }
                    }
                    else
                    {
                      EnterCriticalSection(&RouterStateLock);
                      if ( (_DWORD)RouterState )
                      {
                        v22 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
                        goto LABEL_106;
                      }
                      LeaveCriticalSection(&RouterStateLock);
                      RtlAcquireResourceExclusive(&Resource, 1u);
                      HandleSolicitations();
LABEL_116:
                      RtlReleaseResource(&Resource);
                    }
                  }
                  else
                  {
                    EnterCriticalSection(&RouterStateLock);
                    if ( !(_DWORD)RouterState )
                    {
                      LeaveCriticalSection(&RouterStateLock);
                      RtlAcquireResourceExclusive(&Resource, 1u);
                      v23 = Microsoft_Windows_RRASEnableBits;
                      if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                      {
                        McTemplateU0z_EventWriteTransfer(
                          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                          RasRtrmgrTraceInfo,
                          L"WorkerThread: Router Discovery Timer event received");
                        v23 = Microsoft_Windows_RRASEnableBits;
                      }
                      if ( (__int64 *)g_leTimerQueueHead == &g_leTimerQueueHead )
                      {
                        if ( v23 < 0 )
                          McTemplateU0z_EventWriteTransfer(
                            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                            RasRtrmgrTraceInfo,
                            L"WorkerThread: Router Discovery Timer went off but no timer items");
                      }
                      else
                      {
                        HandleRtrDiscTimer();
                      }
                      goto LABEL_116;
                    }
                    v20 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
LABEL_88:
                    if ( !v20 )
                    {
                      v21 = L"WorkerThread: Router discovery timer fired while shutting down. Ignoring";
LABEL_90:
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasRtrmgrTraceInfo,
                        v21);
                    }
LABEL_91:
                    v11 = &RouterStateLock;
LABEL_28:
                    LeaveCriticalSection(v11);
                  }
                }
                else
                {
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                    McTemplateU0z_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasRtrmgrTraceInfo,
                      L"WorkerThread: Routing protocol notification for IPv6 received");
                  HandleRoutingProtocolNotification(0);
                  if ( (g_dwMarkedForStopping & 2) != 0 && (unsigned int)AllRoutingProtocolsStopped(0) )
                  {
                    v31 = -1;
                    if ( (unsigned int)HandleRouteStopEvent(0x57u) )
                    {
                      v1 = v31;
                    }
                    else
                    {
                      g_dwMarkedForStopping &= ~2u;
LABEL_50:
                      RouterManagerCleanup(87);
                      v12 = 87;
LABEL_51:
                      ((void (__fastcall *)(__int64, _QWORD))RouterStopped)(v12, 0);
                      if ( !g_dwLoadedTransports )
                        goto LABEL_141;
                    }
                  }
                }
              }
              else if ( v2 == 7 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                  McTemplateU0z_EventWriteTransfer(
                    &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    RasRtrmgrTraceInfo,
                    L"WorkerThread: Routing protocol notification for IPv4 received");
                HandleRoutingProtocolNotification(1);
                if ( (g_dwMarkedForStopping & 1) != 0 && (unsigned int)AllRoutingProtocolsStopped(1) )
                {
                  v30 = -1;
                  if ( !(unsigned int)HandleRouteStopEvent(0x21u) )
                  {
                    g_dwMarkedForStopping &= ~1u;
LABEL_63:
                    RouterManagerCleanup(33);
                    v12 = 33;
                    goto LABEL_51;
                  }
                  v1 = v30;
                }
              }
              else if ( v2 )
              {
                v3 = v2 - 1;
                if ( !v3 )
                {
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                    McTemplateU0z_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasRtrmgrTraceInfo,
                      L"WorkerThread: Demand Dial IPv6 event received");
                  v13 = 0;
                  goto LABEL_71;
                }
                v4 = v3 - 1;
                if ( v4 )
                {
                  v5 = v4 - 1;
                  if ( v5 )
                  {
                    v6 = v5 - 1;
                    if ( !v6 )
                    {
                      EnterCriticalSection(&g_csFwdState);
                      if ( g_bEnableFwdRequestV4 != g_bFwdEnabledV4 )
                      {
                        *((_QWORD *)&v36 + 1) = g_hForwardingChangeEvent;
                        if ( g_bEnableFwdRequestV4 )
                        {
                          if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                            McTemplateU0z_EventWriteTransfer(
                              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              RasRtrmgrTraceInfo,
                              L"WorkerThread: **--Enabling IPv4 forwarding--**\n\n");
                          v10 = EnableOrDisableIPForwarding(1, 1, (unsigned int)&v35, 1, (__int64)&v27);
                          g_bFwdEnabledV4 = 1;
                        }
                        else
                        {
                          if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                            McTemplateU0z_EventWriteTransfer(
                              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              RasRtrmgrTraceInfo,
                              L"WorkerThread: **--Disabling IPv4 forwarding--**\n\n");
                          v10 = EnableOrDisableIPForwarding(0, 1, (unsigned int)&v35, 1, (__int64)&v27);
                          g_bFwdEnabledV4 = 0;
                        }
                        goto LABEL_36;
                      }
LABEL_27:
                      v11 = &g_csFwdState;
                      goto LABEL_28;
                    }
                    v7 = v6 - 1;
                    if ( !v7 )
                    {
                      EnterCriticalSection(&g_csFwdState);
                      if ( g_bEnableFwdRequestV6 != g_bFwdEnabledV6 )
                      {
                        *((_QWORD *)&v36 + 1) = g_hForwardingChangeEvent;
                        if ( g_bEnableFwdRequestV6 )
                        {
                          if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                            McTemplateU0z_EventWriteTransfer(
                              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              RasRtrmgrTraceInfo,
                              L"WorkerThread: **--Enabling IPv6 forwarding--**\n\n");
                          v10 = EnableOrDisableIPForwarding(1, 0, (unsigned int)&v35, 1, 0);
                          g_bFwdEnabledV6 = 1;
                        }
                        else
                        {
                          if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                            McTemplateU0z_EventWriteTransfer(
                              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              RasRtrmgrTraceInfo,
                              L"WorkerThread: **--Disabling IPv6 forwarding--**\n\n");
                          v10 = EnableOrDisableIPForwarding(0, 0, (unsigned int)&v35, 1, (__int64)&v27);
                          g_bFwdEnabledV6 = 0;
                        }
LABEL_36:
                        if ( v10 )
                        {
                          if ( v10 != 997 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                          {
                            LOWORD(v38) = 0;
                            FormatRRASErrorString(&v38, L"WorkerThread: Error %d from call", v10);
                            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                              McTemplateU0z_EventWriteTransfer(
                                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                RasRtrMgrTraceError,
                                &v38);
                          }
                        }
                        goto LABEL_27;
                      }
                      goto LABEL_27;
                    }
                    if ( v7 != 1 )
                      goto LABEL_127;
                    if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                    {
                      v8 = L"WorkerThread: **--Forwarding change event--**\n\n";
                      v9 = RasRtrmgrTraceInfo;
                      goto LABEL_130;
                    }
                  }
                  else
                  {
                    v28 = -1;
                    if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasRtrmgrTraceInfo,
                        L"WorkerThread: **--STOP Router for v6--**\n\n");
                    if ( (g_dwLoadedTransports & 2) == 0 && !g_dwLoadedTransports )
                      goto LABEL_141;
                    if ( g_bFwdEnabledV6 )
                    {
                      EnterCriticalSection(&g_csFwdState);
                      *((_QWORD *)&v36 + 1) = g_hForwardingChangeEvent;
                      if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                        McTemplateU0z_EventWriteTransfer(
                          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                          RasRtrmgrTraceInfo,
                          L"WorkerThread: **--Disabling IPv6 forwarding--**\n\n");
                      EnableOrDisableIPForwarding(0, 0, (unsigned int)&v35, 1, (__int64)&v27);
                      g_bFwdEnabledV6 = 0;
                      LeaveCriticalSection(&g_csFwdState);
                    }
                    if ( !(unsigned int)HandleRouteStopEvent(0x57u) )
                      goto LABEL_50;
                    v1 = v28;
                    g_dwMarkedForStopping |= 2u;
                  }
                }
                else
                {
                  v29 = -1;
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                    McTemplateU0z_EventWriteTransfer(
                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      RasRtrmgrTraceInfo,
                      L"WorkerThread: **--STOP Router for v4--**\n\n");
                  if ( (g_dwLoadedTransports & 1) == 0 && !g_dwLoadedTransports )
                    goto LABEL_141;
                  if ( g_bFwdEnabledV4 )
                  {
                    EnterCriticalSection(&g_csFwdState);
                    *((_QWORD *)&v36 + 1) = g_hForwardingChangeEvent;
                    if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                      McTemplateU0z_EventWriteTransfer(
                        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        RasRtrmgrTraceInfo,
                        L"WorkerThread: **--Disabling IPv4 forwarding--**\n\n");
                    EnableOrDisableIPForwarding(0, 1, (unsigned int)&v35, 1, (__int64)&v27);
                    g_bFwdEnabledV4 = 0;
                    LeaveCriticalSection(&g_csFwdState);
                  }
                  if ( !(unsigned int)HandleRouteStopEvent(0x21u) )
                    goto LABEL_63;
                  v1 = v29;
                  g_dwMarkedForStopping |= 1u;
                }
              }
              else
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
                  McTemplateU0z_EventWriteTransfer(
                    &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    RasRtrmgrTraceInfo,
                    L"WorkerThread: Demand Dial IPv4 event received");
                v13 = 1;
LABEL_71:
                HandleDemandDialEventAsync(v13);
              }
            }
          }
          if ( v2 == 258 )
            break;
LABEL_127:
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            LOWORD(v38) = 0;
            LastError = GetLastError();
            FormatRRASErrorString(&v38, L"WorkerThread: Wait failed with following error %d", LastError);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v8 = (const wchar_t *)&v38;
              v9 = RasRtrMgrTraceError;
LABEL_130:
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v9, v8);
            }
          }
        }
        v25 = 0;
        v34 = 0;
        if ( (g_dwMarkedForStopping & 1) != 0 )
        {
          v1 = -1;
          v32 = -1;
          if ( (unsigned int)HandleRouteStopEvent(0x21u) )
          {
            v1 = v32;
            v25 = 1;
            v34 = 1;
          }
          else
          {
            g_dwMarkedForStopping &= ~1u;
            RouterManagerCleanup(33);
            ((void (__fastcall *)(__int64))RouterStopped)(33);
            if ( !g_dwLoadedTransports )
              goto LABEL_141;
          }
        }
      }
      while ( (g_dwMarkedForStopping & 2) == 0 );
      v33 = -1;
      if ( !(unsigned int)HandleRouteStopEvent(0x57u) )
        break;
      v1 = v33;
    }
    g_dwMarkedForStopping &= ~2u;
    if ( !v25 )
      v1 = -1;
    RouterManagerCleanup(87);
    ((void (__fastcall *)(__int64))RouterStopped)(87);
  }
  while ( g_dwLoadedTransports );
LABEL_141:
  WaitForAPIsToExitBeforeStopping();
  if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"WorkerThread: Worker thread stopping");
  RouterManagerCleanup(0xFFFFFFFFLL);
  LODWORD(RouterState) = 2;
  if ( g_hOwnModule )
    FreeLibraryAndExitThread(g_hOwnModule, 0);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"WorkerThread: Exit");
  return 0;
}

```

## disassembly

```asm
0x180050e40  push    rbx
0x180050e42  push    rsi
0x180050e43  push    rdi
0x180050e44  push    r12
0x180050e46  push    r13
0x180050e48  push    r14
0x180050e4a  push    r15
0x180050e4c  sub     rsp, 910h
0x180050e53  mov     rax, cs:__security_cookie
0x180050e5a  xor     rax, rsp
0x180050e5d  mov     [rsp+948h+var_48], rax
0x180050e65  mov     r12d, 80h
0x180050e6b  mov     r8d, r12d; Size
0x180050e6e  xor     edx, edx; Val
0x180050e70  lea     rcx, [rsp+948h+Handles]; void *
0x180050e78  call    memset_0
0x180050e7d  xor     r15d, r15d
0x180050e80  mov     [rsp+948h+var_910], r15d
0x180050e85  xorps   xmm0, xmm0
0x180050e88  movups  [rsp+948h+var_8F0], xmm0
0x180050e8d  movups  [rsp+948h+var_8E0], xmm0
0x180050e92  mov     [rsp+948h+var_848], r15d
0x180050e9a  xor     edx, edx; Val
0x180050e9c  mov     r8d, 7FCh; Size
0x180050ea2  lea     rcx, [rsp+948h+var_844]; void *
0x180050eaa  call    memset_0
0x180050eaf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180050eb6  jge     short loc_180050F08
0x180050eb8  mov     word ptr [rsp+948h+var_848], r15w
0x180050ec1  lea     r8, aWorkerthread; "WorkerThread"
0x180050ec8  lea     rdx, aEnteredWs; "Entered: %ws"
0x180050ecf  lea     rcx, [rsp+948h+var_848]
0x180050ed7  call    FormatRRASErrorString
0x180050edc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180050ee3  jge     short loc_180050F08
0x180050ee5  lea     r8, [rsp+948h+var_848]
0x180050eed  lea     rsi, RasRtrmgrTraceInfo
0x180050ef4  mov     rdx, rsi
0x180050ef7  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180050efe  mov     rcx, rbx
0x180050f01  call    McTemplateU0z_EventWriteTransfer
0x180050f06  jmp     short loc_180050F16
0x180050f08  lea     rsi, RasRtrmgrTraceInfo
0x180050f0f  lea     rbx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180050f16  mov     rax, cs:g_hDemandDialEvent
0x180050f1d  mov     [rsp+948h+Handles], rax
0x180050f25  mov     rax, cs:g_hDemandDialEventV6
0x180050f2c  mov     [rsp+948h+var_8C0], rax
0x180050f34  mov     rax, cs:g_hStopRouterEvent
0x180050f3b  mov     [rsp+948h+var_8B8], rax
0x180050f43  mov     rax, cs:g_hStopRouterEventV6
0x180050f4a  mov     [rsp+948h+var_8B0], rax
0x180050f52  mov     rax, cs:g_hSetForwardingEventV4
0x180050f59  mov     [rsp+948h+var_8A8], rax
0x180050f61  mov     rax, cs:g_hSetForwardingEventV6
0x180050f68  mov     [rsp+948h+var_8A0], rax
0x180050f70  mov     rax, cs:g_hForwardingChangeEvent
0x180050f77  mov     [rsp+948h+var_898], rax
0x180050f7f  mov     rax, cs:g_hRoutingProtocolEvent
0x180050f86  mov     [rsp+948h+var_890], rax
0x180050f8e  mov     rax, cs:g_hRoutingProtocolEventV6
0x180050f95  mov     [rsp+948h+var_888], rax
0x180050f9d  mov     rax, cs:g_hRtrDiscTimer
0x180050fa4  mov     [rsp+948h+var_880], rax
0x180050fac  mov     rax, cs:g_hRtrDiscSocketEvent
0x180050fb3  mov     [rsp+948h+var_878], rax
0x180050fbb  mov     rax, cs:g_hMcMiscSocketEvent
0x180050fc2  mov     [rsp+948h+var_870], rax
0x180050fca  mov     rax, cs:g_hMzapTimer
0x180050fd1  mov     [rsp+948h+var_860], rax
0x180050fd9  mov     rax, cs:g_hMzapSocketEvent
0x180050fe0  mov     [rsp+948h+var_858], rax
0x180050fe8  mov     rax, cs:g_hRasAdvTimer
0x180050fef  mov     [rsp+948h+var_850], rax
0x180050ff7  mov     rax, cs:g_hMHbeatSocketEvent
0x180050ffe  mov     [rsp+948h+var_868], rax
0x180051006  or      r14d, 0FFFFFFFFh
0x18005100a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005100e  mov     cs:g_AddrChangeSocketV4, rax
0x180051015  mov     cs:g_AddrChangeSocketV6, rax
0x18005101c  xorps   xmm0, xmm0
0x18005101f  movups  [rsp+948h+var_8F0], xmm0
0x180051024  movups  [rsp+948h+var_8E0], xmm0
0x180051029  lea     r13d, [rax+2]
0x18005102d  lea     rdi, RouterStateLock
0x180051034  mov     [rsp+948h+bAlertable], r13d; bAlertable
0x180051039  mov     r9d, r14d; dwMilliseconds
0x18005103c  xor     r8d, r8d; bWaitAll
0x18005103f  lea     rdx, [rsp+948h+Handles]; lpHandles
0x180051047  lea     ecx, [r8+10h]; nCount
0x18005104b  call    cs:__imp_WaitForMultipleObjectsEx
0x180051051  mov     ecx, 0C0h
0x180051056  cmp     eax, ecx
0x180051058  ja      loc_180051839
0x18005105e  jz      loc_180051834
0x180051064  cmp     eax, 7
0x180051067  ja      loc_180051576
0x18005106d  jz      loc_1800514FE
0x180051073  test    eax, eax
0x180051075  jz      loc_1800514CF
0x18005107b  sub     eax, r13d
0x18005107e  jz      loc_1800514A9
0x180051084  sub     eax, r13d
0x180051087  jz      loc_1800513BB
0x18005108d  sub     eax, r13d
0x180051090  jz      loc_1800512B4
0x180051096  sub     eax, r13d
0x180051099  jz      loc_180051186
0x18005109f  sub     eax, r13d
0x1800510a2  jz      short loc_1800510D0
0x1800510a4  sub     eax, r13d
0x1800510a7  jnz     loc_180051840
0x1800510ad  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800510b4  and     al, r12b
0x1800510b7  mov     [rsp+948h+var_918], al
0x1800510bb  jz      loc_180051834
0x1800510c1  lea     r8, aWorkerthreadFo; "WorkerThread: **--Forwarding change eve"...
0x1800510c8  mov     rdx, rsi
0x1800510cb  jmp     loc_180051887
0x1800510d0  lea     rcx, g_csFwdState; lpCriticalSection
0x1800510d7  call    cs:__imp_EnterCriticalSection
0x1800510dd  mov     ecx, cs:g_bEnableFwdRequestV6
0x1800510e3  cmp     ecx, cs:g_bFwdEnabledV6
0x1800510e9  jz      loc_1800511A1
0x1800510ef  mov     rax, cs:g_hForwardingChangeEvent
0x1800510f6  mov     qword ptr [rsp+948h+var_8E0+8], rax
0x1800510fb  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180051102  test    ecx, ecx
0x180051104  jz      short loc_180051144
0x180051106  and     al, r12b
0x180051109  mov     [rsp+948h+var_918], al
0x18005110d  jz      short loc_180051121
0x18005110f  lea     r8, aWorkerthreadEn; "WorkerThread: **--Enabling IPv6 forward"...
0x180051116  mov     rdx, rsi
0x180051119  mov     rcx, rbx
0x18005111c  call    McTemplateU0z_EventWriteTransfer
0x180051121  mov     qword ptr [rsp+948h+bAlertable], r15
0x180051126  mov     r9d, r13d
0x180051129  lea     r8, [rsp+948h+var_8F0]
0x18005112e  xor     edx, edx
0x180051130  mov     ecx, r13d
0x180051133  call    EnableOrDisableIPForwarding
0x180051138  mov     cs:g_bFwdEnabledV6, r13d
0x18005113f  jmp     loc_180051249
0x180051144  and     al, r12b
0x180051147  mov     [rsp+948h+var_918], al
0x18005114b  jz      short loc_18005115F
0x18005114d  lea     r8, aWorkerthreadDi; "WorkerThread: **--Disabling IPv6 forwar"...
0x180051154  mov     rdx, rsi
0x180051157  mov     rcx, rbx
0x18005115a  call    McTemplateU0z_EventWriteTransfer
0x18005115f  lea     rax, [rsp+948h+var_910]
0x180051164  mov     qword ptr [rsp+948h+bAlertable], rax
0x180051169  mov     r9d, r13d
0x18005116c  lea     r8, [rsp+948h+var_8F0]
0x180051171  xor     edx, edx
0x180051173  xor     ecx, ecx
0x180051175  call    EnableOrDisableIPForwarding
0x18005117a  mov     cs:g_bFwdEnabledV6, r15d
0x180051181  jmp     loc_180051249
0x180051186  lea     rcx, g_csFwdState; lpCriticalSection
0x18005118d  call    cs:__imp_EnterCriticalSection
0x180051193  mov     ecx, cs:g_bEnableFwdRequestV4
0x180051199  cmp     ecx, cs:g_bFwdEnabledV4
0x18005119f  jnz     short loc_1800511B3
0x1800511a1  lea     rcx, g_csFwdState; lpCriticalSection
0x1800511a8  call    cs:__imp_LeaveCriticalSection
0x1800511ae  jmp     loc_180051834
0x1800511b3  mov     rax, cs:g_hForwardingChangeEvent
0x1800511ba  mov     qword ptr [rsp+948h+var_8E0+8], rax
0x1800511bf  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800511c6  test    ecx, ecx
0x1800511c8  jz      short loc_18005120B
0x1800511ca  and     al, r12b
0x1800511cd  mov     [rsp+948h+var_918], al
0x1800511d1  jz      short loc_1800511E5
0x1800511d3  lea     r8, aWorkerthreadEn_0; "WorkerThread: **--Enabling IPv4 forward"...
0x1800511da  mov     rdx, rsi
0x1800511dd  mov     rcx, rbx
0x1800511e0  call    McTemplateU0z_EventWriteTransfer
0x1800511e5  lea     rax, [rsp+948h+var_910]
0x1800511ea  mov     qword ptr [rsp+948h+bAlertable], rax
0x1800511ef  mov     r9d, r13d
0x1800511f2  lea     r8, [rsp+948h+var_8F0]
0x1800511f7  mov     edx, r13d
0x1800511fa  mov     ecx, r13d
0x1800511fd  call    EnableOrDisableIPForwarding
0x180051202  mov     cs:g_bFwdEnabledV4, r13d
0x180051209  jmp     short loc_180051249
0x18005120b  and     al, r12b
0x18005120e  mov     [rsp+948h+var_918], al
0x180051212  jz      short loc_180051226
0x180051214  lea     r8, aWorkerthreadDi_0; "WorkerThread: **--Disabling IPv4 forwar"...
0x18005121b  mov     rdx, rsi
0x18005121e  mov     rcx, rbx
0x180051221  call    McTemplateU0z_EventWriteTransfer
0x180051226  lea     rax, [rsp+948h+var_910]
0x18005122b  mov     qword ptr [rsp+948h+bAlertable], rax
0x180051230  mov     r9d, r13d
0x180051233  lea     r8, [rsp+948h+var_8F0]
0x180051238  mov     edx, r13d
0x18005123b  xor     ecx, ecx
0x18005123d  call    EnableOrDisableIPForwarding
0x180051242  mov     cs:g_bFwdEnabledV4, r15d
0x180051249  mov     r8d, eax
0x18005124c  test    eax, eax
0x18005124e  jz      loc_1800511A1
0x180051254  cmp     eax, 3E5h
0x180051259  jz      loc_1800511A1
0x18005125f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180051266  jz      loc_1800511A1
0x18005126c  mov     eax, r15d
0x18005126f  mov     word ptr [rsp+948h+var_848], ax
0x180051277  lea     rdx, aWorkerthreadEr; "WorkerThread: Error %d from call"
0x18005127e  lea     rcx, [rsp+948h+var_848]
0x180051286  call    FormatRRASErrorString
0x18005128b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180051292  jz      loc_1800511A1
0x180051298  lea     r8, [rsp+948h+var_848]
0x1800512a0  lea     rdx, RasRtrMgrTraceError
0x1800512a7  mov     rcx, rbx
0x1800512aa  call    McTemplateU0z_EventWriteTransfer
0x1800512af  jmp     loc_1800511A1
0x1800512b4  mov     [rsp+948h+var_90C], 0FFFFFFFFh
0x1800512bc  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800512c3  and     al, r12b
0x1800512c6  mov     [rsp+948h+var_918], al
0x1800512ca  jz      short loc_1800512DE
0x1800512cc  lea     r8, aWorkerthreadSt_0; "WorkerThread: **--STOP Router for v6--*"...
0x1800512d3  mov     rdx, rsi
0x1800512d6  mov     rcx, rbx
0x1800512d9  call    McTemplateU0z_EventWriteTransfer
0x1800512de  mov     eax, cs:g_dwLoadedTransports
0x1800512e4  test    al, 2
0x1800512e6  jnz     short loc_1800512F0
0x1800512e8  test    eax, eax
0x1800512ea  jz      loc_18005196B
0x1800512f0  cmp     cs:g_bFwdEnabledV6, r15d
0x1800512f7  jz      short loc_180051363
0x1800512f9  lea     rcx, g_csFwdState; lpCriticalSection
0x180051300  call    cs:__imp_EnterCriticalSection
0x180051306  mov     rax, cs:g_hForwardingChangeEvent
0x18005130d  mov     qword ptr [rsp+948h+var_8E0+8], rax
0x180051312  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180051319  and     al, r12b
0x18005131c  mov     [rsp+948h+var_918], al
0x180051320  jz      short loc_180051334
0x180051322  lea     r8, aWorkerthreadDi; "WorkerThread: **--Disabling IPv6 forwar"...
0x180051329  mov     rdx, rsi
0x18005132c  mov     rcx, rbx
0x18005132f  call    McTemplateU0z_EventWriteTransfer
0x180051334  lea     rax, [rsp+948h+var_910]
0x180051339  mov     qword ptr [rsp+948h+bAlertable], rax
0x18005133e  mov     r9d, r13d
0x180051341  lea     r8, [rsp+948h+var_8F0]
0x180051346  xor     edx, edx
0x180051348  xor     ecx, ecx
0x18005134a  call    EnableOrDisableIPForwarding
0x18005134f  mov     cs:g_bFwdEnabledV6, r15d
0x180051356  lea     rcx, g_csFwdState; lpCriticalSection
0x18005135d  call    cs:__imp_LeaveCriticalSection
0x180051363  lea     rdx, [rsp+948h+var_90C]
0x180051368  mov     ecx, 57h ; 'W'; unsigned int
0x18005136d  call    HandleRouteStopEvent
0x180051372  test    eax, eax
0x180051374  jnz     short loc_1800513A5
0x180051376  mov     ecx, 57h ; 'W'
0x18005137b  call    RouterManagerCleanup
0x180051380  mov     ecx, 57h ; 'W'
0x180051385  xor     edx, edx
0x180051387  mov     rax, cs:RouterStopped
0x18005138e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051393  cmp     cs:g_dwLoadedTransports, r15d
0x18005139a  jz      loc_18005196B
0x1800513a0  jmp     loc_180051834
0x1800513a5  mov     r14d, [rsp+948h+var_90C]
0x1800513aa  mov     [rsp+948h+var_914], r14d
0x1800513af  or      cs:g_dwMarkedForStopping, 2
0x1800513b6  jmp     loc_180051834
0x1800513bb  mov     [rsp+948h+var_908], 0FFFFFFFFh
0x1800513c3  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800513ca  and     al, r12b
0x1800513cd  mov     [rsp+948h+var_918], al
0x1800513d1  jz      short loc_1800513E5
0x1800513d3  lea     r8, aWorkerthreadSt; "WorkerThread: **--STOP Router for v4--*"...
0x1800513da  mov     rdx, rsi
0x1800513dd  mov     rcx, rbx
0x1800513e0  call    McTemplateU0z_EventWriteTransfer
0x1800513e5  mov     eax, cs:g_dwLoadedTransports
0x1800513eb  test    r13b, al
0x1800513ee  jnz     short loc_1800513F8
0x1800513f0  test    eax, eax
0x1800513f2  jz      loc_18005196B
0x1800513f8  cmp     cs:g_bFwdEnabledV4, r15d
0x1800513ff  jz      short loc_18005146C
0x180051401  lea     rcx, g_csFwdState; lpCriticalSection
0x180051408  call    cs:__imp_EnterCriticalSection
0x18005140e  mov     rax, cs:g_hForwardingChangeEvent
0x180051415  mov     qword ptr [rsp+948h+var_8E0+8], rax
0x18005141a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
  ... truncated ...
```
