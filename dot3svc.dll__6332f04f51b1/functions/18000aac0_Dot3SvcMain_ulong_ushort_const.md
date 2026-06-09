# Dot3SvcMain(ulong,ushort const * *)

- ea: `0x18000aac0`
- end: `0x18000b5d5`
- name: `?Dot3SvcMain@@YAXKPEAPEBG@Z`
- size: `2837`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003114`
- `0x180003be4`
- `0x180009558`
- `0x18000a9c0`
- `0x18000aac0`
- `0x18000b71c`
- `0x18000b9fc`
- `0x18000c02c`
- `0x18000c1c8`
- `0x18000c200`
- `0x18000c230`
- `0x18000c2f4`
- `0x18000c3d8`
- `0x18000cbc0`
- `0x180010af0`
- `0x180010ea4`
- `0x180013330`
- `0x18001346c`
- `0x180014100`
- `0x1800142f4`
- `0x18001c780`
- `0x18001ef10`
- `0x180020450`
- `0x180025164`
- `0x180027318`
- `0x180035348`
- `0x18003dc94`
- `0x180040010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000acd5`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000acd5`
- `dot3msm!Dot3MsmInit` at `0x18000b3da`
- `dot3msm!Dot3MsmInit` at `0x18000b3da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ac1e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ac1e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ac95`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ac95`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ae18`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ae18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b56b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ace7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b56b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b549`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b549`
- `MobileNetworking!CreateReadWriteLock` at `0x18000b17c`
- `MobileNetworking!CreateReadWriteLock` at `0x18000b17c`
- `MobileNetworking!HtCreateHandleTable` at `0x18000aba0`
- `MobileNetworking!HtCreateHandleTable` at `0x18000aba0`
- `ext-ms-win-dot3-grouppolicy-l1-1-0!LANGPAInit` at `0x18000b0ab`
- `ext-ms-win-dot3-grouppolicy-l1-1-0!LANGPAInit` at `0x18000b0ab`

## pseudocode

