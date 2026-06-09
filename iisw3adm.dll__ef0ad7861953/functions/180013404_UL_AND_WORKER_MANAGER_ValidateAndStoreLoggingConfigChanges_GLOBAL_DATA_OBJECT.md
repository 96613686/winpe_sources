# UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges(GLOBAL_DATA_OBJECT *)

- ea: `0x180013404`
- end: `0x180013c59`
- name: `?ValidateAndStoreLoggingConfigChanges@UL_AND_WORKER_MANAGER@@AEAAXPEAVGLOBAL_DATA_OBJECT@@@Z`
- size: `2133`
- prototype: `void __fastcall(UL_AND_WORKER_MANAGER *__hidden this, struct GLOBAL_DATA_OBJECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800130a4`

## callees

- `0x180005878`
- `0x18000f210`
- `0x180011064`
- `0x180013404`
- `0x18003d94c`
- `0x18003da9c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001380f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013c1e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001380f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013c1e`
- `iisutil!PuDbgPrint` at `0x1800135d7`
- `iisutil!PuDbgPrint` at `0x180013801`
- `iisutil!PuDbgPrint` at `0x18001392e`
- `iisutil!PuDbgPrint` at `0x180013bd5`
- `iisutil!PuDbgPrint` at `0x1800135d7`
- `iisutil!PuDbgPrint` at `0x180013801`
- `iisutil!PuDbgPrint` at `0x18001392e`
- `iisutil!PuDbgPrint` at `0x180013bd5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013618`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001396c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180013618`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001396c`

## string_xrefs

- `0x1800135be`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x1800137f1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180013916`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x180013bb1`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\ul_and_worker_manager.cxx`
- `0x1800135b2`: `BinaryLogging Properties ( as they come in from config ) are \n    CentralW3CBinaryLoggingEnabled = %S \n   CentralBinaryLoggingEnabled = %S \n   BinaryLogFilePeriod = %d, %S \n   BinaryLogFileTruncateSize = %d, %S \n   BinaryLogFileDirectory = %S, %S \n   FileLocaltimeRollover = %S \n`
- `0x180013558`: `UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges`
- `0x1800137c0`: `UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges`
- `0x1800138ae`: `UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges`
- `0x180013b90`: `UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges`
- `0x1800137e6`: `CentralBinaryLogging Properties ( as they go to http.sys ) are \n    LogFilePeriod = %d \n   LogFileTruncateSize = %d \n   LogFileDirectory = %S \n   LocaltimeRollover = %S \n`
- `0x1800138f8`: `W3CLogging Properties ( as they come in from config ) are \n    CentralW3CLoggingEnabled = %S \n   CentralBinaryLoggingEnabled = %S \n   W3CLogFilePeriod = %d, %S \n   W3CLogFileTruncateSize = %d, %S \n   W3CLogFileDirectory = %S, %S \n   FileLocaltimeRollover = %S \n   W3CLogExtFileFlags = %d, %S \n`
- `0x180013ba7`: `CentralW3CLogging Properties ( as they go to http.sys ) are \n    LogFilePeriod = %d \n   LogFileTruncateSize = %d \n   LogFileDirectory = %S \n   LogExtFileFlags = %d \n   LocaltimeRollover = %S \n`

## pseudocode

```c
void __fastcall UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges(
        UL_AND_WORKER_MANAGER *this,
        struct GLOBAL_DATA_OBJECT *a2)
{
  __int64 v2; // rax
  wchar_t *v5; // r12
  WMS_ERROR_LOGGER *v6; // r14
  WMS_ERROR_LOGGER *i; // rcx
  __int64 v8; // r8
  int v9; // eax
  _DWORD *v10; // r13
  __int64 v11; // rcx
  int v12; // eax
  const wchar_t *v13; // r9
  int v14; // ecx
  LPCWSTR *v15; // rbx
  const wchar_t *v16; // r11
  const wchar_t *v17; // r10
  const wchar_t *v18; // rax
  const wchar_t *v19; // r8
  const wchar_t *v20; // rdx
  const wchar_t *v21; // rcx
  int LogFileDirectory; // eax
  unsigned int v23; // ebx
  int v24; // edx
  int v25; // edi
  WMS_ERROR_LOGGER *v26; // rax
  __int64 v27; // rdx
  const unsigned __int16 *v28; // r8
  WMS_ERROR_LOGGER *j; // rax
  __int64 v30; // rax
  WMS_ERROR_LOGGER *v31; // rax
  __int64 v32; // r8
  const wchar_t *v33; // rcx
  const wchar_t *v34; // rax
  int v35; // ecx
  const wchar_t *v36; // rdx
  const wchar_t **v37; // rax
  const wchar_t *v38; // rdi
  const wchar_t *v39; // r9
  const wchar_t *v40; // r11
  const wchar_t *v41; // r10
  const wchar_t *v42; // rax
  const wchar_t *v43; // r8
  const wchar_t *v44; // rcx
  struct PROTOCOL **v45; // rcx
  signed int v46; // r13d
  unsigned int v47; // ebx
  WMS_ERROR_LOGGER *k; // rax
  __int64 v49; // rdx
  const unsigned __int16 *v50; // r8
  WMS_ERROR_LOGGER *m; // rax
  int v52; // edi
  WMS_ERROR_LOGGER *n; // rax
  __int64 v54; // r8
  int v55; // edx
  WMS_ERROR_LOGGER *v56; // rax
  __int64 v57; // r8
  const wchar_t *v58; // rax
  const wchar_t *v59; // rcx
  bool v60; // zf
  int v61; // eax
  unsigned int v62[2]; // [rsp+28h] [rbp-61h]
  unsigned __int16 *v63; // [rsp+30h] [rbp-59h]
  unsigned __int16 *v64; // [rsp+30h] [rbp-59h]
  unsigned __int16 *v65; // [rsp+30h] [rbp-59h]
  int v66; // [rsp+38h] [rbp-51h]
  __int64 v67; // [rsp+40h] [rbp-49h]
  int v68; // [rsp+80h] [rbp-9h]
  HGLOBAL hMem; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int16 *v70; // [rsp+90h] [rbp+7h] BYREF
  struct PROTOCOL *v71; // [rsp+F0h] [rbp+67h] BYREF
  WMS_ERROR_LOGGER *v72; // [rsp+F8h] [rbp+6Fh]
  int Protocol; // [rsp+100h] [rbp+77h]
  unsigned int v74; // [rsp+108h] [rbp+7Fh]

