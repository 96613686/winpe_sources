# CscServiceMain(ulong,ushort * *)

- ea: `0x180054340`
- end: `0x180054a60`
- name: `?CscServiceMain@@YAXKPEAPEAG@Z`
- size: `1824`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180024880`
- `0x18002f10c`
- `0x180036394`
- `0x180039610`
- `0x18003c460`
- `0x18005409c`
- `0x180054144`
- `0x180054340`
- `0x180054c68`
- `0x180054d80`
- `0x180054e64`
- `0x180055248`
- `0x1800555fc`
- `0x180055a8c`
- `0x18006ffb8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800546c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800549d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800546c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800549d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800543f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800543f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800547a6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005481f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800547a6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005481f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800546b9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180054737`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800549b7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800546b9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180054737`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800549b7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180054463`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180054463`
- `USER32!PeekMessageW` at `0x18005458d`
- `USER32!PeekMessageW` at `0x18005458d`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800545e9`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18005464c`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x1800545e9`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18005464c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180054861`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180054861`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800544f9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800544f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054530`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180054530`

## string_xrefs

- `0x18005445c`: `CscService`

## pseudocode

```c
void __fastcall CscServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int v2; // edi
  int v3; // eax
  signed int LastError; // ebx
  CObjectMonitor *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  int Error; // eax
  CObjectMonitor *v9; // rcx
  SERVICE_STATUS_HANDLE v10; // rcx
  DWORD v11; // eax
  LPVOID ppv; // [rsp+30h] [rbp-49h] BYREF
  struct tagMSG Msg; // [rsp+38h] [rbp-41h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+68h] [rbp-11h] BYREF
  int v15; // [rsp+84h] [rbp+Bh]
  SERVICE_STATUS_HANDLE v16; // [rsp+88h] [rbp+Fh]
  __int64 v17; // [rsp+90h] [rbp+17h]

  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
  _InterlockedOr64(&g_StageMap, 0);
  g_bReady = 0;
  *(_OWORD *)&g_CscServiceInfo.dwServiceType = 0;
  g_bDone = 0;
  *(_OWORD *)&g_CscServiceInfo.dwServiceSpecificExitCode = 0;
  g_hevtStop = 0;
  *(_OWORD *)&hServiceStatus = 0;
  g_hevtDone = 0;
  g_hevtReady = 0;
  g_lEncryptionInProgress = 0;
  g_idServiceMainThread = 0;
  g_hrServiceInit = 0;
  g_hthdPreShutdownCleanup = 0;
  g_idServiceMainThread = GetCurrentThreadId();
  g_CscServiceInfo.dwServiceType = 48;
  g_CscServiceInfo.dwCurrentState = 2;
  *(_QWORD *)&g_CscServiceInfo.dwControlsAccepted = 128;
  *(_QWORD *)&g_CscServiceInfo.dwServiceSpecificExitCode = 0;
  g_CscServiceInfo.dwWaitHint = 0;
  *(&hServiceStatus + 1) = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"CscService", CscService_CtrlHandler, 0);
  if ( !hServiceStatus )
  {
    Error = ResultFromLastError();
    g_hrServiceInit = Error;
    goto LABEL_64;
  }
  v2 = 0;
  _InterlockedOr64(&g_StageMap, 1u);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
  g_hrServiceInit = CscService_CreateGlobalThreadSyncObjects();
  if ( g_hrServiceInit >= 0 )
  {
    _InterlockedOr64(&g_StageMap, 2u);
    _InterlockedOr64(&g_StageMap, 4u);
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
    g_hrServiceInit = CoInitializeEx(0, 0);
    if ( g_hrServiceInit >= 0 )
    {
      ppv = 0;
      v2 = 1;
      if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      _InterlockedOr64(&g_StageMap, 8u);
      memset(&Msg, 0, sizeof(Msg));
      PeekMessageW(&Msg, 0, 0x400u, 0x400u, 0);
      g_hrServiceInit = CscService_Initialize();
      if ( g_hrServiceInit >= 0 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
        }
        g_hrServiceInit = CoRegisterClassObject(
                            &CLSID_OfflineFilesService,
                            &g_ServiceObjectClassFactory,
                            4u,
                            1u,
                            (LPDWORD)&hServiceStatus + 2);
        if ( g_hrServiceInit >= 0 )
        {
          _InterlockedOr64(&g_StageMap, 0x1000u);
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
          }
          g_hrServiceInit = CoRegisterClassObject(
                              &CLSID_OfflineFilesSetting,
                              &g_SettingObjectClassFactory,
                              4u,
                              1u,
                              (LPDWORD)&hServiceStatus + 3);
          if ( g_hrServiceInit >= 0 )
          {
            _InterlockedOr64(&g_StageMap, 0x2000u);
            v3 = CscDriverSetCachingSettings();
            g_hrServiceInit = v3 | 0x10000000;
            if ( v3 >= 0 )
            {
              g_CscServiceInfo.dwCurrentState = 4;
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
              }
              if ( !SetServiceStatus(hServiceStatus, &g_CscServiceInfo) )
              {
                LastError = GetLastError();
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                {
                  goto LABEL_44;
                }
                v6 = 124;
LABEL_43:
                WPP_SF_d(
                  *((_QWORD *)v5 + 2),
                  v6,
                  WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
                  (unsigned int)LastError);
LABEL_44:
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
                g_hrServiceInit = LastError;
                goto LABEL_56;
              }
              g_hrServiceInit = CscService_InitializeMaintenanceTasks();
              if ( g_hrServiceInit < 0 )
                goto LABEL_56;
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
              }
              g_CscServiceInfo.dwControlsAccepted |= 1u;
              if ( !SetServiceStatus(hServiceStatus, &g_CscServiceInfo) )
              {
                LastError = GetLastError();
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                {
                  goto LABEL_44;
                }
                v6 = 126;
                goto LABEL_43;
              }
              _InterlockedOr64(&g_StageMap, 0x40000u);
              CscEvt_ServiceRunning();
              g_bReady = 1;
              SetEvent(g_hevtReady);
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
              }
              v7 = CscService_MainLoop();
              g_hrServiceInit = v7;
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
                v7 = g_hrServiceInit;
              }
              if ( v7 >= 0 )
                CscService_PostShutdownCleanup();
              _InterlockedOr64(&g_StageMap, 0x8000000u);
            }
          }
        }
      }
    }
