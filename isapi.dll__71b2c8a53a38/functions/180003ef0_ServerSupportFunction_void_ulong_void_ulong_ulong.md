# ServerSupportFunction(void *,ulong,void *,ulong *,ulong *)

- ea: `0x180003ef0`
- end: `0x180004ae0`
- name: `?ServerSupportFunction@@YAHPEAXK0PEAK1@Z`
- size: `3056`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *this, unsigned int, struct _HSE_EXEC_URL_STATUS *, unsigned __int16 *, struct _HSE_UNICODE_URL_MAPEX_INFO *)`
- caller_count: `0`
- callee_count: `51`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800033a0`
- `0x180003ef0`
- `0x180004ae8`
- `0x180005e34`
- `0x180005e88`
- `0x180005ed0`
- `0x180005f90`
- `0x180006118`
- `0x180006428`
- `0x180006588`
- `0x1800067e4`
- `0x1800068bc`
- `0x180006970`
- `0x1800071cc`
- `0x1800073d4`
- `0x18000750c`
- `0x180007680`
- `0x180007714`
- `0x1800077f4`
- `0x180007a18`
- `0x180007b7c`
- `0x180007c50`
- `0x180007d9c`
- `0x180007e70`
- `0x180007fd8`
- `0x180008118`
- `0x1800082b0`
- `0x1800084a4`
- `0x180008584`
- `0x18000866c`
- `0x1800087c8`
- `0x180008898`
- `0x18000896c`
- `0x180008b3c`
- `0x180008d70`
- `0x180008f58`
- `0x18000917c`
- `0x18000928c`
- `0x180009428`
- `0x180009604`
- `0x1800097a0`
- `0x180009980`
- `0x180009b88`
- `0x180009d40`
- `0x180009f10`
- `0x18000a100`
- `0x18000a1ec`
- `0x18000a820`
- `0x18000b060`
- `0x1800124c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042ed`
- `iisutil!PuDbgPrint` at `0x1800042dd`
- `iisutil!PuDbgPrint` at `0x180004333`
- `iisutil!PuDbgPrint` at `0x180004380`
- `iisutil!PuDbgPrint` at `0x1800045e4`
- `iisutil!PuDbgPrint` at `0x18000490a`
- `iisutil!PuDbgPrint` at `0x18000499c`
- `iisutil!PuDbgPrint` at `0x1800049f5`
- `iisutil!PuDbgPrint` at `0x1800042dd`
- `iisutil!PuDbgPrint` at `0x180004333`
- `iisutil!PuDbgPrint` at `0x180004380`
- `iisutil!PuDbgPrint` at `0x1800045e4`
- `iisutil!PuDbgPrint` at `0x18000490a`
- `iisutil!PuDbgPrint` at `0x18000499c`
- `iisutil!PuDbgPrint` at `0x1800049f5`

## string_xrefs