  v2 = *((_QWORD *)this + 55);
  hMem = 0;
  v5 = 0;
  v71 = 0;
  *(_DWORD *)(v2 + 20) = 0;
  v68 = 0;
  Protocol = UL_AND_WORKER_MANAGER::FindProtocol(this, (const unsigned __int16 *)a2, &v71);
  if ( Protocol >= 0 && v71 )
    v68 = *((_DWORD *)v71 + 94);
  v6 = (struct GLOBAL_DATA_OBJECT *)((char *)a2 + 224);
  for ( i = (WMS_ERROR_LOGGER *)*((_QWORD *)a2 + 28); i != v6; i = *(WMS_ERROR_LOGGER **)i )
  {
    v8 = *((_QWORD *)i - 1);
    if ( *(_DWORD *)(v8 + 8) == 52 )
    {
      if ( v8 )
        WMS_ERROR_LOGGER::LogInvalidValue(
          i,
          L"system.applicationHost/log",
          *(const unsigned __int16 **)(v8 + 48),
          *(const unsigned __int16 **)(v8 + 160),
          *(const unsigned __int16 **)(v8 + 104),
          v62[0]);
      break;
    }
  }
  if ( *((_DWORD *)a2 + 16) != 1 || (v9 = 1, !*((_DWORD *)a2 + 17)) )
    v9 = 0;
  *(_DWORD *)(*((_QWORD *)this + 55) + 136LL) = v9;
  v10 = (_DWORD *)((char *)a2 + 72);
  v11 = *((_QWORD *)this + 55);
  if ( *((_DWORD *)a2 + 16) != 2 || (v12 = 1, !*v10) )
    v12 = 0;
  *(_DWORD *)(v11 + 140) = v12;
  LOBYTE(v11) = (g_dwDebugFlags & 0x50000) != 0;
  if ( ((unsigned __int8)v11 & ((g_dwDebugFlags & 3) != 0)) != 0 )
  {
    v13 = L"<NULL>";
    v14 = *((_DWORD *)a2 + 60);
    v15 = (LPCWSTR *)((char *)a2 + 112);
    v16 = L"TRUE";
    v17 = L"TRUE";
    if ( !*((_DWORD *)a2 + 36) )
      v16 = L"FALSE";
    v18 = L"TRUE";
    v19 = L"TRUE";
    if ( (v14 & 0x2000) == 0 )
      v17 = L"FALSE";
    if ( *v15 )
      v13 = *v15;
    if ( (v14 & 0x800) == 0 )
      v18 = L"FALSE";
    if ( (v14 & 0x400) == 0 )
      v19 = L"FALSE";
    v20 = L"TRUE";
    if ( !*((_DWORD *)a2 + 17) )
      v20 = L"FALSE";
    v21 = L"TRUE";
    if ( !*v10 )
      v21 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      2504,
      "UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges",
      "BinaryLogging Properties ( as they come in from config ) are \n"
      "    CentralW3CBinaryLoggingEnabled = %S \n"
      "   CentralBinaryLoggingEnabled = %S \n"
      "   BinaryLogFilePeriod = %d, %S \n"
      "   BinaryLogFileTruncateSize = %d, %S \n"
      "   BinaryLogFileDirectory = %S, %S \n"
      "   FileLocaltimeRollover = %S \n",
      v21,
      v20,
      *((_DWORD *)a2 + 34),
      v19,
      *((_DWORD *)a2 + 35),
      v18,
      v13,
      v17,
      v16);
  }
  else
  {
    v15 = (LPCWSTR *)((char *)a2 + 112);
  }
  if ( (*((_DWORD *)a2 + 60) & 0x2000) != 0 )
  {
    LogFileDirectory = CreateLogFileDirectory(*v15, (unsigned __int16 **)&hMem);
    Protocol = LogFileDirectory;
    if ( LogFileDirectory < 0 )
    {
      v46 = LogFileDirectory;
      goto LABEL_97;
    }
    v5 = (wchar_t *)hMem;
    STRU::Copy((STRU *)(*((_QWORD *)this + 55) + 24LL), (const unsigned __int16 *)hMem);
  }
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v74 = 0;
  v60 = (*((_DWORD *)a2 + 60) & 0x400) == 0;
  LODWORD(v71) = 0;
  LODWORD(v72) = 0;
  if ( !v60 )
  {
    v26 = *(WMS_ERROR_LOGGER **)v6;
    v23 = *((_DWORD *)a2 + 34);
    v74 = v23;
    if ( v26 != v6 )
    {
      while ( 1 )
      {
        v27 = *((_QWORD *)v26 - 1);
        if ( *(_DWORD *)(v27 + 8) == 63 )
          break;
        v26 = *(WMS_ERROR_LOGGER **)v26;
        if ( v26 == v6 )
          goto LABEL_46;
      }
      if ( v27 )
      {
        v28 = *(const unsigned __int16 **)(v27 + 160);
        v64 = *(unsigned __int16 **)(v27 + 104);
        if ( *(_DWORD *)(v27 + 192) == 2 )
          WMS_ERROR_LOGGER::LogRangeGlobal(
            *(WMS_ERROR_LOGGER **)(v27 + 184),
            *(const unsigned __int16 **)(v27 + 48),
            v28,
            1,
            **(_DWORD **)(v27 + 184),
            *(_DWORD *)(*(_QWORD *)(v27 + 184) + 8LL),
            v64,
            v66);
        else
          WMS_ERROR_LOGGER::LogRangeGlobal(
            (WMS_ERROR_LOGGER *)v11,
            *(const unsigned __int16 **)(v27 + 48),
            v28,
            0,
            0,
            0,
            v64,
            v66);
      }
LABEL_46:
      v24 = 0;
    }
    *(_DWORD *)(*((_QWORD *)this + 55) + 148LL) = v23;
  }
  if ( (*((_DWORD *)a2 + 60) & 0x800) != 0 )
  {
    for ( j = *(WMS_ERROR_LOGGER **)v6; j != v6; j = *(WMS_ERROR_LOGGER **)j )
    {
      v11 = *((_QWORD *)j - 1);
      if ( *(_DWORD *)(v11 + 8) == 64 )
        goto LABEL_54;
    }
    v11 = 0;
LABEL_54:
    if ( !v23 && v11 )
    {
      v70 = *(unsigned __int16 **)(v11 + 160);
      WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0x800013C9, 1u, (const unsigned __int16 **const)&v70, 0);
    }
    v24 = *((_DWORD *)a2 + 35);
    v30 = *((_QWORD *)this + 55);
    LODWORD(v71) = v24;
    *(_DWORD *)(v30 + 152) = v24;
  }
  if ( (*((_DWORD *)a2 + 60) & 0x1000) != 0 )
  {
    v25 = *((_DWORD *)a2 + 36);
    v31 = *(WMS_ERROR_LOGGER **)v6;
    LODWORD(v72) = v25;
    while ( v31 != v6 )
    {
      v32 = *((_QWORD *)v31 - 1);
      if ( *(_DWORD *)(v32 + 8) == 65 )
      {
        if ( v32 )
        {
          WMS_ERROR_LOGGER::LogInvalidValue(
            (WMS_ERROR_LOGGER *)v11,
            L"system.applicationHost/log",
            *(const unsigned __int16 **)(v32 + 48),
            *(const unsigned __int16 **)(v32 + 160),
            *(const unsigned __int16 **)(v32 + 104),
            v62[0]);
          v24 = (int)v71;
        }
        break;
      }
      v31 = *(WMS_ERROR_LOGGER **)v31;
    }
    *(_DWORD *)(*((_QWORD *)this + 55) + 144LL) = v25;
  }
  if ( (g_dwDebugFlags & 0x1010000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    v33 = L"TRUE";
    if ( !v25 )
      v33 = L"FALSE";
    v34 = L"<NULL>";
    if ( v5 )
      v34 = v5;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      2626,
      "UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges",
      "CentralBinaryLogging Properties ( as they go to http.sys ) are \n"
      "    LogFilePeriod = %d \n"
      "   LogFileTruncateSize = %d \n"
      "   LogFileDirectory = %S \n"
      "   LocaltimeRollover = %S \n",
      v23,
      v24,
      v34,
      v33);
  }
  if ( v5 )
  {
    GlobalFree(v5);
    v5 = 0;
    hMem = 0;
  }
  if ( (g_dwDebugFlags & 0x50000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    v35 = *((_DWORD *)a2 + 60);
    v36 = L"TRUE";
    v37 = (const wchar_t **)((char *)a2 + 184);
    v38 = L"TRUE";
    v39 = L"<NULL>";
    if ( (v35 & 0x10000) == 0 )
      v38 = L"FALSE";
    v40 = L"TRUE";
    v41 = L"TRUE";
    if ( !*((_DWORD *)a2 + 54) )
      v40 = L"FALSE";
    if ( (v35 & 0x40000) == 0 )
      v41 = L"FALSE";
    if ( *v37 )
      v39 = *v37;
    v42 = L"TRUE";
    if ( (v35 & 0x8000) == 0 )
      v42 = L"FALSE";
    v43 = L"TRUE";
    if ( (v35 & 0x4000) == 0 )
      v43 = L"FALSE";
    if ( !*((_DWORD *)a2 + 17) )
      v36 = L"FALSE";
    v44 = L"TRUE";
    if ( !*v10 )
      v44 = L"FALSE";
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      2661,
      "UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges",
      "W3CLogging Properties ( as they come in from config ) are \n"
      "    CentralW3CLoggingEnabled = %S \n"
      "   CentralBinaryLoggingEnabled = %S \n"
      "   W3CLogFilePeriod = %d, %S \n"
      "   W3CLogFileTruncateSize = %d, %S \n"
      "   W3CLogFileDirectory = %S, %S \n"
      "   FileLocaltimeRollover = %S \n"
      "   W3CLogExtFileFlags = %d, %S \n",
      v44,
      v36,
      *((_DWORD *)a2 + 52),
      v43,
      *((_DWORD *)a2 + 53),
      v42,
      v39,
      v41,
      v40,
      *((_DWORD *)a2 + 55),
      v38);
  }
  v45 = (struct PROTOCOL **)((char *)a2 + 184);
  if ( (*((_DWORD *)a2 + 60) & 0x40000) != 0 )
  {
    v46 = CreateLogFileDirectory((LPCWSTR)*v45, (unsigned __int16 **)&hMem);
    if ( v46 >= 0 )
    {
      v5 = (wchar_t *)hMem;
      STRU::Copy((STRU *)(*((_QWORD *)this + 55) + 80LL), (const unsigned __int16 *)hMem);
      goto LABEL_99;
    }
LABEL_97:
    v5 = (wchar_t *)hMem;
    goto LABEL_154;
  }
  v46 = Protocol;