LABEL_56:
    SetEvent(g_hevtReady);
    Error = g_hrServiceInit;
    if ( g_hrServiceInit >= 0 )
      goto LABEL_58;
  }
  CscService_FailedInitCleanup();
  Error = g_hrServiceInit;
LABEL_58:
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
    CoUninitialize();
    _InterlockedOr64(&g_StageMap, 0x40000000u);
    Error = g_hrServiceInit;
  }
LABEL_64:
  if ( Error >= 0 )
  {
LABEL_68:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_69;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control )
    goto LABEL_72;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      130,
      WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
      (unsigned int)Error);
    goto LABEL_68;
  }
LABEL_69:
  if ( v9 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v9 + 2), 131, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
LABEL_72:
  CscService_DestroyGlobalThreadSyncObjects();
  _InterlockedOr64(&g_StageMap, 0x80000000);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      132,
      WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
      (unsigned int)g_hrServiceInit);
  v10 = hServiceStatus;
  ServiceStatus.dwServiceType = g_CscServiceInfo.dwServiceType;
  ServiceStatus.dwControlsAccepted = g_CscServiceInfo.dwControlsAccepted;
  ServiceStatus.dwServiceSpecificExitCode = g_CscServiceInfo.dwServiceSpecificExitCode;
  ServiceStatus.dwCheckPoint = g_CscServiceInfo.dwCheckPoint;
  ServiceStatus.dwWaitHint = g_CscServiceInfo.dwWaitHint;
  ServiceStatus.dwWin32ExitCode = (unsigned __int16)g_hrServiceInit;
  v15 = 0;
  v17 = 0;
  ServiceStatus.dwCurrentState = 1;
  v16 = hServiceStatus;
  g_bReady = 0;
  g_bDone = 0;
  g_hevtStop = 0;
  g_hevtDone = 0;
  g_hevtReady = 0;
  g_idServiceMainThread = 0;
  g_hrServiceInit = 0;
  g_hthdPreShutdownCleanup = 0;
  *(_OWORD *)&g_CscServiceInfo.dwServiceType = 0;
  *(_OWORD *)&g_CscServiceInfo.dwServiceSpecificExitCode = 0;
  *(_OWORD *)&hServiceStatus = 0;
  g_lEncryptionInProgress = 0;
  if ( v16 )
  {
    if ( SetServiceStatus(v10, &ServiceStatus) )
    {
      _InterlockedOr64(&g_StageMap, 0x100000000uLL);
    }
    else if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, v11);
    }
  }
  CscEvt_ServiceTerminated();
  _InterlockedOr64(&g_StageMap, 0x200000000uLL);
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids);
}