```c
void __fastcall Dot3SvcMain(unsigned int a1, const unsigned __int16 **a2)
{
  DWORD HandleTable; // ebx
  struct _LIST_ENTRY *v5; // rcx
  DWORD LastError; // eax
  __int64 v7; // rdx
  int v8; // ebx
  unsigned int updated; // eax
  __int64 v10; // rdx
  struct _LIST_ENTRY *v11; // rcx
  struct _LIST_ENTRY *v12; // rcx
  DWORD v13; // eax
  const struct wil::FailureInfo *v14; // rdx
  _BYTE v15[232]; // [rsp+40h] [rbp-E8h] BYREF

  g_nThreads = 1;
  qword_180052C78 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ServiceCtlGuid;
  qword_180052C70 = 0;
  WPP_GLOBAL_Control = (struct _LIST_ENTRY *)&WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  if ( wil::details::g_pfnLoggingCallback && (char *)wil::details::g_pfnLoggingCallback != (char *)ResultLoggingCallback )
  {
    memset_0(v15, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v15, v14);
  }
  wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))ResultLoggingCallback;
  McGenEventRegister_EtwEventRegister();
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
  }
  Dot3LogEvent(&Dot3svcStartingEventDesc, 0, 0);
  HandleTable = HtCreateHandleTable(0, 100, &g_hHandleTable);
  if ( HandleTable )
    goto LABEL_46;
  if ( !g_svcHostGlobalData )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 11, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    HandleTable = 13;
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 12, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
  }
  g_hStopServiceEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_hStopServiceEvent )
  {
    LastError = GetLastError();
    HandleTable = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v7 = 13;
LABEL_34:
      WPP_SF_d(v5[1].Flink, v7, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, LastError);
      v5 = WPP_GLOBAL_Control;
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  g_bDisableAuthentication = 0;
  v8 = 0;
  if ( a1 )
  {
    while ( wcscmp_0(a2[v8], L"disableauth") )
    {
      if ( ++v8 >= a1 )
        goto LABEL_26;
    }
    g_bDisableAuthentication = 1;
  }
LABEL_26:
  InitializeCriticalSection(&g_csDot3Migration);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
  }
  g_hLanServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"dot3svc", NhScmNotificationHandler, 0);
  if ( !g_hLanServiceStatusHandle )
  {
    LastError = GetLastError();
    HandleTable = LastError;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v7 = 15;
      goto LABEL_34;
    }
LABEL_35:
    if ( HandleTable )
      goto LABEL_47;
LABEL_183:
    _InterlockedDecrement((volatile signed __int32 *)&g_nThreads);
    return;
  }
  *(_QWORD *)&g_LanServiceStatus.dwCurrentState = 2;
  g_LanServiceStatus.dwServiceType = 32;
  g_LanServiceStatus.dwCheckPoint = 0;
  g_LanServiceStatus.dwWaitHint = 4000;
  *(_QWORD *)&g_LanServiceStatus.dwWin32ExitCode = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 16, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
  }
  updated = LanSvcUpdateStatus();
  HandleTable = updated;
  if ( updated )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 17;
LABEL_45:
      WPP_SF_d(v5[1].Flink, v10, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, updated);
LABEL_46:
      v5 = WPP_GLOBAL_Control;
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 18, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
  }
  updated = StInit();
  HandleTable = updated;
  if ( !updated )
  {
    g_Deinit |= 1u;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 20, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
    }
    updated = LanSvcContextInit();
    HandleTable = updated;
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 21;
        goto LABEL_45;
      }
      goto LABEL_47;
    }
    g_Deinit |= 2u;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 22, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(v11[1].Blink) >= 4u && (BYTE4(v11[1].Blink) & 1) != 0 )
        {
          WPP_SF_(v11[1].Flink, 10, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids);
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(v11[1].Blink) >= 4u
          && (BYTE4(v11[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(v11[1].Flink, 11, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids, 0);
        }
      }
    }
    g_Deinit |= 4u;
    HandleTable = TmInit();
    if ( HandleTable )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 24, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    g_Deinit |= 0x18u;
    g_fLanTimerStarted = 1;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 25, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
    }
    updated = PmInit();
    HandleTable = updated;
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 26;
        goto LABEL_45;
      }
      goto LABEL_47;
    }
    g_Deinit |= 0x20u;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 27, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
    }
    updated = WimInit();
    HandleTable = updated;
    if ( updated )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 28;
        goto LABEL_45;
      }
      goto LABEL_47;
    }
    g_Deinit |= 0x40u;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 29, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
    }
    if ( !(unsigned __int8)IsLANGPADeInitPresent() || (HandleTable = LANGPAInit(&g_Dot3AcmGpFuncTable)) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
LABEL_110:
        g_Deinit |= 0x80u;
        if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(v12[1].Blink) >= 4u
          && (BYTE4(v12[1].Blink) & 1) != 0 )
        {
          WPP_SF_(v12[1].Flink, 31, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
        }
        updated = NhRegisterWmiNotification(1u);
        HandleTable = updated;
        if ( updated )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v10 = 32;
            goto LABEL_45;
          }
        }
        else
        {
          g_Deinit |= 0x100u;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 33, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
          }
          Block = 0;
          updated = CreateReadWriteLock(qword_180052DF0);
          HandleTable = updated;
          if ( updated )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              v10 = 34;
              goto LABEL_45;
            }
          }
          else
          {
            g_Deinit |= 0x2000u;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 35, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
            }
            updated = LanSvcInitRPCServer();
            HandleTable = updated;
            if ( updated )
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                v10 = 36;
                goto LABEL_45;
              }
            }
            else
            {
              g_Deinit |= 0x200u;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control[1].Flink, 37, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
              }
              updated = LanSvcStartRPCServer();
              HandleTable = updated;
              if ( updated )
              {
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  v10 = 38;
                  goto LABEL_45;
                }
              }
              else
              {
                g_Deinit |= 0x400u;
                updated = LanNotifyInit();
                HandleTable = updated;
                if ( updated )
                {
                  v5 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    v10 = 39;
                    goto LABEL_45;
                  }
                }
                else
                {
                  g_Deinit |= 0x800u;
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
                    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                  {
                    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 40, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
                  }
                  g_LanServiceStatus.dwCurrentState = 4;
                  g_LanServiceStatus.dwControlsAccepted = 133;
                  *(_QWORD *)&g_LanServiceStatus.dwCheckPoint = 0;
                  updated = LanSvcUpdateStatus();
                  HandleTable = updated;
                  if ( updated )
                  {
                    v5 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                    {
                      v10 = 41;
                      goto LABEL_45;
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
                      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                    {
                      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 42, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
                    }
                    updated = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_svcHostGlobalData
                               + 24))(
                                &g_hWaitObject,
                                L"dot3svc",
                                g_hStopServiceEvent,
                                LanStopService,
                                0,
                                8);
                    HandleTable = updated;
                    if ( updated )
                    {
                      v5 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                      {
                        v10 = 43;
                        goto LABEL_45;
                      }
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
                        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                      {
                        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 44, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
                      }
                      updated = Dot3MsmInit(&g_AcmFuncTable);
                      HandleTable = updated;
                      if ( updated )
                      {
                        v5 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                        {
                          v10 = 45;
                          goto LABEL_45;
                        }
                      }
                      else
                      {
                        g_Deinit |= 0x1000u;
                        Dot3LogEvent(&Dot3svcStartEventDesc, 0, 0);
                        updated = WimLoadInterfaces();
                        HandleTable = updated;
                        if ( updated )
                        {
                          v5 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                          {
                            v10 = 46;
                            goto LABEL_45;
                          }
                        }
                        else
                        {
                          g_bDisableAuthentication = 0;
                          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
                            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                          {
                            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 47, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
                          }
                          updated = NhRegisterNSINotifications();
                          HandleTable = updated;
                          if ( !updated )
                          {
                            CompleteMigration();
                            Dot3AcmNotifySessionChange();
                            goto LABEL_183;
                          }
                          v5 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                          {
                            v10 = 48;
                            goto LABEL_45;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        goto LABEL_47;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 30, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, HandleTable);
    }
    v12 = WPP_GLOBAL_Control;
    goto LABEL_110;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v10 = 19;
    goto LABEL_45;
  }
LABEL_47:
  if ( g_hWaitObject )
  {
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v5[1].Blink) & 1) != 0 )
      WPP_SF_(v5[1].Flink, 49, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
    *(_QWORD *)&g_LanServiceStatus.dwCurrentState = 3;
    g_LanServiceStatus.dwCheckPoint = 0;
    g_LanServiceStatus.dwWaitHint = 60000;
    g_LanServiceStatus.dwWin32ExitCode = HandleTable;
    LanSvcUpdateStatus();
    _InterlockedDecrement((volatile signed __int32 *)&g_nThreads);
    SetEvent(g_hStopServiceEvent);
  }
  else
  {
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v5[1].Blink) & 1) != 0 )
      WPP_SF_(v5[1].Flink, 50, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids);
    if ( g_hLanServiceStatusHandle )
    {
      *(_QWORD *)&g_LanServiceStatus.dwCurrentState = 3;
      g_LanServiceStatus.dwCheckPoint = 0;
      g_LanServiceStatus.dwWaitHint = 60000;
      g_LanServiceStatus.dwWin32ExitCode = HandleTable;
      LanSvcUpdateStatus();
      LanSvcShutdown();
      WppCleanupUm();
      McGenEventUnregister_EtwEventUnregister();
      g_nThreads = 0;
      g_LanServiceStatus.dwCurrentState = 1;
      g_LanServiceStatus.dwWaitHint = 0;
      LanSvcUpdateStatus();
    }
    else
    {
      if ( g_hStopServiceEvent )
      {
        if ( !CloseHandle(g_hStopServiceEvent)
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          v13 = GetLastError();
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 51, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids, v13);
        }
        g_hStopServiceEvent = 0;
      }
      WppCleanupUm();
      McGenEventUnregister_EtwEventUnregister();
      g_nThreads = 0;
    }
  }
}

```

