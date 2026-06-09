# CGPService::DoAsyncInitialization(void *)

- ea: `0x180036340`
- end: `0x18003716f`
- name: `?DoAsyncInitialization@CGPService@@CAKPEAX@Z`
- size: `3631`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180035570`

## callees

- `0x180014080`
- `0x180036340`
- `0x180037178`
- `0x1800371c4`
- `0x1800373cc`
- `0x180037470`
- `0x180037804`
- `0x1800379b0`
- `0x180038420`
- `0x1800384b0`
- `0x180038a60`
- `0x18006d498`
- `0x18006f70c`
- `0x180075ec0`
- `0x18007d320`
- `0x18007d770`
- `0x18007de08`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180036e91`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x180036e91`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800369a9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036cb7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036d11`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800369a9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036cb7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180036d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ff0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036b18`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036a0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036a0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180036629`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180036629`
- `ntdll!EtwEventWrite` at `0x180036aff`
- `ntdll!EtwEventWrite` at `0x180036fe6`
- `ntdll!EtwEventWrite` at `0x180036aff`
- `ntdll!EtwEventWrite` at `0x180036fe6`
- `ntdll!EtwEventActivityIdControl` at `0x180036a93`
- `ntdll!EtwEventActivityIdControl` at `0x180036a93`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18003650a`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18003650a`
- `DSROLE!DsRoleFreeMemory` at `0x180036558`
- `DSROLE!DsRoleFreeMemory` at `0x180036558`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180036bfc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180036bfc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180036386`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180036386`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800370f9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800370f9`

## string_xrefs