- `0x1800042ba`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x18000432c`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180004379`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x1800045dd`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x18000497a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x1800049e8`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x180003fb8`: `HSE_REQ_MAP_URL_TO_PATH`
- `0x1800040a9`: `HSE_REQ_MAP_URL_TO_PATH_EX`
- `0x1800040fa`: `HSE_REQ_MAP_UNICODE_URL_TO_PATH`
- `0x1800040ee`: `HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX`
- `0x180004045`: `HSE_REQ_GET_IMPERSONATION_TOKEN`
- `0x180004039`: `HSE_REQ_IO_COMPLETION`
- `0x18000400f`: `HSE_REQ_ASYNC_READ_CLIENT`
- `0x180004112`: `HSE_REQ_GET_VIRTUAL_PATH_TOKEN`
- `0x180004182`: `HSE_REQ_UNICODE_VIRTUAL_PATH_TOKEN`
- `0x1800041a6`: `HSE_REQ_ADD_FRAGMENT_TO_CACHE`
- `0x1800041b2`: `HSE_REQ_READ_FRAGMENT_FROM_CACHE`
- `0x1800041be`: `HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE`
- `0x180004021`: `HSE_REQ_REFRESH_ISAPI_ACL`
- `0x1800041e2`: `HSE_REQ_GET_ANONYMOUS_TOKEN`
- `0x1800041ee`: `HSE_REQ_GET_UNICODE_ANONYMOUS_TOKEN`
- `0x1800041fa`: `HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK`
- `0x18000422a`: `HSE_REQ_GET_CONFIG_OBJECT`
- `0x180004242`: `HSE_REQ_GET_PROTOCOL_MANAGER_CUSTOM_INTERFACE_CALLBACK`
- `0x18000425a`: `HSE_REQ_GET_CHANNEL_BINDING_TOKEN`
- `0x18000426d`: `Unknown command: 0x%08x (%d)`
- `0x1800042c6`: `\n  ServerSupportFunction[%p]:  Command failed\n    Returning FALSE, LastError=0x%08x (%d)\n  <END>\n\n`
- `0x180004985`: `\n  ServerSupportFunction[%p]:  Command failed\n    Returning FALSE, LastError=0x%08x (%d)\n  <END>\n\n`
- `0x180004315`: `\n  ServerSupportFunction[%p]: Function Entry\n    Command: %s\n  <END>\n\n`
- `0x1800045bf`: `\n  ServerSupportFunction[%p]: Command not implemented in this IIS version\n  <END>\n\n`
- `0x180004903`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall ServerSupportFunction(
        struct ISAPI_CONTEXT *this,
        unsigned int a2,
        struct _HSE_EXEC_URL_STATUS *a3,
        unsigned __int16 *a4,
        struct _HSE_UNICODE_URL_MAPEX_INFO *a5)
{
  int v5; // eax
  int v10; // eax
  int v11; // r14d
  unsigned int v12; // eax
  int v13; // ecx
  DWORD v14; // ecx
  ISAPI_CONTEXT *v16; // rcx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned int v21; // ebx
  int v22; // eax
  int Client; // eax
  ISAPI_CONTEXT *v24; // rcx
  int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  unsigned int v30; // ebx
  unsigned int v31; // ebx
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  unsigned int v37; // ebx
  int v38; // r8d
  int v39; // r9d
  int v40; // r9d
  __int64 v41; // rbx
  unsigned int v42; // eax
  void *v43[2]; // [rsp+40h] [rbp-51h] BYREF
  char v44[64]; // [rsp+50h] [rbp-41h] BYREF

  v5 = g_dwDebugFlags;
  v43[0] = 0;
  if ( (g_dwDebugFlags & 0x2000000) == 0 )
    goto LABEL_91;
  if ( a2 > 0x402 )
  {
    switch ( a2 )
    {
      case 0x403u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_EXEC_URL_STATUS");
        break;
      case 0x404u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_SEND_CUSTOM_ERROR");
        break;
      case 0x405u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_CUSTOM_ERROR_PAGE");
        break;
      case 0x406u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_IS_IN_PROCESS");
        break;
      case 0x407u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_UNICODE_VIRTUAL_PATH_TOKEN");
        break;
      case 0x408u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_REPORT_UNHEALTHY");
        break;
      case 0x409u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_NORMALIZE_URL");
        break;
      case 0x40Au:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_ADD_FRAGMENT_TO_CACHE");
        break;
      case 0x40Bu:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_READ_FRAGMENT_FROM_CACHE");
        break;
      case 0x40Cu:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_REMOVE_FRAGMENT_FROM_CACHE");
        break;
      case 0x40Du:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_VECTOR_SEND");
        break;
      case 0x40Eu:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_ANONYMOUS_TOKEN");
        break;
      case 0x40Fu:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_METADATA_PROPERTY");
        break;
      case 0x410u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_CACHE_INVALIDATION_CALLBACK");
        break;
      case 0x411u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_UNICODE_ANONYMOUS_TOKEN");
        break;
      case 0x412u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_TRACE_INFO");
        break;
      case 0x413u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_SET_FLUSH_FLAG");
        break;
      case 0x414u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_TRACE_INFO_EX");
        break;
      case 0x415u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_RAISE_TRACE_EVENT");
        break;
      case 0x416u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_CONFIG_OBJECT");
        break;
      case 0x417u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_WORKER_PROCESS_SETTINGS");
        break;
      case 0x418u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_PROTOCOL_MANAGER_CUSTOM_INTERFACE_CALLBACK");
        break;
      case 0x419u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_CANCEL_IO");
        break;
      case 0x41Au:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_CHANNEL_BINDING_TOKEN");
        break;
      default:
        goto LABEL_82;
    }
    goto LABEL_83;
  }
  if ( a2 == 1026 )
  {
    v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_EXEC_URL");
    goto LABEL_83;
  }
  if ( a2 > 0x3F3 )
  {
    if ( a2 > 0x3FA )
    {
      switch ( a2 )
      {
        case 0x3FDu:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_VIRTUAL_PATH_TOKEN");
          goto LABEL_83;
        case 0x3FEu:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_VECTOR_SEND_DEPRECATED");
          goto LABEL_83;
        case 0x3FFu:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_MAP_UNICODE_URL_TO_PATH");
          goto LABEL_83;
        case 0x400u:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX");
          goto LABEL_83;
        case 0x401u:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_EXEC_UNICODE");
          goto LABEL_83;
      }
    }
    else
    {
      switch ( a2 )
      {
        case 0x3FAu:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_IS_CONNECTED");
          goto LABEL_83;
        case 0x3F4u:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_MAP_URL_TO_PATH_EX");
          goto LABEL_83;
        case 0x3F6u:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_ABORTIVE_CLOSE");
          goto LABEL_83;
        case 0x3F7u:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_CERT_INFO_EX");
          goto LABEL_83;
        case 0x3F8u:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_SEND_RESPONSE_HEADER_EX");
          goto LABEL_83;
        case 0x3F9u:
          v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_CLOSE_CONNECTION");
          goto LABEL_83;
      }
    }
    goto LABEL_82;
  }
  if ( a2 == 1011 )
  {
    v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_IMPERSONATION_TOKEN");
    goto LABEL_83;
  }
  if ( a2 > 0x3EB )
  {
    switch ( a2 )
    {
      case 0x3EDu:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_IO_COMPLETION");
        goto LABEL_83;
      case 0x3EEu:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_TRANSMIT_FILE");
        goto LABEL_83;
      case 0x3EFu:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_REFRESH_ISAPI_ACL");
        goto LABEL_83;
      case 0x3F0u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_IS_KEEP_CONN");
        goto LABEL_83;
      case 0x3F2u:
        v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_ASYNC_READ_CLIENT");
        goto LABEL_83;
    }
LABEL_82:
    v10 = StringCchPrintfA(v44, 0x40u, "Unknown command: 0x%08x (%d)", a2, a2);
    goto LABEL_83;
  }
  switch ( a2 )
  {
    case 0x3EBu:
      v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_APPEND_LOG_PARAMETER");
      break;
    case 1u:
      v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_SEND_URL_REDIRECT_RESP");
      break;
    case 2u:
      v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_SEND_URL");
      break;
    case 3u:
      v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_SEND_RESPONSE_HEADER");
      break;
    case 4u:
      v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_DONE_WITH_SESSION");
      break;
    case 0x3E9u:
      v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_MAP_URL_TO_PATH");
      break;
    case 0x3EAu:
      v10 = StringCchPrintfA(v44, 0x40u, "HSE_REQ_GET_SSPI_INFO");
      break;
    default:
      goto LABEL_82;
  }
LABEL_83:
  v11 = v10;
  v5 = g_dwDebugFlags;
  if ( v11 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    {
      v12 = WIN32_FROM_HRESULT(v11);
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        1253,
        "ServerSupportFunction",
        "\r\n"
        "  ServerSupportFunction[%p]:  Command failed\r\n"
        "    Returning FALSE, LastError=0x%08x (%d)\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v11,
        v12);
    }
    v13 = v11;
LABEL_87:
    v14 = WIN32_FROM_HRESULT(v13);
LABEL_88:
    SetLastError(v14);
    return 0;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
      1266,
      "ServerSupportFunction",
      "\r\n  ServerSupportFunction[%p]: Function Entry\r\n    Command: %s\r\n  <END>\r\n\r\n",
      this,
      v44);
    v5 = g_dwDebugFlags;
  }
LABEL_91:
  if ( !this )
  {
    if ( (v5 & 3) != 0 && (v5 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        1282,
        "ServerSupportFunction",
        "\r\n"
        "  ServerSupportFunction[%p]: Invalid ConnID\r\n"
        "    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
        "  <END>\r\n"
        "\r\n",
        0);
    v14 = 87;
    goto LABEL_88;
  }
  ISAPI_CONTEXT::ReferenceIsapiContext(this);
  if ( a2 > 0x402 )
  {
    switch ( a2 )
    {
      case 0x403u:
        v22 = SSFGetExecuteUrlStatus(this, a3);
        goto LABEL_121;
      case 0x404u:
        ISAPI_CONTEXT::IsapiDoRevertHack((ISAPI_CONTEXT *)&_ImageBase, v43, 1);
        Client = SSFSendCustomError(this, (struct _HSE_CUSTOM_ERROR_INFO *)a3);
        goto LABEL_111;
      case 0x405u:
        ISAPI_CONTEXT::IsapiDoRevertHack((ISAPI_CONTEXT *)&_ImageBase, v43, 1);
        Client = SSFGetCustomErrorPage(this, (struct _HSE_CUSTOM_ERROR_PAGE_INFO *)a3);
        goto LABEL_111;
      case 0x406u:
        v22 = SSFIsInProcess(this, (unsigned int *)a3);
        goto LABEL_121;
      case 0x407u:
        ISAPI_CONTEXT::IsapiDoRevertHack((ISAPI_CONTEXT *)&_ImageBase, v43, 1);
        v39 = 1;
        goto LABEL_150;
      case 0x408u:
        v22 = SSFReportUnhealthy(this, (char *)a3);
        goto LABEL_121;
      case 0x409u:
        v22 = SSFNormalizeUrl((char *)a3);
        goto LABEL_121;
      case 0x40Au:
        v22 = SSFAddFragmentToCache(this, (struct _HSE_VECTOR_ELEMENT *)a3, a4);
        goto LABEL_121;
      case 0x40Bu:
        v22 = SSFReadFragmentFromCache(this, a5->lpszPath, (unsigned __int8 *)a3, (unsigned int *)a4);
        goto LABEL_121;
      case 0x40Cu:
        v22 = SSFRemoveFragmentFromCache(this, (unsigned __int16 *)a3);
        goto LABEL_121;
      case 0x40Du:
        ISAPI_CONTEXT::IsapiDoRevertHack((ISAPI_CONTEXT *)&_ImageBase, v43, 1);
        Client = SSFVectorSend(this, (struct _HSE_RESPONSE_VECTOR *)a3);
        goto LABEL_111;
      case 0x40Eu:
        ISAPI_CONTEXT::IsapiDoRevertHack((ISAPI_CONTEXT *)&_ImageBase, v43, 1);
        v40 = 0;
        break;
      case 0x40Fu:
        v22 = SSFGetMetadataProperty(this, (unsigned __int64)a5, (unsigned __int8 *)a3, (unsigned int *)a4);
        goto LABEL_121;
      case 0x410u:
        v22 = SSFGetCacheInvalidationCallback(this, (int (**)(unsigned __int16 *))a3);
        goto LABEL_121;
      case 0x411u:
        ISAPI_CONTEXT::IsapiDoRevertHack((ISAPI_CONTEXT *)&_ImageBase, v43, 1);
        v40 = 1;
        break;
      case 0x412u:
        v22 = SSFGetTraceInfo(this, (struct _HSE_TRACE_INFO *)a3);
        goto LABEL_121;
      case 0x413u:
        v22 = SSFSetImmediateFlushFlag(this, (int)a3);
        goto LABEL_121;
      case 0x414u:
        v22 = SSFGetTraceInfoEx(this, (struct HTTP_TRACE_CONFIGURATION *)a3);
        goto LABEL_121;
      case 0x415u:
        v22 = SSFRaiseTraceEvent(this, (struct HTTP_TRACE_EVENT *)a3);
        goto LABEL_121;
      case 0x416u:
        v22 = SSFGetConfigObject(this, (struct IAppHostAdminManager **)a3);
        goto LABEL_121;
      case 0x417u:
        v22 = SSFGetWorkerProcessSettings(this, (struct IWpfSettings **)a3);
        goto LABEL_121;
      case 0x418u:
        v22 = SSFGetProtocolManagerCustomInterfaceCallback(
                this,
                (int (**)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **))a3);
        goto LABEL_121;
      case 0x419u:
        v41 = *((_QWORD *)this + 24);
        if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
            5073,
            "SSFCancelIo",
            "\r\n  HSE_REQ_CANCEL_IO [%p]: Function Entry\r\n  <END>\r\n\r\n",
            this);
        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 264LL))(v41);
        goto LABEL_121;
      case 0x41Au:
        v22 = SSFGetChannelBindingToken(this, (unsigned __int8 **)a3, (unsigned int *)a4);
        goto LABEL_121;
      default:
        goto LABEL_181;
    }
    Client = SSFGetAnonymousToken(this, (char *)a3, (void **)a4, v40);
    goto LABEL_111;
  }
  if ( a2 == 1026 )
  {
    ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
    v38 = 0;
    goto LABEL_152;
  }
  if ( a2 <= 0x3F3 )
  {
    if ( a2 == 1011 )
    {
      ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
      Client = SSFGetImpersonationToken(this, (void **)a3);
      goto LABEL_111;
    }
    if ( a2 <= 0x3EB )
    {
      if ( a2 == 1003 )
      {
        v22 = SSFAppendLog(this, (char *)a3);
        goto LABEL_121;
      }
      v17 = a2 - 1;
      if ( v17 && (v18 = v17 - 1) != 0 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            v21 = v20 - 997;
            if ( v21 )
            {
              if ( v21 == 1 )
              {
                v22 = SSFGetSspiInfo(this, (struct _SecHandle *)a3, (struct _SecHandle *)a5);
LABEL_121:
                v25 = v22;
                goto LABEL_182;
              }
              goto LABEL_181;
            }
            ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
            Client = SSFMapUrlToPath(this, (char *)a3, (unsigned int *)a4);
          }
          else
          {
            ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
            Client = SSFDoneWithSession(this, (unsigned int *)a3);
          }
        }
        else
        {
          ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
          Client = SSFSendResponseHeader(this, (char *)a3, (char *)a5);
        }
      }
      else
      {
        ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
        Client = SSFSendRedirect(this, (char *)a3);
      }
LABEL_111:
      v25 = Client;
      ISAPI_CONTEXT::IsapiUndoRevertHack(v24, v43);
      goto LABEL_182;
    }
    v26 = a2 - 1005;
    if ( !v26 )
    {
      v22 = SSFIoCompletion(
              this,
              (void (*)(struct _EXTENSION_CONTROL_BLOCK *, void *, unsigned int, unsigned int))a3,
              a5);
      goto LABEL_121;
    }
    v27 = v26 - 1;
    if ( !v27 )
    {
      ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
      Client = SSFTransmitFile(this, (struct _HSE_TF_INFO *)a3);
      goto LABEL_111;
    }
    v28 = v27 - 1;
    if ( v28 )
    {
      v29 = v28 - 1;
      if ( !v29 )
      {
        v22 = SSFIsKeepConn(this, (int *)a3);
        goto LABEL_121;
      }
      if ( v29 == 2 )
      {
        ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
        Client = SSFAsyncReadClient(this, a3, (unsigned int *)a4);
        goto LABEL_111;
      }
LABEL_181:
      v25 = -2147024776;
      goto LABEL_182;
    }
    goto LABEL_135;
  }
  if ( a2 > 0x3FA )
  {
    v34 = a2 - 1021;
    if ( !v34 )
    {
      ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
      v39 = 0;
LABEL_150:
      Client = SSFGetVirtualPathToken(this, (char *)a3, (void **)a4, v39);
      goto LABEL_111;
    }
    v35 = v34 - 1;
    if ( !v35 )
    {
      ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
      Client = SSFVectorSendDeprecated(this, (struct _HSE_RESPONSE_VECTOR_DEPRECATED *)a3);
      goto LABEL_111;
    }
    v36 = v35 - 1;
    if ( !v36 )
    {
      ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
      Client = SSFMapUnicodeUrlToPath(this, (unsigned __int16 *)a3, (unsigned int *)a4);
      goto LABEL_111;
    }
    v37 = v36 - 1;
    if ( !v37 )
    {
      ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
      Client = SSFMapUnicodeUrlToPathEx(this, (unsigned __int16 *)a3, a5, (unsigned int *)a4);
      goto LABEL_111;
    }
    if ( v37 != 1 )
      goto LABEL_181;
    ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
    v38 = 1;
LABEL_152:
    Client = SSFExecuteUrl(this, a3, v38);
    goto LABEL_111;
  }
  if ( a2 == 1018 )
  {
    v22 = SSFIsConnected(this, (int *)a3);
    goto LABEL_121;
  }
  v30 = a2 - 1012;
  if ( !v30 )
  {
    ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
    Client = SSFMapUrlToPathEx(this, (char *)a3, (struct _HSE_URL_MAPEX_INFO *)a5, (unsigned int *)a4);
    goto LABEL_111;
  }
  v31 = v30 - 2;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( !v32 )
    {
      v22 = SSFGetCertInfoEx(this, (struct _CERT_CONTEXT_EX *)a3);
      goto LABEL_121;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      ISAPI_CONTEXT::IsapiDoRevertHack(v16, v43, 1);
      Client = SSFSendResponseHeaderEx(this, (struct _HSE_SEND_HEADER_EX_INFO *)a3);
      goto LABEL_111;
    }
    if ( v33 == 1 )
    {
      v22 = SSFCloseConnection(this);
      goto LABEL_121;
    }
    goto LABEL_181;
  }
LABEL_135:
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
      1686,
      "ServerSupportFunction",
      "\r\n  ServerSupportFunction[%p]: Command not implemented in this IIS version\r\n  <END>\r\n\r\n",
      this);
  v25 = 0;
LABEL_182:
  ISAPI_CONTEXT::DereferenceIsapiContext(this);
  if ( v25 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    {
      v42 = WIN32_FROM_HRESULT(v25);
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        1811,
        "ServerSupportFunction",
        "\r\n"
        "  ServerSupportFunction[%p]:  Command failed\r\n"
        "    Returning FALSE, LastError=0x%08x (%d)\r\n"
        "  <END>\r\n"
        "\r\n",
        this,
        v25,
        v42);
    }
    v13 = v25;
    goto LABEL_87;
  }
  if ( (g_dwDebugFlags & 0x2000000) != 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
      1827,
      "ServerSupportFunction",
      "\r\n  ServerSupportFunction[%p]: Succeeded\r\n    Returning TRUE\r\n  <END>\r\n\r\n",
      this);
  return 1;
}

```

