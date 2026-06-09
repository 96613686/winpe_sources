# ServiceStart

- ea: `0x14000664c`
- end: `0x14000711c`
- name: `ServiceStart`
- size: `2768`
- prototype: `void()`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140005890`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x14000429c`
- `0x140004bd4`
- `0x140004dd8`
- `0x140005134`
- `0x140005180`
- `0x1400053e0`
- `0x140005af8`
- `0x140005d78`
- `0x14000642c`
- `0x14000664c`
- `0x140007630`
- `0x14000fa94`
- `0x14000facc`
- `0x140010be4`
- `0x140010c98`
- `0x14001830e`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140006db4`
- `ADVAPI32!EventWrite` at `0x140006fcf`
- `ADVAPI32!EventWrite` at `0x140006db4`
- `ADVAPI32!EventWrite` at `0x140006fcf`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140006771`
- `ADVAPI32!AdjustTokenPrivileges` at `0x140006771`
- `ADVAPI32!OpenProcessToken` at `0x140006706`
- `ADVAPI32!OpenProcessToken` at `0x140006706`
- `KERNEL32!GetCurrentProcess` at `0x1400066f4`
- `KERNEL32!GetCurrentProcess` at `0x1400066f4`
- `KERNEL32!HeapFree` at `0x14000679d`
- `KERNEL32!HeapFree` at `0x14000679d`
- `KERNEL32!GetProcessHeap` at `0x1400066c8`
- `KERNEL32!GetProcessHeap` at `0x14000678f`
- `KERNEL32!GetProcessHeap` at `0x1400066c8`
- `KERNEL32!GetProcessHeap` at `0x14000678f`
- `KERNEL32!HeapAlloc` at `0x1400066e0`
- `KERNEL32!HeapAlloc` at `0x1400066e0`
- `KERNEL32!GetLastError` at `0x140006710`
- `KERNEL32!GetLastError` at `0x140006777`
- `KERNEL32!GetLastError` at `0x140006710`
- `KERNEL32!GetLastError` at `0x140006777`
- `KERNEL32!CreateEventW` at `0x140006bd3`
- `KERNEL32!CreateEventW` at `0x140006bd3`
- `KERNEL32!CloseHandle` at `0x140006782`
- `KERNEL32!CloseHandle` at `0x140006782`
- `KERNEL32!SetLastError` at `0x140006d1b`
- `KERNEL32!SetLastError` at `0x140006d67`
- `KERNEL32!SetLastError` at `0x140006fe1`
- `KERNEL32!SetLastError` at `0x140006d1b`
- `KERNEL32!SetLastError` at `0x140006d67`
- `KERNEL32!SetLastError` at `0x140006fe1`
- `KERNEL32!CreateThread` at `0x140006c25`
- `KERNEL32!CreateThread` at `0x140006c25`
- `msvcrt!_errno` at `0x140006df8`
- `msvcrt!_errno` at `0x140006df8`
- `msvcrt!free` at `0x140006cd2`
- `msvcrt!free` at `0x1400070d2`
- `msvcrt!free` at `0x140006cd2`
- `msvcrt!free` at `0x1400070d2`
- `msvcrt!_beginthreadex` at `0x140006dda`
- `msvcrt!_beginthreadex` at `0x140006dda`
- `WS2_32!FreeAddrInfoW` at `0x140006960`
- `WS2_32!FreeAddrInfoW` at `0x140006960`
- `WS2_32!GetAddrInfoW` at `0x140006907`
- `WS2_32!GetAddrInfoW` at `0x140006907`
- `WS2_32!GetHostNameW` at `0x1400068b8`
- `WS2_32!GetHostNameW` at `0x1400068b8`
- `WS2_32!__imp_WSAGetLastError` at `0x14000692b`
- `WS2_32!__imp_WSAGetLastError` at `0x14000697e`
- `WS2_32!__imp_WSAGetLastError` at `0x14000692b`
- `WS2_32!__imp_WSAGetLastError` at `0x14000697e`
- `WS2_32!__imp_WSAStartup` at `0x1400067fe`
- `WS2_32!__imp_WSAStartup` at `0x1400067fe`
- `WS2_32!__imp_WSACleanup` at `0x1400070c4`
- `WS2_32!__imp_WSACleanup` at `0x1400070c4`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140006cc2`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x140006cc2`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x140006e55`
- `RPCRT4!RpcMgmtWaitServerListen` at `0x140006e55`
- `RPCRT4!RpcServerListen` at `0x140006d5b`
- `RPCRT4!RpcServerListen` at `0x140006d5b`
- `RPCRT4!RpcServerRegisterIf` at `0x140006d0f`
- `RPCRT4!RpcServerRegisterIf` at `0x140006d0f`

## string_xrefs

- `0x140006cac`: `DiskAccess`
- `0x140006837`: `base\fs\remotefs\nfs4\client\nfsclient\service.c`
- `0x140006a36`: `base\fs\remotefs\nfs4\client\nfsclient\service.c`
- `0x140006b8e`: `base\fs\remotefs\nfs4\client\nfsclient\service.c`
- `0x140006ed4`: `base\fs\remotefs\nfs4\client\nfsclient\service.c`
- `0x140006ff6`: `base\fs\remotefs\nfs4\client\nfsclient\service.c`
- `0x140007037`: `base\fs\remotefs\nfs4\client\nfsclient\service.c`

## pseudocode

```c
void ServiceStart()
{
  void *v0; // rsi
  HANDLE ProcessHeap; // rax
  struct _TOKEN_PRIVILEGES *v2; // rbx
  signed int LastError; // edi
  HANDLE CurrentProcess; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  LUID v7; // rax
  HANDLE v8; // rax
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rbx
  unsigned int Error; // eax
  __int64 v17; // rdx
  int v18; // eax
  NTSTATUS v19; // edx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  NTSTATUS v23; // edx
  unsigned int v24; // ebx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 *v29; // rcx
  int v30; // r9d
  RPC_STATUS v31; // ebx
  RPC_STATUS v32; // eax
  RPC_STATUS v33; // eax
  int *v34; // rax
  const wchar_t *v35; // rdx
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  unsigned int v38; // eax
  unsigned int v39; // ebx
  unsigned int v40; // eax
  PSRWLOCK v41; // rcx
  PADDRINFOW ppResult; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int ThrdAddr; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  void *SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR name[1032]; // [rsp+1F0h] [rbp+F0h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  v0 = 0;
  SecurityDescriptor = 0;
  ThrdAddr = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
  TokenHandle = 0;
  ProcessHeap = GetProcessHeap();
  v2 = (struct _TOKEN_PRIVILEGES *)HeapAlloc(ProcessHeap, 8u, 0xF4u);
  LastError = 8;
  if ( v2 )
    LastError = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    LastError = GetLastError();
  if ( LastError < 0 )
  {
    if ( !v2 )
      goto LABEL_14;
  }
  else
  {
    v2->PrivilegeCount = 20;
    v5 = 0;
    do
    {
      v6 = v5;
      v7 = (LUID)*((int *)qword_14001C1F0 + v5++);
      ppResult = (PADDRINFOW)v7;
      v2->Privileges[v6].Luid = v7;
      v2->Privileges[v6].Attributes = 4;
    }
    while ( v5 != 20 );
    AdjustTokenPrivileges(TokenHandle, 0, v2, 0, 0, 0);
    GetLastError();
    CloseHandle(TokenHandle);
  }
  v8 = GetProcessHeap();
  HeapFree(v8, 0, v2);
LABEL_14:
  DaServiceLuid = 999;
  v9 = SafeInitializeCriticalSection(&DeviceListCS);
  if ( !v9 )
  {
    v11 = WSAStartup(0x101u, &WSAData);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v11);
      LOG_ERROR_EVENT_WIN32(
        (int)&EVENT_ERROR_WSASTARTUP,
        0,
        (int)L"base\\fs\\remotefs\\nfs4\\client\\nfsclient\\service.c",
        154);
      goto LABEL_180;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
    if ( !(unsigned int)ReportStatusToSCMgr(2, 0, 3000) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 14;
LABEL_54:
        WPP_SF_(v12[2], v13, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        goto LABEL_178;
      }
      goto LABEL_178;
    }
    if ( GetHostNameW(name, 1025) == -1 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_47:
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
          WPP_SF_(v14[2], 19, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
LABEL_50:
        if ( !(unsigned int)ReportStatusToSCMgr(2, 0, 6000) )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v13 = 20;
            goto LABEL_54;
          }
LABEL_178:
          WSACleanup();
          if ( v0 )
            free(v0);
          goto LABEL_180;
        }
        v18 = InitializeUpCall();
        if ( v18 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids,
              (unsigned int)v18);
          LOG_ERROR_EVENT_NTSTATUS((int)&EVENT_ERROR_INIT_REDIRECTOR, v19);
          goto LABEL_178;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        if ( !(unsigned int)ReportStatusToSCMgr(2, 0, 6000) )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v21 = 23;
LABEL_174:
            WPP_SF_(v20[2], v21, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
          }
LABEL_175:
          v41 = g_PasswdGroupContext;
          NfsClntGlobals = 1;
          if ( g_PasswdGroupContext )
            NfsUpCallPasswdGroupContextDestroy(g_PasswdGroupContext);
          ShutdownUpCall(v41);
          goto LABEL_178;
        }
        NfsUpCallPasswdGroupContextCreate();
        while ( 1 )
        {
          v24 = InitializeRedirector();
          if ( !v24 )
            break;
          v22 = dword_140021B44;
          if ( dword_140021B44 >= 5 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v24);
            LOG_ERROR_EVENT_NTSTATUS((int)&EVENT_ERROR_INIT_REDIRECTOR, v23);
            goto LABEL_175;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids,
              v24,
              dword_140021B44);
            v22 = dword_140021B44;
          }
          dword_140021B44 = v22 + 1;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        if ( !(unsigned int)ReportStatusToSCMgr(4, 0, 0) )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v26 = 27;