- `0x180036ba9`: `Updating the service status to be RUNNING and processing triggers.`
- `0x180036bd0`: `Updating the service status to be RUNNING and processing triggers.`
- `0x1800363ab`: `CGPService::DoAsyncInitialization started.`
- `0x1800363d2`: `CGPService::DoAsyncInitialization started.`
- `0x1800363fd`: `CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass`
- `0x180036424`: `CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass`
- `0x180036466`: `CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass failed with 0x%x.`
- `0x180036497`: `CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass failed with 0x%x.`
- `0x1800364c0`: `CGPService::DoAsyncInitialization: GetDomainMembershipOfMachine.`
- `0x1800364e5`: `CGPService::DoAsyncInitialization: GetDomainMembershipOfMachine.`
- `0x1800365e6`: `CGPService::DoAsyncInitialization: GetVersionEx.`
- `0x18003660b`: `CGPService::DoAsyncInitialization: GetVersionEx.`
- `0x18003665b`: `CGPService::DoAsyncInitialization Domain Controller.`
- `0x180036680`: `CGPService::DoAsyncInitialization Domain Controller.`
- `0x18003669d`: `CGPService::DoAsyncInitialization Not a Domain Controller.`
- `0x1800366c2`: `CGPService::DoAsyncInitialization Not a Domain Controller.`
- `0x18003670e`: `CGPService::DoAsyncInitialization Terminal Server.`
- `0x180036735`: `CGPService::DoAsyncInitialization Terminal Server.`
- `0x180036757`: `CGPService::DoAsyncInitialization Not a Terminal Server.`
- `0x18003677c`: `CGPService::DoAsyncInitialization Not a Terminal Server.`
- `0x1800367a2`: `CGPService::DoAsyncInitialization: CConnectivityManager::InitializeClass.`
- `0x1800367c9`: `CGPService::DoAsyncInitialization: CConnectivityManager::InitializeClass.`
- `0x180036950`: `CGPService::DoAsyncInitialization: CGPSqm::Initialize.`
- `0x180036977`: `CGPService::DoAsyncInitialization: CGPSqm::Initialize.`
- `0x1800369c4`: `CGPService::DoAsyncInitialization m_hAsyncInitializationCompletedEvent set.`
- `0x1800369eb`: `CGPService::DoAsyncInitialization m_hAsyncInitializationCompletedEvent set.`
- `0x180036b38`: `CGPService::DoAsyncInitialization Signalling service to stop.`
- `0x180036b5f`: `CGPService::DoAsyncInitialization Signalling service to stop.`
- `0x180036c25`: `CGPService::DoAsyncInitialization UpdateServiceStatusAsRunning(TRUE).`
- `0x180036c4c`: `CGPService::DoAsyncInitialization UpdateServiceStatusAsRunning(TRUE).`
- `0x180036c6a`: `CGPService::DoAsyncInitialization No idle timer.`
- `0x180036c91`: `CGPService::DoAsyncInitialization No idle timer.`
- `0x180036cd2`: `CGPService::DoAsyncInitialization pGPService->SetServiceInitialized().`
- `0x180036cf9`: `CGPService::DoAsyncInitialization pGPService->SetServiceInitialized().`
- `0x180036d2c`: `CGPService::DoAsyncInitialization SetEvent( s_hEventInitialized ).`
- `0x180036d53`: `CGPService::DoAsyncInitialization SetEvent( s_hEventInitialized ).`
- `0x180036d83`: `CGPService::DoAsyncInitialization: DeletePolicyTask.`
- `0x180036daa`: `CGPService::DoAsyncInitialization: DeletePolicyTask.`
- `0x180036ddd`: `Cleanup Machine Background Task 0x%x.`
- `0x180036e04`: `Cleanup Machine Background Task 0x%x.`
- `0x180036e34`: `Cleanup User Background Task 0x%x.`
- `0x180036e5b`: `Cleanup User Background Task 0x%x.`
- `0x18003700a`: `CGPService::DoAsyncInitialization CGPServiceConfiguration::Initialize().`
- `0x18003702f`: `CGPService::DoAsyncInitialization CGPServiceConfiguration::Initialize().`
- `0x180037059`: `CGPService::DoAsyncInitialization CGPServiceState::Initialize().`
- `0x18003707e`: `CGPService::DoAsyncInitialization CGPServiceState::Initialize().`
- `0x1800370be`: `CGPService::DoAsyncInitialization CGPExtensionExecutionState::Initialize().`
- `0x1800370e3`: `CGPService::DoAsyncInitialization CGPExtensionExecutionState::Initialize().`
- `0x180037113`: `CGPService::DoAsyncInitialization completed.`
- `0x180037138`: `CGPService::DoAsyncInitialization completed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGPService::DoAsyncInitialization(char *Parameter)
{
  HRESULT v2; // r13d
  DWORD PrimaryDomainInformation; // r15d
  int v4; // r14d
  unsigned int v5; // r12d
  int v6; // ebx
  PBYTE v7; // rdx
  int v8; // edi
  int v9; // r15d
  BOOL v10; // ebx
  struct IGPEventSubSystem *v11; // rdi
  BYTE *v12; // rax
  CConnectivityManager *v13; // rcx
  __int64 v14; // r8
  unsigned int EventDataDescriptorStorage; // eax
  _QWORD *v16; // rdi
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned __int64 v19; // r14
  __int64 v20; // r8
  unsigned int v21; // eax
  __int64 v22; // rax
  void *v23; // rcx
  void (*v24)(unsigned int, const unsigned __int16 *, ...); // rax
  __int64 v25; // r8
  __int64 v26; // r8
  unsigned int ServiceConfiguration; // ebx
  __int64 v28; // r11
  __int64 v29; // rdx
  wchar_t *v30; // r8
  __int64 v31; // rcx
  __int64 v32; // r9
  HLOCAL *p_hMem; // r10
  wchar_t v34; // ax
  HLOCAL *v35; // rax
  wchar_t *v36; // rdx
  int v37; // r9d
  wchar_t v38; // ax
  __int64 v39; // rax
  __int64 *v40; // rdx
  PBYTE Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v44; // [rsp+168h] [rbp+68h]
  char v45; // [rsp+16Ah] [rbp+6Ah]
  HLOCAL *v46; // [rsp+170h] [rbp+70h] BYREF
  int v47; // [rsp+178h] [rbp+78h]
  int v48; // [rsp+17Ch] [rbp+7Ch]
  PBYTE *v49; // [rsp+180h] [rbp+80h]
  __int64 v50; // [rsp+188h] [rbp+88h]
  HLOCAL hMem; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v52; // [rsp+1A8h] [rbp+A8h]
  wchar_t v54[16]; // [rsp+1C0h] [rbp+C0h] BYREF

  memset_0(&VersionInformation, 0, 0x11Cu);
  v2 = CoInitializeEx(0, 0);
  InitDebugSupport(0);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization started.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization started.");
    }
  }
  CGPService::OutputDeveloperLogHeader();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass");
    }
  }
  PrimaryDomainInformation = CDefaultPolicyApplier::InitializeClass();
  v4 = 0;
  v5 = 2;
  if ( PrimaryDomainInformation )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          2u,
          L"CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass failed with 0x%x.",
          PrimaryDomainInformation);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          2u,
          L"CGPService::DoAsyncInitialization: CDefaultPolicyApplier::InitializeClass failed with 0x%x.",
          PrimaryDomainInformation);
      }
    }
    goto LABEL_118;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization: GetDomainMembershipOfMachine.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization: GetDomainMembershipOfMachine.");
    }
  }
  Buffer[0] = 0;
  v6 = 2;
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, Buffer);
  v7 = Buffer[0];
  if ( !PrimaryDomainInformation )
  {
    if ( (*(_DWORD *)Buffer[0] & 0xFFFFFFFD) != 0 )
    {
      if ( (unsigned int)(*(_DWORD *)Buffer[0] - 4) > 1 )
      {
        if ( (*((_DWORD *)Buffer[0] + 1) & 0x1000000) == 0
          || (unsigned int)IsNullGUID((const struct _GUID *)Buffer[0] + 2) )
        {
          v6 = 1;
        }
        goto LABEL_34;
      }
    }
    else
    {
      v6 = 0;
    }
    PrimaryDomainInformation = 0;
  }
LABEL_34:
  if ( v7 )
    DsRoleFreeMemory(v7);
  if ( PrimaryDomainInformation )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"GetDomainMembershipOfMachine failed with 0x%x.", PrimaryDomainInformation);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"GetDomainMembershipOfMachine failed with 0x%x.", PrimaryDomainInformation);
      }
    }
    goto LABEL_118;
  }
  v8 = 0;
  v9 = 0;
  LOBYTE(v4) = v6 == 2;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization: GetVersionEx.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization: GetVersionEx.");
    }
  }
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( v45 == 2 )
    {
      v8 = 1;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization Domain Controller.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization Domain Controller.");
        }
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization Not a Domain Controller.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization Not a Domain Controller.");
      }
    }
    if ( (v44 & 0x10) == 0 || (v44 & 0x100) != 0 || (unsigned __int8)(v45 - 2) > 1u )
    {
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_84;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization Not a Terminal Server.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization Not a Terminal Server.");
      }
    }
    else
    {
      v9 = 1;
      if ( !*(_DWORD *)&g_dwDebugLevel )
        goto LABEL_84;
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization Terminal Server.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization Terminal Server.");
      }
    }
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization: CConnectivityManager::InitializeClass.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization: CConnectivityManager::InitializeClass.");
    }
  }
LABEL_84:
  v10 = v8 || v9;
  if ( CConnectivityManager::s_pInstance )
  {
    PrimaryDomainInformation = 1247;
    goto LABEL_104;
  }
  v11 = (struct IGPEventSubSystem *)*((_QWORD *)Parameter + 12);
  v12 = (BYTE *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  Buffer[0] = v12;
  if ( !v12 )
  {
    CConnectivityManager::s_pInstance = 0;
    goto LABEL_103;
  }
  CConnectivityManager::s_pInstance = CConnectivityManager::CConnectivityManager((CConnectivityManager *)v12);
  if ( !CConnectivityManager::s_pInstance )
  {
LABEL_103:
    PrimaryDomainInformation = 14;
    goto LABEL_104;
  }
  PrimaryDomainInformation = CConnectivityManager::Initialize(v13, v4, v10, v11);
  if ( !PrimaryDomainInformation )
  {
    PrimaryDomainInformation = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CConnectivityManager::InitializeClass succeeded.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CConnectivityManager::InitializeClass succeeded.");
      }
    }
    goto LABEL_110;
  }
  if ( CConnectivityManager::s_pInstance )
    (**(void (__fastcall ***)(CConnectivityManager *, __int64))CConnectivityManager::s_pInstance)(
      CConnectivityManager::s_pInstance,
      1);
  CConnectivityManager::s_pInstance = 0;
LABEL_104:
  v14 = PrimaryDomainInformation;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CConnectivityManager::InitializeClass failed with 0x%x.", PrimaryDomainInformation);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"CConnectivityManager::InitializeClass failed with 0x%x.", PrimaryDomainInformation);
    }
  }
LABEL_110:
  g_hGPServiceInitialized = CGPService::s_hEventInitialized;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization: CGPSqm::Initialize.", v14);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization: CGPSqm::Initialize.", v14);
    }
  }
  if ( !CGPSqm::s_IsInitialized )
  {
    CGPSqm::s_bADDomainJoined = v4;
    CGPSqm::s_IsInitialized = 1;
  }
LABEL_118:
  SetEvent(*((HANDLE *)Parameter + 14));
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization m_hAsyncInitializationCompletedEvent set.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization m_hAsyncInitializationCompletedEvent set.");
    }
  }
  hMem = 0;
  v52 = 0;
  LODWORD(Buffer[0]) = GetTickCount() - CGPService::s_ServiceInitTime;
  EventDataDescriptorStorage = COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem);
  v16 = hMem;
  v17 = HIDWORD(v52);
  if ( !EventDataDescriptorStorage )
  {
    v18 = 2LL * HIDWORD(v52);
    *((_QWORD *)hMem + v18) = Buffer;
    v16[v18 + 1] = 4;
    HIDWORD(v52) = ++v17;
  }
  v19 = CGPServiceEventReporting::s_pEventProviderHandle;
  v20 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_BYTE *)(v20 + 8) == 1 )
  {
    v21 = EtwEventActivityIdControl(2, v20 + 16);
    if ( v21 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
            v21);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
            v21);
        }
      }
    }
  }
  if ( (unsigned int)EtwEventWrite(v19, gpEvent_GP_SERVICE_INIT_END, v17, v16) )
    GetLastError();
  if ( v16 )
    LocalFree(v16);
  if ( !PrimaryDomainInformation )
  {
    if ( g_idleTimer )
    {
      if ( !*((_DWORD *)Parameter + 32) )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Updating the service status to be RUNNING and processing triggers.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Updating the service status to be RUNNING and processing triggers.");
          }
        }
        *((_DWORD *)Parameter + 15) = 4;
        *(_QWORD *)(Parameter + 76) = 0;
        *((_DWORD *)Parameter + 16) = 1345;
        if ( !SetServiceStatus(*(SERVICE_STATUS_HANDLE *)Parameter, (LPSERVICE_STATUS)Parameter + 2) )
          GetLastError();
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization UpdateServiceStatusAsRunning(TRUE).");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization UpdateServiceStatusAsRunning(TRUE).");
        }
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization No idle timer.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization No idle timer.");
      }
    }
    v22 = *((_QWORD *)Parameter + 11);
    if ( v22 )
    {
      v23 = *(void **)(v22 + 352);
      if ( v23 )
        SetEvent(v23);
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization pGPService->SetServiceInitialized().");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization pGPService->SetServiceInitialized().");
      }
    }
    SetEvent(CGPService::s_hEventInitialized);
    v24 = g_lpDebugMsg;
    if ( !*(_DWORD *)&g_dwDebugLevel )
      goto LABEL_184;
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization SetEvent( s_hEventInitialized ).");
    }
    else
    {
      if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
      {
LABEL_184:
        if ( *((_DWORD *)Parameter + 31) )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( v24 )
            {
              v24(4u, L"CGPService::DoAsyncInitialization: DeletePolicyTask.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization: DeletePolicyTask.");
            }
          }
          v25 = (unsigned int)DeletePolicyTask(1);
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"Cleanup Machine Background Task 0x%x.", v25);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"Cleanup Machine Background Task 0x%x.", v25);
            }
          }
          v26 = (unsigned int)DeletePolicyTask(0);
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"Cleanup User Background Task 0x%x.", v26);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"Cleanup User Background Task 0x%x.", v26);
            }
          }
        }
        goto LABEL_203;
      }
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization SetEvent( s_hEventInitialized ).");
    }
    v24 = g_lpDebugMsg;
    goto LABEL_184;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization Signalling service to stop.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization Signalling service to stop.");
    }
  }
  CGPService::Stop((struct CGPService *)Parameter);
LABEL_203:
  CGPServiceConfiguration::m_CurrentConfiguration = 0;
  ServiceConfiguration = CGPServiceConfiguration::ReadServiceConfiguration();
  LODWORD(Buffer[0]) = ServiceConfiguration;
  _itow(4160, v54, 10);
  v28 = 2147483646;
  v29 = 2147483646;
  v30 = L"%%";
  v31 = 13;
  v32 = 13;
  p_hMem = &hMem;
  while ( v29 )
  {
    v34 = *v30;
    if ( !*v30 )
      break;
    ++v30;
    *(_WORD *)p_hMem = v34;
    p_hMem = (HLOCAL *)((char *)p_hMem + 2);
    --v29;
    if ( !--v32 )
    {
      *((_WORD *)p_hMem - 1) = 0;
      goto LABEL_225;
    }
  }
  *(_WORD *)p_hMem = 0;
  v35 = &hMem;
  while ( *(_WORD *)v35 )
  {
    v35 = (HLOCAL *)((char *)v35 + 2);
    if ( !--v31 )
      goto LABEL_225;
  }
  v36 = v54;
  v30 = v54 - v31 + 2;
  v37 = 0;
  while ( v28 )
  {
    v38 = *v36;
    if ( !*v36 )
      break;
    ++v36;
    *v30++ = v38;
    --v28;
    if ( !--v31 )
    {
      --v30;
      v37 = -2147024774;
      break;
    }
  }
  *v30 = 0;
  if ( v37 >= 0 )
  {
    v46 = &hMem;
    v39 = -1;
    do
      ++v39;
    while ( *((_WORD *)&hMem + v39) );
    v47 = 2 * v39 + 2;
    v48 = 0;
    if ( ServiceConfiguration )
    {
      v49 = Buffer;
      v50 = 4;
      v40 = OPERATIONAL_ERROR_MESSAGE;
    }
    else
    {
      v5 = 1;
      v40 = OPERATIONAL_INFORMATION_MESSAGE;
    }
    if ( (unsigned int)EtwEventWrite(CGPServiceEventReporting::s_pEventProviderHandle, v40, v5, &v46) )
      GetLastError();
  }
LABEL_225:
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization CGPServiceConfiguration::Initialize().", v30);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization CGPServiceConfiguration::Initialize().", v30);
    }
  }
  CGPServiceState::Initialize();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization CGPServiceState::Initialize().");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization CGPServiceState::Initialize().");
    }
  }
  if ( !CGPExtensionExecutionState::m_Initialized )
    CGPExtensionExecutionState::m_Initialized = CGPExtensionExecutionState::Synchronize() == 0;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization CGPExtensionExecutionState::Initialize().");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization CGPExtensionExecutionState::Initialize().");
    }
  }
  if ( v2 >= 0 )
    CoUninitialize();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPService::DoAsyncInitialization completed.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPService::DoAsyncInitialization completed.");
    }
  }
  return PrimaryDomainInformation;
}

```

