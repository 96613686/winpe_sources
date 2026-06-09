# InitializeServiceGlobals

- ea: `0x140024994`
- end: `0x14002518d`
- name: `InitializeServiceGlobals`
- size: `2041`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400236a0`

## callees

- `0x1400023cc`
- `0x140002906`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x14000e888`
- `0x140024994`
- `0x140025a0c`
- `0x140025a4c`
- `0x140025a8c`
- `0x140025acc`
- `0x1400508b4`
- `0x140067168`
- `0x140070b0c`
- `0x140075fb4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140024c39`
- `KERNEL32!GetLastError` at `0x140024c64`
- `KERNEL32!GetLastError` at `0x140024cc7`
- `KERNEL32!GetLastError` at `0x140024d16`
- `KERNEL32!GetLastError` at `0x140024c39`
- `KERNEL32!GetLastError` at `0x140024c64`
- `KERNEL32!GetLastError` at `0x140024cc7`
- `KERNEL32!GetLastError` at `0x140024d16`
- `KERNEL32!SetLastError` at `0x140025150`
- `KERNEL32!SetLastError` at `0x140025150`
- `KERNEL32!CreateEventW` at `0x140024c52`
- `KERNEL32!CreateEventW` at `0x140024cb5`
- `KERNEL32!CreateEventW` at `0x140024c52`
- `KERNEL32!CreateEventW` at `0x140024cb5`
- `KERNEL32!CreateSemaphoreW` at `0x140024d04`
- `KERNEL32!CreateSemaphoreW` at `0x140024d04`
- `KERNEL32!InitializeCriticalSection` at `0x140024d53`
- `KERNEL32!InitializeCriticalSection` at `0x140024d60`
- `KERNEL32!InitializeCriticalSection` at `0x140024d6d`
- `KERNEL32!InitializeCriticalSection` at `0x140024d7a`
- `KERNEL32!InitializeCriticalSection` at `0x140024d87`
- `KERNEL32!InitializeCriticalSection` at `0x140024d94`
- `KERNEL32!InitializeCriticalSection` at `0x140024da1`
- `KERNEL32!InitializeCriticalSection` at `0x140024dae`
- `KERNEL32!InitializeCriticalSection` at `0x140024dbb`
- `KERNEL32!InitializeCriticalSection` at `0x140024dc8`
- `KERNEL32!InitializeCriticalSection` at `0x140024dd5`
- `KERNEL32!InitializeCriticalSection` at `0x140024de2`
- `KERNEL32!InitializeCriticalSection` at `0x140024def`
- `KERNEL32!InitializeCriticalSection` at `0x140024dfc`
- `KERNEL32!InitializeCriticalSection` at `0x140024d53`
- `KERNEL32!InitializeCriticalSection` at `0x140024d60`
- `KERNEL32!InitializeCriticalSection` at `0x140024d6d`
- `KERNEL32!InitializeCriticalSection` at `0x140024d7a`
- `KERNEL32!InitializeCriticalSection` at `0x140024d87`
- `KERNEL32!InitializeCriticalSection` at `0x140024d94`
- `KERNEL32!InitializeCriticalSection` at `0x140024da1`
- `KERNEL32!InitializeCriticalSection` at `0x140024dae`
- `KERNEL32!InitializeCriticalSection` at `0x140024dbb`
- `KERNEL32!InitializeCriticalSection` at `0x140024dc8`
- `KERNEL32!InitializeCriticalSection` at `0x140024dd5`
- `KERNEL32!InitializeCriticalSection` at `0x140024de2`
- `KERNEL32!InitializeCriticalSection` at `0x140024def`
- `KERNEL32!InitializeCriticalSection` at `0x140024dfc`

## string_xrefs

