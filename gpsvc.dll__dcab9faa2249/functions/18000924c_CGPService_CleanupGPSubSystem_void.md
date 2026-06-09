# CGPService::CleanupGPSubSystem(void)

- ea: `0x18000924c`
- end: `0x180009a88`
- name: `?CleanupGPSubSystem@CGPService@@AEAAXXZ`
- size: `2108`
- prototype: `void __fastcall(CGPService *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180008e18`

## callees

- `0x18000885c`
- `0x180009100`
- `0x18000924c`
- `0x180009a90`
- `0x180009aec`
- `0x180009b60`
- `0x180009c78`
- `0x18000a684`
- `0x1800517f0`
- `0x180066ac4`
- `0x180075150`
- `0x180075ec0`
- `0x18007d6f0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a2a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000983f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009444`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000983f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a61`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800092ee`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000943a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000951c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800097ca`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009835`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000988b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800098ce`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800099d3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009a57`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800092ee`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000943a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000951c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800097ca`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009835`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000988b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800098ce`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800099d3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180009a57`
- `SYSNTFY!SysNotifyStopServer` at `0x180009355`
- `SYSNTFY!SysNotifyStopServer` at `0x180009355`

## string_xrefs

- `0x180009291`: `CGPService::CleanupGPSubSystem RejectNewCallers()`
- `0x1800092b3`: `CGPService::CleanupGPSubSystem RejectNewCallers()`
- `0x18000931d`: `CGPService::CleanupGPSubSystem GPUnRegisterForWinLogonEventNotification()`
- `0x18000933f`: `CGPService::CleanupGPSubSystem GPUnRegisterForWinLogonEventNotification()`
- `0x180009399`: `CGPService::CleanupGPSubSystem GroupPolicyOnServiceStop()`
- `0x1800093bb`: `CGPService::CleanupGPSubSystem GroupPolicyOnServiceStop()`
- `0x18000947b`: `CGPService::CleanupGPSubSystem StopRPCServer()`
- `0x18000949d`: `CGPService::CleanupGPSubSystem StopRPCServer()`
- `0x180009559`: `CGPService::CleanupGPSubSystem - Waiting for network connectivity`
- `0x18000957b`: `CGPService::CleanupGPSubSystem - Waiting for network connectivity`
- `0x1800095b3`: `UpdateWNFTrigger (refresh machine) failed with 0x%x.`
- `0x1800095d5`: `UpdateWNFTrigger (refresh machine) failed with 0x%x.`
- `0x1800095f9`: `UpdateWNFTrigger (refresh machine) succeeded.`
- `0x18000961b`: `UpdateWNFTrigger (refresh machine) succeeded.`
- `0x180009652`: `UpdateWNFTrigger (refresh user) failed with 0x%x.`
- `0x18000967f`: `UpdateWNFTrigger (refresh user) failed with 0x%x.`
- `0x1800096a3`: `UpdateWNFTrigger (refresh user) succeeded.`
- `0x1800096be`: `UpdateWNFTrigger (refresh user) succeeded.`
- `0x1800096db`: `CGPService::CleanupGPSubSystem - Not waiting for network connectivity`
- `0x1800096fd`: `CGPService::CleanupGPSubSystem - Not waiting for network connectivity`
- `0x180009729`: `CGPService::CleanupGPSubSystem StopSendingResourceReachableEvent()`
- `0x18000974b`: `CGPService::CleanupGPSubSystem StopSendingResourceReachableEvent()`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CGPService::CleanupGPSubSystem(CGPService *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  int v5; // eax
  SERVICE_STATUS_HANDLE v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // edi
  int v9; // eax
  SERVICE_STATUS_HANDLE v10; // rcx
  CGPRPCServerBase *v11; // rcx
  unsigned int v12; // edi
  int v13; // eax
  SERVICE_STATUS_HANDLE v14; // rcx
  CConnectivityManager *v15; // rdi
  unsigned int updated; // eax
  unsigned int v17; // eax
  void (*v18)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v19; // rdx
  unsigned int v20; // edi
  void (*v21)(unsigned int, const unsigned __int16 *, ...); // rax
  int v22; // eax
  SERVICE_STATUS_HANDLE v23; // rcx
  void *v24; // rdi
  int v25; // eax
  SERVICE_STATUS_HANDLE v26; // rcx
  int v27; // eax
  SERVICE_STATUS_HANDLE v28; // rcx
  int v29; // eax
  SERVICE_STATUS_HANDLE v30; // rcx
  int v31; // eax
  CConnectivityManager *v32; // rcx
  unsigned int v33; // edi
  int v34; // eax
  SERVICE_STATUS_HANDLE v35; // rcx
  int v36; // eax
  SERVICE_STATUS_HANDLE v37; // rcx

  v3 = *((_QWORD *)this + 13);
  if ( v3 )
  {
    if ( *((_DWORD *)this + 8) )
    {
      *(_DWORD *)(v3 + 32) = 1;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CGPService::CleanupGPSubSystem RejectNewCallers()");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CGPService::CleanupGPSubSystem RejectNewCallers()");
        }
      }
    }
  }
  v5 = ++*((_DWORD *)this + 30);
  if ( !*((_DWORD *)this + 32) )
  {
    v6 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v5;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v6, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  if ( *((_DWORD *)this + 7) && *((_QWORD *)this + 12) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::CleanupGPSubSystem GPUnRegisterForWinLogonEventNotification()");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::CleanupGPSubSystem GPUnRegisterForWinLogonEventNotification()");
      }
    }
    if ( !(unsigned int)SysNotifyStopServer(*((_QWORD *)this + 12) + 16LL) )
      *((_DWORD *)this + 7) = 0;
  }
  v7 = *((_QWORD *)this + 12);
  if ( v7 )
  {
    v8 = CGPEventSubSystem::GroupPolicyOnServiceStop(v7, *((_DWORD *)this + 13) == 1);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::CleanupGPSubSystem GroupPolicyOnServiceStop()");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::CleanupGPSubSystem GroupPolicyOnServiceStop()");
      }
    }
    if ( v8 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"Failed to notify svc stop with 0x%x", v8);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"Failed to notify svc stop with 0x%x", v8);
      }
    }
  }
  v9 = ++*((_DWORD *)this + 30);
  if ( !*((_DWORD *)this + 32) )
  {
    v10 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v9;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v10, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  v11 = (CGPRPCServerBase *)*((_QWORD *)this + 13);
  if ( v11 && *((_DWORD *)this + 8) )
  {
    v12 = CGPRPCServerBase::StopRPCServer(v11);
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::CleanupGPSubSystem StopRPCServer()");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::CleanupGPSubSystem StopRPCServer()");
      }
    }
    if ( v12 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"StopRPCServer failed with 0x%x", v12);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"StopRPCServer failed with 0x%x", v12);
      }
    }
  }
  v13 = ++*((_DWORD *)this + 30);
  if ( !*((_DWORD *)this + 32) )
  {
    v14 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v13;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v14, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  v15 = CConnectivityManager::s_pInstance;
  if ( CConnectivityManager::s_pInstance )
  {
    if ( *((_DWORD *)CConnectivityManager::s_pInstance + 30) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CGPService::CleanupGPSubSystem - Waiting for network connectivity");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CGPService::CleanupGPSubSystem - Waiting for network connectivity");
        }
      }
      updated = UpdateWNFTrigger(1, 1);
      if ( (updated & 0x80000000) == 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"UpdateWNFTrigger (refresh machine) succeeded.", updated);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"UpdateWNFTrigger (refresh machine) succeeded.", updated);
          }
        }
      }
      else if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"UpdateWNFTrigger (refresh machine) failed with 0x%x.", updated);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"UpdateWNFTrigger (refresh machine) failed with 0x%x.", updated);
        }
      }
      v17 = UpdateWNFTrigger(0, 1);
      a3 = v17;
      if ( (v17 & 0x80000000) != 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"UpdateWNFTrigger (refresh user) failed with 0x%x.", v17);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"UpdateWNFTrigger (refresh user) failed with 0x%x.", v17);
          }
        }
        goto LABEL_98;
      }
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_98;
      v18 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v19 = L"UpdateWNFTrigger (refresh user) succeeded.";
LABEL_94:
        v18(4u, v19, a3);
        goto LABEL_98;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(4u, L"UpdateWNFTrigger (refresh user) succeeded.", a3);
    }
    else
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_98;
      v18 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v19 = L"CGPService::CleanupGPSubSystem - Not waiting for network connectivity";
        goto LABEL_94;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        RedirectDebugMsg(4u, L"CGPService::CleanupGPSubSystem - Not waiting for network connectivity", a3);
    }
LABEL_98:
    v20 = CConnectivityManager::StopSendingResourceReachableEvent(v15);
    v21 = g_lpDebugMsg;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::CleanupGPSubSystem StopSendingResourceReachableEvent()");
LABEL_104:
        v21 = g_lpDebugMsg;
        goto LABEL_105;
      }
      if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::CleanupGPSubSystem StopSendingResourceReachableEvent()");
        goto LABEL_104;
      }
    }
LABEL_105:
    if ( v20 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( v21 )
      {
        v21(2u, L"StopSendingResourceReachableEvent failed with 0x%x", v20);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"StopSendingResourceReachableEvent failed with 0x%x", v20);
      }
    }
  }
  v22 = ++*((_DWORD *)this + 30);
  if ( !*((_DWORD *)this + 32) )
  {
    v23 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v22;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v23, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  v24 = (void *)*((_QWORD *)this + 11);
  if ( v24 )
  {
    CGPApplicationService::~CGPApplicationService(*((CGPApplicationService **)this + 11));
    operator delete(v24);
  }
  *((_QWORD *)this + 11) = 0;
  TraceLoggingUnregister_EventUnregister(&dword_180128070);
  v25 = ++*((_DWORD *)this + 30);
  CGPCSETelemetry::m_fUploadedMachineTelemety = 0;
  CGPCSETelemetry::m_fUploadedUserTelemety = 0;
  if ( !*((_DWORD *)this + 32) )
  {
    v26 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v25;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v26, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  if ( CGPRPCServerBase::m_instance )
    (**(void (__fastcall ***)(struct CGPRPCServerBase *, __int64))CGPRPCServerBase::m_instance)(
      CGPRPCServerBase::m_instance,
      1);
  v27 = ++*((_DWORD *)this + 30);
  CGPRPCServerBase::m_instance = 0;
  *((_QWORD *)this + 13) = 0;
  if ( !*((_DWORD *)this + 32) )
  {
    v28 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v27;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v28, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  operator delete(*((void **)this + 12));
  v29 = ++*((_DWORD *)this + 30);
  *((_QWORD *)this + 12) = 0;
  if ( !*((_DWORD *)this + 32) )
  {
    v30 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v29;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v30, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  v31 = NLMConnectionManager::CleanupClass();
  if ( v31 < 0 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"NLMConnectionManager::CleanupClass failed with 0x%x.", (unsigned __int16)v31);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"NLMConnectionManager::CleanupClass failed with 0x%x.", (unsigned __int16)v31);
    }
  }
  if ( CConnectivityManager::s_pInstance )
  {
    v33 = CConnectivityManager::Cleanup(v32);
    if ( CConnectivityManager::s_pInstance )
      (**(void (__fastcall ***)(CConnectivityManager *, __int64))CConnectivityManager::s_pInstance)(
        CConnectivityManager::s_pInstance,
        1);
    CConnectivityManager::s_pInstance = 0;
    if ( v33 && *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"CConnectivityManager::CleanupClass failed with 0x%x.", v33);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"CConnectivityManager::CleanupClass failed with 0x%x.", v33);
      }
    }
  }
  v34 = ++*((_DWORD *)this + 30);
  if ( !*((_DWORD *)this + 32) )
  {
    v35 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v34;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v35, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  if ( CDefaultPolicyApplier::s_pInstance )
  {
    operator delete(CDefaultPolicyApplier::s_pInstance);
    CDefaultPolicyApplier::s_pInstance = 0;
  }
  if ( g_bStatusCallbackInited )
  {
    DeleteCriticalSection(&g_StatusCallbackCS);
    g_bStatusCallbackInited = 0;
  }
  if ( g_bGPOCSInited )
  {
    DeleteCriticalSection(&g_GPOCS);
    g_bGPOCSInited = 0;
  }
  v36 = ++*((_DWORD *)this + 30);
  if ( !*((_DWORD *)this + 32) )
  {
    v37 = *(SERVICE_STATUS_HANDLE *)this;
    *((_DWORD *)this + 15) = 3;
    *((_DWORD *)this + 19) = v36;
    *((_DWORD *)this + 20) = 30000;
    if ( !SetServiceStatus(v37, (LPSERVICE_STATUS)this + 2) )
      GetLastError();
  }
  CGPExtensionExecutionState::Uninitialize();
  CGPServiceState::Uninitialize();
  CGPServiceConfiguration::m_CurrentConfiguration = 0;
}

```