LABEL_99:
  v60 = (*((_DWORD *)a2 + 60) & 0x4000) == 0;
  Protocol = 0;
  if ( v60 )
  {
    v47 = v74;
  }
  else
  {
    v47 = *((_DWORD *)a2 + 52);
    for ( k = *(WMS_ERROR_LOGGER **)v6; k != v6; k = *(WMS_ERROR_LOGGER **)k )
    {
      v49 = *((_QWORD *)k - 1);
      if ( *(_DWORD *)(v49 + 8) == 67 )
      {
        if ( v49 )
        {
          v50 = *(const unsigned __int16 **)(v49 + 160);
          v65 = *(unsigned __int16 **)(v49 + 104);
          if ( *(_DWORD *)(v49 + 192) == 2 )
            WMS_ERROR_LOGGER::LogRangeGlobal(
              *(WMS_ERROR_LOGGER **)(v49 + 184),
              *(const unsigned __int16 **)(v49 + 48),
              v50,
              1,
              **(_DWORD **)(v49 + 184),
              *(_DWORD *)(*(_QWORD *)(v49 + 184) + 8LL),
              v65,
              v66);
          else
            WMS_ERROR_LOGGER::LogRangeGlobal(
              (WMS_ERROR_LOGGER *)v45,
              *(const unsigned __int16 **)(v49 + 48),
              v50,
              0,
              0,
              0,
              v65,
              v66);
        }
        break;
      }
    }
    *(_DWORD *)(*((_QWORD *)this + 55) + 164LL) = v47;
  }
  if ( (*((_DWORD *)a2 + 60) & 0x8000) != 0 )
  {
    for ( m = *(WMS_ERROR_LOGGER **)v6; m != v6; m = *(WMS_ERROR_LOGGER **)m )
    {
      v45 = (struct PROTOCOL **)*((_QWORD *)m - 1);
      if ( *((_DWORD *)v45 + 2) == 68 )
        goto LABEL_117;
    }
    v45 = 0;
LABEL_117:
    if ( !v47 && v45 )
    {
      v71 = v45[20];
      WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0x800013C9, 1u, (const unsigned __int16 **const)&v71, 0);
    }
    v52 = *((_DWORD *)a2 + 53);
    *(_DWORD *)(*((_QWORD *)this + 55) + 168LL) = v52;
  }
  else
  {
    v52 = (int)v71;
  }
  if ( (*((_DWORD *)a2 + 60) & 0x20000) != 0 )
  {
    LODWORD(v72) = *((_DWORD *)a2 + 54);
    for ( n = *(WMS_ERROR_LOGGER **)v6; n != v6; n = *(WMS_ERROR_LOGGER **)n )
    {
      v54 = *((_QWORD *)n - 1);
      if ( *(_DWORD *)(v54 + 8) == 69 )
      {
        if ( v54 )
          WMS_ERROR_LOGGER::LogInvalidValue(
            (WMS_ERROR_LOGGER *)v45,
            L"system.applicationHost/log",
            *(const unsigned __int16 **)(v54 + 48),
            *(const unsigned __int16 **)(v54 + 160),
            *(const unsigned __int16 **)(v54 + 104),
            v62[0]);
        break;
      }
    }
    v45 = (struct PROTOCOL **)(unsigned int)v72;
    *(_DWORD *)(*((_QWORD *)this + 55) + 160LL) = (_DWORD)v72;
  }
  if ( (*((_DWORD *)a2 + 60) & 0x10000) != 0 )
  {
    v55 = *((_DWORD *)a2 + 55);
    v56 = *(WMS_ERROR_LOGGER **)v6;
    Protocol = v55;
    while ( v56 != v6 )
    {
      v57 = *((_QWORD *)v56 - 1);
      if ( *(_DWORD *)(v57 + 8) == 70 )
      {
        if ( v57 )
        {
          WMS_ERROR_LOGGER::LogInvalidValue(
            (WMS_ERROR_LOGGER *)v45,
            L"system.applicationHost/log",
            *(const unsigned __int16 **)(v57 + 48),
            *(const unsigned __int16 **)(v57 + 160),
            *(const unsigned __int16 **)(v57 + 104),
            v62[0]);
          v55 = Protocol;
        }
        break;
      }
      v56 = *(WMS_ERROR_LOGGER **)v56;
    }
    *(_DWORD *)(*((_QWORD *)this + 55) + 156LL) = v55;
  }
  else
  {
    v55 = Protocol;
  }
  if ( (g_dwDebugFlags & 0x1010000) != 0 && (g_dwDebugFlags & 3) != 0 )
  {
    v58 = L"TRUE";
    if ( !(_DWORD)v72 )
      v58 = L"FALSE";
    v59 = L"<NULL>";
    LODWORD(v67) = v55;
    if ( v5 )
      v59 = v5;
    LODWORD(v63) = v52;
    v62[0] = v47;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\ul_and_worker_manager.cxx",
      2805,
      "UL_AND_WORKER_MANAGER::ValidateAndStoreLoggingConfigChanges",
      "CentralW3CLogging Properties ( as they go to http.sys ) are \n"
      "    LogFilePeriod = %d \n"
      "   LogFileTruncateSize = %d \n"
      "   LogFileDirectory = %S \n"
      "   LogExtFileFlags = %d \n"
      "   LocaltimeRollover = %S \n",
      *(_QWORD *)v62,
      v63,
      v59,
      v67,
      v58);
  }
  if ( v68 == 1 )
  {
    v60 = (*((_DWORD *)a2 + 60) & 0x3E00) == 0;
    goto LABEL_152;
  }
  if ( v68 != 2 )
    goto LABEL_154;
  v61 = *((_DWORD *)a2 + 60);
  if ( (v61 & 0x3C200) == 0 )
  {
    v60 = (v61 & 0x40000) == 0;
LABEL_152:
    if ( v60 )
      goto LABEL_154;
  }
  *(_DWORD *)(*((_QWORD *)this + 55) + 20LL) = 1;