## disassembly

```asm
0x180036340  push    rbp
0x180036342  push    rbx
0x180036343  push    rsi
0x180036344  push    rdi
0x180036345  push    r12
0x180036347  push    r13
0x180036349  push    r14
0x18003634b  push    r15
0x18003634d  lea     rbp, [rsp-0F8h]
0x180036355  sub     rsp, 1F8h
0x18003635c  mov     rax, cs:__security_cookie
0x180036363  xor     rax, rsp
0x180036366  mov     [rbp+130h+var_50], rax
0x18003636d  mov     rsi, rcx
0x180036370  xor     edx, edx; Val
0x180036372  mov     r8d, 11Ch; Size
0x180036378  lea     rcx, [rsp+230h+VersionInformation]; void *
0x18003637d  call    memset_0
0x180036382  xor     edx, edx; dwCoInit
0x180036384  xor     ecx, ecx; pvReserved
0x180036386  call    cs:__imp_CoInitializeEx
0x18003638c  mov     r13d, eax
0x18003638f  xor     ecx, ecx
0x180036391  call    InitDebugSupport
0x180036396  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18003639d  jz      short loc_1800363E3
0x18003639f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800363a6  test    rax, rax
0x1800363a9  jz      short loc_1800363BE
0x1800363ab  lea     rdx, aCgpserviceDoas_8; "CGPService::DoAsyncInitialization start"...
0x1800363b2  mov     ecx, 4
0x1800363b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363bc  jmp     short loc_1800363E3
0x1800363be  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800363c6  jz      short loc_1800363E3
0x1800363c8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800363d0  jz      short loc_1800363E3
0x1800363d2  lea     rdx, aCgpserviceDoas_8; "CGPService::DoAsyncInitialization start"...
0x1800363d9  mov     ecx, 4; unsigned int
0x1800363de  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800363e3  call    ?OutputDeveloperLogHeader@CGPService@@CAXXZ; CGPService::OutputDeveloperLogHeader(void)
0x1800363e8  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800363ef  jz      short loc_180036435
0x1800363f1  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800363f8  test    rax, rax
0x1800363fb  jz      short loc_180036410
0x1800363fd  lea     rdx, aCgpserviceDoas_7; "CGPService::DoAsyncInitialization: CDef"...
0x180036404  mov     ecx, 4
0x180036409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003640e  jmp     short loc_180036435
0x180036410  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180036418  jz      short loc_180036435
0x18003641a  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180036422  jz      short loc_180036435
0x180036424  lea     rdx, aCgpserviceDoas_7; "CGPService::DoAsyncInitialization: CDef"...
0x18003642b  mov     ecx, 4; unsigned int
0x180036430  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180036435  call    ?InitializeClass@CDefaultPolicyApplier@@SAKXZ; CDefaultPolicyApplier::InitializeClass(void)
0x18003643a  mov     r15d, eax
0x18003643d  xor     r14d, r14d
0x180036440  mov     r12d, 2
0x180036446  test    eax, eax
0x180036448  jz      short loc_1800364AB
0x18003644a  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x180036451  jz      loc_1800369A5
0x180036457  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003645e  test    rax, rax
0x180036461  jz      short loc_18003647A
0x180036463  mov     r8d, r15d
0x180036466  lea     rdx, aCgpserviceDoas_17; "CGPService::DoAsyncInitialization: CDef"...
0x18003646d  mov     ecx, r12d
0x180036470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036475  jmp     loc_1800369A5
0x18003647a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x180036481  jz      loc_1800369A5
0x180036487  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003648e  jz      loc_1800369A5
0x180036494  mov     r8d, r15d
0x180036497  lea     rdx, aCgpserviceDoas_17; "CGPService::DoAsyncInitialization: CDef"...
0x18003649e  mov     ecx, r12d; unsigned int
0x1800364a1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800364a6  jmp     loc_1800369A5
0x1800364ab  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x1800364b2  jz      short loc_1800364F6
0x1800364b4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800364bb  test    rax, rax
0x1800364be  jz      short loc_1800364D3
0x1800364c0  lea     rdx, aCgpserviceDoas_13; "CGPService::DoAsyncInitialization: GetD"...
0x1800364c7  mov     ecx, 4
0x1800364cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364d1  jmp     short loc_1800364F6
0x1800364d3  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x1800364da  jz      short loc_1800364F6
0x1800364dc  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800364e3  jz      short loc_1800364F6
0x1800364e5  lea     rdx, aCgpserviceDoas_13; "CGPService::DoAsyncInitialization: GetD"...
0x1800364ec  mov     ecx, 4; unsigned int
0x1800364f1  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800364f6  mov     [rsp+230h+Buffer], r14
0x1800364fb  mov     ebx, r12d
0x1800364fe  lea     r8, [rsp+230h+Buffer]; Buffer
0x180036503  mov     edx, 1; InfoLevel
0x180036508  xor     ecx, ecx; lpServer
0x18003650a  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180036510  mov     r15d, eax
0x180036513  mov     rdx, [rsp+230h+Buffer]
0x180036518  test    eax, eax
0x18003651a  jnz     short loc_180036550
0x18003651c  mov     eax, [rdx]
0x18003651e  test    eax, 0FFFFFFFDh
0x180036523  jz      short loc_18003654A
0x180036525  add     eax, 0FFFFFFFCh
0x180036528  cmp     eax, 1
0x18003652b  jbe     short loc_18003654D
0x18003652d  test    dword ptr [rdx+4], 1000000h
0x180036534  jz      short loc_180036543
0x180036536  lea     rcx, [rdx+20h]; struct _GUID *
0x18003653a  call    ?IsNullGUID@@YAHAEBU_GUID@@@Z; IsNullGUID(_GUID const &)
0x18003653f  test    eax, eax
0x180036541  jz      short loc_180036550
0x180036543  mov     ebx, 1
0x180036548  jmp     short loc_180036550
0x18003654a  mov     ebx, r14d
0x18003654d  mov     r15d, r14d
0x180036550  test    rdx, rdx
0x180036553  jz      short loc_18003655E
0x180036555  mov     rcx, rdx; Buffer
0x180036558  call    cs:__imp_DsRoleFreeMemory
0x18003655e  test    r15d, r15d
0x180036561  jz      short loc_1800365C4
0x180036563  cmp     cs:?g_dwDebugLevel@@3KA, r14d; ulong g_dwDebugLevel
0x18003656a  jz      loc_1800369A5
0x180036570  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180036577  test    rax, rax
0x18003657a  jz      short loc_180036593
0x18003657c  mov     r8d, r15d
0x18003657f  lea     rdx, aGetdomainmembe; "GetDomainMembershipOfMachine failed wit"...
0x180036586  mov     ecx, r12d
0x180036589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003658e  jmp     loc_1800369A5
0x180036593  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r14; void * g_lpDebugMsgContextInstance
0x18003659a  jz      loc_1800369A5
0x1800365a0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r14; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800365a7  jz      loc_1800369A5
0x1800365ad  mov     r8d, r15d
0x1800365b0  lea     rdx, aGetdomainmembe; "GetDomainMembershipOfMachine failed wit"...
0x1800365b7  mov     ecx, r12d; unsigned int
0x1800365ba  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800365bf  jmp     loc_1800369A5
0x1800365c4  mov     edi, r14d
0x1800365c7  mov     r15d, r14d
0x1800365ca  cmp     ebx, r12d
0x1800365cd  setz    r14b
0x1800365d1  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800365d8  jz      short loc_18003661C
0x1800365da  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800365e1  test    rax, rax
0x1800365e4  jz      short loc_1800365F9
0x1800365e6  lea     rdx, aCgpserviceDoas_16; "CGPService::DoAsyncInitialization: GetV"...
0x1800365ed  mov     ecx, 4
0x1800365f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365f7  jmp     short loc_18003661C
0x1800365f9  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdi; void * g_lpDebugMsgContextInstance
0x180036600  jz      short loc_18003661C
0x180036602  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180036609  jz      short loc_18003661C
0x18003660b  lea     rdx, aCgpserviceDoas_16; "CGPService::DoAsyncInitialization: GetV"...
0x180036612  mov     ecx, 4; unsigned int
0x180036617  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003661c  mov     [rsp+230h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180036624  lea     rcx, [rsp+230h+VersionInformation]; lpVersionInformation
0x180036629  call    cs:__imp_GetVersionExW
0x18003662f  test    eax, eax
0x180036631  jz      loc_18003678D
0x180036637  cmp     [rbp+130h+var_C6], r12b
0x18003663b  jnz     short loc_180036689
0x18003663d  mov     edi, 1
0x180036642  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180036649  jz      loc_1800366D3
0x18003664f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180036656  test    rax, rax
0x180036659  jz      short loc_18003666E
0x18003665b  lea     rdx, aCgpserviceDoas_14; "CGPService::DoAsyncInitialization Domai"...
0x180036662  mov     ecx, 4
0x180036667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003666c  jmp     short loc_1800366D3
0x18003666e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180036675  jz      short loc_1800366D3
0x180036677  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003667e  jz      short loc_1800366D3
0x180036680  lea     rdx, aCgpserviceDoas_14; "CGPService::DoAsyncInitialization Domai"...
0x180036687  jmp     short loc_1800366C9
0x180036689  cmp     cs:?g_dwDebugLevel@@3KA, edi; ulong g_dwDebugLevel
0x18003668f  jz      short loc_1800366D3
0x180036691  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180036698  test    rax, rax
0x18003669b  jz      short loc_1800366B0
0x18003669d  lea     rdx, aCgpserviceDoas_11; "CGPService::DoAsyncInitialization Not a"...
0x1800366a4  mov     ecx, 4
0x1800366a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800366ae  jmp     short loc_1800366D3
0x1800366b0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rdi; void * g_lpDebugMsgContextInstance
0x1800366b7  jz      short loc_1800366D3
0x1800366b9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rdi; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800366c0  jz      short loc_1800366D3
0x1800366c2  lea     rdx, aCgpserviceDoas_11; "CGPService::DoAsyncInitialization Not a"...
0x1800366c9  mov     ecx, 4; unsigned int
0x1800366ce  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800366d3  test    byte ptr [rbp+130h+var_C8], 10h
0x1800366d7  jz      short loc_18003673E
0x1800366d9  mov     eax, 100h
0x1800366de  test    [rbp+130h+var_C8], ax
0x1800366e2  jnz     short loc_18003673E
0x1800366e4  movzx   eax, [rbp+130h+var_C6]
0x1800366e8  sub     al, r12b
0x1800366eb  cmp     al, 1
0x1800366ed  ja      short loc_18003673E
0x1800366ef  mov     r15d, 1
0x1800366f5  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800366fc  jz      loc_1800367DA
0x180036702  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180036709  test    rax, rax
0x18003670c  jz      short loc_180036721
0x18003670e  lea     rdx, aCgpserviceDoas_19; "CGPService::DoAsyncInitialization Termi"...
0x180036715  mov     ecx, 4
0x18003671a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003671f  jmp     short loc_18003678D
0x180036721  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180036729  jz      short loc_18003678D
0x18003672b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180036733  jz      short loc_18003678D
0x180036735  lea     rdx, aCgpserviceDoas_19; "CGPService::DoAsyncInitialization Termi"...
0x18003673c  jmp     short loc_180036783
0x18003673e  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180036745  jz      loc_1800367DA
0x18003674b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180036752  test    rax, rax
0x180036755  jz      short loc_18003676A
0x180036757  lea     rdx, aCgpserviceDoas_4; "CGPService::DoAsyncInitialization Not a"...
0x18003675e  mov     ecx, 4
0x180036763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036768  jmp     short loc_18003678D
0x18003676a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180036771  jz      short loc_18003678D
0x180036773  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18003677a  jz      short loc_18003678D
0x18003677c  lea     rdx, aCgpserviceDoas_4; "CGPService::DoAsyncInitialization Not a"...
0x180036783  mov     ecx, 4; unsigned int
0x180036788  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18003678d  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180036794  jz      short loc_1800367DA
0x180036796  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18003679d  test    rax, rax
0x1800367a0  jz      short loc_1800367B5
0x1800367a2  lea     rdx, aCgpserviceDoas_6; "CGPService::DoAsyncInitialization: CCon"...
0x1800367a9  mov     ecx, 4
0x1800367ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367b3  jmp     short loc_1800367DA
0x1800367b5  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800367bd  jz      short loc_1800367DA
0x1800367bf  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800367c7  jz      short loc_1800367DA
0x1800367c9  lea     rdx, aCgpserviceDoas_6; "CGPService::DoAsyncInitialization: CCon"...
0x1800367d0  mov     ecx, 4; unsigned int
0x1800367d5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800367da  test    edi, edi
0x1800367dc  jnz     short loc_1800367E7
0x1800367de  test    r15d, r15d
0x1800367e1  jnz     short loc_1800367E7
0x1800367e3  xor     ebx, ebx
0x1800367e5  jmp     short loc_1800367EC
0x1800367e7  mov     ebx, 1
0x1800367ec  cmp     cs:?s_pInstance@CConnectivityManager@@0PEAV1@EA, 0; CConnectivityManager * CConnectivityManager::s_pInstance
0x1800367f4  jz      short loc_180036801
0x1800367f6  mov     r15d, 4DFh
0x1800367fc  jmp     loc_1800368E1
0x180036801  mov     rdi, [rsi+60h]
0x180036805  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003680c  mov     ecx, 80h; unsigned __int64
0x180036811  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036816  mov     [rsp+230h+Buffer], rax
0x18003681b  test    rax, rax
0x18003681e  jz      loc_1800368D0
0x180036824  mov     rcx, rax; this
0x180036827  call    ??0CConnectivityManager@@AEAA@XZ; CConnectivityManager::CConnectivityManager(void)
0x18003682c  mov     cs:?s_pInstance@CConnectivityManager@@0PEAV1@EA, rax; CConnectivityManager * CConnectivityManager::s_pInstance
0x180036833  test    rax, rax
0x180036836  jz      loc_1800368DB
0x18003683c  mov     r9, rdi; struct IGPEventSubSystem *
0x18003683f  mov     r8d, ebx; int
0x180036842  mov     edx, r14d; int
0x180036845  call    ?Initialize@CConnectivityManager@@AEAAKHHPEAVIGPEventSubSystem@@@Z; CConnectivityManager::Initialize(int,int,IGPEventSubSystem *)
0x18003684a  mov     r15d, eax
0x18003684d  test    eax, eax
0x18003684f  jz      short loc_180036878
0x180036851  mov     rcx, cs:?s_pInstance@CConnectivityManager@@0PEAV1@EA; CConnectivityManager * CConnectivityManager::s_pInstance
0x180036858  test    rcx, rcx
0x18003685b  jz      short loc_18003686D
0x18003685d  mov     rax, [rcx]
0x180036860  mov     edx, 1
  ... truncated ...
```
