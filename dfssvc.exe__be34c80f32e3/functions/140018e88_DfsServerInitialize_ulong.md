# DfsServerInitialize(ulong)

- ea: `0x140018e88`
- end: `0x140019b82`
- name: `?DfsServerInitialize@@YAKK@Z`
- size: `3322`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140057640`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140002a28`
- `0x140005a94`
- `0x140006ab0`
- `0x140006bf0`
- `0x1400096ac`
- `0x14000abc4`
- `0x14001179c`
- `0x140015f64`
- `0x140016204`
- `0x140017ac4`
- `0x140017cb0`
- `0x140018304`
- `0x140018a50`
- `0x140018c28`
- `0x140018e88`
- `0x14001a9b4`
- `0x14001a9f4`
- `0x14001aae0`
- `0x14001ac2c`
- `0x1400331fc`
- `0x14003466c`
- `0x140034a04`
- `0x140035920`
- `0x14003b214`
- `0x14003b698`
- `0x14004a144`
- `0x14004ac38`
- `0x14005a934`
- `0x14005ab08`
- `0x14005b1b8`
- `0x14005c994`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001936d`
- `ntdll!RtlInitUnicodeString` at `0x14001936d`
- `ntdll!RtlNtStatusToDosError` at `0x14001955e`
- `ntdll!RtlNtStatusToDosError` at `0x14001955e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001945e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001945e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019b04`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14001944e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x14001944e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001947c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001947c`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x140019510`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x140019510`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019aef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019aef`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140018f5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x140018f5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140018eea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140018eea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14001991d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14001991d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140019631`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001987b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400199ac`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140019631`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001987b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400199ac`
- `WS2_32!__imp_WSAStartup` at `0x140018f9a`
- `WS2_32!__imp_WSAStartup` at `0x140018f9a`

## pseudocode

```c
__int64 __fastcall DfsServerInitialize()
{
  int v0; // r15d
  ULONGLONG TickCount64; // rax
  unsigned int v2; // eax
  unsigned int *v3; // rcx
  DWORD LastError; // ebx
  unsigned int *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int *v8; // rcx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  DfsSiteNameCache *v11; // rax
  DfsSiteNameCache *v12; // rdi
  DfsSite *v13; // rax
  DfsGeneric *v14; // rbx
  DfsGeneric *v16; // rax
  __int64 v17; // rcx
  DfsGeneric *v18; // rdi
  NTSTATUS v19; // eax
  unsigned int v20; // eax
  unsigned int *v21; // rcx
  HANDLE Thread; // rax
  DWORD v23; // eax
  CConfigurationSettings *Instance; // rax
  unsigned int ISTGHandleSupport; // eax
  unsigned int *v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // eax
  struct _TP_POOL **v29; // rax
  unsigned int v30; // ecx
  unsigned int inited; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  _BYTE ThreadId[40]; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v35; // [rsp+60h] [rbp-A8h]
  struct _SYSTEMTIME SystemTime_8; // [rsp+70h] [rbp-98h] BYREF
  WSAData WSAData; // [rsp+88h] [rbp-80h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  v0 = 0;
  memset_0(&DfsServerGlobalData, 0, 0x140u);
  TickCount64 = GetTickCount64();
  qword_140071540 = 0;
  qword_140071648 = TickCount64;
  word_140071515 = 1;
  DfsServerGlobalData = 128;
  DfsPerfCounters::Init();
  DfsSqmWrapper::gm_IsWinSqmEnabled = 0;
  DfsSqmService::gm_TotalRequests_NetDfsAdd2 = 0;
  SystemTime_8 = 0;
  DfsSqmService::gm_TotalRequests_NetDfsRemove2 = 0;
  DfsSqmService::gm_TotalRequests_NetDfsSetInfo2 = 0;
  DfsSqmService::gm_TotalRequests_NetDfsEnumEx = 0;
  DfsSqmService::gm_NumOfTrustedDomains = 0;
  DfsSqmService::gm_MaxTrustedDomainReferralSize = 0;
  GetLocalTime(&SystemTime_8);
  DfsSqmService::gm_wDay = SystemTime_8.wDay;
  McGenEventRegister_EtwEventRegister();
  if ( !(unsigned int)DfsAdjustPrivilege(17) )
    DfsAdjustPrivilege(18);
  v2 = WSAStartup(0x101u, &WSAData);
  *(_DWORD *)ThreadId = v2;
  LastError = v2;
  if ( v2 )
  {
    DfsLogDfsEvent(0xC00038AE, 0, 0, v2);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_175;
    v5 = pWppControl;
    if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
      goto LABEL_175;
    v6 = 10;
    goto LABEL_9;
  }
  if ( !CConfigurationSettings::_GetInstance(v3) )
  {
    LastError = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x820) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_(*((_QWORD *)pWppControl + 2), 11, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids);
    }
    goto LABEL_64;
  }
  CLocalMachine::_GetInstance((unsigned int *)ThreadId);
  LastError = *(_DWORD *)ThreadId;
  if ( *(_DWORD *)ThreadId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x820) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_D(
        *((_QWORD *)pWppControl + 2),
        12,
        WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids,
        *(unsigned int *)ThreadId);
    }
    v9 = -1073727308;
    goto LABEL_174;
  }
  CLdap::gm_DefaultTimeOut = *((_DWORD *)CConfigurationSettings::_GetInstance(v8) + 7);
  v10 = CLdap::_AllocTlsIndex();
  LastError = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_175;
    v5 = pWppControl;
    if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
      goto LABEL_175;
    v6 = 13;
    goto LABEL_30;
  }
  if ( !DfsInitializeSecurity() )
  {
    LastError = GetLastError();
    DfsLogDfsEvent(0xC00038AF, 0, 0, LastError);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_175;
    v5 = pWppControl;
    if ( !pWppControl
      || (((1 << (LastError != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) == 0
      || !*((_BYTE *)pWppControl + 25) )
    {
      goto LABEL_175;
    }
    v6 = 14;
    goto LABEL_9;
  }
  qword_140071610 = 0;
  qword_140071620 = (__int64)&qword_140071618;
  qword_140071618 = (__int64)&qword_140071618;
  qword_140071628 = 0;
  qword_140071608 = (__int64)&qword_140071600;
  qword_140071600 = (__int64)&qword_140071600;
  qword_140071630 = 0;
  v11 = (DfsSiteNameCache *)operator new(8u);
  v12 = v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = 0;
    LastError = DfsSiteNameCache::DfsInitializeSiteCache(v11);
    if ( !LastError )
      goto LABEL_42;
    operator delete(v12);
  }
  else
  {
    LastError = 8;
  }
  v12 = 0;
LABEL_42:
  *(_DWORD *)ThreadId = LastError;
  qword_140071558 = v12;
  if ( !v12 )
  {
    DfsLogDfsEvent(0xC00038B1, 0, 0, LastError);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_175;
    v5 = pWppControl;
    if ( !pWppControl
      || (((1 << (LastError != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) == 0
      || !*((_BYTE *)pWppControl + 25) )
    {
      goto LABEL_175;
    }
    v6 = 15;
    goto LABEL_9;
  }
  qword_140071560 = DfsSiteNameSupport::CreateSiteNameSupport((unsigned int *)ThreadId, 0x40u);
  if ( !qword_140071560 )
  {
    LastError = *(_DWORD *)ThreadId;
    DfsLogDfsEvent(0xC00038B1, 0, 0, *(unsigned int *)ThreadId);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_175;
    v5 = pWppControl;
    if ( !pWppControl
      || (((1 << (LastError != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) == 0
      || !*((_BYTE *)pWppControl + 25) )
    {
      goto LABEL_175;
    }
    v6 = 16;
    goto LABEL_9;
  }
  SystemTime_8 = 0;
  v13 = (DfsSite *)operator new(0x30u);
  if ( !v13 )
    goto LABEL_58;
  v14 = DfsSite::DfsSite(v13);
  if ( v14 )
  {
    RtlInitUnicodeString((PUNICODE_STRING)&SystemTime_8, 0);
    if ( DfsSite::Initialize(v14, (struct _UNICODE_STRING *)&SystemTime_8) )
    {
      DfsGeneric::ReleaseReference(v14);
LABEL_58:
      qword_140071568 = 0;
LABEL_59:
      LastError = 8;
      DfsLogDfsEvent(0xC00038B1, 0, 0, 8u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x820) != 0
        && *((_BYTE *)pWppControl + 25) )
      {
        WPP_SF_D(*((_QWORD *)pWppControl + 2), 17, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, 8);
      }
      goto LABEL_64;
    }
  }
  qword_140071568 = (__int64)v14;
  if ( !v14 )
    goto LABEL_59;
  if ( !InitializeCriticalSectionAndSpinCount(&CriticalSection, 0xFA0u) )
  {
    LastError = GetLastError();
    goto LABEL_175;
  }
  hEvent = CreateEventW(0, 1, 0, 0);
  if ( !hEvent )
  {
    LastError = GetLastError();
    DfsLogDfsEvent(0xC00038B3, 0, 0, LastError);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_175;
    v5 = pWppControl;
    if ( !pWppControl
      || (((1 << (LastError != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) == 0
      || !*((_BYTE *)pWppControl + 25) )
    {
      goto LABEL_175;
    }
    v6 = 18;
    goto LABEL_9;
  }
  PrefixTableHeapHandle = HeapCreate(0, 0, 0);
  DfsCreateRequiredDfsKeys();
  v16 = (DfsGeneric *)operator new(0x18u);
  v18 = v16;
  if ( v16 )
  {
    *((_DWORD *)v16 + 2) = 1;
    *((_DWORD *)v16 + 3) = 1968395076;
    *(_QWORD *)v16 = &DfsSiteSupport::`vftable';
    *((_QWORD *)v16 + 2) = 0;
    v19 = DfsInitializeNameTable(v17, (char *)v16 + 16);
    LastError = RtlNtStatusToDosError(v19);
    if ( !LastError )
      goto LABEL_80;
    DfsGeneric::ReleaseReference(v18);
  }
  else
  {
    LastError = 8;
  }
  v18 = 0;
LABEL_80:
  qword_140071550 = v18;
  if ( !v18 )
  {
    v9 = -1073727300;
LABEL_174:
    DfsLogDfsEvent(v9, 0, 0, LastError);
    goto LABEL_175;
  }
  DfsGetGlobalRegistrySettings();
  v20 = DfsRootSynchronizeInit();
  LastError = v20;
  if ( v20 )
  {
    DfsLogDfsEvent(0xC00038B2, 0, 0, v20);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_175;
    v5 = pWppControl;
    if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
      goto LABEL_175;
    v6 = 19;
    goto LABEL_9;
  }
  if ( (unsigned int)DfsIsLocalMachineDc() )
  {
    *(_DWORD *)ThreadId = 0;
    Thread = CreateThread(0, 0, DcUpdateLoop, 0, 0, (LPDWORD)ThreadId);
    if ( Thread )
    {
      hHandle = Thread;
    }
    else
    {
      v23 = GetLastError();
      LastError = v23;
      if ( v23 )
      {
        DfsLogDfsEvent(0xC00038B6, 0, 0, v23);
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_175;
        v5 = pWppControl;
        if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
          goto LABEL_175;
        v6 = 20;
        goto LABEL_9;
      }
    }
  }
  else
  {
    Instance = CConfigurationSettings::_GetInstance(v21);
    CConfigurationSettings::LoadServerConsolidationSettings(Instance);
  }
  DfsCreateGlobalPerfCounterInstances();
  v0 = 1;
  ISTGHandleSupport = DfsISTGHandleSupport::DfsCreateISTGHandleSupport(&qword_1400715F8);
  LastError = ISTGHandleSupport;
  if ( !ISTGHandleSupport )
  {
    LastError = DfsInitializePrefixTable(&qword_1400715E8);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_111;
      v26 = pWppControl;
      if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
        goto LABEL_111;
      v27 = 22;
    }
    else
    {
      qword_1400715F0 = 0;
      if ( !(unsigned int)DfsIsLocalMachineDc() || (LastError = DfsInitializePrefixTable(&qword_1400715F0)) == 0 )
      {
        v28 = DfsRegisterStores();
        LastError = v28;
        if ( v28 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && (pWppControl[7] & 0x820) != 0
            && *((_BYTE *)pWppControl + 25) )
          {
            WPP_SF_D(*((_QWORD *)pWppControl + 2), 24, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v28);
          }
          v9 = -1073727303;
          goto LABEL_174;
        }
        *(_DWORD *)&ThreadId[4] = 0;
        hObject = CreateThread(0, 0, DfsSiteSupportThread, 0, 4u, (LPDWORD)&ThreadId[4]);
        if ( !hObject )
        {
          v33 = GetLastError();
          LastError = v33;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && (pWppControl[7] & 0x20) != 0
            && *((_BYTE *)pWppControl + 25) )
          {
            WPP_SF_D(*((_QWORD *)pWppControl + 2), 26, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v33);
          }
          v9 = -1073727312;
          goto LABEL_174;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_D(
            *((_QWORD *)pWppControl + 2),
            25,
            WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids,
            *(unsigned int *)&ThreadId[4]);
        }
        memset(&ThreadId[8], 0, 32);
        v35 = 0;
        v29 = (struct _TP_POOL **)operator new(8u);
        if ( v29 )
          *v29 = 0;
        else
          v29 = 0;
        Block = v29;
        if ( v29 )
        {
          GetSystemInfo((LPSYSTEM_INFO)&ThreadId[8]);
          LastError = DfsCreateThreadpool(v30, 2 * v35, Block);
          v7 = LastError;
          if ( !LastError )
          {
            qword_1400715A8 = CreateThread(0, 0, DfsWorkerThread, 0, 0, (LPDWORD)&ThreadId[4]);
            if ( !qword_1400715A8 )
            {
              v32 = GetLastError();
              LastError = v32;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x20) != 0
                && *((_BYTE *)pWppControl + 25) )
              {
                WPP_SF_D(*((_QWORD *)pWppControl + 2), 29, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v32);
              }
              CloseHandle(hObject);
              hObject = 0;
              goto LABEL_175;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (pWppControl[7] & 0x20) != 0
              && *((_BYTE *)pWppControl + 25) )
            {
              WPP_SF_D(
                *((_QWORD *)pWppControl + 2),
                28,
                WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids,
                *(unsigned int *)&ThreadId[4]);
            }
            inited = DfsInitDfsFilterInterface();
            LastError = inited;
            if ( inited )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && pWppControl
                && (pWppControl[7] & 0x820) != 0
                && *((_BYTE *)pWppControl + 25) )
              {
                WPP_SF_D(*((_QWORD *)pWppControl + 2), 30, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, inited);
              }
              v9 = -1073727302;
              goto LABEL_174;
            }
            v10 = DfsApiInit();
            LastError = v10;
            if ( !v10 )
              goto LABEL_175;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_175;
            v5 = pWppControl;
            if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
              goto LABEL_175;
            v6 = 31;
LABEL_30:
            v7 = v10;
            goto LABEL_10;
          }
        }
        else
        {
          v7 = 14;
          LastError = 14;
        }
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_175;
        v5 = pWppControl;
        if ( !pWppControl
          || (((1 << ((_DWORD)v7 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) == 0
          || !*((_BYTE *)pWppControl + 25) )
        {
          goto LABEL_175;
        }
        v6 = 27;
        goto LABEL_10;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_111;
      v26 = pWppControl;
      if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
        goto LABEL_111;
      v27 = 23;
    }
    WPP_SF_D(*((_QWORD *)v26 + 2), v27, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, LastError);
LABEL_111:
    v9 = -1073727305;
    goto LABEL_174;
  }
  DfsLogDfsEvent(0xC00038B6, 0, 0, ISTGHandleSupport);
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_175;
  v5 = pWppControl;
  if ( !pWppControl || (pWppControl[7] & 0x820) == 0 || !*((_BYTE *)pWppControl + 25) )
    goto LABEL_175;
  v6 = 21;
LABEL_9:
  v7 = LastError;
LABEL_10:
  WPP_SF_D(*((_QWORD *)v5 + 2), v6, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v7);
LABEL_175:
  if ( !LastError )
    return LastError;
  if ( v0 )
    DfsDeleteGlobalPerfCounterInstances();
LABEL_64:
  McGenEventUnregister_EtwEventUnregister();
  return LastError;
}

```

## disassembly

```asm
0x140018e88  mov     rax, rsp
0x140018e8b  mov     [rax+8], rbx
0x140018e8f  mov     [rax+10h], rsi
0x140018e93  mov     [rax+18h], rdi
0x140018e97  push    rbp
0x140018e98  push    r12
0x140018e9a  push    r13
0x140018e9c  push    r14
0x140018e9e  push    r15
0x140018ea0  lea     rbp, [rax-158h]
0x140018ea7  sub     rsp, 230h
0x140018eae  mov     rax, cs:__security_cookie
0x140018eb5  xor     rax, rsp
0x140018eb8  mov     [rbp+150h+var_30], rax
0x140018ebf  xor     edx, edx; Val
0x140018ec1  lea     rcx, [rbp+150h+WSAData]; void *
0x140018ec5  mov     r8d, 198h; Size
0x140018ecb  call    memset_0
0x140018ed0  xor     r12d, r12d
0x140018ed3  lea     rcx, ?DfsServerGlobalData@@3U_DFS_SERVER_GLOBAL_DATA@@A; void *
0x140018eda  xor     edx, edx; Val
0x140018edc  mov     r8d, 140h; Size
0x140018ee2  mov     r15d, r12d
0x140018ee5  call    memset_0
0x140018eea  call    cs:__imp_GetTickCount64
0x140018ef1  nop     dword ptr [rax+rax+00h]
0x140018ef6  lea     r13d, [r12+1]
0x140018efb  mov     cs:qword_140071540, r12
0x140018f02  mov     cs:qword_140071648, rax
0x140018f09  mov     cs:word_140071515, r13w
0x140018f11  mov     cs:?DfsServerGlobalData@@3U_DFS_SERVER_GLOBAL_DATA@@A, 80h; _DFS_SERVER_GLOBAL_DATA DfsServerGlobalData
0x140018f1b  call    ?Init@DfsPerfCounters@@SAKXZ; DfsPerfCounters::Init(void)
0x140018f20  xorps   xmm0, xmm0
0x140018f23  mov     cs:?gm_IsWinSqmEnabled@DfsSqmWrapper@@0HA, r12d; int DfsSqmWrapper::gm_IsWinSqmEnabled
0x140018f2a  lea     rcx, [rsp+250h+SystemTime.wHour]; lpSystemTime
0x140018f2f  mov     cs:?gm_TotalRequests_NetDfsAdd2@DfsSqmService@@2KA, r12d; ulong DfsSqmService::gm_TotalRequests_NetDfsAdd2
0x140018f36  movups  xmmword ptr [rsp+250h+SystemTime.wHour], xmm0
0x140018f3b  mov     cs:?gm_TotalRequests_NetDfsRemove2@DfsSqmService@@2KA, r12d; ulong DfsSqmService::gm_TotalRequests_NetDfsRemove2
0x140018f42  mov     cs:?gm_TotalRequests_NetDfsSetInfo2@DfsSqmService@@2KA, r12d; ulong DfsSqmService::gm_TotalRequests_NetDfsSetInfo2
0x140018f49  mov     cs:?gm_TotalRequests_NetDfsEnumEx@DfsSqmService@@2KA, r12d; ulong DfsSqmService::gm_TotalRequests_NetDfsEnumEx
0x140018f50  mov     cs:?gm_NumOfTrustedDomains@DfsSqmService@@2KA, r12d; ulong DfsSqmService::gm_NumOfTrustedDomains
0x140018f57  mov     cs:?gm_MaxTrustedDomainReferralSize@DfsSqmService@@2KA, r12d; ulong DfsSqmService::gm_MaxTrustedDomainReferralSize
0x140018f5e  call    cs:__imp_GetLocalTime
0x140018f65  nop     dword ptr [rax+rax+00h]
0x140018f6a  movzx   eax, [rsp+250h+SystemTime.wMilliseconds]
0x140018f6f  mov     cs:?gm_wDay@DfsSqmService@@2GA, ax; ushort DfsSqmService::gm_wDay
0x140018f76  call    McGenEventRegister_EtwEventRegister
0x140018f7b  lea     ecx, [r12+11h]
0x140018f80  call    DfsAdjustPrivilege
0x140018f85  test    eax, eax
0x140018f87  jnz     short loc_140018F91
0x140018f89  lea     ecx, [rax+12h]
0x140018f8c  call    DfsAdjustPrivilege
0x140018f91  mov     ecx, 101h; wVersionRequested
0x140018f96  lea     rdx, [rbp+150h+WSAData]; lpWSAData
0x140018f9a  call    cs:__imp_WSAStartup
0x140018fa1  nop     dword ptr [rax+rax+00h]
0x140018fa6  mov     [rsp+250h+ThreadId], eax
0x140018faa  mov     ebx, eax
0x140018fac  test    eax, eax
0x140018fae  jz      short loc_14001901F
0x140018fb0  xor     edx, edx; unsigned __int16
0x140018fb2  mov     r9d, eax; unsigned int
0x140018fb5  xor     r8d, r8d; unsigned __int16 **
0x140018fb8  mov     ecx, 0C00038AEh; unsigned int
0x140018fbd  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x140018fc2  lea     rsi, WPP_GLOBAL_Control
0x140018fc9  cmp     cs:WPP_GLOBAL_Control, rsi
0x140018fd0  jz      loc_140019B67
0x140018fd6  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140018fdd  test    rcx, rcx
0x140018fe0  jz      loc_140019B67
0x140018fe6  mov     edi, 20h ; ' '
0x140018feb  bts     edi, 0Bh
0x140018fef  test    [rcx+1Ch], edi
0x140018ff2  jz      loc_140019B67
0x140018ff8  cmp     [rcx+19h], r13b
0x140018ffc  jb      loc_140019B67
0x140019002  mov     edx, 0Ah
0x140019007  mov     r9d, ebx
0x14001900a  mov     rcx, [rcx+10h]
0x14001900e  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x140019015  call    WPP_SF_D
0x14001901a  jmp     loc_140019B67
0x14001901f  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x140019024  test    rax, rax
0x140019027  jnz     short loc_140019082
0x140019029  lea     ebx, [rax+8]
0x14001902c  lea     rsi, WPP_GLOBAL_Control
0x140019033  cmp     cs:WPP_GLOBAL_Control, rsi
0x14001903a  jz      loc_1400193FA
0x140019040  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140019047  test    rcx, rcx
0x14001904a  jz      loc_1400193FA
0x140019050  lea     edi, [rax+20h]
0x140019053  bts     edi, 0Bh
0x140019057  test    [rcx+1Ch], edi
0x14001905a  jz      loc_1400193FA
0x140019060  cmp     [rcx+19h], r13b
0x140019064  jb      loc_1400193FA
0x14001906a  mov     rcx, [rcx+10h]
0x14001906e  lea     edx, [rax+0Bh]
0x140019071  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x140019078  call    WPP_SF_
0x14001907d  jmp     loc_1400193FA
0x140019082  lea     rcx, [rsp+250h+ThreadId]; unsigned int *
0x140019087  call    ?_GetInstance@CLocalMachine@@SAPEAV1@PEAK@Z; CLocalMachine::_GetInstance(ulong *)
0x14001908c  mov     ebx, [rsp+250h+ThreadId]
0x140019090  test    ebx, ebx
0x140019092  jz      short loc_1400190E1
0x140019094  lea     rsi, WPP_GLOBAL_Control
0x14001909b  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400190a2  jz      short loc_1400190D7
0x1400190a4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400190ab  test    rcx, rcx
0x1400190ae  jz      short loc_1400190D7
0x1400190b0  test    dword ptr [rcx+1Ch], 820h
0x1400190b7  jz      short loc_1400190D7
0x1400190b9  cmp     [rcx+19h], r13b
0x1400190bd  jb      short loc_1400190D7
0x1400190bf  mov     rcx, [rcx+10h]
0x1400190c3  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x1400190ca  mov     edx, 0Ch
0x1400190cf  mov     r9d, ebx
0x1400190d2  call    WPP_SF_D
0x1400190d7  mov     ecx, 0C00038B4h
0x1400190dc  jmp     loc_140019B5A
0x1400190e1  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x1400190e6  mov     ecx, [rax+1Ch]
0x1400190e9  mov     cs:?gm_DefaultTimeOut@CLdap@@0KA, ecx; ulong CLdap::gm_DefaultTimeOut
0x1400190ef  call    ?_AllocTlsIndex@CLdap@@SAKXZ; CLdap::_AllocTlsIndex(void)
0x1400190f4  mov     ebx, eax
0x1400190f6  test    eax, eax
0x1400190f8  jz      short loc_140019147
0x1400190fa  lea     rsi, WPP_GLOBAL_Control
0x140019101  cmp     cs:WPP_GLOBAL_Control, rsi
0x140019108  jz      loc_140019B67
0x14001910e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140019115  test    rcx, rcx
0x140019118  jz      loc_140019B67
0x14001911e  mov     edi, 20h ; ' '
0x140019123  bts     edi, 0Bh
0x140019127  test    [rcx+1Ch], edi
0x14001912a  jz      loc_140019B67
0x140019130  cmp     [rcx+19h], r13b
0x140019134  jb      loc_140019B67
0x14001913a  mov     edx, 0Dh
0x14001913f  mov     r9d, eax
0x140019142  jmp     loc_14001900A
0x140019147  call    ?DfsInitializeSecurity@@YAEXZ; DfsInitializeSecurity(void)
0x14001914c  test    al, al
0x14001914e  jnz     short loc_1400191C5
0x140019150  call    cs:__imp_GetLastError
0x140019157  nop     dword ptr [rax+rax+00h]
0x14001915c  xor     edx, edx; unsigned __int16
0x14001915e  xor     r8d, r8d; unsigned __int16 **
0x140019161  mov     r9d, eax; unsigned int
0x140019164  mov     ecx, 0C00038AFh; unsigned int
0x140019169  mov     ebx, eax
0x14001916b  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x140019170  lea     rsi, WPP_GLOBAL_Control
0x140019177  cmp     cs:WPP_GLOBAL_Control, rsi
0x14001917e  jz      loc_140019B67
0x140019184  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001918b  test    rcx, rcx
0x14001918e  jz      loc_140019B67
0x140019194  mov     eax, ebx
0x140019196  mov     edi, 20h ; ' '
0x14001919b  neg     eax
0x14001919d  sbb     edx, edx
0x14001919f  and     edx, 0FFFFFFECh
0x1400191a2  add     edx, 1Fh
0x1400191a5  bts     edi, edx
0x1400191a8  test    [rcx+1Ch], edi
0x1400191ab  jz      loc_140019B67
0x1400191b1  cmp     [rcx+19h], r13b
0x1400191b5  jb      loc_140019B67
0x1400191bb  mov     edx, 0Eh
0x1400191c0  jmp     loc_140019007
0x1400191c5  lea     rax, qword_140071618
0x1400191cc  mov     cs:qword_140071610, r12
0x1400191d3  mov     cs:qword_140071620, rax
0x1400191da  mov     r14d, 8
0x1400191e0  mov     cs:qword_140071618, rax
0x1400191e7  mov     ecx, r14d; Size
0x1400191ea  lea     rax, qword_140071600
0x1400191f1  mov     cs:qword_140071628, r12
0x1400191f8  mov     cs:qword_140071608, rax
0x1400191ff  mov     cs:qword_140071600, rax
0x140019206  mov     cs:qword_140071630, r12
0x14001920d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019212  mov     rdi, rax
0x140019215  test    rax, rax
0x140019218  jz      short loc_140019235
0x14001921a  mov     rcx, rax; this
0x14001921d  mov     [rax], r12
0x140019220  call    ?DfsInitializeSiteCache@DfsSiteNameCache@@QEAAKXZ; DfsSiteNameCache::DfsInitializeSiteCache(void)
0x140019225  mov     ebx, eax
0x140019227  test    eax, eax
0x140019229  jz      short loc_14001923B
0x14001922b  mov     rcx, rdi; Block
0x14001922e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140019233  jmp     short loc_140019238
0x140019235  mov     ebx, r14d
0x140019238  mov     rdi, r12
0x14001923b  mov     [rsp+250h+ThreadId], ebx
0x14001923f  mov     cs:qword_140071558, rdi
0x140019246  test    rdi, rdi
0x140019249  jnz     short loc_1400192B2
0x14001924b  xor     edx, edx; unsigned __int16
0x14001924d  mov     r9d, ebx; unsigned int
0x140019250  xor     r8d, r8d; unsigned __int16 **
0x140019253  mov     ecx, 0C00038B1h; unsigned int
0x140019258  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x14001925d  lea     rsi, WPP_GLOBAL_Control
0x140019264  cmp     cs:WPP_GLOBAL_Control, rsi
0x14001926b  jz      loc_140019B67
0x140019271  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140019278  test    rcx, rcx
0x14001927b  jz      loc_140019B67
0x140019281  mov     eax, ebx
0x140019283  mov     edi, 20h ; ' '
0x140019288  neg     eax
0x14001928a  sbb     edx, edx
0x14001928c  and     edx, 0FFFFFFECh
0x14001928f  add     edx, 1Fh
0x140019292  bts     edi, edx
0x140019295  test    [rcx+1Ch], edi
0x140019298  jz      loc_140019B67
0x14001929e  cmp     [rcx+19h], r13b
0x1400192a2  jb      loc_140019B67
0x1400192a8  mov     edx, 0Fh
0x1400192ad  jmp     loc_140019007
0x1400192b2  mov     edx, 40h ; '@'; unsigned int
0x1400192b7  lea     rcx, [rsp+250h+ThreadId]; unsigned int *
0x1400192bc  call    ?CreateSiteNameSupport@DfsSiteNameSupport@@SAPEAV1@PEAKK@Z; DfsSiteNameSupport::CreateSiteNameSupport(ulong *,ulong)
0x1400192c1  mov     cs:qword_140071560, rax
0x1400192c8  test    rax, rax
0x1400192cb  jnz     short loc_140019338
0x1400192cd  mov     ebx, [rsp+250h+ThreadId]
0x1400192d1  xor     edx, edx; unsigned __int16
0x1400192d3  mov     r9d, ebx; unsigned int
0x1400192d6  xor     r8d, r8d; unsigned __int16 **
0x1400192d9  mov     ecx, 0C00038B1h; unsigned int
0x1400192de  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x1400192e3  lea     rsi, WPP_GLOBAL_Control
0x1400192ea  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400192f1  jz      loc_140019B67
0x1400192f7  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400192fe  test    rcx, rcx
0x140019301  jz      loc_140019B67
0x140019307  mov     eax, ebx
0x140019309  mov     edi, 20h ; ' '
0x14001930e  neg     eax
0x140019310  sbb     edx, edx
0x140019312  and     edx, 0FFFFFFECh
0x140019315  add     edx, 1Fh
0x140019318  bts     edi, edx
0x14001931b  test    [rcx+1Ch], edi
0x14001931e  jz      loc_140019B67
0x140019324  cmp     [rcx+19h], r13b
0x140019328  jb      loc_140019B67
0x14001932e  mov     edx, 10h
0x140019333  jmp     loc_140019007
0x140019338  xorps   xmm0, xmm0
0x14001933b  mov     ecx, 30h ; '0'; Size
0x140019340  movups  xmmword ptr [rsp+250h+SystemTime.wHour], xmm0
0x140019345  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001934a  test    rax, rax
0x14001934d  jz      short loc_140019396
0x14001934f  mov     rcx, rax; this
0x140019352  call    ??0DfsSite@@QEAA@XZ; DfsSite::DfsSite(void)
0x140019357  mov     rbx, rax
0x14001935a  mov     rdi, rax
0x14001935d  test    rax, rax
0x140019360  jz      loc_140019432
0x140019366  xor     edx, edx; SourceString
0x140019368  lea     rcx, [rsp+250h+SystemTime.wHour]; DestinationString
0x14001936d  call    cs:__imp_RtlInitUnicodeString
0x140019374  nop     dword ptr [rax+rax+00h]
0x140019379  lea     rdx, [rsp+250h+SystemTime.wHour]; struct _UNICODE_STRING *
0x14001937e  mov     rcx, rbx; this
0x140019381  call    ?Initialize@DfsSite@@QEAAKPEAU_UNICODE_STRING@@@Z; DfsSite::Initialize(_UNICODE_STRING *)
0x140019386  test    eax, eax
0x140019388  jz      loc_140019432
0x14001938e  mov     rcx, rbx; this
0x140019391  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x140019396  mov     cs:qword_140071568, r12
0x14001939d  xor     edx, edx; unsigned __int16
0x14001939f  mov     r9d, r14d; unsigned int
0x1400193a2  xor     r8d, r8d; unsigned __int16 **
0x1400193a5  mov     ecx, 0C00038B1h; unsigned int
0x1400193aa  mov     ebx, r14d
0x1400193ad  call    ?DfsLogDfsEvent@@YAKKGQEAPEBGK@Z; DfsLogDfsEvent(ulong,ushort,ushort const * * const,ulong)
0x1400193b2  lea     rsi, WPP_GLOBAL_Control
0x1400193b9  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400193c0  jz      short loc_1400193FA
0x1400193c2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400193c9  test    rcx, rcx
0x1400193cc  jz      short loc_1400193FA
  ... truncated ...
```
