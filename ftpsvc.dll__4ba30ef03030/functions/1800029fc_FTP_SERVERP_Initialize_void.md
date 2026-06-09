# FTP_SERVERP::Initialize(void)

- ea: `0x1800029fc`
- end: `0x180003bd1`
- name: `?Initialize@FTP_SERVERP@@QEAAJXZ`
- size: `4565`
- prototype: `__int64 __fastcall(FTP_SERVERP *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005b60`

## callees

- `0x180001210`
- `0x180001250`
- `0x180001814`
- `0x180001fe8`
- `0x1800026b4`
- `0x1800029fc`
- `0x180003bd8`
- `0x180003f78`
- `0x180004a18`
- `0x180007244`
- `0x180008418`
- `0x18000af60`
- `0x18000b308`
- `0x18000bdac`
- `0x1800115f8`
- `0x18001386c`
- `0x1800171ec`
- `0x18001e53c`
- `0x18001fc30`
- `0x180021a98`
- `0x180021d70`
- `0x180021e94`
- `0x180022ca0`
- `0x180023860`
- `0x180023f3c`
- `0x1800252dc`
- `0x180025a58`
- `0x18002f540`
- `0x180033d3c`
- `0x180046cf0`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180002e92`
- `KERNEL32!CreateTimerQueueTimer` at `0x180002fbc`
- `KERNEL32!CreateTimerQueueTimer` at `0x180003a8a`
- `KERNEL32!CreateTimerQueueTimer` at `0x180002e92`
- `KERNEL32!CreateTimerQueueTimer` at `0x180002fbc`
- `KERNEL32!CreateTimerQueueTimer` at `0x180003a8a`
- `KERNEL32!FreeLibrary` at `0x1800033fb`
- `KERNEL32!FreeLibrary` at `0x1800033fb`
- `KERNEL32!InitializeCriticalSection` at `0x180003a2a`
- `KERNEL32!InitializeCriticalSection` at `0x180003a2a`
- `KERNEL32!GetLastError` at `0x180002e9c`
- `KERNEL32!GetLastError` at `0x180002fc6`
- `KERNEL32!GetLastError` at `0x180003a94`
- `KERNEL32!GetLastError` at `0x180002e9c`
- `KERNEL32!GetLastError` at `0x180002fc6`
- `KERNEL32!GetLastError` at `0x180003a94`
- `KERNEL32!GetSystemInfo` at `0x180002fee`
- `KERNEL32!GetSystemInfo` at `0x180002fee`
- `WS2_32!GetHostNameW` at `0x180002d59`
- `WS2_32!GetHostNameW` at `0x180002d59`
- `WS2_32!__imp_WSAStartup` at `0x180002c6b`
- `WS2_32!__imp_WSAStartup` at `0x180002c6b`
- `WS2_32!__imp_WSACleanup` at `0x180002ced`
- `WS2_32!__imp_WSACleanup` at `0x180002ced`
- `ole32!CoRegisterClassObject` at `0x18000373a`
- `ole32!CoRegisterClassObject` at `0x18000373a`
- `ole32!CoUninitialize` at `0x180002c50`
- `ole32!CoUninitialize` at `0x180002c50`
- `ole32!CoInitializeEx` at `0x180002bdf`
- `ole32!CoInitializeEx` at `0x180002bdf`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002b89`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002bb8`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002b89`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002bb8`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800035fd`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800035fd`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180002e5b`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x18000323e`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x18000337a`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x1800034b4`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180002e5b`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x18000323e`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x18000337a`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x1800034b4`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180002e2e`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003214`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003320`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003496`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180002e2e`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003214`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003320`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180003496`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000329f`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003419`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000329f`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180003419`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d90`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002d90`
- `iisutil!InitializeLocalRequest` at `0x180002cff`
- `iisutil!InitializeLocalRequest` at `0x180002cff`
- `iisutil!PuDbgPrint` at `0x180002ca5`
- `iisutil!PuDbgPrint` at `0x180002d3b`
- `iisutil!PuDbgPrint` at `0x18000307b`
- `iisutil!PuDbgPrint` at `0x180002ca5`
- `iisutil!PuDbgPrint` at `0x180002d3b`
- `iisutil!PuDbgPrint` at `0x18000307b`
- `iisutil!HandleMigration` at `0x180002b96`
- `iisutil!HandleMigration` at `0x180002b96`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180002b14`
- `iisutil!?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z` at `0x180002b14`
- `iisutil!PuDbgPrintError` at `0x180002b6d`
- `iisutil!PuDbgPrintError` at `0x180002c4a`
- `iisutil!PuDbgPrintError` at `0x180002ce7`
- `iisutil!PuDbgPrintError` at `0x180002ee1`
- `iisutil!PuDbgPrintError` at `0x180003189`
- `iisutil!PuDbgPrintError` at `0x18000328a`
- `iisutil!PuDbgPrintError` at `0x1800033dd`
- `iisutil!PuDbgPrintError` at `0x180003772`
- `iisutil!PuDbgPrintError` at `0x180003840`
- `iisutil!PuDbgPrintError` at `0x180003935`
- `iisutil!PuDbgPrintError` at `0x18000399f`
- `iisutil!PuDbgPrintError` at `0x180003b84`
- `iisutil!PuDbgPrintError` at `0x180002b6d`
- `iisutil!PuDbgPrintError` at `0x180002c4a`
- `iisutil!PuDbgPrintError` at `0x180002ce7`
- `iisutil!PuDbgPrintError` at `0x180002ee1`
- `iisutil!PuDbgPrintError` at `0x180003189`
- `iisutil!PuDbgPrintError` at `0x18000328a`
- `iisutil!PuDbgPrintError` at `0x1800033dd`
- `iisutil!PuDbgPrintError` at `0x180003772`
- `iisutil!PuDbgPrintError` at `0x180003840`
- `iisutil!PuDbgPrintError` at `0x180003935`
- `iisutil!PuDbgPrintError` at `0x18000399f`
- `iisutil!PuDbgPrintError` at `0x180003b84`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002aa5`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x180002aa5`

## string_xrefs