## disassembly

```asm
0x18000aac0  push    rbx
0x18000aac2  push    rbp
0x18000aac3  push    rsi
0x18000aac4  push    rdi
0x18000aac5  push    r12
0x18000aac7  push    r13
0x18000aac9  push    r14
0x18000aacb  push    r15
0x18000aacd  sub     rsp, 0E8h
0x18000aad4  mov     ebp, 1
0x18000aad9  mov     rsi, rdx
0x18000aadc  mov     cs:?g_nThreads@@3KA, ebp; ulong g_nThreads
0x18000aae2  mov     edi, ecx
0x18000aae4  lea     rax, WPP_ThisDir_CTLGUID_ServiceCtlGuid
0x18000aaeb  mov     cs:qword_180052C78, rbp
0x18000aaf2  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000aaf9  xor     r14d, r14d
0x18000aafc  lea     rax, WPP_MAIN_CB
0x18000ab03  mov     cs:qword_180052C70, r14
0x18000ab0a  mov     cs:WPP_GLOBAL_Control, rax
0x18000ab11  mov     cs:WPP_MAIN_CB, r14
0x18000ab18  call    WppInitUm
0x18000ab1d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ab24  lea     rcx, ?ResultLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z; ResultLoggingCallback(wil::FailureInfo const &)
0x18000ab2b  test    rax, rax
0x18000ab2e  jz      short loc_18000AB39
0x18000ab30  cmp     rax, rcx
0x18000ab33  jnz     loc_18000B5B8
0x18000ab39  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18000ab40  call    McGenEventRegister_EtwEventRegister
0x18000ab45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab4c  lea     r15, WPP_GLOBAL_Control
0x18000ab53  lea     r12, WPP_7c106312fff73e774f9cb9a41d296a0a_Traceguids
0x18000ab5a  mov     r13d, 4
0x18000ab60  cmp     rcx, r15
0x18000ab63  jz      short loc_18000AB81
0x18000ab65  cmp     [rcx+19h], r13b
0x18000ab69  jb      short loc_18000AB81
0x18000ab6b  test    [rcx+1Ch], bpl
0x18000ab6f  jz      short loc_18000AB81
0x18000ab71  mov     rcx, [rcx+10h]
0x18000ab75  lea     edx, [r13+6]
0x18000ab79  mov     r8, r12
0x18000ab7c  call    WPP_SF_
0x18000ab81  xor     r8d, r8d; struct _EVENT_DATA_DESCRIPTOR *
0x18000ab84  lea     rcx, Dot3svcStartingEventDesc; struct _EVENT_DESCRIPTOR *
0x18000ab8b  xor     edx, edx; unsigned int
0x18000ab8d  call    ?Dot3LogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z; Dot3LogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x18000ab92  lea     r8, ?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18000ab99  mov     edx, 64h ; 'd'
0x18000ab9e  xor     ecx, ecx
0x18000aba0  call    cs:__imp_HtCreateHandleTable
0x18000aba6  mov     ebx, eax
0x18000aba8  test    eax, eax
0x18000abaa  jnz     loc_18000ADB3
0x18000abb0  cmp     cs:?g_svcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, r14; _SVCHOST_GLOBAL_DATA * g_svcHostGlobalData
0x18000abb7  jnz     short loc_18000ABEB
0x18000abb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abc0  cmp     rcx, r15
0x18000abc3  jz      short loc_18000ABE1
0x18000abc5  test    [rcx+1Ch], bpl
0x18000abc9  jz      short loc_18000ABE1
0x18000abcb  mov     rcx, [rcx+10h]
0x18000abcf  lea     edx, [rax+0Bh]
0x18000abd2  mov     r8, r12
0x18000abd5  call    WPP_SF_
0x18000abda  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abe1  mov     ebx, 0Dh
0x18000abe6  jmp     loc_18000ADBA
0x18000abeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abf2  cmp     rcx, r15
0x18000abf5  jz      short loc_18000AC14
0x18000abf7  cmp     [rcx+19h], r13b
0x18000abfb  jb      short loc_18000AC14
0x18000abfd  test    [rcx+1Ch], bpl
0x18000ac01  jz      short loc_18000AC14
0x18000ac03  mov     rcx, [rcx+10h]
0x18000ac07  mov     edx, 0Ch
0x18000ac0c  mov     r8, r12
0x18000ac0f  call    WPP_SF_
0x18000ac14  xor     r9d, r9d; lpName
0x18000ac17  xor     r8d, r8d; bInitialState
0x18000ac1a  xor     edx, edx; bManualReset
0x18000ac1c  xor     ecx, ecx; lpEventAttributes
0x18000ac1e  call    cs:__imp_CreateEventW
0x18000ac24  mov     cs:?g_hStopServiceEvent@@3PEAXEA, rax; void * g_hStopServiceEvent
0x18000ac2b  test    rax, rax
0x18000ac2e  jnz     short loc_18000AC5C
0x18000ac30  call    cs:__imp_GetLastError
0x18000ac36  mov     ebx, eax
0x18000ac38  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac3f  cmp     rcx, r15
0x18000ac42  jz      loc_18000AD1C
0x18000ac48  test    [rcx+1Ch], bpl
0x18000ac4c  jz      loc_18000AD1C
0x18000ac52  mov     edx, 0Dh
0x18000ac57  jmp     loc_18000AD06
0x18000ac5c  mov     cs:?g_bDisableAuthentication@@3HA, r14d; int g_bDisableAuthentication
0x18000ac63  mov     ebx, r14d
0x18000ac66  test    edi, edi
0x18000ac68  jz      short loc_18000AC8E
0x18000ac6a  mov     ecx, ebx
0x18000ac6c  lea     rdx, aDisableauth; "disableauth"
0x18000ac73  mov     rcx, [rsi+rcx*8]; String1
0x18000ac77  call    wcscmp_0
0x18000ac7c  test    eax, eax
0x18000ac7e  jz      short loc_18000AC88
0x18000ac80  add     ebx, ebp
0x18000ac82  cmp     ebx, edi
0x18000ac84  jb      short loc_18000AC6A
0x18000ac86  jmp     short loc_18000AC8E
0x18000ac88  mov     cs:?g_bDisableAuthentication@@3HA, ebp; int g_bDisableAuthentication
0x18000ac8e  lea     rcx, ?g_csDot3Migration@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ac95  call    cs:__imp_InitializeCriticalSection
0x18000ac9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aca2  cmp     rcx, r15
0x18000aca5  jz      short loc_18000ACC4
0x18000aca7  cmp     [rcx+19h], r13b
0x18000acab  jb      short loc_18000ACC4
0x18000acad  test    [rcx+1Ch], bpl
0x18000acb1  jz      short loc_18000ACC4
0x18000acb3  mov     rcx, [rcx+10h]
0x18000acb7  mov     edx, 0Eh
0x18000acbc  mov     r8, r12
0x18000acbf  call    WPP_SF_
0x18000acc4  xor     r8d, r8d; lpContext
0x18000acc7  lea     rdx, ?NhScmNotificationHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18000acce  lea     rcx, ServiceName; "dot3svc"
0x18000acd5  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000acdb  mov     cs:?g_hLanServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hLanServiceStatusHandle
0x18000ace2  test    rax, rax
0x18000ace5  jnz     short loc_18000AD29
0x18000ace7  call    cs:__imp_GetLastError
0x18000aced  mov     ebx, eax
0x18000acef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000acf6  cmp     rcx, r15
0x18000acf9  jz      short loc_18000AD1C
0x18000acfb  test    [rcx+1Ch], bpl
0x18000acff  jz      short loc_18000AD1C
0x18000ad01  mov     edx, 0Fh
0x18000ad06  mov     rcx, [rcx+10h]
0x18000ad0a  mov     r9d, eax
0x18000ad0d  mov     r8, r12
0x18000ad10  call    WPP_SF_d
0x18000ad15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad1c  test    ebx, ebx
0x18000ad1e  jz      loc_18000B4BB
0x18000ad24  jmp     loc_18000ADBA
0x18000ad29  mov     edi, 20h ; ' '
0x18000ad2e  mov     qword ptr cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_LanServiceStatus ...
0x18000ad39  mov     cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, edi; _SERVICE_STATUS g_LanServiceStatus ...
0x18000ad3f  mov     cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14d; _SERVICE_STATUS g_LanServiceStatus ...
0x18000ad46  mov     cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0FA0h; _SERVICE_STATUS g_LanServiceStatus ...
0x18000ad50  mov     qword ptr cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r14; _SERVICE_STATUS g_LanServiceStatus ...
0x18000ad57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad5e  cmp     rcx, r15
0x18000ad61  jz      short loc_18000AD7E
0x18000ad63  cmp     [rcx+19h], r13b
0x18000ad67  jb      short loc_18000AD7E
0x18000ad69  test    [rcx+1Ch], bpl
0x18000ad6d  jz      short loc_18000AD7E
0x18000ad6f  mov     rcx, [rcx+10h]
0x18000ad73  lea     edx, [rdi-10h]
0x18000ad76  mov     r8, r12
0x18000ad79  call    WPP_SF_
0x18000ad7e  call    ?LanSvcUpdateStatus@@YAKXZ; LanSvcUpdateStatus(void)
0x18000ad83  mov     ebx, eax
0x18000ad85  test    eax, eax
0x18000ad87  jz      loc_18000AE23
0x18000ad8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad94  cmp     rcx, r15
0x18000ad97  jz      short loc_18000ADBA
0x18000ad99  test    [rcx+1Ch], bpl
0x18000ad9d  jz      short loc_18000ADBA
0x18000ad9f  mov     edx, 11h
0x18000ada4  mov     rcx, [rcx+10h]
0x18000ada8  mov     r9d, eax
0x18000adab  mov     r8, r12
0x18000adae  call    WPP_SF_d
0x18000adb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adba  cmp     cs:?g_hWaitObject@@3PEAXEA, r14; void * g_hWaitObject
0x18000adc1  jz      loc_18000B4C7
0x18000adc7  cmp     rcx, r15
0x18000adca  jz      short loc_18000ADE3
0x18000adcc  test    [rcx+1Ch], bpl
0x18000add0  jz      short loc_18000ADE3
0x18000add2  mov     rcx, [rcx+10h]
0x18000add6  mov     edx, 31h ; '1'
0x18000addb  mov     r8, r12
0x18000adde  call    WPP_SF_
0x18000ade3  mov     qword ptr cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_LanServiceStatus ...
0x18000adee  mov     cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14d; _SERVICE_STATUS g_LanServiceStatus ...
0x18000adf5  mov     cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS g_LanServiceStatus ...
0x18000adff  mov     cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS g_LanServiceStatus ...
0x18000ae05  call    ?LanSvcUpdateStatus@@YAKXZ; LanSvcUpdateStatus(void)
0x18000ae0a  lock dec cs:?g_nThreads@@3KA; ulong g_nThreads
0x18000ae11  mov     rcx, cs:?g_hStopServiceEvent@@3PEAXEA; hEvent
0x18000ae18  call    cs:__imp_SetEvent
0x18000ae1e  jmp     loc_18000B5A4
0x18000ae23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae2a  cmp     rcx, r15
0x18000ae2d  jz      short loc_18000AE4C
0x18000ae2f  cmp     [rcx+19h], r13b
0x18000ae33  jb      short loc_18000AE4C
0x18000ae35  test    [rcx+1Ch], bpl
0x18000ae39  jz      short loc_18000AE4C
0x18000ae3b  mov     rcx, [rcx+10h]
0x18000ae3f  mov     edx, 12h
0x18000ae44  mov     r8, r12
0x18000ae47  call    WPP_SF_
0x18000ae4c  call    ?StInit@@YAKXZ; StInit(void)
0x18000ae51  mov     ebx, eax
0x18000ae53  test    eax, eax
0x18000ae55  jz      short loc_18000AE7B
0x18000ae57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae5e  cmp     rcx, r15
0x18000ae61  jz      loc_18000ADBA
0x18000ae67  test    [rcx+1Ch], bpl
0x18000ae6b  jz      loc_18000ADBA
0x18000ae71  mov     edx, 13h
0x18000ae76  jmp     loc_18000ADA4
0x18000ae7b  or      cs:?g_Deinit@@3W4DeinitFlags@@A, ebp; DeinitFlags g_Deinit
0x18000ae81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae88  cmp     rcx, r15
0x18000ae8b  jz      short loc_18000AEAA
0x18000ae8d  cmp     [rcx+19h], r13b
0x18000ae91  jb      short loc_18000AEAA
0x18000ae93  test    [rcx+1Ch], bpl
0x18000ae97  jz      short loc_18000AEAA
0x18000ae99  mov     rcx, [rcx+10h]
0x18000ae9d  mov     edx, 14h
0x18000aea2  mov     r8, r12
0x18000aea5  call    WPP_SF_
0x18000aeaa  call    ?LanSvcContextInit@@YAKXZ; LanSvcContextInit(void)
0x18000aeaf  mov     ebx, eax
0x18000aeb1  test    eax, eax
0x18000aeb3  jz      short loc_18000AED9
0x18000aeb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aebc  cmp     rcx, r15
0x18000aebf  jz      loc_18000ADBA
0x18000aec5  test    [rcx+1Ch], bpl
0x18000aec9  jz      loc_18000ADBA
0x18000aecf  mov     edx, 15h
0x18000aed4  jmp     loc_18000ADA4
0x18000aed9  or      cs:?g_Deinit@@3W4DeinitFlags@@A, 2; DeinitFlags g_Deinit
0x18000aee0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aee7  cmp     rcx, r15
0x18000aeea  jz      short loc_18000AF66
0x18000aeec  cmp     [rcx+19h], r13b
0x18000aef0  jb      short loc_18000AF10
0x18000aef2  test    [rcx+1Ch], bpl
0x18000aef6  jz      short loc_18000AF10
0x18000aef8  mov     rcx, [rcx+10h]
0x18000aefc  mov     edx, 16h
0x18000af01  mov     r8, r12
0x18000af04  call    WPP_SF_
0x18000af09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af10  cmp     rcx, r15
0x18000af13  jz      short loc_18000AF66
0x18000af15  cmp     [rcx+19h], r13b
0x18000af19  jb      short loc_18000AF3D
0x18000af1b  test    [rcx+1Ch], bpl
0x18000af1f  jz      short loc_18000AF3D
0x18000af21  mov     rcx, [rcx+10h]
0x18000af25  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x18000af2c  mov     edx, 0Ah
0x18000af31  call    WPP_SF_
0x18000af36  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af3d  cmp     rcx, r15
0x18000af40  jz      short loc_18000AF66
0x18000af42  cmp     [rcx+19h], r13b
0x18000af46  jb      short loc_18000AF66
0x18000af48  test    [rcx+1Ch], bpl
0x18000af4c  jz      short loc_18000AF66
0x18000af4e  mov     rcx, [rcx+10h]
0x18000af52  lea     r8, WPP_aec9d19e1f3e379af4fc1a482b2abd1d_Traceguids
0x18000af59  mov     edx, 0Bh
0x18000af5e  xor     r9d, r9d
0x18000af61  call    WPP_SF_d
0x18000af66  or      cs:?g_Deinit@@3W4DeinitFlags@@A, r13d; DeinitFlags g_Deinit
0x18000af6d  call    ?TmInit@@YAKXZ; TmInit(void)
0x18000af72  mov     ebx, eax
0x18000af74  test    eax, eax
0x18000af76  jz      short loc_18000AFA8
0x18000af78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af7f  cmp     rcx, r15
0x18000af82  jz      loc_18000ADBA
0x18000af88  test    [rcx+1Ch], bpl
0x18000af8c  jz      loc_18000ADBA
0x18000af92  mov     rcx, [rcx+10h]
0x18000af96  mov     edx, 18h
0x18000af9b  mov     r8, r12
0x18000af9e  call    WPP_SF_
0x18000afa3  jmp     loc_18000ADB3
0x18000afa8  or      cs:?g_Deinit@@3W4DeinitFlags@@A, 18h; DeinitFlags g_Deinit
0x18000afaf  mov     cs:?g_fLanTimerStarted@@3HA, ebp; int g_fLanTimerStarted
0x18000afb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afbc  cmp     rcx, r15
0x18000afbf  jz      short loc_18000AFDE
0x18000afc1  cmp     [rcx+19h], r13b
  ... truncated ...
```