LABEL_154:
  if ( v5 )
    GlobalFree(v5);
  if ( v46 < 0 )
    WEB_ADMIN_SERVICE::LogEvent(g_pWebAdminService, 0xC00013CA, 0, 0, v46);
}

```

## disassembly

```asm
0x180013404  push    rbp
0x180013406  push    rbx
0x180013407  push    rsi
0x180013408  push    rdi
0x180013409  push    r12
0x18001340b  push    r13
0x18001340d  push    r14
0x18001340f  push    r15
0x180013411  lea     rbp, [rsp-1Fh]
0x180013416  sub     rsp, 0A8h
0x18001341d  mov     rax, [rcx+1B8h]
0x180013424  lea     r8, [rbp+57h+arg_0]; struct PROTOCOL **
0x180013428  xor     ebx, ebx
0x18001342a  mov     rsi, rdx
0x18001342d  mov     r15, rcx
0x180013430  mov     [rbp+57h+hMem], rbx
0x180013434  mov     r12d, ebx
0x180013437  mov     [rbp+57h+arg_0], rbx
0x18001343b  mov     [rax+14h], ebx
0x18001343e  mov     [rbp+57h+var_60], ebx
0x180013441  call    ?FindProtocol@UL_AND_WORKER_MANAGER@@QEAAJPEBGPEAPEAVPROTOCOL@@@Z; UL_AND_WORKER_MANAGER::FindProtocol(ushort const *,PROTOCOL * *)
0x180013446  mov     [rbp+57h+arg_10], eax
0x180013449  test    eax, eax
0x18001344b  js      short loc_18001345F
0x18001344d  mov     rcx, [rbp+57h+arg_0]
0x180013451  test    rcx, rcx
0x180013454  jz      short loc_18001345F
0x180013456  mov     eax, [rcx+178h]
0x18001345c  mov     [rbp+57h+var_60], eax
0x18001345f  lea     r14, [rsi+0E0h]
0x180013466  mov     rcx, [r14]
0x180013469  jmp     short loc_180013479
0x18001346b  mov     r8, [rcx-8]
0x18001346f  cmp     dword ptr [r8+8], 34h ; '4'
0x180013474  jz      short loc_180013480
0x180013476  mov     rcx, [rcx]; this
0x180013479  cmp     rcx, r14
0x18001347c  jnz     short loc_18001346B
0x18001347e  jmp     short loc_1800134A5
0x180013480  test    r8, r8
0x180013483  jz      short loc_1800134A5
0x180013485  mov     rax, [r8+68h]
0x180013489  lea     rdx, aSystemApplicat; "system.applicationHost/log"
0x180013490  mov     r9, [r8+0A0h]; unsigned __int16 *
0x180013497  mov     r8, [r8+30h]; unsigned __int16 *
0x18001349b  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x1800134a0  call    ?LogInvalidValue@WMS_ERROR_LOGGER@@QEAAXPEBG000H@Z; WMS_ERROR_LOGGER::LogInvalidValue(ushort const *,ushort const *,ushort const *,ushort const *,int)
0x1800134a5  mov     rcx, [r15+1B8h]
0x1800134ac  mov     edx, 1
0x1800134b1  cmp     [rsi+40h], edx
0x1800134b4  jnz     short loc_1800134BD
0x1800134b6  mov     eax, edx
0x1800134b8  cmp     [rsi+44h], ebx
0x1800134bb  jnz     short loc_1800134BF
0x1800134bd  mov     eax, ebx
0x1800134bf  mov     [rcx+88h], eax
0x1800134c5  lea     r13, [rsi+48h]
0x1800134c9  cmp     dword ptr [rsi+40h], 2
0x1800134cd  mov     rcx, [r15+1B8h]
0x1800134d4  jnz     short loc_1800134DE
0x1800134d6  mov     eax, edx
0x1800134d8  cmp     [r13+0], ebx
0x1800134dc  jnz     short loc_1800134E0
0x1800134de  mov     eax, ebx
0x1800134e0  mov     [rcx+8Ch], eax
0x1800134e6  lea     rdx, aFalse_1; "FALSE"
0x1800134ed  mov     eax, cs:g_dwDebugFlags
0x1800134f3  lea     rdi, aTrue_1; "TRUE"
0x1800134fa  test    eax, 50000h
0x1800134ff  setnz   cl
0x180013502  test    al, 3
0x180013504  setnz   al
0x180013507  test    al, cl
0x180013509  jz      loc_1800135DF
0x18001350f  cmp     [rsi+90h], ebx
0x180013515  lea     r9, aNull_1; "<NULL>"
0x18001351c  mov     ecx, [rsi+0F0h]
0x180013522  lea     rbx, [rsi+70h]
0x180013526  mov     r11, rdi
0x180013529  mov     r10, rdi
0x18001352c  cmovz   r11, rdx
0x180013530  mov     rax, rdi
0x180013533  bt      ecx, 0Dh
0x180013537  mov     [rsp+0E0h+var_78], r11
0x18001353c  mov     r8, rdi
0x18001353f  cmovnb  r10, rdx
0x180013543  cmp     [rbx], r12
0x180013546  mov     [rsp+0E0h+var_80], r10
0x18001354b  cmovnz  r9, [rbx]
0x18001354f  bt      ecx, 0Bh
0x180013553  mov     [rsp+0E0h+var_88], r9
0x180013558  lea     r9, aUlAndWorkerMan_10; "UL_AND_WORKER_MANAGER::ValidateAndStore"...
0x18001355f  cmovnb  rax, rdx
0x180013563  bt      ecx, 0Ah
0x180013567  mov     [rsp+0E0h+var_90], rax
0x18001356c  lea     rcx, aFalse_1; "FALSE"
0x180013573  mov     eax, [rsi+8Ch]
0x180013579  cmovnb  r8, rdx
0x18001357d  cmp     [rsi+44h], r12d
0x180013581  mov     rdx, rdi
0x180013584  mov     dword ptr [rsp+0E0h+var_98], eax
0x180013588  mov     eax, [rsi+88h]
0x18001358e  cmovz   rdx, rcx
0x180013592  cmp     [r13+0], r12d
0x180013596  mov     rcx, rdi
0x180013599  mov     [rsp+0E0h+var_A0], r8
0x18001359e  lea     rdi, aFalse_1; "FALSE"
0x1800135a5  mov     dword ptr [rsp+0E0h+var_A8], eax
0x1800135a9  cmovz   rcx, rdi
0x1800135ad  mov     [rsp+0E0h+var_B0], rdx
0x1800135b2  lea     rax, aBinaryloggingP; "BinaryLogging Properties ( as they come"...
0x1800135b9  mov     qword ptr [rsp+0E0h+var_B8], rcx
0x1800135be  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800135c5  mov     rcx, cs:g_pDebug
0x1800135cc  mov     r8d, 9C8h
0x1800135d2  mov     [rsp+0E0h+var_C0], rax
0x1800135d7  call    cs:__imp_PuDbgPrint
0x1800135dd  jmp     short loc_1800135E3
0x1800135df  lea     rbx, [rsi+70h]
0x1800135e3  test    dword ptr [rsi+0F0h], 2000h
0x1800135ed  jz      short loc_18001361E
0x1800135ef  mov     rcx, [rbx]; lpSrc
0x1800135f2  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x1800135f6  call    ?CreateLogFileDirectory@@YAJPEBGPEAPEAG@Z; CreateLogFileDirectory(ushort const *,ushort * *)
0x1800135fb  mov     [rbp+57h+arg_10], eax
0x1800135fe  test    eax, eax
0x180013600  js      loc_180013974
0x180013606  mov     rcx, [r15+1B8h]
0x18001360d  mov     r12, [rbp+57h+hMem]
0x180013611  add     rcx, 18h
0x180013615  mov     rdx, r12
0x180013618  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001361e  xor     ebx, ebx
0x180013620  xor     edx, edx
0x180013622  xor     edi, edi
0x180013624  mov     [rbp+57h+arg_18], ebx
0x180013627  test    dword ptr [rsi+0F0h], 400h
0x180013631  mov     dword ptr [rbp+57h+arg_0], edx
0x180013634  mov     dword ptr [rbp+57h+arg_8], edi
0x180013637  jz      loc_1800136BF
0x18001363d  mov     rax, [r14]
0x180013640  mov     ebx, [rsi+88h]
0x180013646  mov     [rbp+57h+arg_18], ebx
0x180013649  cmp     rax, r14
0x18001364c  jz      short loc_1800136B2
0x18001364e  mov     rdx, [rax-8]
0x180013652  cmp     dword ptr [rdx+8], 3Fh ; '?'
0x180013656  jz      short loc_180013662
0x180013658  mov     rax, [rax]
0x18001365b  cmp     rax, r14
0x18001365e  jnz     short loc_18001364E
0x180013660  jmp     short loc_1800136B0
0x180013662  test    rdx, rdx
0x180013665  jz      short loc_1800136B0
0x180013667  cmp     dword ptr [rdx+0C0h], 2
0x18001366e  mov     rax, [rdx+68h]
0x180013672  mov     r8, [rdx+0A0h]; unsigned __int16 *
0x180013679  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 *
0x18001367e  jnz     short loc_18001369C
0x180013680  mov     rcx, [rdx+0B8h]
0x180013687  mov     r9d, 1
0x18001368d  mov     eax, [rcx+8]
0x180013690  mov     [rsp+0E0h+var_B8], eax
0x180013694  mov     eax, [rcx]
0x180013696  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18001369a  jmp     short loc_1800136A7
0x18001369c  mov     [rsp+0E0h+var_B8], edi; unsigned int
0x1800136a0  xor     r9d, r9d; int
0x1800136a3  mov     dword ptr [rsp+0E0h+var_C0], edi; Value
0x1800136a7  mov     rdx, [rdx+30h]; unsigned __int16 *
0x1800136ab  call    ?LogRangeGlobal@WMS_ERROR_LOGGER@@QEAAXPEBG0HKK0H@Z; WMS_ERROR_LOGGER::LogRangeGlobal(ushort const *,ushort const *,int,ulong,ulong,ushort const *,int)
0x1800136b0  mov     edx, edi
0x1800136b2  mov     rax, [r15+1B8h]
0x1800136b9  mov     [rax+94h], ebx
0x1800136bf  test    dword ptr [rsi+0F0h], 800h
0x1800136c9  jz      short loc_18001372B
0x1800136cb  mov     rax, [r14]
0x1800136ce  jmp     short loc_1800136DD
0x1800136d0  mov     rcx, [rax-8]
0x1800136d4  cmp     dword ptr [rcx+8], 40h ; '@'
0x1800136d8  jz      short loc_1800136E4
0x1800136da  mov     rax, [rax]
0x1800136dd  cmp     rax, r14
0x1800136e0  jnz     short loc_1800136D0
0x1800136e2  xor     ecx, ecx
0x1800136e4  test    ebx, ebx
0x1800136e6  jnz     short loc_180013715
0x1800136e8  test    rcx, rcx
0x1800136eb  jz      short loc_180013715
0x1800136ed  mov     rax, [rcx+0A0h]
0x1800136f4  lea     r8d, [rbx+1]; unsigned __int16
0x1800136f8  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x1800136ff  lea     r9, [rbp+57h+var_50]; unsigned __int16 **
0x180013703  mov     edx, 800013C9h; unsigned int
0x180013708  mov     [rbp+57h+var_50], rax
0x18001370c  mov     dword ptr [rsp+0E0h+var_C0], edi; unsigned int
0x180013710  call    ?LogEvent@WEB_ADMIN_SERVICE@@QEAAXKGQEAPEBGK@Z; WEB_ADMIN_SERVICE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180013715  mov     edx, [rsi+8Ch]
0x18001371b  mov     rax, [r15+1B8h]
0x180013722  mov     dword ptr [rbp+57h+arg_0], edx
0x180013725  mov     [rax+98h], edx
0x18001372b  test    dword ptr [rsi+0F0h], 1000h
0x180013735  jz      short loc_18001378F
0x180013737  mov     edi, [rsi+90h]
0x18001373d  mov     rax, [r14]
0x180013740  mov     dword ptr [rbp+57h+arg_8], edi
0x180013743  jmp     short loc_180013753
0x180013745  mov     r8, [rax-8]
0x180013749  cmp     dword ptr [r8+8], 41h ; 'A'
0x18001374e  jz      short loc_18001375A
0x180013750  mov     rax, [rax]
0x180013753  cmp     rax, r14
0x180013756  jnz     short loc_180013745
0x180013758  jmp     short loc_180013782
0x18001375a  test    r8, r8
0x18001375d  jz      short loc_180013782
0x18001375f  mov     rax, [r8+68h]
0x180013763  lea     rdx, aSystemApplicat; "system.applicationHost/log"
0x18001376a  mov     r9, [r8+0A0h]; unsigned __int16 *
0x180013771  mov     r8, [r8+30h]; unsigned __int16 *
0x180013775  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x18001377a  call    ?LogInvalidValue@WMS_ERROR_LOGGER@@QEAAXPEBG000H@Z; WMS_ERROR_LOGGER::LogInvalidValue(ushort const *,ushort const *,ushort const *,ushort const *,int)
0x18001377f  mov     edx, dword ptr [rbp+57h+arg_0]
0x180013782  mov     rax, [r15+1B8h]
0x180013789  mov     [rax+90h], edi
0x18001378f  mov     eax, cs:g_dwDebugFlags
0x180013795  test    eax, 1010000h
0x18001379a  setnz   cl
0x18001379d  test    al, 3
0x18001379f  setnz   al
0x1800137a2  test    al, cl
0x1800137a4  jz      short loc_180013807
0x1800137a6  test    edi, edi
0x1800137a8  lea     rax, aFalse_1; "FALSE"
0x1800137af  lea     rcx, aTrue_1; "TRUE"
0x1800137b6  mov     r8d, 0A42h
0x1800137bc  cmovz   rcx, rax
0x1800137c0  lea     r9, aUlAndWorkerMan_10; "UL_AND_WORKER_MANAGER::ValidateAndStore"...
0x1800137c7  mov     [rsp+0E0h+var_A0], rcx
0x1800137cc  lea     rax, aNull_1; "<NULL>"
0x1800137d3  mov     rcx, cs:g_pDebug
0x1800137da  test    r12, r12
0x1800137dd  cmovnz  rax, r12
0x1800137e1  mov     [rsp+0E0h+var_A8], rax
0x1800137e6  lea     rax, aCentralbinaryl_0; "CentralBinaryLogging Properties ( as th"...
0x1800137ed  mov     dword ptr [rsp+0E0h+var_B0], edx
0x1800137f1  lea     rdx, aServercommonIn_68; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800137f8  mov     [rsp+0E0h+var_B8], ebx
0x1800137fc  mov     [rsp+0E0h+var_C0], rax
0x180013801  call    cs:__imp_PuDbgPrint
0x180013807  test    r12, r12
0x18001380a  jz      short loc_18001381C
0x18001380c  mov     rcx, r12; hMem
0x18001380f  call    cs:__imp_GlobalFree
0x180013815  xor     r12d, r12d
0x180013818  mov     [rbp+57h+hMem], r12
0x18001381c  mov     eax, cs:g_dwDebugFlags
0x180013822  test    eax, 50000h
0x180013827  setnz   cl
0x18001382a  test    al, 3
0x18001382c  setnz   al
0x18001382f  test    al, cl
0x180013831  jz      loc_180013934
0x180013837  mov     ecx, [rsi+0F0h]
0x18001383d  lea     rdx, aTrue_1; "TRUE"
0x180013844  mov     ebx, [rsi+0DCh]
0x18001384a  lea     r8, aFalse_1; "FALSE"
0x180013851  bt      ecx, 10h
0x180013855  lea     rax, [rsi+0B8h]
0x18001385c  mov     rdi, rdx
0x18001385f  lea     r9, aNull_1; "<NULL>"
0x180013866  cmovnb  rdi, r8
0x18001386a  mov     r11, rdx
0x18001386d  cmp     dword ptr [rsi+0D8h], 0
0x180013874  mov     r10, rdx
0x180013877  mov     [rsp+0E0h+var_68], rdi
0x18001387c  cmovz   r11, r8
0x180013880  mov     [rsp+0E0h+var_70], ebx
0x180013884  bt      ecx, 12h
0x180013888  mov     [rsp+0E0h+var_78], r11
0x18001388d  cmovnb  r10, r8
0x180013891  cmp     qword ptr [rax], 0
0x180013895  mov     [rsp+0E0h+var_80], r10
0x18001389a  cmovnz  r9, [rax]
0x18001389e  bt      ecx, 0Fh
0x1800138a2  mov     [rsp+0E0h+var_88], r9
0x1800138a7  mov     rax, rdx
0x1800138aa  cmovnb  rax, r8
0x1800138ae  lea     r9, aUlAndWorkerMan_10; "UL_AND_WORKER_MANAGER::ValidateAndStore"...
0x1800138b5  mov     [rsp+0E0h+var_90], rax
0x1800138ba  bt      ecx, 0Eh
0x1800138be  mov     eax, [rsi+0D4h]
0x1800138c4  lea     rcx, aFalse_1; "FALSE"
0x1800138cb  mov     dword ptr [rsp+0E0h+var_98], eax
0x1800138cf  mov     r8, rdx
0x1800138d2  mov     eax, [rsi+0D0h]
0x1800138d8  cmovnb  r8, rcx
0x1800138dc  cmp     dword ptr [rsi+44h], 0
0x1800138e0  mov     [rsp+0E0h+var_A0], r8
0x1800138e5  mov     r8d, 0A65h
  ... truncated ...
```