```

## disassembly

```asm
0x180054340  push    rbp
0x180054342  push    rbx
0x180054343  push    rsi
0x180054344  push    rdi
0x180054345  push    r13
0x180054347  push    r14
0x180054349  push    r15
0x18005434b  lea     rbp, [rsp-27h]
0x180054350  sub     rsp, 0A0h
0x180054357  mov     rax, cs:__security_cookie
0x18005435e  xor     rax, rsp
0x180054361  mov     [rbp+57h+var_38], rax
0x180054365  mov     rcx, cs:WPP_GLOBAL_Control
0x18005436c  lea     r14, WPP_GLOBAL_Control
0x180054373  lea     r15, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x18005437a  cmp     rcx, r14
0x18005437d  jz      short loc_180054396
0x18005437f  test    byte ptr [rcx+1Ch], 8
0x180054383  jz      short loc_180054396
0x180054385  mov     rcx, [rcx+10h]
0x180054389  mov     edx, 75h ; 'u'
0x18005438e  mov     r8, r15
0x180054391  call    WPP_SF_
0x180054396  xor     esi, esi
0x180054398  lock or cs:?g_StageMap@@3_JA, rsi; __int64 g_StageMap
0x1800543a0  xorps   xmm0, xmm0
0x1800543a3  mov     cs:?g_bReady@@3HA, esi; int g_bReady
0x1800543a9  movups  xmmword ptr cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwServiceType, xmm0; CSC_SERVICE_INFO g_CscServiceInfo ...
0x1800543b0  mov     cs:?g_bDone@@3HA, esi; int g_bDone
0x1800543b6  movups  xmmword ptr cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwServiceSpecificExitCode, xmm0; CSC_SERVICE_INFO g_CscServiceInfo ...
0x1800543bd  mov     cs:?g_hevtStop@@3PEAXEA, rsi; void * g_hevtStop
0x1800543c4  movups  cs:hServiceStatus, xmm0
0x1800543cb  mov     cs:?g_hevtDone@@3PEAXEA, rsi; void * g_hevtDone
0x1800543d2  mov     cs:?g_hevtReady@@3PEAXEA, rsi; void * g_hevtReady
0x1800543d9  mov     cs:?g_lEncryptionInProgress@@3JC, esi; long volatile g_lEncryptionInProgress
0x1800543df  mov     cs:?g_idServiceMainThread@@3KA, esi; ulong g_idServiceMainThread
0x1800543e5  mov     cs:?g_hrServiceInit@@3JA, esi; long g_hrServiceInit
0x1800543eb  mov     cs:?g_hthdPreShutdownCleanup@@3PEAXEA, rsi; void * g_hthdPreShutdownCleanup
0x1800543f2  call    cs:__imp_GetCurrentThreadId
0x1800543f8  mov     cs:?g_idServiceMainThread@@3KA, eax; ulong g_idServiceMainThread
0x1800543fe  mov     cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwServiceType, 30h ; '0'; CSC_SERVICE_INFO g_CscServiceInfo ...
0x180054408  mov     cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwCurrentState, 2; CSC_SERVICE_INFO g_CscServiceInfo ...
0x180054412  mov     qword ptr cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwControlsAccepted, 80h; CSC_SERVICE_INFO g_CscServiceInfo ...
0x18005441d  mov     qword ptr cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwServiceSpecificExitCode, rsi; CSC_SERVICE_INFO g_CscServiceInfo ...
0x180054424  mov     cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwWaitHint, esi; CSC_SERVICE_INFO g_CscServiceInfo ...
0x18005442a  mov     qword ptr cs:hServiceStatus+8, rsi
0x180054431  mov     rcx, cs:WPP_GLOBAL_Control
0x180054438  cmp     rcx, r14
0x18005443b  jz      short loc_180054452
0x18005443d  test    byte ptr [rcx+1Ch], 8
0x180054441  jz      short loc_180054452
0x180054443  mov     rcx, [rcx+10h]
0x180054447  lea     edx, [rsi+76h]
0x18005444a  mov     r8, r15
0x18005444d  call    WPP_SF_
0x180054452  xor     r8d, r8d; lpContext
0x180054455  lea     rdx, ?CscService_CtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18005445c  lea     rcx, ServiceName; "CscService"
0x180054463  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180054469  mov     qword ptr cs:hServiceStatus, rax
0x180054470  mov     r13d, 1
0x180054476  test    rax, rax
0x180054479  jz      loc_18005487B
0x18005447f  mov     edi, esi
0x180054481  lock or cs:?g_StageMap@@3_JA, r13; __int64 g_StageMap
0x180054489  mov     rcx, cs:WPP_GLOBAL_Control
0x180054490  cmp     rcx, r14
0x180054493  jz      short loc_1800544AB
0x180054495  test    byte ptr [rcx+1Ch], 8
0x180054499  jz      short loc_1800544AB
0x18005449b  mov     rcx, [rcx+10h]
0x18005449f  lea     edx, [r13+76h]
0x1800544a3  mov     r8, r15
0x1800544a6  call    WPP_SF_
0x1800544ab  call    ?CscService_CreateGlobalThreadSyncObjects@@YAJXZ; CscService_CreateGlobalThreadSyncObjects(void)
0x1800544b0  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x1800544b6  test    eax, eax
0x1800544b8  js      loc_18005482F
0x1800544be  lock or cs:?g_StageMap@@3_JA, 2; __int64 g_StageMap
0x1800544c7  mov     ebx, 4
0x1800544cc  lock or cs:?g_StageMap@@3_JA, rbx; __int64 g_StageMap
0x1800544d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544db  cmp     rcx, r14
0x1800544de  jz      short loc_1800544F5
0x1800544e0  test    byte ptr [rcx+1Ch], 8
0x1800544e4  jz      short loc_1800544F5
0x1800544e6  mov     rcx, [rcx+10h]
0x1800544ea  lea     edx, [rbx+74h]
0x1800544ed  mov     r8, r15
0x1800544f0  call    WPP_SF_
0x1800544f5  xor     edx, edx; dwCoInit
0x1800544f7  xor     ecx, ecx; pvReserved
0x1800544f9  call    cs:__imp_CoInitializeEx
0x1800544ff  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x180054505  test    eax, eax
0x180054507  js      loc_180054818
0x18005450d  lea     rax, [rbp+57h+var_A0]
0x180054511  mov     [rbp+57h+var_A0], rsi
0x180054515  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18005451c  mov     [rsp+0D0h+ppv], rax; ppv
0x180054521  mov     r8d, r13d; dwClsContext
0x180054524  lea     rcx, CLSID_GlobalOptions; rclsid
0x18005452b  xor     edx, edx; pUnkOuter
0x18005452d  mov     edi, r13d
0x180054530  call    cs:__imp_CoCreateInstance
0x180054536  test    eax, eax
0x180054538  js      short loc_180054562
0x18005453a  mov     rcx, [rbp+57h+var_A0]
0x18005453e  mov     r8, r13
0x180054541  mov     edx, 5
0x180054546  mov     rax, [rcx]
0x180054549  mov     rax, [rax+18h]
0x18005454d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054552  mov     rcx, [rbp+57h+var_A0]
0x180054556  mov     rax, [rcx]
0x180054559  mov     rax, [rax+10h]
0x18005455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054562  lock or cs:?g_StageMap@@3_JA, 8; __int64 g_StageMap
0x18005456b  xorps   xmm0, xmm0
0x18005456e  mov     dword ptr [rsp+0D0h+ppv], esi; wRemoveMsg
0x180054572  mov     r8d, 400h; wMsgFilterMin
0x180054578  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18005457c  mov     r9d, r8d; wMsgFilterMax
0x18005457f  xor     edx, edx; hWnd
0x180054581  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180054585  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180054589  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18005458d  call    cs:__imp_PeekMessageW
0x180054593  call    ?CscService_Initialize@@YAJXZ; CscService_Initialize(void)
0x180054598  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x18005459e  test    eax, eax
0x1800545a0  js      loc_180054818
0x1800545a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800545ad  cmp     rcx, r14
0x1800545b0  jz      short loc_1800545C9
0x1800545b2  test    byte ptr [rcx+1Ch], 8
0x1800545b6  jz      short loc_1800545C9
0x1800545b8  mov     rcx, [rcx+10h]
0x1800545bc  mov     edx, 79h ; 'y'
0x1800545c1  mov     r8, r15
0x1800545c4  call    WPP_SF_
0x1800545c9  lea     rax, hServiceStatus+8
0x1800545d0  mov     r9d, r13d; flags
0x1800545d3  mov     r8d, ebx; dwClsContext
0x1800545d6  mov     [rsp+0D0h+ppv], rax; lpdwRegister
0x1800545db  lea     rdx, ?g_ServiceObjectClassFactory@@3VCClassFactory@@A; pUnk
0x1800545e2  lea     rcx, CLSID_OfflineFilesService; rclsid
0x1800545e9  call    cs:__imp_CoRegisterClassObject
0x1800545ef  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x1800545f5  test    eax, eax
0x1800545f7  js      loc_180054818
0x1800545fd  lock or cs:?g_StageMap@@3_JA, 1000h; __int64 g_StageMap
0x180054609  mov     rcx, cs:WPP_GLOBAL_Control
0x180054610  cmp     rcx, r14
0x180054613  jz      short loc_18005462C
0x180054615  test    byte ptr [rcx+1Ch], 8
0x180054619  jz      short loc_18005462C
0x18005461b  mov     rcx, [rcx+10h]
0x18005461f  mov     edx, 7Ah ; 'z'
0x180054624  mov     r8, r15
0x180054627  call    WPP_SF_
0x18005462c  lea     rax, hServiceStatus+0Ch
0x180054633  mov     r9d, r13d; flags
0x180054636  mov     r8d, ebx; dwClsContext
0x180054639  mov     [rsp+0D0h+ppv], rax; lpdwRegister
0x18005463e  lea     rdx, ?g_SettingObjectClassFactory@@3VCClassFactory@@A; pUnk
0x180054645  lea     rcx, CLSID_OfflineFilesSetting; rclsid
0x18005464c  call    cs:__imp_CoRegisterClassObject
0x180054652  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x180054658  test    eax, eax
0x18005465a  js      loc_180054818
0x180054660  lock or cs:?g_StageMap@@3_JA, 2000h; __int64 g_StageMap
0x18005466c  call    CscDriverSetCachingSettings
0x180054671  or      eax, 10000000h
0x180054676  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x18005467c  jl      loc_180054818
0x180054682  mov     cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwCurrentState, ebx; CSC_SERVICE_INFO g_CscServiceInfo ...
0x180054688  mov     rcx, cs:WPP_GLOBAL_Control
0x18005468f  cmp     rcx, r14
0x180054692  jz      short loc_1800546AB
0x180054694  test    byte ptr [rcx+1Ch], 8
0x180054698  jz      short loc_1800546AB
0x18005469a  mov     rcx, [rcx+10h]
0x18005469e  mov     edx, 7Bh ; '{'
0x1800546a3  mov     r8, r15
0x1800546a6  call    WPP_SF_
0x1800546ab  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x1800546b2  lea     rdx, ?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A; lpServiceStatus
0x1800546b9  call    cs:__imp_SetServiceStatus
0x1800546bf  test    eax, eax
0x1800546c1  jnz     short loc_1800546EC
0x1800546c3  call    cs:__imp_GetLastError
0x1800546c9  mov     ebx, eax
0x1800546cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800546d2  cmp     rcx, r14
0x1800546d5  jz      loc_18005476F
0x1800546db  test    byte ptr [rcx+1Ch], 2
0x1800546df  jz      loc_18005476F
0x1800546e5  mov     edx, 7Ch ; '|'
0x1800546ea  jmp     short loc_180054760
0x1800546ec  call    ?CscService_InitializeMaintenanceTasks@@YAJXZ; CscService_InitializeMaintenanceTasks(void)
0x1800546f1  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x1800546f7  test    eax, eax
0x1800546f9  js      loc_180054818
0x1800546ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180054706  cmp     rcx, r14
0x180054709  jz      short loc_180054722
0x18005470b  test    byte ptr [rcx+1Ch], 8
0x18005470f  jz      short loc_180054722
0x180054711  mov     rcx, [rcx+10h]
0x180054715  mov     edx, 7Dh ; '}'
0x18005471a  mov     r8, r15
0x18005471d  call    WPP_SF_
0x180054722  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x180054729  lea     rdx, ?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A; lpServiceStatus
0x180054730  or      cs:?g_CscServiceInfo@@3UCSC_SERVICE_INFO@@A.dwControlsAccepted, r13d; CSC_SERVICE_INFO g_CscServiceInfo ...
0x180054737  call    cs:__imp_SetServiceStatus
0x18005473d  test    eax, eax
0x18005473f  jnz     short loc_180054787
0x180054741  call    cs:__imp_GetLastError
0x180054747  mov     ebx, eax
0x180054749  mov     rcx, cs:WPP_GLOBAL_Control
0x180054750  cmp     rcx, r14
0x180054753  jz      short loc_18005476F
0x180054755  test    byte ptr [rcx+1Ch], 2
0x180054759  jz      short loc_18005476F
0x18005475b  mov     edx, 7Eh ; '~'
0x180054760  mov     rcx, [rcx+10h]
0x180054764  mov     r9d, ebx
0x180054767  mov     r8, r15
0x18005476a  call    WPP_SF_d
0x18005476f  test    ebx, ebx
0x180054771  jle     short loc_18005477C
0x180054773  movzx   ebx, bx
0x180054776  or      ebx, 80070000h
0x18005477c  mov     cs:?g_hrServiceInit@@3JA, ebx; long g_hrServiceInit
0x180054782  jmp     loc_180054818
0x180054787  lock or cs:?g_StageMap@@3_JA, 40000h; __int64 g_StageMap
0x180054793  call    ?CscEvt_ServiceRunning@@YAKXZ; CscEvt_ServiceRunning(void)
0x180054798  mov     rcx, cs:?g_hevtReady@@3PEAXEA; hEvent
0x18005479f  mov     cs:?g_bReady@@3HA, r13d; int g_bReady
0x1800547a6  call    cs:__imp_SetEvent
0x1800547ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547b3  cmp     rcx, r14
0x1800547b6  jz      short loc_1800547CF
0x1800547b8  test    byte ptr [rcx+1Ch], 8
0x1800547bc  jz      short loc_1800547CF
0x1800547be  mov     rcx, [rcx+10h]
0x1800547c2  mov     edx, 7Fh
0x1800547c7  mov     r8, r15
0x1800547ca  call    WPP_SF_
0x1800547cf  call    ?CscService_MainLoop@@YAJXZ; CscService_MainLoop(void)
0x1800547d4  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x1800547da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800547e1  cmp     rcx, r14
0x1800547e4  jz      short loc_180054803
0x1800547e6  test    byte ptr [rcx+1Ch], 8
0x1800547ea  jz      short loc_180054803
0x1800547ec  mov     rcx, [rcx+10h]
0x1800547f0  mov     edx, 80h
0x1800547f5  mov     r8, r15
0x1800547f8  call    WPP_SF_
0x1800547fd  mov     eax, cs:?g_hrServiceInit@@3JA; long g_hrServiceInit
0x180054803  test    eax, eax
0x180054805  js      short loc_18005480C
0x180054807  call    ?CscService_PostShutdownCleanup@@YAXXZ; CscService_PostShutdownCleanup(void)
0x18005480c  lock or cs:?g_StageMap@@3_JA, 8000000h; __int64 g_StageMap
0x180054818  mov     rcx, cs:?g_hevtReady@@3PEAXEA; hEvent
0x18005481f  call    cs:__imp_SetEvent
0x180054825  mov     eax, cs:?g_hrServiceInit@@3JA; long g_hrServiceInit
0x18005482b  test    eax, eax
0x18005482d  jns     short loc_18005483A
0x18005482f  call    ?CscService_FailedInitCleanup@@YAXXZ; CscService_FailedInitCleanup(void)
0x180054834  mov     eax, cs:?g_hrServiceInit@@3JA; long g_hrServiceInit
0x18005483a  test    edi, edi
0x18005483c  jz      short loc_180054886
0x18005483e  mov     rcx, cs:WPP_GLOBAL_Control
0x180054845  cmp     rcx, r14
0x180054848  jz      short loc_180054861
0x18005484a  test    byte ptr [rcx+1Ch], 8
0x18005484e  jz      short loc_180054861
0x180054850  mov     rcx, [rcx+10h]
0x180054854  mov     edx, 81h
0x180054859  mov     r8, r15
0x18005485c  call    WPP_SF_
0x180054861  call    cs:__imp_CoUninitialize
0x180054867  lock or cs:?g_StageMap@@3_JA, 40000000h; __int64 g_StageMap
0x180054873  mov     eax, cs:?g_hrServiceInit@@3JA; long g_hrServiceInit
0x180054879  jmp     short loc_180054886
0x18005487b  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180054880  mov     cs:?g_hrServiceInit@@3JA, eax; long g_hrServiceInit
0x180054886  test    eax, eax
0x180054888  jns     short loc_1800548B0
0x18005488a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054891  cmp     rcx, r14
0x180054894  jz      short loc_1800548D3
0x180054896  test    byte ptr [rcx+1Ch], 2
0x18005489a  jz      short loc_1800548B7
0x18005489c  mov     rcx, [rcx+10h]
0x1800548a0  mov     edx, 82h
  ... truncated ...
```