LABEL_81:
            WPP_SF_(v25[2], v26, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
            goto LABEL_162;
          }
          goto LABEL_162;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        g_hShutdownEvent = CreateEventW(0, 0, 0, 0);
        if ( !g_hShutdownEvent )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v26 = 29;
            goto LABEL_81;
          }
LABEL_162:
          v40 = StopRedirector();
          if ( v40 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v40);
            LOG_ERROR_EVENT_WIN32(
              (int)&EVENT_ERROR_STOP_REDIRECTOR,
              0,
              (int)L"base\\fs\\remotefs\\nfs4\\client\\nfsclient\\service.c",
              451);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
          if ( !(unsigned int)ReportStatusToSCMgr(3, 0, 3000) )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v21 = 46;
              goto LABEL_174;
            }
          }
          goto LABEL_175;
        }
        g_hRegNotificationThread = (__int64)CreateThread(0, 0, CheckForRegNotification, 0, 0, &g_dwThreadId);
        if ( !g_hRegNotificationThread )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v26 = 30;
            goto LABEL_81;
          }
          goto LABEL_162;
        }
        if ( !(unsigned int)CreateDefaultSecDescEx(&SecurityDescriptor, v27, 1180159, v28) )
        {
          v0 = SecurityDescriptor;
          v29 = EVENT_ERROR_CREATE_SD;
          v30 = 295;
LABEL_160:
          LODWORD(v35) = 0;
LABEL_161:
          LOG_ERROR_EVENT_WIN32((int)v29, (int)v35, (int)L"base\\fs\\remotefs\\nfs4\\client\\nfsclient\\service.c", v30);
          goto LABEL_162;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        v0 = SecurityDescriptor;
        v31 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0x14u, (RPC_WSTR)L"DiskAccess", SecurityDescriptor);
        if ( v0 )
        {
          free(v0);
          v0 = 0;
        }
        if ( v31 )
        {
          SetLastError(v31);
          v30 = 324;
          goto LABEL_159;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        v32 = RpcServerRegisterIf(qword_14001A930, 0, 0);
        if ( v32 )
        {
          SetLastError(v32);
          v30 = 338;
LABEL_159:
          v29 = (__int64 *)&EVENT_ERROR_RPC_FAIL;
          goto LABEL_160;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        v33 = RpcServerListen(3u, 0x14u, 1u);
        if ( v33 )
        {
          SetLastError(v33);
          v30 = 352;
          goto LABEL_159;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        if ( g_hEventProviderHandle )
          EventWrite(g_hEventProviderHandle, &EVENT_SUCCESS_START_NFS_CLIENT, 0, 0);
        if ( _beginthreadex(0, 0, DABrowse, 0, 0, &ThrdAddr) == -1 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v34 = _errno();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids,
              (unsigned int)*v34);
          }
          v29 = EVENT_ERROR_BEGINTHREAD;
          v30 = 369;
          v35 = L"DaBrowse";
          goto LABEL_161;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        if ( RpcMgmtWaitServerListen() )
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_136;
          v37 = 38;
        }
        else
        {
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
            goto LABEL_136;
          v37 = 37;
        }
        WPP_SF_(v36[2], v37, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
LABEL_136:
        v38 = StopRedirector();
        v39 = v38;
        if ( v38 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v38);
          LOG_ERROR_EVENT_WIN32(
            (int)&EVENT_ERROR_STOP_REDIRECTOR,
            0,
            (int)L"base\\fs\\remotefs\\nfs4\\client\\nfsclient\\service.c",
            408);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
          if ( !(unsigned int)ReportStatusToSCMgr(3, v39, 3000)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
          if ( (unsigned int)ReportStatusToSCMgr(1, 0, 0) )
          {
            sshStatusHandle = 0;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
          }
          if ( g_hEventProviderHandle )
            EventWrite(g_hEventProviderHandle, &EVENT_SUCCESS_STOP_NFS_CLIENT, 0, 0);
        }
        NFSFreeLanList();
        return;
      }
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      Error = WSAGetLastError();
      v17 = 18;
    }
    else
    {
      ppResult = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, name);
      if ( !GetAddrInfoW(name, 0, 0, &ppResult) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
        FreeAddrInfoW(ppResult);
        goto LABEL_46;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_47;
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      Error = WSAGetLastError();
      v17 = 16;
    }
    WPP_SF_d(v15, v17, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, Error);