- `0x14002516c`: `CFaxConfiguration::CFaxConfiguration - StringDup on lpRegKeyName failed`
- `0x140024bcf`: `Microsoft-Windows-Fax-Common-DeviceLimit`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 InitializeServiceGlobals()
{
  CMapDeviceId *v0; // rbx
  __int64 i; // rcx
  __int64 j; // rcx
  __int64 k; // rcx
  unsigned int v4; // ebx
  DWORD LastError; // ebx
  DWORD v6; // eax
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  __int64 v10; // rax
  _DWORD *v11; // rax
  CFaxAccountList *v12; // rax
  __int64 v13; // rcx
  CFaxAccountList *v14; // rbx
  _QWORD *v15; // rax
  CClientsMap *v16; // rax
  CClientsMap *v17; // rbx
  _QWORD *v18; // rdi
  _QWORD *v19; // rax
  void *v20; // rbx
  COutboundRoutingGroupsMap *v21; // rax
  COutboundRoutingGroupsMap *v22; // rbx
  COutboundRulesMap *v23; // rax
  COutboundRulesMap *v24; // rbx
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-20h] BYREF

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  g_pFaxPerfCounters = 0;
  qword_1400A1838 = 0;
  dword_1400A1840 = 0;
  dword_1400A1844 = 0;
  *(_DWORD *)&Data = 0;
  memset_0(&g_ReceiptsConfig, 0, 0x50u);
  g_ReceiptsConfig = 80;
  g_ActivityLoggingConfig = 0;
  *(_OWORD *)&fDesiredAccess = 0;
  qword_1400A1630 = 0;
  g_ActivityLoggingConfig = 40;
  *(_OWORD *)((char *)&g_ServerActivity + 4) = 0;
  *(__int128 *)((char *)&xmmword_14009DBA0 + 4) = 0;
  g_ServerActivity = 36;
  g_hDispatchEventsCompPort = 0;
  g_hSendEventsCompPort = 0;
  g_dwlClientID = 0;
  g_FaxQuotaWarn = 0;
  g_hArchiveQuotaWarningEvent = 0;
  g_dwConnectionCount = 0;
  g_hInboxActivityLogFile = (HANDLE)-1LL;
  g_hOutboxActivityLogFile = (HANDLE)-1LL;
  g_fLogStringTableInit = 0;
  g_dwQueueCount = 0;
  g_hJobQueueEvent = 0;
  g_ScanQueueAfterTimeout = 0;
  g_dwReceiveDevicesCount = 0;
  g_bDelaySuicideAttempt = 0;
  g_bServiceCanSuicide = 1;
  g_dwCountRoutingMethods = 0;
  g_pLineCountryList = 0;
  g_dwLastUniqueId = 0;
  g_bServiceIsDown = 0;
  g_TapiCompletionPort = 0;
  g_hLineApp = 0;
  ServiceStatus.dwServiceType = 48;
  ServiceStatus.dwCurrentState = 2;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  g_hRPCListeningThread = 0;
  g_lServiceThreadsCount = 0;
  g_hThreadCountEvent = 0;
  for ( i = 0; i != 14; ++i )
    qword_14009D688[4 * i] = 0;
  for ( j = 0; j != 50; ++j )
    qword_14009D048[4 * j] = 0;
  for ( k = 0; k != 59; ++k )
    qword_14009DBC8[2 * k] = 0;
  g_StatusCompletionPortHandle = 0;
  g_pFaxSD = 0;
  g_dwDeviceCount = 0;
  g_dwDeviceEnabledCount = 0;
  if ( v0 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 2) != 0 && *((_BYTE *)v0 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v0 + 2), 17, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
  if ( (int)GetLicensingPolicyValue((wchar_t *)L"Microsoft-Windows-Fax-Common-DeviceLimit") < 0 )
  {
    v4 = 1;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
    }
  }
  else
  {
    v4 = 0;
  }
  g_dwDeviceEnabledLimit = v4;
  g_hTapiWorkerThread = 0;
  g_hJobQueueThread = 0;
  g_hResource = (LPCVOID)GetResInst();
  if ( !g_hResource )
  {
    LastError = GetLastError();
    goto LABEL_74;
  }
  g_hServiceShutDownEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hServiceShutDownEvent )
  {
    v6 = GetLastError();
    LastError = v6;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v8 = 14;
    goto LABEL_28;
  }
  g_hSCMServiceShutDownEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hSCMServiceShutDownEvent )
  {
    v6 = GetLastError();
    LastError = v6;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v8 = 15;
    goto LABEL_28;
  }
  g_hServiceIsDownSemaphore = CreateSemaphoreW(0, 0, 2, 0);
  if ( !g_hServiceIsDownSemaphore )
  {
    v6 = GetLastError();
    LastError = v6;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v8 = 16;
LABEL_28:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v6);
    goto LABEL_74;
  }
  InitializeCriticalSection(&g_CsConfig);
  InitializeCriticalSection(&g_CsInboundActivityLogging);
  InitializeCriticalSection(&g_CsOutboundActivityLogging);
  InitializeCriticalSection(&g_CsJob);
  InitializeCriticalSection(&g_CsQueue);
  InitializeCriticalSection(&g_CsPerfCounters);
  InitializeCriticalSection(&g_CsSecurity);
  InitializeCriticalSection(&g_csUniqueQueueFile);
  InitializeCriticalSection(&g_CsLine);
  InitializeCriticalSection(&g_CsRouting);
  InitializeCriticalSection(&g_CsServiceThreads);
  InitializeCriticalSection(&g_CsHandleTable);
  InitializeCriticalSection(&g_CsActivity);
  InitializeCriticalSection(&g_CsClients);
  qword_1400A1358 = (__int64)&g_DeviceProvidersListHead;
  g_DeviceProvidersListHead = (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead;
  qword_1400A1468 = (__int64)&g_HandleTableListHead;
  g_HandleTableListHead = (struct _HANDLE_ENTRY *)&g_HandleTableListHead;
  qword_1400A14C8 = (__int64)&g_JobListHead;
  g_JobListHead.Flink = &g_JobListHead;
  g_QueueListHead.Blink = &g_QueueListHead;
  g_QueueListHead.Flink = &g_QueueListHead;
  qword_1400A1550 = (__int64)&g_lstRoutingExtensions;
  g_lstRoutingExtensions = &g_lstRoutingExtensions;
  qword_1400A1588 = (__int64)&g_lstRoutingMethods;
  g_lstRoutingMethods.Flink = &g_lstRoutingMethods;
  qword_1400A1748 = (__int64)&g_TapiLinesListHead;
  g_TapiLinesListHead = (DWORD_PTR)&g_TapiLinesListHead;
  qword_1400A1788 = (__int64)&g_RemovedTapiLinesListHead;
  g_RemovedTapiLinesListHead = (struct _LINE_INFO *)&g_RemovedTapiLinesListHead;
  g_pFaxConfig = 0;
  g_pFaxArchiving = 0;
  g_pClientsMap = 0;
  g_pNotificationMap = 0;
  g_pTAPIDevicesIdsMap = 0;
  g_pGroupsMap = 0;
  g_pRulesMap = 0;
  g_pAccountList = 0;
  g_pAccountDefaults = 0;
  v9 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    *v9 = &CFaxConfiguration::`vftable';
    v9[6] = 0;
    v9[7] = 0;
    v9[12] = 0;
    *((_DWORD *)v9 + 32) = 0;
    v10 = StringDup(L"Software\\Microsoft\\Fax");
    v9[15] = v10;
    if ( !v10 )
    {
      std::runtime_error::runtime_error(
        (std::runtime_error *)pExceptionObject,
        "CFaxConfiguration::CFaxConfiguration - StringDup on lpRegKeyName failed");
      throw (std::runtime_error *)pExceptionObject;
    }
  }
  else
  {
    v9 = 0;
  }
  g_pFaxConfig = (CFaxConfiguration *)v9;
  if ( v9 )
  {
    v11 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v11 )
    {
      *v11 = 0;
      g_pFaxArchiving = v11;
      v12 = (CFaxAccountList *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v12;
      if ( v12 )
      {
        *(_QWORD *)v12 = 0;
        *((_QWORD *)v12 + 1) = 0;
        *(_QWORD *)v12 = std::_List_alloc<0,std::_List_base_types<unsigned long>>::_Buynode0(v13, 0, 0);
        *((_DWORD *)v14 + 4) = 0;
      }
      else
      {
        v14 = 0;
      }
      g_pAccountList = v14;
      if ( v14 )
      {
        v15 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v15 )
        {
          *v15 = &CFaxAccount::`vftable';
          v15[1] = 0;
          v15[2] = 0;
          *((_DWORD *)v15 + 6) = 0;
          g_pAccountDefaults = (CFaxAccount *)v15;
          v16 = (CClientsMap *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          v17 = v16;
          if ( v16 )
          {
            *(_QWORD *)v16 = 0;
            *((_QWORD *)v16 + 1) = 0;
            *(_QWORD *)v16 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CClientID const,CClient>>>::_Buyheadnode();
          }
          else
          {
            v17 = 0;
          }
          g_pClientsMap = v17;
          if ( v17 )
          {
            v18 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v18 )
            {
              *v18 = &CNotificationMap::`vftable';
              v18[1] = 0;
              *((_BYTE *)v18 + 56) = 0;
              v18[8] = 0;
              v18[9] = 0;
              v18[8] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CDeviceAndGUID const,CSinksList *>>>::_Buyheadnode();
              *((_DWORD *)v18 + 20) = 0;
            }
            else
            {
              v18 = 0;
            }
            g_pNotificationMap = (struct CNotificationMap *)v18;
            if ( v18 )
            {
              v19 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
              v20 = v19;
              if ( v19 )
              {
                *v19 = 0;
                v19[1] = 0;
                *v19 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,unsigned long>>>::_Buyheadnode();
              }
              else
              {
                v20 = 0;
              }
              g_pTAPIDevicesIdsMap = v20;
              if ( v20 )
              {
                v21 = (COutboundRoutingGroupsMap *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                v22 = v21;
                if ( v21 )
                {
                  *(_QWORD *)v21 = 0;
                  *((_QWORD *)v21 + 1) = 0;
                  *(_QWORD *)v21 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,COutboundRoutingGroup>>>::_Buyheadnode();
                }
                else
                {
                  v22 = 0;
                }
                g_pGroupsMap = v22;
                if ( v22 )
                {
                  v23 = (COutboundRulesMap *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                  v24 = v23;
                  if ( v23 )
                  {
                    *(_QWORD *)v23 = 0;
                    *((_QWORD *)v23 + 1) = 0;
                    *(_QWORD *)v23 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CDeviceAndGUID const,CSinksList *>>>::_Buyheadnode();
                  }
                  else
                  {
                    v24 = 0;
                  }
                  g_pRulesMap = v24;
                  if ( v24 )
                    return 1;
                }
              }
            }
          }
        }
        else
        {
          g_pAccountDefaults = 0;
        }
      }
    }
    else
    {
      g_pFaxArchiving = 0;
    }
  }
  LastError = 8;
LABEL_74:
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x140024994  mov     [rsp-28h+arg_10], rbx
0x140024999  push    rbp
0x14002499a  push    rsi
0x14002499b  push    rdi
0x14002499c  push    r14
0x14002499e  push    r15
0x1400249a0  mov     rbp, rsp
0x1400249a3  sub     rsp, 40h
0x1400249a7  lea     rsi, WPP_GLOBAL_Control
0x1400249ae  lea     r15, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400249b5  mov     rbx, cs:WPP_GLOBAL_Control
0x1400249bc  cmp     rbx, rsi
0x1400249bf  jz      short loc_1400249E5
0x1400249c1  test    byte ptr [rbx+1Ch], 4
0x1400249c5  jz      short loc_1400249E5
0x1400249c7  cmp     byte ptr [rbx+19h], 5
0x1400249cb  jb      short loc_1400249E5
0x1400249cd  mov     edx, 0Dh
0x1400249d2  mov     r8, r15
0x1400249d5  mov     rcx, [rbx+10h]
0x1400249d9  call    WPP_SF_
0x1400249de  mov     rbx, cs:WPP_GLOBAL_Control
0x1400249e5  xor     r14d, r14d
0x1400249e8  mov     cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA, r14; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x1400249ef  mov     cs:qword_1400A1838, r14
0x1400249f6  mov     cs:dword_1400A1840, r14d
0x1400249fd  mov     cs:dword_1400A1844, r14d
0x140024a04  mov     cs:Data, r14d
0x140024a0b  lea     edi, [r14+50h]
0x140024a0f  mov     r8d, edi; Size
0x140024a12  xor     edx, edx; Val
0x140024a14  lea     rcx, ?g_ReceiptsConfig@@3U_FAX_SERVER_RECEIPTS_CONFIGW@@A; void *
0x140024a1b  call    memset_0
0x140024a20  mov     cs:?g_ReceiptsConfig@@3U_FAX_SERVER_RECEIPTS_CONFIGW@@A, edi; _FAX_SERVER_RECEIPTS_CONFIGW g_ReceiptsConfig
0x140024a26  xorps   xmm0, xmm0
0x140024a29  xor     eax, eax
0x140024a2b  movups  cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A, xmm0; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x140024a32  movups  cs:fDesiredAccess, xmm0
0x140024a39  mov     cs:qword_1400A1630, rax
0x140024a40  mov     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A, 28h ; '('; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x140024a4a  movdqu  cs:?g_ServerActivity@@3U_FAX_SERVER_ACTIVITY@@A+4, xmm0; _FAX_SERVER_ACTIVITY g_ServerActivity
0x140024a52  xorps   xmm1, xmm1
0x140024a55  movdqu  cs:xmmword_14009DBA0+4, xmm1
0x140024a5d  mov     dword ptr cs:?g_ServerActivity@@3U_FAX_SERVER_ACTIVITY@@A, 24h ; '$'; _FAX_SERVER_ACTIVITY g_ServerActivity
0x140024a67  mov     cs:?g_hDispatchEventsCompPort@@3PEAXEA, r14; void * g_hDispatchEventsCompPort
0x140024a6e  mov     cs:?g_hSendEventsCompPort@@3PEAXEA, r14; void * g_hSendEventsCompPort
0x140024a75  mov     cs:?g_dwlClientID@@3_KA, r14; unsigned __int64 g_dwlClientID
0x140024a7c  mov     cs:?g_FaxQuotaWarn@@3U_FAX_QUOTA_WARN@@A, r14; _FAX_QUOTA_WARN g_FaxQuotaWarn
0x140024a83  mov     cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA, r14; void * g_hArchiveQuotaWarningEvent
0x140024a8a  mov     cs:?g_dwConnectionCount@@3KA, r14d; ulong g_dwConnectionCount
0x140024a91  or      rax, 0FFFFFFFFFFFFFFFFh
0x140024a95  mov     cs:?g_hInboxActivityLogFile@@3PEAXEA, rax; void * g_hInboxActivityLogFile
0x140024a9c  mov     cs:?g_hOutboxActivityLogFile@@3PEAXEA, rax; void * g_hOutboxActivityLogFile
0x140024aa3  mov     cs:?g_fLogStringTableInit@@3HA, r14d; int g_fLogStringTableInit
0x140024aaa  mov     cs:?g_dwQueueCount@@3KA, r14d; ulong g_dwQueueCount
0x140024ab1  mov     cs:?g_hJobQueueEvent@@3PEAXEA, r14; void * g_hJobQueueEvent
0x140024ab8  mov     cs:?g_ScanQueueAfterTimeout@@3HA, r14d; int g_ScanQueueAfterTimeout
0x140024abf  mov     cs:?g_dwReceiveDevicesCount@@3KA, r14d; ulong g_dwReceiveDevicesCount
0x140024ac6  mov     cs:?g_bDelaySuicideAttempt@@3HA, r14d; int g_bDelaySuicideAttempt
0x140024acd  mov     cs:?g_bServiceCanSuicide@@3HA, 1; int g_bServiceCanSuicide
0x140024ad7  mov     cs:?g_dwCountRoutingMethods@@3KA, r14d; ulong g_dwCountRoutingMethods
0x140024ade  mov     cs:?g_pLineCountryList@@3PEAUlinecountrylist_tag@@EA, r14; linecountrylist_tag * g_pLineCountryList
0x140024ae5  mov     cs:?g_dwLastUniqueId@@3_KA, r14; unsigned __int64 g_dwLastUniqueId
0x140024aec  mov     cs:?g_bServiceIsDown@@3HA, r14d; int g_bServiceIsDown
0x140024af3  mov     cs:?g_TapiCompletionPort@@3PEAXEA, r14; void * g_TapiCompletionPort
0x140024afa  mov     cs:?g_hLineApp@@3KA, r14d; ulong g_hLineApp
0x140024b01  mov     cs:ServiceStatus.dwServiceType, 30h ; '0'
0x140024b0b  lea     edi, [rax+3]
0x140024b0e  mov     cs:ServiceStatus.dwCurrentState, edi
0x140024b14  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x140024b1b  mov     cs:?g_hRPCListeningThread@@3PEAXEA, r14; void * g_hRPCListeningThread
0x140024b22  mov     cs:?g_lServiceThreadsCount@@3JA, r14d; long g_lServiceThreadsCount
0x140024b29  mov     cs:?g_hThreadCountEvent@@3PEAXEA, r14; void * g_hThreadCountEvent
0x140024b30  mov     ecx, r14d
0x140024b33  lea     rdx, __ImageBase
0x140024b3a  mov     rax, rcx
0x140024b3d  shl     rax, 5
0x140024b41  mov     [rax+rdx+9D688h], r14
0x140024b49  inc     rcx
0x140024b4c  cmp     rcx, 0Eh
0x140024b50  jnz     short loc_140024B3A
0x140024b52  mov     rcx, r14
0x140024b55  mov     rax, rcx
0x140024b58  shl     rax, 5
0x140024b5c  mov     [rax+rdx+9D048h], r14
0x140024b64  inc     rcx
0x140024b67  cmp     rcx, 32h ; '2'
0x140024b6b  jnz     short loc_140024B55
0x140024b6d  mov     rcx, r14
0x140024b70  mov     rax, rcx
0x140024b73  add     rax, rax
0x140024b76  mov     rva qword_14009DBC8[rdx+rax*8], r14
0x140024b7e  inc     rcx
0x140024b81  cmp     rcx, 3Bh ; ';'
0x140024b85  jnz     short loc_140024B70
0x140024b87  mov     cs:?g_StatusCompletionPortHandle@@3PEAXEA, r14; void * g_StatusCompletionPortHandle
0x140024b8e  mov     cs:?g_pFaxSD@@3PEAXEA, r14; void * g_pFaxSD
0x140024b95  mov     cs:?g_dwDeviceCount@@3KA, r14d; ulong g_dwDeviceCount
0x140024b9c  mov     cs:?g_dwDeviceEnabledCount@@3KA, r14d; ulong g_dwDeviceEnabledCount
0x140024ba3  cmp     rbx, rsi
0x140024ba6  jz      short loc_140024BC7
0x140024ba8  test    [rbx+1Ch], dil
0x140024bac  jz      short loc_140024BC7
0x140024bae  cmp     byte ptr [rbx+19h], 5
0x140024bb2  jb      short loc_140024BC7
0x140024bb4  lea     edx, [rcx-2Ah]
0x140024bb7  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140024bbe  mov     rcx, [rbx+10h]
0x140024bc2  call    WPP_SF_
0x140024bc7  mov     dword ptr [rbp+arg_0], r14d
0x140024bcb  lea     rdx, [rbp+arg_0]
0x140024bcf  lea     rcx, aMicrosoftWindo_1; "Microsoft-Windows-Fax-Common-DeviceLimi"...
0x140024bd6  call    GetLicensingPolicyValue
0x140024bdb  test    eax, eax
0x140024bdd  js      short loc_140024BE4
0x140024bdf  mov     ebx, dword ptr [rbp+arg_0]
0x140024be2  jmp     short loc_140024C14
0x140024be4  mov     ebx, 1
0x140024be9  mov     rcx, cs:WPP_GLOBAL_Control
0x140024bf0  cmp     rcx, rsi
0x140024bf3  jz      short loc_140024C14
0x140024bf5  test    [rcx+1Ch], dil
0x140024bf9  jz      short loc_140024C14
0x140024bfb  cmp     byte ptr [rcx+19h], 3
0x140024bff  jb      short loc_140024C14
0x140024c01  lea     edx, [rbx+11h]
0x140024c04  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140024c0b  mov     rcx, [rcx+10h]
0x140024c0f  call    WPP_SF_
0x140024c14  mov     cs:?g_dwDeviceEnabledLimit@@3KA, ebx; ulong g_dwDeviceEnabledLimit
0x140024c1a  mov     cs:?g_hTapiWorkerThread@@3PEAXEA, r14; void * g_hTapiWorkerThread
0x140024c21  mov     cs:?g_hJobQueueThread@@3PEAXEA, r14; void * g_hJobQueueThread
0x140024c28  call    GetResInst
0x140024c2d  mov     cs:?g_hResource@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResource
0x140024c34  test    rax, rax
0x140024c37  jnz     short loc_140024C46
0x140024c39  call    cs:__imp_GetLastError
0x140024c3f  mov     ebx, eax
0x140024c41  jmp     loc_14002514E
0x140024c46  xor     r9d, r9d; lpName
0x140024c49  xor     r8d, r8d; bInitialState
0x140024c4c  lea     edx, [r9+1]; bManualReset
0x140024c50  xor     ecx, ecx; lpEventAttributes
0x140024c52  call    cs:__imp_CreateEventW
0x140024c58  mov     cs:?g_hServiceShutDownEvent@@3PEAXEA, rax; void * g_hServiceShutDownEvent
0x140024c5f  test    rax, rax
0x140024c62  jnz     short loc_140024CA9
0x140024c64  call    cs:__imp_GetLastError
0x140024c6a  mov     ebx, eax
0x140024c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c73  cmp     rcx, rsi
0x140024c76  jz      loc_14002514E
0x140024c7c  test    byte ptr [rcx+1Ch], 4
0x140024c80  jz      loc_14002514E
0x140024c86  cmp     [rcx+19h], dil
0x140024c8a  jb      loc_14002514E
0x140024c90  mov     edx, 0Eh
0x140024c95  mov     r9d, eax
0x140024c98  mov     r8, r15
0x140024c9b  mov     rcx, [rcx+10h]
0x140024c9f  call    WPP_SF_d
0x140024ca4  jmp     loc_14002514E
0x140024ca9  xor     r9d, r9d; lpName
0x140024cac  xor     r8d, r8d; bInitialState
0x140024caf  lea     edx, [r9+1]; bManualReset
0x140024cb3  xor     ecx, ecx; lpEventAttributes
0x140024cb5  call    cs:__imp_CreateEventW
0x140024cbb  mov     cs:?g_hSCMServiceShutDownEvent@@3PEAXEA, rax; void * g_hSCMServiceShutDownEvent
0x140024cc2  test    rax, rax
0x140024cc5  jnz     short loc_140024CFA
0x140024cc7  call    cs:__imp_GetLastError
0x140024ccd  mov     ebx, eax
0x140024ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x140024cd6  cmp     rcx, rsi
0x140024cd9  jz      loc_14002514E
0x140024cdf  test    byte ptr [rcx+1Ch], 4
0x140024ce3  jz      loc_14002514E
0x140024ce9  cmp     [rcx+19h], dil
0x140024ced  jb      loc_14002514E
0x140024cf3  mov     edx, 0Fh
0x140024cf8  jmp     short loc_140024C95
0x140024cfa  xor     r9d, r9d; lpName
0x140024cfd  mov     r8d, edi; lMaximumCount
0x140024d00  xor     edx, edx; lInitialCount
0x140024d02  xor     ecx, ecx; lpSemaphoreAttributes
0x140024d04  call    cs:__imp_CreateSemaphoreW
0x140024d0a  mov     cs:?g_hServiceIsDownSemaphore@@3PEAXEA, rax; void * g_hServiceIsDownSemaphore
0x140024d11  test    rax, rax
0x140024d14  jnz     short loc_140024D4C
0x140024d16  call    cs:__imp_GetLastError
0x140024d1c  mov     ebx, eax
0x140024d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024d25  cmp     rcx, rsi
0x140024d28  jz      loc_14002514E
0x140024d2e  test    byte ptr [rcx+1Ch], 4
0x140024d32  jz      loc_14002514E
0x140024d38  cmp     [rcx+19h], dil
0x140024d3c  jb      loc_14002514E
0x140024d42  mov     edx, 10h
0x140024d47  jmp     loc_140024C95
0x140024d4c  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024d53  call    cs:__imp_InitializeCriticalSection
0x140024d59  lea     rcx, ?g_CsInboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024d60  call    cs:__imp_InitializeCriticalSection
0x140024d66  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024d6d  call    cs:__imp_InitializeCriticalSection
0x140024d73  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024d7a  call    cs:__imp_InitializeCriticalSection
0x140024d80  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024d87  call    cs:__imp_InitializeCriticalSection
0x140024d8d  lea     rcx, ?g_CsPerfCounters@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024d94  call    cs:__imp_InitializeCriticalSection
0x140024d9a  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024da1  call    cs:__imp_InitializeCriticalSection
0x140024da7  lea     rcx, ?g_csUniqueQueueFile@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024dae  call    cs:__imp_InitializeCriticalSection
0x140024db4  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024dbb  call    cs:__imp_InitializeCriticalSection
0x140024dc1  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024dc8  call    cs:__imp_InitializeCriticalSection
0x140024dce  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024dd5  call    cs:__imp_InitializeCriticalSection
0x140024ddb  lea     rcx, ?g_CsHandleTable@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024de2  call    cs:__imp_InitializeCriticalSection
0x140024de8  lea     rcx, ?g_CsActivity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024def  call    cs:__imp_InitializeCriticalSection
0x140024df5  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140024dfc  call    cs:__imp_InitializeCriticalSection
0x140024e02  lea     rax, ?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceProvidersListHead
0x140024e09  mov     cs:qword_1400A1358, rax
0x140024e10  mov     cs:?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_DeviceProvidersListHead
0x140024e17  lea     rax, ?g_HandleTableListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_HandleTableListHead
0x140024e1e  mov     cs:qword_1400A1468, rax
0x140024e25  mov     cs:?g_HandleTableListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_HandleTableListHead
0x140024e2c  lea     rax, ?g_JobListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_JobListHead
0x140024e33  mov     cs:qword_1400A14C8, rax
0x140024e3a  mov     cs:?g_JobListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_JobListHead
0x140024e41  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x140024e48  mov     cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Blink, rax; _LIST_ENTRY g_QueueListHead ...
0x140024e4f  mov     cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink, rax; _LIST_ENTRY g_QueueListHead ...
0x140024e56  lea     rax, ?g_lstRoutingExtensions@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingExtensions
0x140024e5d  mov     cs:qword_1400A1550, rax
0x140024e64  mov     cs:?g_lstRoutingExtensions@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_lstRoutingExtensions
0x140024e6b  lea     rax, ?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x140024e72  mov     cs:qword_1400A1588, rax
0x140024e79  mov     cs:?g_lstRoutingMethods@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_lstRoutingMethods
0x140024e80  lea     rax, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140024e87  mov     cs:qword_1400A1748, rax
0x140024e8e  mov     cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_TapiLinesListHead
0x140024e95  lea     rax, ?g_RemovedTapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RemovedTapiLinesListHead
0x140024e9c  mov     cs:qword_1400A1788, rax
0x140024ea3  mov     cs:?g_RemovedTapiLinesListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_RemovedTapiLinesListHead
0x140024eaa  mov     cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA, r14; CFaxConfiguration * g_pFaxConfig
0x140024eb1  mov     cs:?g_pFaxArchiving@@3PEAVCFaxArchiving@@EA, r14; CFaxArchiving * g_pFaxArchiving
0x140024eb8  mov     cs:?g_pClientsMap@@3PEAVCClientsMap@@EA, r14; CClientsMap * g_pClientsMap
0x140024ebf  mov     cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA, r14; CNotificationMap * g_pNotificationMap
0x140024ec6  mov     cs:?g_pTAPIDevicesIdsMap@@3PEAVCMapDeviceId@@EA, r14; CMapDeviceId * g_pTAPIDevicesIdsMap
0x140024ecd  mov     cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA, r14; COutboundRoutingGroupsMap * g_pGroupsMap
0x140024ed4  mov     cs:?g_pRulesMap@@3PEAVCOutboundRulesMap@@EA, r14; COutboundRulesMap * g_pRulesMap
0x140024edb  mov     cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA, r14; CFaxAccountList * g_pAccountList
0x140024ee2  mov     cs:?g_pAccountDefaults@@3PEAVCFaxAccount@@EA, r14; CFaxAccount * g_pAccountDefaults
0x140024ee9  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140024ef0  mov     rdx, r15; struct std::nothrow_t *
0x140024ef3  mov     ecx, 88h; unsigned __int64
0x140024ef8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140024efd  mov     rbx, rax
0x140024f00  mov     [rbp+arg_0], rax
0x140024f04  test    rax, rax
0x140024f07  jz      short loc_140024F41
0x140024f09  lea     rax, ??_7CFaxConfiguration@@6B@; const CFaxConfiguration::`vftable'
0x140024f10  mov     [rbx], rax
0x140024f13  mov     [rbx+30h], r14
0x140024f17  mov     [rbx+38h], r14
0x140024f1b  mov     [rbx+60h], r14
0x140024f1f  mov     [rbx+80h], r14d
0x140024f26  lea     rcx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x140024f2d  call    StringDup
0x140024f32  mov     [rbx+78h], rax
0x140024f36  test    rax, rax
0x140024f39  jz      loc_14002516C
0x140024f3f  jmp     short loc_140024F44
0x140024f41  mov     rbx, r14
0x140024f44  mov     cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA, rbx; CFaxConfiguration * g_pFaxConfig
0x140024f4b  test    rbx, rbx
0x140024f4e  jz      loc_140025149
0x140024f54  mov     rdx, r15; struct std::nothrow_t *
0x140024f57  mov     ecx, 4; unsigned __int64
0x140024f5c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140024f61  mov     [rbp+arg_0], rax
0x140024f65  test    rax, rax
0x140024f68  jz      loc_140025142
0x140024f6e  mov     [rax], r14d
0x140024f71  mov     cs:?g_pFaxArchiving@@3PEAVCFaxArchiving@@EA, rax; CFaxArchiving * g_pFaxArchiving
0x140024f78  mov     rdx, r15; struct std::nothrow_t *
0x140024f7b  mov     ecx, 18h; unsigned __int64
0x140024f80  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140024f85  mov     rbx, rax
0x140024f88  mov     [rbp+arg_0], rax
0x140024f8c  test    rax, rax
0x140024f8f  jz      short loc_140024FAB
  ... truncated ...
```