## disassembly

```asm
0x18000924c  push    rbx
0x18000924e  push    rbp
0x18000924f  push    rsi
0x180009250  push    rdi
0x180009251  push    r12
0x180009253  push    r13
0x180009255  push    r14
0x180009257  push    r15
0x180009259  sub     rsp, 28h
0x18000925d  mov     rax, [rcx+68h]
0x180009261  mov     ebp, 4
0x180009266  xor     esi, esi
0x180009268  mov     rbx, rcx
0x18000926b  lea     r14d, [rbp-3]
0x18000926f  test    rax, rax
0x180009272  jz      short loc_1800092C1
0x180009274  cmp     [rcx+20h], esi
0x180009277  jz      short loc_1800092C1
0x180009279  mov     [rax+20h], r14d
0x18000927d  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180009283  jz      short loc_1800092C1
0x180009285  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000928c  test    rax, rax
0x18000928f  jz      short loc_1800092A1
0x180009291  lea     rdx, aCgpserviceClea_0; "CGPService::CleanupGPSubSystem RejectNe"...
0x180009298  mov     ecx, ebp
0x18000929a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000929f  jmp     short loc_1800092C1
0x1800092a1  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800092a8  jz      short loc_1800092C1
0x1800092aa  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800092b1  jz      short loc_1800092C1
0x1800092b3  lea     rdx, aCgpserviceClea_0; "CGPService::CleanupGPSubSystem RejectNe"...
0x1800092ba  mov     ecx, ebp; unsigned int
0x1800092bc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800092c1  add     [rbx+78h], r14d
0x1800092c5  mov     r12d, 3
0x1800092cb  mov     r13d, 7530h
0x1800092d1  mov     eax, [rbx+78h]
0x1800092d4  cmp     [rbx+80h], esi
0x1800092da  jnz     short loc_1800092FE
0x1800092dc  mov     rcx, [rbx]; hServiceStatus
0x1800092df  lea     rdx, [rbx+38h]; lpServiceStatus
0x1800092e3  mov     [rdx+4], r12d
0x1800092e7  mov     [rbx+4Ch], eax
0x1800092ea  mov     [rbx+50h], r13d
0x1800092ee  call    cs:__imp_SetServiceStatus
0x1800092f4  test    eax, eax
0x1800092f6  jnz     short loc_1800092FE
0x1800092f8  call    cs:__imp_GetLastError
0x1800092fe  cmp     [rbx+1Ch], esi
0x180009301  jz      short loc_180009362
0x180009303  cmp     [rbx+60h], rsi
0x180009307  jz      short loc_180009362
0x180009309  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18000930f  jz      short loc_18000934D
0x180009311  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180009318  test    rax, rax
0x18000931b  jz      short loc_18000932D
0x18000931d  lea     rdx, aCgpserviceClea_1; "CGPService::CleanupGPSubSystem GPUnRegi"...
0x180009324  mov     ecx, ebp
0x180009326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000932b  jmp     short loc_18000934D
0x18000932d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180009334  jz      short loc_18000934D
0x180009336  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000933d  jz      short loc_18000934D
0x18000933f  lea     rdx, aCgpserviceClea_1; "CGPService::CleanupGPSubSystem GPUnRegi"...
0x180009346  mov     ecx, ebp; unsigned int
0x180009348  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000934d  mov     rcx, [rbx+60h]
0x180009351  add     rcx, 10h
0x180009355  call    cs:__imp_SysNotifyStopServer
0x18000935b  test    eax, eax
0x18000935d  jnz     short loc_180009362
0x18000935f  mov     [rbx+1Ch], esi
0x180009362  mov     rcx, [rbx+60h]
0x180009366  mov     r15d, 2
0x18000936c  test    rcx, rcx
0x18000936f  jz      loc_180009419
0x180009375  cmp     [rbx+34h], r14d
0x180009379  mov     edx, esi
0x18000937b  setz    dl
0x18000937e  call    ?GroupPolicyOnServiceStop@CGPEventSubSystem@@QEAAKW4enumStopReasons@@@Z; CGPEventSubSystem::GroupPolicyOnServiceStop(enumStopReasons)
0x180009383  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180009389  mov     edi, eax
0x18000938b  jz      short loc_1800093C9
0x18000938d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180009394  test    rax, rax
0x180009397  jz      short loc_1800093A9
0x180009399  lea     rdx, aCgpserviceClea_2; "CGPService::CleanupGPSubSystem GroupPol"...
0x1800093a0  mov     ecx, ebp
0x1800093a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a7  jmp     short loc_1800093C9
0x1800093a9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800093b0  jz      short loc_1800093C9
0x1800093b2  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800093b9  jz      short loc_1800093C9
0x1800093bb  lea     rdx, aCgpserviceClea_2; "CGPService::CleanupGPSubSystem GroupPol"...
0x1800093c2  mov     ecx, ebp; unsigned int
0x1800093c4  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800093c9  test    edi, edi
0x1800093cb  jz      short loc_180009419
0x1800093cd  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800093d3  jz      short loc_180009419
0x1800093d5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800093dc  test    rax, rax
0x1800093df  jz      short loc_1800093F5
0x1800093e1  mov     r8d, edi
0x1800093e4  lea     rdx, aFailedToNotify; "Failed to notify svc stop with 0x%x"
0x1800093eb  mov     ecx, r15d
0x1800093ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f3  jmp     short loc_180009419
0x1800093f5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800093fc  jz      short loc_180009419
0x1800093fe  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180009405  jz      short loc_180009419
0x180009407  mov     r8d, edi
0x18000940a  lea     rdx, aFailedToNotify; "Failed to notify svc stop with 0x%x"
0x180009411  mov     ecx, r15d; unsigned int
0x180009414  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180009419  add     [rbx+78h], r14d
0x18000941d  mov     eax, [rbx+78h]
0x180009420  cmp     [rbx+80h], esi
0x180009426  jnz     short loc_18000944A
0x180009428  mov     rcx, [rbx]; hServiceStatus
0x18000942b  lea     rdx, [rbx+38h]; lpServiceStatus
0x18000942f  mov     [rdx+4], r12d
0x180009433  mov     [rbx+4Ch], eax
0x180009436  mov     [rbx+50h], r13d
0x18000943a  call    cs:__imp_SetServiceStatus
0x180009440  test    eax, eax
0x180009442  jnz     short loc_18000944A
0x180009444  call    cs:__imp_GetLastError
0x18000944a  mov     rcx, [rbx+68h]; this
0x18000944e  test    rcx, rcx
0x180009451  jz      loc_1800094FB
0x180009457  cmp     [rbx+20h], esi
0x18000945a  jz      loc_1800094FB
0x180009460  call    ?StopRPCServer@CGPRPCServerBase@@QEAAKXZ; CGPRPCServerBase::StopRPCServer(void)
0x180009465  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18000946b  mov     edi, eax
0x18000946d  jz      short loc_1800094AB
0x18000946f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180009476  test    rax, rax
0x180009479  jz      short loc_18000948B
0x18000947b  lea     rdx, aCgpserviceClea_3; "CGPService::CleanupGPSubSystem StopRPCS"...
0x180009482  mov     ecx, ebp
0x180009484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009489  jmp     short loc_1800094AB
0x18000948b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180009492  jz      short loc_1800094AB
0x180009494  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000949b  jz      short loc_1800094AB
0x18000949d  lea     rdx, aCgpserviceClea_3; "CGPService::CleanupGPSubSystem StopRPCS"...
0x1800094a4  mov     ecx, ebp; unsigned int
0x1800094a6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800094ab  test    edi, edi
0x1800094ad  jz      short loc_1800094FB
0x1800094af  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800094b5  jz      short loc_1800094FB
0x1800094b7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800094be  test    rax, rax
0x1800094c1  jz      short loc_1800094D7
0x1800094c3  mov     r8d, edi
0x1800094c6  lea     rdx, aStoprpcserverF; "StopRPCServer failed with 0x%x"
0x1800094cd  mov     ecx, r15d
0x1800094d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d5  jmp     short loc_1800094FB
0x1800094d7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800094de  jz      short loc_1800094FB
0x1800094e0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800094e7  jz      short loc_1800094FB
0x1800094e9  mov     r8d, edi
0x1800094ec  lea     rdx, aStoprpcserverF; "StopRPCServer failed with 0x%x"
0x1800094f3  mov     ecx, r15d; unsigned int
0x1800094f6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800094fb  add     [rbx+78h], r14d
0x1800094ff  mov     eax, [rbx+78h]
0x180009502  cmp     [rbx+80h], esi
0x180009508  jnz     short loc_18000952C
0x18000950a  mov     rcx, [rbx]; hServiceStatus
0x18000950d  lea     rdx, [rbx+38h]; lpServiceStatus
0x180009511  mov     [rdx+4], r12d
0x180009515  mov     [rbx+4Ch], eax
0x180009518  mov     [rbx+50h], r13d
0x18000951c  call    cs:__imp_SetServiceStatus
0x180009522  test    eax, eax
0x180009524  jnz     short loc_18000952C
0x180009526  call    cs:__imp_GetLastError
0x18000952c  mov     rdi, cs:?s_pInstance@CConnectivityManager@@0PEAV1@EA; CConnectivityManager * CConnectivityManager::s_pInstance
0x180009533  test    rdi, rdi
0x180009536  jz      loc_1800097A9
0x18000953c  cmp     [rdi+78h], esi
0x18000953f  jz      loc_1800096C7
0x180009545  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x18000954b  jz      short loc_180009589
0x18000954d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180009554  test    rax, rax
0x180009557  jz      short loc_180009569
0x180009559  lea     rdx, aCgpserviceClea; "CGPService::CleanupGPSubSystem - Waitin"...
0x180009560  mov     ecx, ebp
0x180009562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009567  jmp     short loc_180009589
0x180009569  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180009570  jz      short loc_180009589
0x180009572  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180009579  jz      short loc_180009589
0x18000957b  lea     rdx, aCgpserviceClea; "CGPService::CleanupGPSubSystem - Waitin"...
0x180009582  mov     ecx, ebp; unsigned int
0x180009584  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180009589  mov     edx, r14d; int
0x18000958c  mov     ecx, r14d; int
0x18000958f  call    ?UpdateWNFTrigger@@YAJHH@Z; UpdateWNFTrigger(int,int)
0x180009594  mov     r8d, eax
0x180009597  test    eax, eax
0x180009599  jns     short loc_1800095E5
0x18000959b  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800095a1  jz      loc_180009629
0x1800095a7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800095ae  test    rax, rax
0x1800095b1  jz      short loc_1800095C3
0x1800095b3  lea     rdx, aUpdatewnftrigg_6; "UpdateWNFTrigger (refresh machine) fail"...
0x1800095ba  mov     ecx, ebp
0x1800095bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c1  jmp     short loc_180009629
0x1800095c3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800095ca  jz      short loc_180009629
0x1800095cc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800095d3  jz      short loc_180009629
0x1800095d5  lea     rdx, aUpdatewnftrigg_6; "UpdateWNFTrigger (refresh machine) fail"...
0x1800095dc  mov     ecx, ebp; unsigned int
0x1800095de  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800095e3  jmp     short loc_180009629
0x1800095e5  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800095eb  jz      short loc_180009629
0x1800095ed  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800095f4  test    rax, rax
0x1800095f7  jz      short loc_180009609
0x1800095f9  lea     rdx, aUpdatewnftrigg_10; "UpdateWNFTrigger (refresh machine) succ"...
0x180009600  mov     ecx, ebp
0x180009602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009607  jmp     short loc_180009629
0x180009609  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x180009610  jz      short loc_180009629
0x180009612  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180009619  jz      short loc_180009629
0x18000961b  lea     rdx, aUpdatewnftrigg_10; "UpdateWNFTrigger (refresh machine) succ"...
0x180009622  mov     ecx, ebp; unsigned int
0x180009624  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180009629  mov     edx, r14d; int
0x18000962c  xor     ecx, ecx; int
0x18000962e  call    ?UpdateWNFTrigger@@YAJHH@Z; UpdateWNFTrigger(int,int)
0x180009633  mov     r8d, eax
0x180009636  test    eax, eax
0x180009638  jns     short loc_18000968F
0x18000963a  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180009640  jz      loc_18000970B
0x180009646  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000964d  test    rax, rax
0x180009650  jz      short loc_180009665
0x180009652  lea     rdx, aUpdatewnftrigg_14; "UpdateWNFTrigger (refresh user) failed "...
0x180009659  mov     ecx, ebp
0x18000965b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009660  jmp     loc_18000970B
0x180009665  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x18000966c  jz      loc_18000970B
0x180009672  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180009679  jz      loc_18000970B
0x18000967f  lea     rdx, aUpdatewnftrigg_14; "UpdateWNFTrigger (refresh user) failed "...
0x180009686  mov     ecx, ebp; unsigned int
0x180009688  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000968d  jmp     short loc_18000970B
0x18000968f  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x180009695  jz      short loc_18000970B
0x180009697  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000969e  test    rax, rax
0x1800096a1  jz      short loc_1800096AC
0x1800096a3  lea     rdx, aUpdatewnftrigg; "UpdateWNFTrigger (refresh user) succeed"...
0x1800096aa  jmp     short loc_1800096E2
0x1800096ac  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800096b3  jz      short loc_18000970B
0x1800096b5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800096bc  jz      short loc_18000970B
0x1800096be  lea     rdx, aUpdatewnftrigg; "UpdateWNFTrigger (refresh user) succeed"...
0x1800096c5  jmp     short loc_180009704
0x1800096c7  cmp     cs:?g_dwDebugLevel@@3KA, esi; ulong g_dwDebugLevel
0x1800096cd  jz      short loc_18000970B
0x1800096cf  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800096d6  test    rax, rax
0x1800096d9  jz      short loc_1800096EB
0x1800096db  lea     rdx, aCgpserviceClea_4; "CGPService::CleanupGPSubSystem - Not wa"...
0x1800096e2  mov     ecx, ebp
0x1800096e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096e9  jmp     short loc_18000970B
0x1800096eb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rsi; void * g_lpDebugMsgContextInstance
0x1800096f2  jz      short loc_18000970B
0x1800096f4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rsi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800096fb  jz      short loc_18000970B
0x1800096fd  lea     rdx, aCgpserviceClea_4; "CGPService::CleanupGPSubSystem - Not wa"...
  ... truncated ...
```