LABEL_46:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v9);
LABEL_180:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
    WPP_SF_(v10[2], 47, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
}

```

## disassembly

```asm
0x14000664c  push    rbp
0x14000664e  push    rbx
0x14000664f  push    rsi
0x140006650  push    rdi
0x140006651  push    r12
0x140006653  push    r13
0x140006655  push    r15
0x140006657  lea     rbp, [rsp-910h]
0x14000665f  sub     rsp, 0A10h
0x140006666  mov     rax, cs:__security_cookie
0x14000666d  xor     rax, rsp
0x140006670  mov     [rbp+940h+var_40], rax
0x140006677  xor     edx, edx; Val
0x140006679  lea     rcx, [rsp+0A40h+WSAData]; void *
0x14000667e  mov     r8d, 198h; Size
0x140006684  call    memset_0
0x140006689  xor     esi, esi
0x14000668b  mov     [rsp+0A40h+SecurityDescriptor], rsi
0x140006690  mov     [rsp+0A40h+ThrdAddr], esi
0x140006694  mov     rcx, cs:WPP_GLOBAL_Control
0x14000669b  lea     r15, WPP_GLOBAL_Control
0x1400066a2  lea     r12, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids
0x1400066a9  cmp     rcx, r15
0x1400066ac  jz      short loc_1400066C3
0x1400066ae  test    byte ptr [rcx+1Ch], 1
0x1400066b2  jz      short loc_1400066C3
0x1400066b4  mov     rcx, [rcx+10h]
0x1400066b8  lea     edx, [rsi+0Ah]
0x1400066bb  mov     r8, r12
0x1400066be  call    WPP_SF_
0x1400066c3  mov     [rsp+0A40h+TokenHandle], rsi
0x1400066c8  call    cs:__imp_GetProcessHeap
0x1400066ce  mov     r13d, 8
0x1400066d4  mov     r8d, 0F4h; dwBytes
0x1400066da  mov     rcx, rax; hHeap
0x1400066dd  mov     edx, r13d; dwFlags
0x1400066e0  call    cs:__imp_HeapAlloc
0x1400066e6  mov     rbx, rax
0x1400066e9  mov     edi, r13d
0x1400066ec  xor     eax, eax
0x1400066ee  test    rbx, rbx
0x1400066f1  cmovnz  edi, eax
0x1400066f4  call    cs:__imp_GetCurrentProcess
0x1400066fa  mov     rcx, rax; ProcessHandle
0x1400066fd  lea     r8, [rsp+0A40h+TokenHandle]; TokenHandle
0x140006702  lea     edx, [r13+20h]; DesiredAccess
0x140006706  call    cs:__imp_OpenProcessToken
0x14000670c  test    eax, eax
0x14000670e  jnz     short loc_140006718
0x140006710  call    cs:__imp_GetLastError
0x140006716  mov     edi, eax
0x140006718  test    edi, edi
0x14000671a  js      short loc_14000678A
0x14000671c  mov     dword ptr [rbx], 14h
0x140006722  xor     edx, edx
0x140006724  lea     rcx, [rdx+rdx*2]
0x140006728  lea     rax, qword_14001C1F0
0x14000672f  movsxd  rax, dword ptr [rax+rdx*4]
0x140006733  inc     rdx
0x140006736  mov     dword ptr [rsp+0A40h+ppResult], eax
0x14000673a  shr     rax, 20h
0x14000673e  mov     dword ptr [rsp+0A40h+ppResult+4], eax
0x140006742  mov     rax, [rsp+0A40h+ppResult]
0x140006747  mov     [rbx+rcx*4+4], rax
0x14000674c  mov     dword ptr [rbx+rcx*4+0Ch], 4
0x140006754  cmp     rdx, 14h
0x140006758  jnz     short loc_140006724
0x14000675a  mov     rcx, [rsp+0A40h+TokenHandle]; TokenHandle
0x14000675f  xor     r9d, r9d; BufferLength
0x140006762  mov     [rsp+0A40h+ReturnLength], rsi; ReturnLength
0x140006767  mov     r8, rbx; NewState
0x14000676a  xor     edx, edx; DisableAllPrivileges
0x14000676c  mov     [rsp+0A40h+PreviousState], rsi; PreviousState
0x140006771  call    cs:__imp_AdjustTokenPrivileges
0x140006777  call    cs:__imp_GetLastError
0x14000677d  mov     rcx, [rsp+0A40h+TokenHandle]; hObject
0x140006782  call    cs:__imp_CloseHandle
0x140006788  jmp     short loc_14000678F
0x14000678a  test    rbx, rbx
0x14000678d  jz      short loc_1400067A3
0x14000678f  call    cs:__imp_GetProcessHeap
0x140006795  mov     r8, rbx; lpMem
0x140006798  xor     edx, edx; dwFlags
0x14000679a  mov     rcx, rax; hHeap
0x14000679d  call    cs:__imp_HeapFree
0x1400067a3  lea     rcx, DeviceListCS; lpCriticalSection
0x1400067aa  mov     cs:DaServiceLuid, 3E7h
0x1400067b5  call    SafeInitializeCriticalSection
0x1400067ba  test    eax, eax
0x1400067bc  jz      short loc_1400067F4
0x1400067be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400067c5  cmp     rcx, r15
0x1400067c8  jz      loc_1400070FB
0x1400067ce  mov     edi, 2
0x1400067d3  test    [rcx+1Ch], dil
0x1400067d7  jz      loc_1400070DF
0x1400067dd  mov     rcx, [rcx+10h]
0x1400067e1  lea     edx, [rdi+9]
0x1400067e4  mov     r9d, eax
0x1400067e7  mov     r8, r12
0x1400067ea  call    WPP_SF_d
0x1400067ef  jmp     loc_1400070D8
0x1400067f4  mov     ecx, 101h; wVersionRequested
0x1400067f9  lea     rdx, [rsp+0A40h+WSAData]; lpWSAData
0x1400067fe  call    cs:__imp_WSAStartup
0x140006804  test    eax, eax
0x140006806  jz      short loc_140006851
0x140006808  mov     rcx, cs:WPP_GLOBAL_Control
0x14000680f  mov     edi, 2
0x140006814  cmp     rcx, r15
0x140006817  jz      short loc_140006831
0x140006819  test    [rcx+1Ch], dil
0x14000681d  jz      short loc_140006831
0x14000681f  mov     rcx, [rcx+10h]
0x140006823  lea     edx, [rdi+0Ah]
0x140006826  mov     r9d, eax
0x140006829  mov     r8, r12
0x14000682c  call    WPP_SF_d
0x140006831  mov     r9d, 9Ah; int
0x140006837  lea     r8, aBaseFsRemotefs; "base\\fs\\remotefs\\nfs4\\client\\nfscl"...
0x14000683e  xor     edx, edx; int
0x140006840  lea     rcx, EVENT_ERROR_WSASTARTUP; int
0x140006847  call    LOG_ERROR_EVENT_WIN32
0x14000684c  jmp     loc_1400070D8
0x140006851  mov     rcx, cs:WPP_GLOBAL_Control
0x140006858  cmp     rcx, r15
0x14000685b  jz      short loc_140006874
0x14000685d  test    [rcx+1Ch], r13b
0x140006861  jz      short loc_140006874
0x140006863  mov     rcx, [rcx+10h]
0x140006867  mov     edx, 0Dh
0x14000686c  mov     r8, r12
0x14000686f  call    WPP_SF_
0x140006874  xor     edx, edx
0x140006876  mov     r8d, 0BB8h
0x14000687c  lea     edi, [rdx+2]
0x14000687f  mov     ecx, edi
0x140006881  call    ReportStatusToSCMgr
0x140006886  test    eax, eax
0x140006888  jnz     short loc_1400068AC
0x14000688a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006891  cmp     rcx, r15
0x140006894  jz      loc_1400070C4
0x14000689a  test    [rcx+1Ch], dil
0x14000689e  jz      loc_1400070C4
0x1400068a4  lea     edx, [rdi+0Ch]
0x1400068a7  jmp     loc_1400069EC
0x1400068ac  mov     edx, 401h; namelen
0x1400068b1  lea     rcx, [rbp+940h+name]; name
0x1400068b8  call    cs:__imp_GetHostNameW
0x1400068be  cmp     eax, 0FFFFFFFFh
0x1400068c1  jz      loc_140006968
0x1400068c7  mov     [rsp+0A40h+ppResult], rsi
0x1400068cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400068d3  cmp     rcx, r15
0x1400068d6  jz      short loc_1400068F6
0x1400068d8  test    [rcx+1Ch], r13b
0x1400068dc  jz      short loc_1400068F6
0x1400068de  mov     rcx, [rcx+10h]
0x1400068e2  lea     r9, [rbp+940h+name]
0x1400068e9  mov     edx, 0Fh
0x1400068ee  mov     r8, r12
0x1400068f1  call    WPP_SF_S
0x1400068f6  lea     r9, [rsp+0A40h+ppResult]; ppResult
0x1400068fb  xor     r8d, r8d; pHints
0x1400068fe  xor     edx, edx; pServiceName
0x140006900  lea     rcx, [rbp+940h+name]; pNodeName
0x140006907  call    cs:__imp_GetAddrInfoW
0x14000690d  test    eax, eax
0x14000690f  jz      short loc_140006938
0x140006911  mov     rcx, cs:WPP_GLOBAL_Control
0x140006918  cmp     rcx, r15
0x14000691b  jz      loc_1400069BA
0x140006921  test    [rcx+1Ch], dil
0x140006925  jz      short loc_14000699E
0x140006927  mov     rbx, [rcx+10h]
0x14000692b  call    cs:__imp_WSAGetLastError
0x140006931  mov     edx, 10h
0x140006936  jmp     short loc_140006989
0x140006938  mov     rcx, cs:WPP_GLOBAL_Control
0x14000693f  cmp     rcx, r15
0x140006942  jz      short loc_14000695B
0x140006944  test    [rcx+1Ch], r13b
0x140006948  jz      short loc_14000695B
0x14000694a  mov     rcx, [rcx+10h]
0x14000694e  mov     edx, 11h
0x140006953  mov     r8, r12
0x140006956  call    WPP_SF_
0x14000695b  mov     rcx, [rsp+0A40h+ppResult]; pAddrInfo
0x140006960  call    cs:__imp_FreeAddrInfoW
0x140006966  jmp     short loc_140006997
0x140006968  mov     rcx, cs:WPP_GLOBAL_Control
0x14000696f  cmp     rcx, r15
0x140006972  jz      short loc_1400069BA
0x140006974  test    [rcx+1Ch], dil
0x140006978  jz      short loc_14000699E
0x14000697a  mov     rbx, [rcx+10h]
0x14000697e  call    cs:__imp_WSAGetLastError
0x140006984  mov     edx, 12h
0x140006989  mov     r9d, eax
0x14000698c  mov     r8, r12
0x14000698f  mov     rcx, rbx
0x140006992  call    WPP_SF_d
0x140006997  mov     rcx, cs:WPP_GLOBAL_Control
0x14000699e  cmp     rcx, r15
0x1400069a1  jz      short loc_1400069BA
0x1400069a3  test    [rcx+1Ch], r13b
0x1400069a7  jz      short loc_1400069BA
0x1400069a9  mov     rcx, [rcx+10h]
0x1400069ad  mov     edx, 13h
0x1400069b2  mov     r8, r12
0x1400069b5  call    WPP_SF_
0x1400069ba  mov     ebx, 1770h
0x1400069bf  xor     edx, edx
0x1400069c1  mov     r8d, ebx
0x1400069c4  mov     ecx, edi
0x1400069c6  call    ReportStatusToSCMgr
0x1400069cb  test    eax, eax
0x1400069cd  jnz     short loc_1400069FD
0x1400069cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069d6  cmp     rcx, r15
0x1400069d9  jz      loc_1400070C4
0x1400069df  test    [rcx+1Ch], dil
0x1400069e3  jz      loc_1400070C4
0x1400069e9  lea     edx, [rax+14h]
0x1400069ec  mov     rcx, [rcx+10h]
0x1400069f0  mov     r8, r12
0x1400069f3  call    WPP_SF_
0x1400069f8  jmp     loc_1400070C4
0x1400069fd  call    InitializeUpCall
0x140006a02  test    eax, eax
0x140006a04  jns     short loc_140006A4E
0x140006a06  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a0d  cmp     rcx, r15
0x140006a10  jz      short loc_140006A2C
0x140006a12  test    [rcx+1Ch], dil
0x140006a16  jz      short loc_140006A2C
0x140006a18  mov     rcx, [rcx+10h]
0x140006a1c  mov     edx, 15h
0x140006a21  mov     r9d, eax
0x140006a24  mov     r8, r12
0x140006a27  call    WPP_SF_d
0x140006a2c  mov     r9d, 0CAh
0x140006a32  mov     dword ptr [rsp+0A40h+PreviousState], esi
0x140006a36  lea     r8, aBaseFsRemotefs; "base\\fs\\remotefs\\nfs4\\client\\nfscl"...
0x140006a3d  lea     rcx, EVENT_ERROR_INIT_REDIRECTOR; int
0x140006a44  call    LOG_ERROR_EVENT_NTSTATUS
0x140006a49  jmp     loc_1400070C4
0x140006a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a55  cmp     rcx, r15
0x140006a58  jz      short loc_140006A71
0x140006a5a  test    [rcx+1Ch], r13b
0x140006a5e  jz      short loc_140006A71
0x140006a60  mov     rcx, [rcx+10h]
0x140006a64  mov     edx, 16h
0x140006a69  mov     r8, r12
0x140006a6c  call    WPP_SF_
0x140006a71  mov     r8d, ebx
0x140006a74  xor     edx, edx
0x140006a76  mov     ecx, edi
0x140006a78  call    ReportStatusToSCMgr
0x140006a7d  test    eax, eax
0x140006a7f  jnz     short loc_140006AA3
0x140006a81  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a88  cmp     rcx, r15
0x140006a8b  jz      loc_1400070A4
0x140006a91  test    [rcx+1Ch], dil
0x140006a95  jz      loc_1400070A4
0x140006a9b  lea     edx, [rax+17h]
0x140006a9e  jmp     loc_140007098
0x140006aa3  call    NfsUpCallPasswdGroupContextCreate
0x140006aa8  jmp     short loc_140006AF1
0x140006aaa  mov     eax, cs:dword_140021B44
0x140006ab0  cmp     eax, 5
0x140006ab3  jge     loc_140006B5E
0x140006ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ac0  cmp     rcx, r15
0x140006ac3  jz      short loc_140006AE9
0x140006ac5  test    [rcx+1Ch], r13b
0x140006ac9  jz      short loc_140006AE9
0x140006acb  mov     rcx, [rcx+10h]
0x140006acf  mov     edx, 18h
0x140006ad4  mov     r9d, ebx
0x140006ad7  mov     dword ptr [rsp+0A40h+PreviousState], eax
0x140006adb  mov     r8, r12
0x140006ade  call    WPP_SF_dd
0x140006ae3  mov     eax, cs:dword_140021B44
0x140006ae9  inc     eax
0x140006aeb  mov     cs:dword_140021B44, eax
0x140006af1  call    InitializeRedirector
0x140006af6  mov     ebx, eax
0x140006af8  test    eax, eax
0x140006afa  jnz     short loc_140006AAA
0x140006afc  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b03  cmp     rcx, r15
0x140006b06  jz      short loc_140006B1F
0x140006b08  test    [rcx+1Ch], r13b
0x140006b0c  jz      short loc_140006B1F
0x140006b0e  mov     rcx, [rcx+10h]
0x140006b12  mov     edx, 1Ah
  ... truncated ...
```