## disassembly

```asm
0x180003ef0  push    rbp
0x180003ef2  push    rbx
0x180003ef3  push    rsi
0x180003ef4  push    rdi
0x180003ef5  push    r12
0x180003ef7  push    r13
0x180003ef9  push    r14
0x180003efb  push    r15
0x180003efd  lea     rbp, [rsp-17h]
0x180003f02  sub     rsp, 0A8h
0x180003f09  mov     rax, cs:__security_cookie
0x180003f10  xor     rax, rsp
0x180003f13  mov     [rbp+4Fh+var_50], rax
0x180003f17  mov     eax, cs:g_dwDebugFlags
0x180003f1d  mov     ebx, edx
0x180003f1f  mov     r12, [rbp+4Fh+arg_20]
0x180003f23  mov     edx, 3F3h
0x180003f28  mov     [rbp+4Fh+var_A0], 0
0x180003f30  mov     r15, r9
0x180003f33  mov     rsi, r8
0x180003f36  mov     rdi, rcx
0x180003f39  lea     r8, __ImageBase
0x180003f40  lea     ecx, [rdx-8]
0x180003f43  lea     r9d, [rdx+0Fh]
0x180003f47  lea     r13d, [rdx+7]
0x180003f4b  bt      eax, 19h
0x180003f4f  jnb     loc_18000433F
0x180003f55  cmp     ebx, r9d
0x180003f58  ja      loc_18000412A
0x180003f5e  jz      loc_18000411E
0x180003f64  cmp     ebx, edx
0x180003f66  ja      loc_180004051
0x180003f6c  jz      loc_180004045
0x180003f72  cmp     ebx, ecx
0x180003f74  ja      short loc_180003FEE
0x180003f76  jz      short loc_180003FE5
0x180003f78  mov     eax, ebx
0x180003f7a  sub     eax, 1
0x180003f7d  jz      short loc_180003FDC
0x180003f7f  sub     eax, 1
0x180003f82  jz      short loc_180003FD3
0x180003f84  sub     eax, 1
0x180003f87  jz      short loc_180003FCA
0x180003f89  sub     eax, 1
0x180003f8c  jz      short loc_180003FC1
0x180003f8e  sub     eax, 3E5h
0x180003f93  jz      short loc_180003FB8
0x180003f95  cmp     eax, 1
0x180003f98  jnz     def_180004144; jumptable 0000000180004144 default case
0x180003f9e  lea     r8, aHseReqGetSspiI_2; "HSE_REQ_GET_SSPI_INFO"
0x180003fa5  mov     edx, 40h ; '@'; unsigned __int64
0x180003faa  lea     rcx, [rbp+4Fh+var_90]; char *
0x180003fae  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180003fb3  jmp     loc_180004282
0x180003fb8  lea     r8, aHseReqMapUrlTo_5; "HSE_REQ_MAP_URL_TO_PATH"
0x180003fbf  jmp     short loc_180003FA5
0x180003fc1  lea     r8, aHseReqDoneWith_0; "HSE_REQ_DONE_WITH_SESSION"
0x180003fc8  jmp     short loc_180003FA5
0x180003fca  lea     r8, aHseReqSendResp_4; "HSE_REQ_SEND_RESPONSE_HEADER"
0x180003fd1  jmp     short loc_180003FA5
0x180003fd3  lea     r8, aHseReqSendUrl; "HSE_REQ_SEND_URL"
0x180003fda  jmp     short loc_180003FA5
0x180003fdc  lea     r8, aHseReqSendUrlR; "HSE_REQ_SEND_URL_REDIRECT_RESP"
0x180003fe3  jmp     short loc_180003FA5
0x180003fe5  lea     r8, aHseReqAppendLo; "HSE_REQ_APPEND_LOG_PARAMETER"
0x180003fec  jmp     short loc_180003FA5
0x180003fee  mov     eax, ebx
0x180003ff0  sub     eax, 3EDh
0x180003ff5  jz      short loc_180004039
0x180003ff7  sub     eax, 1
0x180003ffa  jz      short loc_18000402D
0x180003ffc  sub     eax, 1
0x180003fff  jz      short loc_180004021
0x180004001  sub     eax, 1
0x180004004  jz      short loc_180004018
0x180004006  cmp     eax, 2
0x180004009  jnz     def_180004144; jumptable 0000000180004144 default case
0x18000400f  lea     r8, aHseReqAsyncRea_2; "HSE_REQ_ASYNC_READ_CLIENT"
0x180004016  jmp     short loc_180003FA5
0x180004018  lea     r8, aHseReqIsKeepCo; "HSE_REQ_IS_KEEP_CONN"
0x18000401f  jmp     short loc_180003FA5
0x180004021  lea     r8, aHseReqRefreshI; "HSE_REQ_REFRESH_ISAPI_ACL"
0x180004028  jmp     loc_180003FA5
0x18000402d  lea     r8, aHseReqTransmit_6; "HSE_REQ_TRANSMIT_FILE"
0x180004034  jmp     loc_180003FA5
0x180004039  lea     r8, aHseReqIoComple_0; "HSE_REQ_IO_COMPLETION"
0x180004040  jmp     loc_180003FA5
0x180004045  lea     r8, aHseReqGetImper; "HSE_REQ_GET_IMPERSONATION_TOKEN"
0x18000404c  jmp     loc_180003FA5
0x180004051  cmp     ebx, r13d
0x180004054  ja      short loc_1800040C1
0x180004056  jz      short loc_1800040B5
0x180004058  mov     eax, ebx
0x18000405a  sub     eax, 3F4h
0x18000405f  jz      short loc_1800040A9
0x180004061  sub     eax, 2
0x180004064  jz      short loc_18000409D
0x180004066  sub     eax, 1
0x180004069  jz      short loc_180004091
0x18000406b  sub     eax, 1
0x18000406e  jz      short loc_180004085
0x180004070  cmp     eax, 1
0x180004073  jnz     def_180004144; jumptable 0000000180004144 default case
0x180004079  lea     r8, aHseReqCloseCon; "HSE_REQ_CLOSE_CONNECTION"
0x180004080  jmp     loc_180003FA5
0x180004085  lea     r8, aHseReqSendResp; "HSE_REQ_SEND_RESPONSE_HEADER_EX"
0x18000408c  jmp     loc_180003FA5
0x180004091  lea     r8, aHseReqGetCertI_0; "HSE_REQ_GET_CERT_INFO_EX"
0x180004098  jmp     loc_180003FA5
0x18000409d  lea     r8, aHseReqAbortive; "HSE_REQ_ABORTIVE_CLOSE"
0x1800040a4  jmp     loc_180003FA5
0x1800040a9  lea     r8, aHseReqMapUrlTo; "HSE_REQ_MAP_URL_TO_PATH_EX"
0x1800040b0  jmp     loc_180003FA5
0x1800040b5  lea     r8, aHseReqIsConnec; "HSE_REQ_IS_CONNECTED"
0x1800040bc  jmp     loc_180003FA5
0x1800040c1  mov     eax, ebx
0x1800040c3  sub     eax, 3FDh
0x1800040c8  jz      short loc_180004112
0x1800040ca  sub     eax, 1
0x1800040cd  jz      short loc_180004106
0x1800040cf  sub     eax, 1
0x1800040d2  jz      short loc_1800040FA
0x1800040d4  sub     eax, 1
0x1800040d7  jz      short loc_1800040EE
0x1800040d9  cmp     eax, 1
0x1800040dc  jnz     def_180004144; jumptable 0000000180004144 default case
0x1800040e2  lea     r8, aHseReqExecUnic_0; "HSE_REQ_EXEC_UNICODE"
0x1800040e9  jmp     loc_180003FA5
0x1800040ee  lea     r8, aHseReqMapUnico_1; "HSE_REQ_MAP_UNICODE_URL_TO_PATH_EX"
0x1800040f5  jmp     loc_180003FA5
0x1800040fa  lea     r8, aHseReqMapUnico_4; "HSE_REQ_MAP_UNICODE_URL_TO_PATH"
0x180004101  jmp     loc_180003FA5
0x180004106  lea     r8, aHseReqVectorSe_1; "HSE_REQ_VECTOR_SEND_DEPRECATED"
0x18000410d  jmp     loc_180003FA5
0x180004112  lea     r8, aHseReqGetVirtu_0; "HSE_REQ_GET_VIRTUAL_PATH_TOKEN"
0x180004119  jmp     loc_180003FA5
0x18000411e  lea     r8, aHseReqExecUrl; "HSE_REQ_EXEC_URL"
0x180004125  jmp     loc_180003FA5
0x18000412a  lea     eax, [rbx-403h]; switch 24 cases
0x180004130  cmp     eax, 17h
0x180004133  ja      def_180004144; jumptable 0000000180004144 default case
0x180004139  mov     eax, ds:(jpt_180004144 - 180000000h)[r8+rax*4]
0x180004141  add     rax, r8
0x180004144  jmp     rax; switch jump
0x180004146  lea     r8, aHseReqGetExecU_3; jumptable 0000000180004144 case 1027
0x18000414d  jmp     loc_180003FA5
0x180004152  lea     r8, aHseReqSendCust_5; jumptable 0000000180004144 case 1028
0x180004159  jmp     loc_180003FA5
0x18000415e  lea     r8, aHseReqVectorSe_2; jumptable 0000000180004144 case 1037
0x180004165  jmp     loc_180003FA5
0x18000416a  lea     r8, aHseReqGetCusto_1; jumptable 0000000180004144 case 1029
0x180004171  jmp     loc_180003FA5
0x180004176  lea     r8, aHseReqIsInProc; jumptable 0000000180004144 case 1030
0x18000417d  jmp     loc_180003FA5
0x180004182  lea     r8, aHseReqUnicodeV; jumptable 0000000180004144 case 1031
0x180004189  jmp     loc_180003FA5
0x18000418e  lea     r8, aHseReqReportUn_0; jumptable 0000000180004144 case 1032
0x180004195  jmp     loc_180003FA5
0x18000419a  lea     r8, aHseReqNormaliz_2; jumptable 0000000180004144 case 1033
0x1800041a1  jmp     loc_180003FA5
0x1800041a6  lea     r8, aHseReqAddFragm; jumptable 0000000180004144 case 1034
0x1800041ad  jmp     loc_180003FA5
0x1800041b2  lea     r8, aHseReqReadFrag_0; jumptable 0000000180004144 case 1035
0x1800041b9  jmp     loc_180003FA5
0x1800041be  lea     r8, aHseReqRemoveFr_2; jumptable 0000000180004144 case 1036
0x1800041c5  jmp     loc_180003FA5
0x1800041ca  lea     r8, aHseReqGetMetad_0; jumptable 0000000180004144 case 1039
0x1800041d1  jmp     loc_180003FA5
0x1800041d6  lea     r8, aHseReqGetTrace_1; jumptable 0000000180004144 case 1042
0x1800041dd  jmp     loc_180003FA5
0x1800041e2  lea     r8, aHseReqGetAnony_0; jumptable 0000000180004144 case 1038
0x1800041e9  jmp     loc_180003FA5
0x1800041ee  lea     r8, aHseReqGetUnico; jumptable 0000000180004144 case 1041
0x1800041f5  jmp     loc_180003FA5
0x1800041fa  lea     r8, aHseReqGetCache_0; jumptable 0000000180004144 case 1040
0x180004201  jmp     loc_180003FA5
0x180004206  lea     r8, aHseReqSetFlush; jumptable 0000000180004144 case 1043
0x18000420d  jmp     loc_180003FA5
0x180004212  lea     r8, aHseReqGetTrace_2; jumptable 0000000180004144 case 1044
0x180004219  jmp     loc_180003FA5
0x18000421e  lea     r8, aHseReqRaiseTra_2; jumptable 0000000180004144 case 1045
0x180004225  jmp     loc_180003FA5
0x18000422a  lea     r8, aHseReqGetConfi; jumptable 0000000180004144 case 1046
0x180004231  jmp     loc_180003FA5
0x180004236  lea     r8, aHseReqGetWorke; jumptable 0000000180004144 case 1047
0x18000423d  jmp     loc_180003FA5
0x180004242  lea     r8, aHseReqGetProto; jumptable 0000000180004144 case 1048
0x180004249  jmp     loc_180003FA5
0x18000424e  lea     r8, aHseReqCancelIo_0; jumptable 0000000180004144 case 1049
0x180004255  jmp     loc_180003FA5
0x18000425a  lea     r8, aHseReqGetChann; jumptable 0000000180004144 case 1050
0x180004261  jmp     loc_180003FA5
0x180004266  mov     r9d, ebx; jumptable 0000000180004144 default case
0x180004269  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18000426d  lea     r8, aUnknownCommand; "Unknown command: 0x%08x (%d)"
0x180004274  mov     edx, 40h ; '@'; unsigned __int64
0x180004279  lea     rcx, [rbp+4Fh+var_90]; char *
0x18000427d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180004282  mov     r14d, eax
0x180004285  mov     eax, cs:g_dwDebugFlags
0x18000428b  test    r14d, r14d
0x18000428e  jns     short loc_1800042FA
0x180004290  test    al, 3
0x180004292  setnz   cl
0x180004295  bt      eax, 14h
0x180004299  setb    al
0x18000429c  test    al, cl
0x18000429e  jz      short loc_1800042E3
0x1800042a0  mov     ecx, r14d; int
0x1800042a3  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800042a8  mov     rcx, cs:g_pDebug
0x1800042af  lea     r9, aServersupportf_4; "ServerSupportFunction"
0x1800042b6  mov     [rsp+0E0h+var_A8], eax
0x1800042ba  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800042c1  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x1800042c6  lea     rax, aServersupportf_2; "\r\n  ServerSupportFunction[%p]:  Comma"...
0x1800042cd  mov     [rsp+0E0h+var_B8], rdi
0x1800042d2  mov     r8d, 4E5h
0x1800042d8  mov     [rsp+0E0h+var_C0], rax
0x1800042dd  call    cs:__imp_PuDbgPrint
0x1800042e3  mov     ecx, r14d; int
0x1800042e6  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800042eb  mov     ecx, eax; dwErrCode
0x1800042ed  call    cs:__imp_SetLastError
0x1800042f3  xor     eax, eax
0x1800042f5  jmp     loc_1800049FE
0x1800042fa  test    al, 3
0x1800042fc  jz      short loc_18000433F
0x1800042fe  mov     rcx, cs:g_pDebug
0x180004305  lea     rax, [rbp+4Fh+var_90]
0x180004309  mov     [rsp+0E0h+var_B0], rax
0x18000430e  lea     r9, aServersupportf_4; "ServerSupportFunction"
0x180004315  lea     rax, aServersupportf; "\r\n  ServerSupportFunction[%p]: Functi"...
0x18000431c  mov     [rsp+0E0h+var_B8], rdi
0x180004321  mov     r8d, 4F2h
0x180004327  mov     [rsp+0E0h+var_C0], rax
0x18000432c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004333  call    cs:__imp_PuDbgPrint
0x180004339  mov     eax, cs:g_dwDebugFlags
0x18000433f  test    rdi, rdi
0x180004342  jnz     short loc_180004390
0x180004344  test    al, 3
0x180004346  setnz   cl
0x180004349  bt      eax, 14h
0x18000434d  setb    al
0x180004350  test    al, cl
0x180004352  jz      short loc_180004386
0x180004354  mov     rcx, cs:g_pDebug
0x18000435b  lea     rax, aServersupportf_0; "\r\n  ServerSupportFunction[%p]: Invali"...
0x180004362  mov     [rsp+0E0h+var_B8], rdi
0x180004367  lea     r9, aServersupportf_4; "ServerSupportFunction"
0x18000436e  mov     r8d, 502h
0x180004374  mov     [rsp+0E0h+var_C0], rax
0x180004379  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004380  call    cs:__imp_PuDbgPrint
0x180004386  mov     ecx, 57h ; 'W'
0x18000438b  jmp     loc_1800042ED
0x180004390  mov     rcx, rdi; this
0x180004393  call    ?ReferenceIsapiContext@ISAPI_CONTEXT@@QEAAXXZ; ISAPI_CONTEXT::ReferenceIsapiContext(void)
0x180004398  mov     eax, 402h
0x18000439d  mov     r14d, 1
0x1800043a3  cmp     ebx, eax
0x1800043a5  ja      loc_1800046F9
0x1800043ab  jz      loc_1800046DA
0x1800043b1  mov     eax, 3F3h
0x1800043b6  cmp     ebx, eax
0x1800043b8  ja      loc_180004536
0x1800043be  jz      loc_18000451A
0x1800043c4  mov     eax, 3EBh
0x1800043c9  cmp     ebx, eax
0x1800043cb  ja      loc_18000449C
0x1800043d1  jz      loc_18000448F
0x1800043d7  sub     ebx, r14d
0x1800043da  jz      loc_180004476
0x1800043e0  sub     ebx, r14d
0x1800043e3  jz      loc_180004476
0x1800043e9  sub     ebx, r14d
0x1800043ec  jz      short loc_18000444C
0x1800043ee  sub     ebx, r14d
0x1800043f1  jz      short loc_180004433
0x1800043f3  sub     ebx, 3E5h
0x1800043f9  jz      short loc_180004417
0x1800043fb  cmp     ebx, r14d
0x1800043fe  jnz     def_180004719; jumptable 0000000180004719 default case
0x180004404  mov     r8, r12; struct _SecHandle *
0x180004407  mov     rdx, rsi; struct _SecHandle *
0x18000440a  mov     rcx, rdi; struct ISAPI_CONTEXT *
0x18000440d  call    ?SSFGetSspiInfo@@YAJPEAVISAPI_CONTEXT@@PEAU_SecHandle@@1@Z; SSFGetSspiInfo(ISAPI_CONTEXT *,_SecHandle *,_SecHandle *)
0x180004412  jmp     loc_1800044E7
0x180004417  mov     r8d, r14d; int
0x18000441a  lea     rdx, [rbp+4Fh+var_A0]; void **
0x18000441e  call    ?IsapiDoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAXH@Z; ISAPI_CONTEXT::IsapiDoRevertHack(void * *,int)
0x180004423  mov     r8, r15; unsigned int *
0x180004426  mov     rdx, rsi; char *
0x180004429  mov     rcx, rdi; struct ISAPI_CONTEXT *
0x18000442c  call    ?SSFMapUrlToPath@@YAJPEAVISAPI_CONTEXT@@PEADPEAK@Z; SSFMapUrlToPath(ISAPI_CONTEXT *,char *,ulong *)
0x180004431  jmp     short loc_180004466
0x180004433  mov     r8d, r14d; int
0x180004436  lea     rdx, [rbp+4Fh+var_A0]; void **
0x18000443a  call    ?IsapiDoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAXH@Z; ISAPI_CONTEXT::IsapiDoRevertHack(void * *,int)
  ... truncated ...
```