- `0x180002bf8`: `Could not initialize COM.`
- `0x180002c27`: `CoInitializeSecurity failed.`
- `0x180002dad`: `Could not copy local host name 0x%x\n`
- `0x180003b5d`: `Could not create FTP_LOG_NT_EVENT_TABLE\n`
- `0x180003026`: `System\CurrentControlSet\Services\FTPSVC\Parameters`
- `0x18000305c`: `Failed to create ThreadPool for Strmfilt\n`
- `0x180003b40`: `Failed to allocate memory for CREDENTIALS_CACHE\n`
- `0x180003267`: `Failed to initialize CREDENTIALS_CACHE\n`
- `0x180003b23`: `Failed to allocate memory for TOKEN_CACHE\n`
- `0x1800033ba`: `Failed to initialize TOKEN_CACHE\n`
- `0x180003ae5`: `Failed to initialize FTP_SITE_CONFIG\n`
- `0x180003a53`: `Failed to allocate memory for FTP_SQM_WRITER\n`
- `0x1800035f3`: `FTP_SITE_CONFIG`
- `0x180003316`: `TOKEN_CACHE`
- `0x18000320a`: `CREDENTIALS_CACHE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SERVERP::Initialize(FTP_SERVERP *this)
{
  FTP_SERVERP *v1; // rdi
  EVENT_LOG *v2; // rax
  EVENT_LOG *v3; // rax
  int PortRange; // ebx
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  bool v8; // sf
  FTP_SERVERP *v9; // rcx
  __int64 v10; // r8
  const char *v11; // rax
  __int64 v12; // r8
  int v13; // eax
  int v14; // eax
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  signed int LastError; // eax
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  unsigned __int64 v19; // r13
  __int64 v20; // rax
  bool v21; // cf
  size_t v22; // rax
  unsigned __int64 *v23; // rax
  _QWORD *v24; // rbx
  signed int v25; // eax
  DWORD dwNumberOfProcessors; // eax
  FTP_SITE_MANAGER *v27; // rax
  FTP_SITE_MANAGER *v28; // rax
  const char *v29; // rax
  void *v30; // rsi
  CLKRHashTable *v31; // rbx
  void *v32; // rsi
  CLKRHashTable *v33; // rbx
  int v34; // edx
  int v35; // r8d
  CLKRHashTable *v36; // rsi
  HMODULE v37; // rcx
  CLKRHashTable *v38; // rbx
  FTP_SERVERP *v39; // rcx
  ALLOC_CACHE_HANDLER *v40; // rax
  ALLOC_CACHE_HANDLER *v41; // rax
  _DWORD *v42; // rbx
  _DWORD *v43; // rax
  _DWORD *v44; // rax
  void *v45; // rsi
  int v46; // edx
  _DWORD *v47; // rbx
  void (__fastcall ***v48)(_QWORD, __int64); // rcx
  char *v49; // rax
  void **v50; // rbx
  signed int v51; // eax
  bool v52; // sf
  void (__fastcall ***v53)(_QWORD, __int64); // rcx
  int DueTime; // [rsp+28h] [rbp-E0h]
  DWORD Period[2]; // [rsp+30h] [rbp-D8h]
  const char *Perioda; // [rsp+30h] [rbp-D8h]
  int Periodb; // [rsp+30h] [rbp-D8h]
  unsigned __int16 v59; // [rsp+60h] [rbp-A8h] BYREF
  unsigned __int16 v60; // [rsp+64h] [rbp-A4h] BYREF
  _BYTE v61[80]; // [rsp+68h] [rbp-A0h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+C8h] [rbp-40h] BYREF
  _DWORD v63[4]; // [rsp+F8h] [rbp-10h] BYREF
  WSAData WSAData; // [rsp+108h] [rbp+0h] BYREF
  WCHAR name[1032]; // [rsp+2A8h] [rbp+1A0h] BYREF

  v1 = g_pFtpServer;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  memset_0(v61, 0, 0x54u);
  memset_0(&WSAData, 0, sizeof(WSAData));
  v60 = 0;
  v59 = 0;
  memset_0(name, 0, 0x802u);
  v2 = (EVENT_LOG *)operator new(4u);
  if ( v2 )
    v3 = EVENT_LOG::EVENT_LOG(v2, L"FTPSVC");
  else
    v3 = 0;
  FTP_LOG_NT_EVENT::sm_pEventLog = v3;
  if ( !v3 )
  {
    PortRange = -2147024882;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        73,
        "FTP_SERVERP::Initialize",
        -2147024882,
        "NT event log initialization failed.");
    goto LABEL_216;
  }
  *((_DWORD *)v1 + 2) = 1;
  v5 = CEtwTracer::Register(
         (FTP_SERVERP *)((char *)v1 + 16),
         &`FTPServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid,
         0,
         0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        94,
        "FTP_SERVERP::Initialize",
        v6,
        "Warning: ETW initialization failed.");
    EVENT_LOG::LogEvent((EVENT_LOG *)FTP_LOG_NT_EVENT::sm_pEventLog, 0x80000025, 0, 0, v6);
  }
  *((_DWORD *)v1 + 2) = 2;
  v7 = SETUP_HELPER::HandleMigration();
  PortRange = v7;
  if ( !v7 )
  {
    *((_DWORD *)v1 + 2) = 3;
    PortRange = CoInitializeEx(0, 0);
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        Perioda = "Could not initialize COM.";
        DueTime = PortRange;
        v10 = 137;
LABEL_215:
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          v10,
          "FTP_SERVERP::Initialize",
          DueTime,
          Perioda);
        goto LABEL_216;
      }
      goto LABEL_216;
    }
    PortRange = FTP_SERVERP::InitializeCOMSecurity(v9);
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          146,
          "FTP_SERVERP::Initialize",
          PortRange,
          "CoInitializeSecurity failed.");
      CoUninitialize();
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 4;
    if ( WSAStartup(2u, &WSAData) )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        return (unsigned int)PortRange;
      v11 = "Could not initialize winsock 0x%x\n";
      v12 = 163;
LABEL_26:
      Period[0] = PortRange;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        v12,
        "FTP_SERVERP::Initialize",
        v11,
        *(_QWORD *)Period);
      return (unsigned int)PortRange;
    }
    PortRange = FTP_ASYNC_SOCKET::GlobalInitialize();
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          172,
          "FTP_SERVERP::Initialize",
          PortRange,
          "Could not initialize sockets\n");
      WSACleanup();
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 5;
    v13 = InitializeLocalRequest();
    PortRange = v13;
    if ( v13 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        Period[0] = v13;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          194,
          "FTP_SERVERP::Initialize",
          "Could not initialize list of local addresses 0x%x\n",
          *(_QWORD *)Period);
      }
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 6;
    if ( GetHostNameW(name, 1024) < 0 )
    {
      if ( (g_dwDebugFlags & 3) == 0 )
        return (unsigned int)PortRange;
      v11 = "Could not lookup the local host name 0x%x\n";
      v12 = 210;
      goto LABEL_26;
    }
    v14 = STRU::Copy((FTP_SERVERP *)((char *)v1 + 248), name);
    PortRange = v14;
    if ( v14 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        Period[0] = v14;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          222,
          "FTP_SERVERP::Initialize",
          "Could not copy local host name 0x%x\n",
          *(_QWORD *)Period);
      }
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 7;
    v15 = operator new(0x58u);
    v16 = v15;
    if ( v15 )
    {
      CLKRHashTable::CLKRHashTable(
        (CLKRHashTable *)(v15 + 1),
        "FTP_LOG_NT_EVENT_TABLE",
        (unsigned __int64 (*)(const void *))CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_ExtractKey,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      *v16 = &FTP_LOG_NT_EVENT_TABLE::`vftable';
      v16[10] = 0;
    }
    else
    {
      v16 = 0;
    }
    *((_QWORD *)v1 + 18) = v16;
    if ( !v16 || !CLKRHashTable::IsValid((CLKRHashTable *)(v16 + 1)) )
    {
      PortRange = -2147024888;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_216;
      v29 = "Could not create FTP_LOG_NT_EVENT_TABLE\n";
      v10 = 329;
      goto LABEL_214;
    }
    if ( !CreateTimerQueueTimer(
            (PHANDLE)(*((_QWORD *)v1 + 18) + 80LL),
            0,
            FTP_LOG_NT_EVENT_TABLE::ScavengerCallback,
            *((PVOID *)v1 + 18),
            0x493E0u,
            0x493E0u,
            0x10u) )
    {
      LastError = GetLastError();
      PortRange = LastError;
      if ( LastError > 0 )
        PortRange = (unsigned __int16)LastError | 0x80070000;
      if ( PortRange < 0 )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
            338,
            "FTP_SERVERP::Initialize",
            PortRange,
            "Could not initialize FTP_LOG_NT_EVENT_TABLE\n");
        v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v1 + 18);
        if ( v18 )
          (**v18)(v18, 1);
        *((_QWORD *)v1 + 18) = 0;
        goto LABEL_216;
      }
    }
    *((_DWORD *)v1 + 2) = 12;
    v19 = *((unsigned int *)v1 + 35);
    v20 = 24 * v19;
    if ( !is_mul_ok(v19, 0x18u) )
      v20 = -1;
    v21 = __CFADD__(v20, 8);
    v22 = v20 + 8;
    if ( v21 )
      v22 = -1;
    v23 = (unsigned __int64 *)operator new(v22);
    if ( v23 )
    {
      *v23 = v19;
      v24 = v23 + 1;
      `eh vector constructor iterator'(
        v23 + 1,
        0x18u,
        v19,
        (void (*)(void *))TIMER_WHEEL_SLOT::TIMER_WHEEL_SLOT,
        (void (*)(void *))TIMER_WHEEL_SLOT::~TIMER_WHEEL_SLOT);
    }
    else
    {
      v24 = 0;
    }
    *((_QWORD *)v1 + 14) = v24;
    if ( !v24 )
    {
      PortRange = -2147024888;
      goto LABEL_216;
    }
    if ( !CreateTimerQueueTimer(
            (PHANDLE)v1 + 16,
            0,
            (WAITORTIMERCALLBACK)FTP_TIMEOUT_MONITOR::DoExpirationCheck,
            (char *)v1 + 112,
            *((_DWORD *)v1 + 34),
            *((_DWORD *)v1 + 34),
            0x10u) )
    {
      v25 = GetLastError();
      PortRange = v25;
      if ( v25 > 0 )
        PortRange = (unsigned __int16)v25 | 0x80070000;
      if ( PortRange < 0 )
        goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 13;
    GetSystemInfo(&SystemInfo);
    PortRange = InitializeThreadPoolConfigWithDefaults((struct THREAD_POOL_CONFIG *)v61);
    if ( PortRange < 0 )
      goto LABEL_216;
    *(_QWORD *)&v61[12] = 600000;
    *(_DWORD *)v61 = 2;
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    if ( SystemInfo.dwNumberOfProcessors < 2 )
      dwNumberOfProcessors = 2;
    *(_DWORD *)&v61[8] = dwNumberOfProcessors;
    PortRange = OverrideThreadPoolConfigWithRegistry(
                  (struct THREAD_POOL_CONFIG *)v61,
                  L"System\\CurrentControlSet\\Services\\FTPSVC\\Parameters");
    if ( PortRange < 0 )
      goto LABEL_216;
    if ( !(unsigned int)THREAD_POOL::CreateThreadPool((void ***)v1 + 10, (struct THREAD_POOL_CONFIG *)v61) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          417,
          "FTP_SERVERP::Initialize",
          "Failed to create ThreadPool for Strmfilt\n");
      PortRange = -2147467259;
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 14;
    PortRange = DATA_STREAM_BUFFER::GlobalInitialize();
    if ( PortRange < 0 )
    {
LABEL_216:
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)v1 + 168LL))(v1);
      FTP_SERVERP::Terminate(v1);
      return (unsigned int)PortRange;
    }
    *((_DWORD *)v1 + 2) = 15;
    PortRange = SSL_STREAM_CONTEXT::GlobalInitialize();
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        Perioda = "Error initializing SSL_STREAM_CONTEXT globals\n";
        DueTime = PortRange;
        v10 = 445;
        goto LABEL_215;
      }
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 16;
    PortRange = FTP_SERVERP::InitializeAppHostConfiguration(
                  v1,
                  1,
                  (struct IAppHostAdminManager **)v1 + 12,
                  (struct FTP_CONFIG_CHANGE_NOTIFICATION **)v1 + 13);
    if ( PortRange < 0 )
      goto LABEL_216;
    v27 = (FTP_SITE_MANAGER *)operator new(0x110u);
    if ( v27 )
      v28 = FTP_SITE_MANAGER::FTP_SITE_MANAGER(v27);
    else
      v28 = 0;
    *((_QWORD *)v1 + 11) = v28;
    if ( !v28 )
    {
      PortRange = -2147024888;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_216;
      v29 = "Failed to allocate memory for FTP_SITE_MANAGER instance\n";
      v10 = 471;
      goto LABEL_214;
    }
    PortRange = FTP_SITE_MANAGER::Initialize(v28);
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          480,
          "FTP_SERVERP::Initialize",
          PortRange,
          "Failed to initialize FTP_SITE_MANAGER instance\n");
      v30 = (void *)*((_QWORD *)v1 + 11);
      if ( v30 )
      {
        FTP_SITE_MANAGER::~FTP_SITE_MANAGER(*((FTP_SITE_MANAGER **)v1 + 11));
        operator delete(v30);
      }
      *((_QWORD *)v1 + 11) = 0;
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 19;
    v31 = (CLKRHashTable *)operator new(0x58u);
    if ( v31 )
    {
      CLKRHashTable::CLKRHashTable(
        v31,
        "CREDENTIALS_CACHE",
        (unsigned __int64 (*)(const void *))CTypedHashTable<CREDENTIALS_CACHE,CREDENTIALS_CACHE_ENTRY,CREDENTIALS_CACHE_KEY *,CLKRHashTable>::_ExtractKey,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CREDENTIALS_CACHE,CREDENTIALS_CACHE_ENTRY,CREDENTIALS_CACHE_KEY *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<CREDENTIALS_CACHE,CREDENTIALS_CACHE_ENTRY,CREDENTIALS_CACHE_KEY *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      *((_QWORD *)v31 + 9) = 0;
      *((_QWORD *)v31 + 10) = 0;
    }
    else
    {
      v31 = 0;
    }
    *((_QWORD *)v1 + 51) = v31;
    if ( !v31 || !CLKRHashTable::IsValid(v31) )
    {
      PortRange = -2147024888;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_216;
      v29 = "Failed to allocate memory for CREDENTIALS_CACHE\n";
      v10 = 502;
      goto LABEL_214;
    }
    PortRange = CREDENTIALS_CACHE::Initialize(*((CREDENTIALS_CACHE **)v1 + 51));
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          514,
          "FTP_SERVERP::Initialize",
          PortRange,
          "Failed to initialize CREDENTIALS_CACHE\n");
      v32 = (void *)*((_QWORD *)v1 + 51);
      if ( v32 )
      {
        CLKRHashTable::~CLKRHashTable(*((CLKRHashTable **)v1 + 51));
        operator delete(v32);
      }
      *((_QWORD *)v1 + 51) = 0;
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 20;
    v33 = (CLKRHashTable *)operator new(0x98u);
    if ( v33 )
    {
      CLKRHashTable::CLKRHashTable(
        v33,
        "TOKEN_CACHE",
        (unsigned __int64 (*)(const void *))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_ExtractKey,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CREDENTIALS_CACHE,CREDENTIALS_CACHE_ENTRY,CREDENTIALS_CACHE_KEY *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<TOKEN_CACHE,TOKEN_CACHE_ENTRY,TOKEN_CACHE_KEY *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      *((_QWORD *)v33 + 9) = 0;
      *((_QWORD *)v33 + 10) = 0;
      *((_QWORD *)v33 + 11) = 0;
      *((_QWORD *)v33 + 12) = 0;
      *((_DWORD *)v33 + 26) &= ~1u;
      *((_DWORD *)v33 + 26) |= 2u;
      *((_DWORD *)v33 + 27) = 0;
      *((_QWORD *)v33 + 16) = 0;
      *((_QWORD *)v33 + 17) = 0;
      *((_QWORD *)v33 + 18) = 0;
      *((_QWORD *)v33 + 15) = (char *)v33 + 112;
      *((_QWORD *)v33 + 14) = (char *)v33 + 112;
    }
    else
    {
      v33 = 0;
    }
    *((_QWORD *)v1 + 20) = v33;
    if ( !v33 || !CLKRHashTable::IsValid(v33) )
    {
      PortRange = -2147024888;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_216;
      v29 = "Failed to allocate memory for TOKEN_CACHE\n";
      v10 = 533;
      goto LABEL_214;
    }
    PortRange = TOKEN_CACHE::Initialize(
                  *((TOKEN_CACHE **)v1 + 20),
                  v34,
                  v35,
                  *(_DWORD *)(*((_QWORD *)v1 + 51) + 72LL),
                  *(_DWORD *)(*((_QWORD *)v1 + 51) + 76LL),
                  Periodb);
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          560,
          "FTP_SERVERP::Initialize",
          PortRange,
          "Failed to initialize TOKEN_CACHE\n");
      v36 = (CLKRHashTable *)*((_QWORD *)v1 + 20);
      if ( v36 )
      {
        v37 = (HMODULE)*((_QWORD *)v36 + 18);
        if ( v37 )
        {
          FreeLibrary(v37);
          *((_QWORD *)v36 + 18) = 0;
          *((_QWORD *)v36 + 16) = 0;
          *((_QWORD *)v36 + 17) = 0;
        }
        CLKRHashTable::~CLKRHashTable(v36);
        operator delete(v36);
      }
      *((_QWORD *)v1 + 20) = 0;
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 21;
    v38 = (CLKRHashTable *)operator new(0x48u);
    if ( v38 )
      CLKRHashTable::CLKRHashTable(
        v38,
        "FTP_METADATA_TABLE",
        (unsigned __int64 (*)(const void *))CTypedHashTable<FTP_BINDING_TABLE,FTP_BINDING,unsigned short const *,CLKRHashTable>::_ExtractKey,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<FTP_PROVIDER_DEFINITION_TABLE,FTP_PROVIDER_DEFINITION,unsigned short const *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<SSL_SERVER_CERT_TABLE,SSL_SERVER_CERT,SSL_CERT_ID *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
    else
      v38 = 0;
    *((_QWORD *)v1 + 19) = v38;
    if ( !v38 || !CLKRHashTable::IsValid(v38) )
    {
      PortRange = -2147024888;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_216;
      v29 = "Failed to allocate memory for FTP_METADATA_TABLE\n";
      v10 = 584;
      goto LABEL_214;
    }
    *((_DWORD *)v1 + 2) = 22;
    PortRange = FTP_SERVERP::GetPortRange(v39, &v60, &v59);
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        Perioda = "Failed to initialize FTP_PORT_RANGE\n";
        DueTime = PortRange;
        v10 = 596;
        goto LABEL_215;
      }
      goto LABEL_216;
    }
    PortRange = FTP_PORT_RANGE::Initialize((FTP_SERVERP *)((char *)v1 + 192), v60, v59);
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        Perioda = "Failed to initialize FTP_PORT_RANGE\n";
        DueTime = PortRange;
        v10 = 606;
        goto LABEL_215;
      }
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 23;
    PortRange = FTP_SESSION_PUBLIC::GlobalInitialize();
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        Perioda = "Failed to initialize FTP_SESSION_PUBLIC\n";
        DueTime = PortRange;
        v10 = 617;
        goto LABEL_215;
      }
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 24;
    PortRange = FTP_SITE_PERF_CTRS::GlobalInitialize();
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        Perioda = "Failed to initialize FTP_SITE_PERF_CTRS\n";
        DueTime = PortRange;
        v10 = 627;
        goto LABEL_215;
      }
      goto LABEL_216;
    }
    *((_DWORD *)v1 + 2) = 25;
    v63[0] = 1;
    v63[1] = 100;
    v63[2] = 1192;
    v40 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
    if ( v40 )
      v41 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
              v40,
              "FTP_SITE_CONFIG",
              (const struct ALLOC_CACHE_CONFIGURATION *)v63,
              1);
    else
      v41 = 0;
    FTP_SITE_CONFIG::sm_pAllocHandler = v41;
    if ( !v41 )
    {
      PortRange = -2147024888;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_216;
      v29 = "Failed to initialize FTP_SITE_CONFIG\n";
      v10 = 638;
      goto LABEL_214;
    }
    FTP_SITE_CONFIG::sm_pRefTraceLog = 0;
    *((_DWORD *)v1 + 2) = 26;
    PortRange = USER_SESSION::GlobalInitialize();
    if ( PortRange < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        Perioda = "Failed to initialize USER_SESSION\n";
        DueTime = PortRange;
        v10 = 649;
        goto LABEL_215;
      }
      goto LABEL_216;
    }
    FTP_LOG_FILE_MANAGER::sm_pRefTraceLog = 0;
    *((_DWORD *)v1 + 2) = 28;
    v42 = operator new(0x20u);
    if ( v42 )
    {
      *(_QWORD *)v42 = &FTP_CONTROL_API_CLASS_FACTORY::`vftable';
      v42[3] = 1;
      v42[6] = 0;
      *((_QWORD *)v42 + 2) = 0;
      v42[2] = 1178817606;
    }
    else
    {
      v42 = 0;
    }
    *((_QWORD *)v1 + 23) = v42;
    if ( !v42 )
    {
      PortRange = -2147024888;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_216;
      v29 = "Failed to allocate memory for FTP_CONTROL_API_CLASS_FACTORY\n";
      v10 = 673;
      goto LABEL_214;
    }
    v43 = operator new(0x20u);
    if ( v43 )
    {
      *(_QWORD *)v43 = &FTP_CONTROL_API::`vftable';
      v43[4] = 0;
      v43[5] = 0;
      v43[3] = 1;
      v43[7] = 0;
      v43[6] = 0;
      v43[2] = 1128354886;
    }
    else
    {
      v43 = 0;
    }
    *((_QWORD *)v42 + 2) = v43;
    if ( v43 )
    {
      PortRange = CoRegisterClassObject(&CLSID_FtpControl, (LPUNKNOWN)v42, 4u, 1u, v42 + 6);
      if ( PortRange >= 0 )
      {
        *((_DWORD *)v1 + 2) = 29;
        v44 = operator new(0x68u);
        if ( v44 )
        {
          *(_QWORD *)v44 = 0;
          v44[12] = 0;
          *((_QWORD *)v44 + 11) = 0;
          v44[25] = 0;
          *((_QWORD *)v44 + 10) = 0;
          *((_QWORD *)v44 + 9) = 0;
        }
        else
        {
          v44 = 0;
        }
        *((_QWORD *)v1 + 38) = v44;
        if ( v44 )
        {
          PortRange = AD_LOOKUP_MANAGER::Initialize((AD_LOOKUP_MANAGER *)v44);
          if ( PortRange < 0 )
          {
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
                713,
                "FTP_SERVERP::Initialize",
                PortRange,
                "Failed to initialize AD_LOOKUP_MANAGER\n");
            v45 = (void *)*((_QWORD *)v1 + 38);
            if ( v45 )
            {
              AD_LOOKUP_MANAGER::Terminate(*((AD_LOOKUP_MANAGER **)v1 + 38));
              operator delete(v45);
            }
            *((_QWORD *)v1 + 38) = 0;
            goto LABEL_216;
          }
          *((_DWORD *)v1 + 2) = 30;
          v47 = operator new(0xC8u);
          if ( v47 )
          {
            *(_QWORD *)v47 = &STTABLE::`vftable';
            STBUFF::STBUFF((STBUFF *)(v47 + 2), v46);
            v47[26] = 0;
            v47[28] = 0;
            *((_QWORD *)v47 + 22) = 0;
            *(_QWORD *)v47 = &DYNAMIC_IP_RESTRICTION_TABLE::`vftable';
            *((_QWORD *)v47 + 23) = 0;
            *((_QWORD *)v47 + 24) = 0;
          }
          else
          {
            v47 = 0;
          }
          *((_QWORD *)v1 + 54) = v47;
          if ( v47 )
          {
            PortRange = DYNAMIC_IP_RESTRICTION_TABLE::Initialize(v47);
            if ( PortRange < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
                  739,
                  "FTP_SERVERP::Initialize",
                  PortRange,
                  "Failed to initialize DYNAMIC_IP_RESTRICTION_TABLE\n");
              v48 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v1 + 54);
              if ( v48 )
                (**v48)(v48, 1);
              *((_QWORD *)v1 + 54) = 0;
              goto LABEL_216;
            }
            *((_DWORD *)v1 + 2) = 31;
            PortRange = IP_RESTRICTION_LIST::Initialize();
            if ( PortRange < 0 )
            {
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
                  753,
                  "FTP_SERVERP::Initialize",
                  PortRange,
                  "Failed to initialize IP_RESTRICTION_LIST\n");
              IP_RESTRICTION_LIST::Terminate();
              goto LABEL_216;
            }
            *((_DWORD *)v1 + 2) = 32;
            if ( !*((_DWORD *)v1 + 110) )
            {
              memset_0(v61, 0, 0x40u);
              *(_OWORD *)v61 = SumGuid_FTP;
              if ( (unsigned int)SumInstrumentationStart(v61) )
                *((_DWORD *)v1 + 110) = 1;
            }
            v49 = (char *)operator new(0x58u);
            v50 = (void **)v49;
            if ( v49 )
            {
              *(_QWORD *)v49 = &FTP_SQM_WRITER::`vftable';
              *((_QWORD *)v49 + 9) = 0;
              *((_DWORD *)v49 + 20) = 0;
              *(_OWORD *)(v49 + 8) = 0;
              *((_DWORD *)v49 + 6) = 0;
              InitializeCriticalSection((LPCRITICAL_SECTION)(v49 + 32));
            }
            else
            {
              v50 = 0;
            }
            *((_QWORD *)v1 + 56) = v50;
            if ( v50 )
            {
              if ( !CreateTimerQueueTimer(
                      v50 + 9,
                      0,
                      (WAITORTIMERCALLBACK)FTP_SQM_WRITER::DataCollectCallback,
                      v50,
                      0x36EE80u,
                      0x36EE80u,
                      0x10u) )
              {
                v51 = GetLastError();
                v52 = v51 < 0;
                if ( v51 > 0 )
                  v52 = 1;
                if ( v52 )
                {
                  v53 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v1 + 56);
                  if ( v53 )
                    (**v53)(v53, 1);
                  *((_QWORD *)v1 + 56) = 0;
                }
              }
              return 0;
            }
            PortRange = -2147024888;
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_216;
            v29 = "Failed to allocate memory for FTP_SQM_WRITER\n";
            v10 = 793;
          }
          else
          {
            PortRange = -2147024888;
            if ( (g_dwDebugFlags & 0xF) == 0 )
              goto LABEL_216;
            v29 = "Failed to allocate memory for DYNAMIC_IP_RESTRICTION_TABLE\n";
            v10 = 729;
          }
        }
        else
        {
          PortRange = -2147024888;
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_216;
          v29 = "Failed to allocate memory for AD_LOOKUP_MANAGER\n";
          v10 = 703;
        }
LABEL_214:
        Perioda = v29;
        DueTime = -2147024888;
        goto LABEL_215;
      }
    }
    else
    {
      PortRange = -2147024882;
    }
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
        683,
        "FTP_SERVERP::Initialize",
        PortRange,
        "Registering class object failed\n");
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v1 + 23) + 16LL))(*((_QWORD *)v1 + 23));
    *((_QWORD *)v1 + 23) = 0;
    goto LABEL_156;
  }
  EVENT_LOG::LogEvent((EVENT_LOG *)FTP_LOG_NT_EVENT::sm_pEventLog, 0xC0000028, 0, 0, v7);
  v8 = PortRange < 0;
  if ( PortRange <= 0 )
    goto LABEL_157;
  PortRange = (unsigned __int16)PortRange | 0x80070000;
LABEL_156:
  v8 = PortRange < 0;
LABEL_157:
  if ( v8 )
    goto LABEL_216;
  return (unsigned int)PortRange;
}

```

## disassembly

```asm
0x1800029fc  mov     rax, rsp
0x1800029ff  push    rbp
0x180002a00  push    rbx
0x180002a01  push    rsi
0x180002a02  push    rdi
0x180002a03  push    r12
0x180002a05  push    r13
0x180002a07  push    r14
0x180002a09  push    r15
0x180002a0b  lea     rbp, [rax-0A18h]
0x180002a12  sub     rsp, 0AD8h
0x180002a19  movaps  xmmword ptr [rax-58h], xmm6
0x180002a1d  mov     rax, cs:__security_cookie
0x180002a24  xor     rax, rsp
0x180002a27  mov     [rbp+0A10h+var_60], rax
0x180002a2e  mov     rdi, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180002a35  xorps   xmm0, xmm0
0x180002a38  movups  xmmword ptr [rbp+0A10h+SystemInfo], xmm0
0x180002a3c  movups  xmmword ptr [rbp+0A10h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180002a40  movups  xmmword ptr [rbp+0A10h+SystemInfo.dwNumberOfProcessors], xmm0
0x180002a44  xor     edx, edx; Val
0x180002a46  lea     r8d, [rdx+54h]; Size
0x180002a4a  lea     rcx, [rsp+0B10h+var_AB8+8]; void *
0x180002a4f  call    memset_0
0x180002a54  xor     edx, edx; Val
0x180002a56  mov     r8d, 198h; Size
0x180002a5c  lea     rcx, [rbp+0A10h+WSAData]; void *
0x180002a60  call    memset_0
0x180002a65  xor     r13d, r13d
0x180002a68  mov     [rsp+0B10h+var_AB8+4], r13w
0x180002a6e  mov     [rsp+0B10h+var_AB8], r13w
0x180002a74  xor     edx, edx; Val
0x180002a76  mov     r8d, 802h; Size
0x180002a7c  lea     rcx, [rbp+0A10h+name]; void *
0x180002a83  call    memset_0
0x180002a88  lea     ecx, [r13+4]; Size
0x180002a8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002a91  mov     qword ptr [rsp+0B10h+var_AC0], rax
0x180002a96  test    rax, rax
0x180002a99  jz      short loc_180002AAD
0x180002a9b  lea     rdx, aFtpsvc; "FTPSVC"
0x180002aa2  mov     rcx, rax
0x180002aa5  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x180002aab  jmp     short loc_180002AB0
0x180002aad  mov     rax, r13
0x180002ab0  mov     cs:?sm_pEventLog@FTP_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA, rax; EVENT_LOG * FTP_LOG_NT_EVENT::sm_pEventLog
0x180002ab7  test    rax, rax
0x180002aba  jnz     short loc_180002AFC
0x180002abc  mov     ebx, 8007000Eh
0x180002ac1  lea     esi, [rax+0Fh]
0x180002ac4  test    byte ptr cs:g_dwDebugFlags, sil
0x180002acb  jz      loc_180003B8A
0x180002ad1  lea     rax, aNtEventLogInit; "NT event log initialization failed."
0x180002ad8  mov     qword ptr [rsp+0B10h+Period], rax
0x180002add  mov     [rsp+0B10h+DueTime], 8007000Eh
0x180002ae5  lea     r9, aFtpServerpInit; "FTP_SERVERP::Initialize"
0x180002aec  lea     r8d, [rsi+3Ah]
0x180002af0  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180002af7  jmp     loc_180003B7D
0x180002afc  mov     dword ptr [rdi+8], 1
0x180002b03  lea     rcx, [rdi+10h]
0x180002b07  xor     r9d, r9d
0x180002b0a  xor     r8d, r8d
0x180002b0d  lea     rdx, ?ProviderGuid@?1??GetProviderGuid@FTPServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FTPServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002b14  call    cs:__imp_?Register@CEtwTracer@@QEAAKPEBU_GUID@@PEAG1@Z; CEtwTracer::Register(_GUID const *,ushort *,ushort *)
0x180002b1a  mov     ebx, eax
0x180002b1c  mov     esi, 0Fh
0x180002b21  lea     r14, aFtpServerpInit; "FTP_SERVERP::Initialize"
0x180002b28  lea     r15, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180002b2f  mov     r12d, 80070000h
0x180002b35  test    eax, eax
0x180002b37  jz      short loc_180002B8F
0x180002b39  jle     short loc_180002B41
0x180002b3b  movzx   ebx, ax
0x180002b3e  or      ebx, r12d
0x180002b41  test    byte ptr cs:g_dwDebugFlags, sil
0x180002b48  jz      short loc_180002B73
0x180002b4a  lea     rax, aWarningEtwInit; "Warning: ETW initialization failed."
0x180002b51  mov     qword ptr [rsp+0B10h+Period], rax
0x180002b56  mov     [rsp+0B10h+DueTime], ebx
0x180002b5a  mov     r9, r14
0x180002b5d  mov     r8d, 5Eh ; '^'
0x180002b63  mov     rdx, r15
0x180002b66  mov     rcx, cs:g_pDebug
0x180002b6d  call    cs:__imp_PuDbgPrintError
0x180002b73  xor     r8d, r8d
0x180002b76  mov     [rsp+0B10h+DueTime], ebx
0x180002b7a  xor     r9d, r9d
0x180002b7d  mov     edx, 80000025h
0x180002b82  mov     rcx, cs:?sm_pEventLog@FTP_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA; EVENT_LOG * FTP_LOG_NT_EVENT::sm_pEventLog
0x180002b89  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180002b8f  mov     dword ptr [rdi+8], 2
0x180002b96  call    cs:__imp_?HandleMigration@SETUP_HELPER@@SAKXZ; SETUP_HELPER::HandleMigration(void)
0x180002b9c  mov     ebx, eax
0x180002b9e  test    eax, eax
0x180002ba0  jz      short loc_180002BD1
0x180002ba2  xor     r8d, r8d
0x180002ba5  mov     [rsp+0B10h+DueTime], eax
0x180002ba9  xor     r9d, r9d
0x180002bac  mov     edx, 0C0000028h
0x180002bb1  mov     rcx, cs:?sm_pEventLog@FTP_LOG_NT_EVENT@@0PEAVEVENT_LOG@@EA; EVENT_LOG * FTP_LOG_NT_EVENT::sm_pEventLog
0x180002bb8  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180002bbe  test    ebx, ebx
0x180002bc0  jle     loc_180003794
0x180002bc6  movzx   ebx, bx
0x180002bc9  or      ebx, r12d
0x180002bcc  jmp     loc_180003792
0x180002bd1  mov     r12d, 3
0x180002bd7  mov     [rdi+8], r12d
0x180002bdb  xor     edx, edx; dwCoInit
0x180002bdd  xor     ecx, ecx; pvReserved
0x180002bdf  call    cs:__imp_CoInitializeEx
0x180002be5  mov     ebx, eax
0x180002be7  test    eax, eax
0x180002be9  jns     short loc_180002C13
0x180002beb  test    byte ptr cs:g_dwDebugFlags, sil
0x180002bf2  jz      loc_180003B8A
0x180002bf8  lea     rax, aCouldNotInitia_4; "Could not initialize COM."
0x180002bff  mov     qword ptr [rsp+0B10h+Period], rax
0x180002c04  mov     [rsp+0B10h+DueTime], ebx
0x180002c08  mov     r8d, 89h
0x180002c0e  jmp     loc_180003B77
0x180002c13  call    ?InitializeCOMSecurity@FTP_SERVERP@@AEAAJXZ; FTP_SERVERP::InitializeCOMSecurity(void)
0x180002c18  mov     ebx, eax
0x180002c1a  test    eax, eax
0x180002c1c  jns     short loc_180002C5B
0x180002c1e  test    byte ptr cs:g_dwDebugFlags, sil
0x180002c25  jz      short loc_180002C50
0x180002c27  lea     rax, aCoinitializese; "CoInitializeSecurity failed."
0x180002c2e  mov     qword ptr [rsp+0B10h+Period], rax
0x180002c33  mov     [rsp+0B10h+DueTime], ebx
0x180002c37  mov     r9, r14
0x180002c3a  mov     r8d, 92h
0x180002c40  mov     rdx, r15
0x180002c43  mov     rcx, cs:g_pDebug
0x180002c4a  call    cs:__imp_PuDbgPrintError
0x180002c50  call    cs:__imp_CoUninitialize
0x180002c56  jmp     loc_180003B8A
0x180002c5b  mov     dword ptr [rdi+8], 4
0x180002c62  mov     ecx, 2; wVersionRequested
0x180002c67  lea     rdx, [rbp+0A10h+WSAData]; lpWSAData
0x180002c6b  call    cs:__imp_WSAStartup
0x180002c71  test    eax, eax
0x180002c73  jz      short loc_180002CB0
0x180002c75  test    byte ptr cs:g_dwDebugFlags, r12b
0x180002c7c  jz      loc_180003BA4
0x180002c82  lea     rax, aCouldNotInitia; "Could not initialize winsock 0x%x\n"
0x180002c89  mov     r8d, 0A3h
0x180002c8f  mov     [rsp+0B10h+Period], ebx
0x180002c93  mov     r9, r14
0x180002c96  mov     qword ptr [rsp+0B10h+DueTime], rax
0x180002c9b  mov     rdx, r15
0x180002c9e  mov     rcx, cs:g_pDebug
0x180002ca5  call    cs:__imp_PuDbgPrint
0x180002cab  jmp     loc_180003BA4
0x180002cb0  call    ?GlobalInitialize@FTP_ASYNC_SOCKET@@SAJXZ; FTP_ASYNC_SOCKET::GlobalInitialize(void)
0x180002cb5  mov     ebx, eax
0x180002cb7  test    eax, eax
0x180002cb9  jns     short loc_180002CF8
0x180002cbb  test    byte ptr cs:g_dwDebugFlags, sil
0x180002cc2  jz      short loc_180002CED
0x180002cc4  lea     rax, aCouldNotInitia_1; "Could not initialize sockets\n"
0x180002ccb  mov     qword ptr [rsp+0B10h+Period], rax
0x180002cd0  mov     [rsp+0B10h+DueTime], ebx
0x180002cd4  mov     r9, r14
0x180002cd7  mov     r8d, 0ACh
0x180002cdd  mov     rdx, r15
0x180002ce0  mov     rcx, cs:g_pDebug
0x180002ce7  call    cs:__imp_PuDbgPrintError
0x180002ced  call    cs:__imp_WSACleanup
0x180002cf3  jmp     loc_180003B8A
0x180002cf8  mov     dword ptr [rdi+8], 5
0x180002cff  call    cs:__imp_?InitializeLocalRequest@@YAJXZ; InitializeLocalRequest(void)
0x180002d05  mov     ebx, eax
0x180002d07  test    eax, eax
0x180002d09  jns     short loc_180002D46
0x180002d0b  test    byte ptr cs:g_dwDebugFlags, r12b
0x180002d12  jz      loc_180003B8A
0x180002d18  mov     [rsp+0B10h+Period], eax
0x180002d1c  lea     rax, aCouldNotInitia_3; "Could not initialize list of local addr"...
0x180002d23  mov     r8d, 0C2h
0x180002d29  mov     r9, r14
0x180002d2c  mov     qword ptr [rsp+0B10h+DueTime], rax
0x180002d31  mov     rdx, r15
0x180002d34  mov     rcx, cs:g_pDebug
0x180002d3b  call    cs:__imp_PuDbgPrint
0x180002d41  jmp     loc_180003B8A
0x180002d46  mov     dword ptr [rdi+8], 6
0x180002d4d  mov     edx, 400h; namelen
0x180002d52  lea     rcx, [rbp+0A10h+name]; name
0x180002d59  call    cs:__imp_GetHostNameW
0x180002d5f  test    eax, eax
0x180002d61  jns     short loc_180002D82
0x180002d63  test    byte ptr cs:g_dwDebugFlags, r12b
0x180002d6a  jz      loc_180003BA4
0x180002d70  lea     rax, aCouldNotLookup; "Could not lookup the local host name 0x"...
0x180002d77  mov     r8d, 0D2h
0x180002d7d  jmp     loc_180002C8F
0x180002d82  lea     rcx, [rdi+0F8h]
0x180002d89  lea     rdx, [rbp+0A10h+name]
0x180002d90  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002d96  mov     ebx, eax
0x180002d98  test    eax, eax
0x180002d9a  jns     short loc_180002DBF
0x180002d9c  test    byte ptr cs:g_dwDebugFlags, r12b
0x180002da3  jz      loc_180003B8A
0x180002da9  mov     [rsp+0B10h+Period], eax
0x180002dad  lea     rax, aCouldNotCopyLo; "Could not copy local host name 0x%x\n"
0x180002db4  mov     r8d, 0DEh
0x180002dba  jmp     loc_180002D29
0x180002dbf  mov     dword ptr [rdi+8], 7
0x180002dc6  mov     ecx, 58h ; 'X'; Size
0x180002dcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002dd0  mov     rbx, rax
0x180002dd3  mov     qword ptr [rsp+0B10h+var_AC0], rax
0x180002dd8  movsd   xmm6, cs:__real@4010000000000000
0x180002de0  test    rax, rax
0x180002de3  jz      short loc_180002E44
0x180002de5  lea     rcx, [rax+8]
0x180002de9  mov     byte ptr [rsp+0B10h+var_AC8], r13b
0x180002dee  mov     dword ptr [rsp+0B10h+var_AD0], r13d
0x180002df3  mov     [rsp+0B10h+var_AD8], 1
0x180002dfb  movsd   qword ptr [rsp+0B10h+Flags], xmm6
0x180002e01  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VFTP_LOG_NT_EVENT_TABLE@@VFTP_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180002e08  mov     qword ptr [rsp+0B10h+Period], rax
0x180002e0d  lea     rax, ?_EqualKeys@?$CTypedHashTable@VFTP_LOG_NT_EVENT_TABLE@@VFTP_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180002e14  mov     qword ptr [rsp+0B10h+DueTime], rax
0x180002e19  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VFTP_LOG_NT_EVENT_TABLE@@VFTP_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180002e20  lea     r8, ?_ExtractKey@?$CTypedHashTable@VFTP_LOG_NT_EVENT_TABLE@@VFTP_LOG_NT_EVENT@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<FTP_LOG_NT_EVENT_TABLE,FTP_LOG_NT_EVENT,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x180002e27  lea     rdx, aFtpLogNtEventT_0; "FTP_LOG_NT_EVENT_TABLE"
0x180002e2e  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180002e34  lea     rax, ??_7FTP_LOG_NT_EVENT_TABLE@@6B@; const FTP_LOG_NT_EVENT_TABLE::`vftable'
0x180002e3b  mov     [rbx], rax
0x180002e3e  mov     [rbx+50h], r13
0x180002e42  jmp     short loc_180002E47
0x180002e44  mov     rbx, r13
0x180002e47  mov     [rdi+90h], rbx
0x180002e4e  test    rbx, rbx
0x180002e51  jz      loc_180003B4F
0x180002e57  lea     rcx, [rbx+8]
0x180002e5b  call    cs:__imp_?IsValid@CLKRHashTable@@QEBA_NXZ; CLKRHashTable::IsValid(void)
0x180002e61  test    al, al
0x180002e63  jz      loc_180003B4F
0x180002e69  mov     r9, [rdi+90h]; Parameter
0x180002e70  lea     rcx, [r9+50h]; phNewTimer
0x180002e74  mov     [rsp+0B10h+Flags], 10h; Flags
0x180002e7c  mov     eax, 493E0h
0x180002e81  mov     [rsp+0B10h+Period], eax; Period
0x180002e85  mov     [rsp+0B10h+DueTime], eax; DueTime
0x180002e89  lea     r8, ?ScavengerCallback@FTP_LOG_NT_EVENT_TABLE@@CAXPEAXE@Z; Callback
0x180002e90  xor     edx, edx; TimerQueue
0x180002e92  call    cs:__imp_CreateTimerQueueTimer
0x180002e98  test    eax, eax
0x180002e9a  jnz     short loc_180002F0F
0x180002e9c  call    cs:__imp_GetLastError
0x180002ea2  mov     ebx, eax
0x180002ea4  test    eax, eax
0x180002ea6  jle     short loc_180002EB1
0x180002ea8  movzx   ebx, ax
0x180002eab  or      ebx, 80070000h
0x180002eb1  test    ebx, ebx
0x180002eb3  jns     short loc_180002F0F
0x180002eb5  test    byte ptr cs:g_dwDebugFlags, sil
0x180002ebc  jz      short loc_180002EE7
0x180002ebe  lea     rax, aCouldNotInitia_2; "Could not initialize FTP_LOG_NT_EVENT_T"...
0x180002ec5  mov     qword ptr [rsp+0B10h+Period], rax
0x180002eca  mov     [rsp+0B10h+DueTime], ebx
0x180002ece  mov     r9, r14
0x180002ed1  mov     r8d, 152h
0x180002ed7  mov     rdx, r15
0x180002eda  mov     rcx, cs:g_pDebug
0x180002ee1  call    cs:__imp_PuDbgPrintError
0x180002ee7  mov     rcx, [rdi+90h]
0x180002eee  test    rcx, rcx
0x180002ef1  jz      short loc_180002F03
0x180002ef3  mov     rax, [rcx]
0x180002ef6  mov     edx, 1
0x180002efb  mov     rax, [rax]
0x180002efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f03  mov     [rdi+90h], r13
0x180002f0a  jmp     loc_180003B8A
0x180002f0f  mov     dword ptr [rdi+8], 0Ch
0x180002f16  mov     r13d, [rdi+8Ch]
0x180002f1d  mov     eax, 18h
0x180002f22  mul     r13
0x180002f25  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002f2c  cmovb   rax, rcx
0x180002f30  add     rax, 8
0x180002f34  cmovb   rax, rcx
0x180002f38  mov     rcx, rax; Size
0x180002f3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002f40  mov     qword ptr [rsp+0B10h+var_AC0], rax
0x180002f45  test    rax, rax
0x180002f48  jz      short loc_180002F79
0x180002f4a  mov     [rax], r13
0x180002f4d  lea     rbx, [rax+8]
0x180002f51  lea     rax, ??1TIMER_WHEEL_SLOT@@QEAA@XZ; TIMER_WHEEL_SLOT::~TIMER_WHEEL_SLOT(void)
0x180002f58  mov     qword ptr [rsp+0B10h+DueTime], rax; void (*)(void *)
0x180002f5d  lea     r9, ??0TIMER_WHEEL_SLOT@@QEAA@XZ; void (*)(void *)
0x180002f64  mov     r8d, r13d; unsigned __int64
  ... truncated ...
```
