# InitializeDriverIoControl

- ea: `0x18000c5e0`
- end: `0x18000c7e3`
- name: `InitializeDriverIoControl`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800022a0`
- `0x18000c5e0`
- `0x18000d92c`
- `0x180021b94`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c73c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c73c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c763`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000c6b2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000c6b2`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18000c698`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x18000c698`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18000c65f`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x18000c65f`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c6ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c6ea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c72a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c72a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c79a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c7b3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c79a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18000c7b3`
- `rtutils!TraceRegisterExA` at `0x18000c618`
- `rtutils!TraceRegisterExA` at `0x18000c618`

## string_xrefs

- `0x18000c675`: `InitializeDriverIoControl: OpenSCManager failed (0x%x)`
- `0x18000c751`: `InitializeDriverIoControl: QueryServiceStatus for TapiSrv failed (0x%x)`
- `0x18000c702`: `InitializeDriverIoControl: CreateEvent failed (0x%x)`
- `0x18000c742`: `InitializeDriverIoControl: CreateThread (TapiSrv monitor thread) failed (0x%x)`
- `0x18000c772`: `InitializeDriverIoControl: TapiSrv service does not exist`
- `0x18000c7a4`: `InitializeDriverIoControl: OpenService for TapiSrv failed (0x%x)`

## pseudocode

```c
__int64 __fastcall InitializeDriverIoControl(int a1, unsigned int a2)
{
  DWORD v4; // eax
  unsigned int LastError; // ebx
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rsi
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  DWORD v10; // eax
  const CHAR *v11; // rcx
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v4 = TraceRegisterExA("RASTAPI", 0);
  g_RasMobileCore = a1;
  dwTraceId = v4;
  LastError = InitializeNdproxyIoControl((__int64)RasTapiCallback, 1, a2);
  if ( LastError )
  {
    RasTapiTrace("InitializeDriverIoControl: NDPROXY init failed (0x%x)");
LABEL_22:
    CleanupDriverIoControl();
    return LastError;
  }
  v6 = OpenSCManagerA(0, 0, 1u);
  v7 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    RasTapiTrace("InitializeDriverIoControl: OpenSCManager failed (0x%x)");
    goto LABEL_21;
  }
  v8 = OpenServiceA(v6, "TapiSrv", 4u);
  v9 = v8;
  if ( v8 )
  {
    if ( !QueryServiceStatus(v8, &ServiceStatus) )
    {
      v10 = GetLastError();
      v11 = "InitializeDriverIoControl: QueryServiceStatus for TapiSrv failed (0x%x)";
      goto LABEL_14;
    }
    if ( ServiceStatus.dwCurrentState == 4 )
    {
      g_fTapiSrvRunning = 1;
      goto LABEL_17;
    }
    g_fTapiSrvRunning = 0;
    g_hTapiSrvMonitorTerminate = CreateEventA(0, 0, 0, 0);
    if ( !g_hTapiSrvMonitorTerminate )
    {
      v10 = GetLastError();
      v11 = "InitializeDriverIoControl: CreateEvent failed (0x%x)";
LABEL_14:
      LastError = v10;
      RasTapiTrace(v11);
LABEL_18:
      CloseServiceHandle(v9);
      goto LABEL_20;
    }
    g_hTapiSrvMonitorThread = CreateThread(0, 0, TapiServiceMonitorThread, 0, 0, 0);
    if ( !g_hTapiSrvMonitorThread )
    {
      v10 = GetLastError();
      v11 = "InitializeDriverIoControl: CreateThread (TapiSrv monitor thread) failed (0x%x)";
      goto LABEL_14;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1060 )
    {
      RasTapiTrace("InitializeDriverIoControl: OpenService for TapiSrv failed (0x%x)");
      goto LABEL_20;
    }
    RasTapiTrace("InitializeDriverIoControl: TapiSrv service does not exist");
    LastError = 0;
  }
LABEL_17:
  RasTapiTrace("InitializeDriverIoControl: TapiSrv running = %d");
  if ( v9 )
    goto LABEL_18;
LABEL_20:
  CloseServiceHandle(v7);
LABEL_21:
  if ( LastError )
    goto LABEL_22;
  return LastError;
}

```

## disassembly

```asm
0x18000c5e0  mov     [rsp+arg_0], rbx
0x18000c5e5  mov     [rsp+arg_10], rsi
0x18000c5ea  push    rdi
0x18000c5eb  sub     rsp, 60h
0x18000c5ef  mov     rax, cs:__security_cookie
0x18000c5f6  xor     rax, rsp
0x18000c5f9  mov     [rsp+68h+var_18], rax
0x18000c5fe  xorps   xmm0, xmm0
0x18000c601  mov     edi, edx
0x18000c603  mov     ebx, ecx
0x18000c605  xor     edx, edx; dwFlags
0x18000c607  movups  xmmword ptr [rsp+68h+ServiceStatus.dwServiceType], xmm0
0x18000c60c  lea     rcx, szCallerName; "RASTAPI"
0x18000c613  movups  xmmword ptr [rsp+68h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000c618  call    cs:__imp_TraceRegisterExA
0x18000c61e  mov     r8d, edi
0x18000c621  mov     cs:g_RasMobileCore, ebx
0x18000c627  mov     edx, 1
0x18000c62c  mov     cs:dwTraceId, eax
0x18000c632  lea     rcx, RasTapiCallback
0x18000c639  call    InitializeNdproxyIoControl
0x18000c63e  mov     ebx, eax
0x18000c640  test    eax, eax
0x18000c642  jz      short loc_18000C657
0x18000c644  mov     edx, eax
0x18000c646  lea     rcx, aInitializedriv_7; "InitializeDriverIoControl: NDPROXY init"...
0x18000c64d  call    RasTapiTrace
0x18000c652  jmp     loc_18000C7BD
0x18000c657  xor     edx, edx; lpDatabaseName
0x18000c659  xor     ecx, ecx; lpMachineName
0x18000c65b  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000c65f  call    cs:__imp_OpenSCManagerA
0x18000c665  mov     rsi, rax
0x18000c668  test    rax, rax
0x18000c66b  jnz     short loc_18000C688
0x18000c66d  call    cs:__imp_GetLastError
0x18000c673  mov     edx, eax
0x18000c675  lea     rcx, aInitializedriv_2; "InitializeDriverIoControl: OpenSCManage"...
0x18000c67c  mov     ebx, eax
0x18000c67e  call    RasTapiTrace
0x18000c683  jmp     loc_18000C7B9
0x18000c688  mov     r8d, 4; dwDesiredAccess
0x18000c68e  lea     rdx, ServiceName; "TapiSrv"
0x18000c695  mov     rcx, rsi; hSCManager
0x18000c698  call    cs:__imp_OpenServiceA
0x18000c69e  mov     rdi, rax
0x18000c6a1  test    rax, rax
0x18000c6a4  jz      loc_18000C763
0x18000c6aa  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x18000c6af  mov     rcx, rax; hService
0x18000c6b2  call    cs:__imp_QueryServiceStatus
0x18000c6b8  test    eax, eax
0x18000c6ba  jz      loc_18000C74B
0x18000c6c0  cmp     [rsp+68h+ServiceStatus.dwCurrentState], 4
0x18000c6c5  jnz     short loc_18000C6D6
0x18000c6c7  mov     cs:g_fTapiSrvRunning, 1
0x18000c6d1  jmp     loc_18000C780
0x18000c6d6  xor     r9d, r9d; lpName
0x18000c6d9  mov     cs:g_fTapiSrvRunning, 0
0x18000c6e3  xor     r8d, r8d; bInitialState
0x18000c6e6  xor     edx, edx; bManualReset
0x18000c6e8  xor     ecx, ecx; lpEventAttributes
0x18000c6ea  call    cs:__imp_CreateEventA
0x18000c6f0  mov     cs:g_hTapiSrvMonitorTerminate, rax
0x18000c6f7  test    rax, rax
0x18000c6fa  jnz     short loc_18000C70B
0x18000c6fc  call    cs:__imp_GetLastError
0x18000c702  lea     rcx, aInitializedriv_4; "InitializeDriverIoControl: CreateEvent "...
0x18000c709  jmp     short loc_18000C758
0x18000c70b  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18000c714  lea     r8, TapiServiceMonitorThread; lpStartAddress
0x18000c71b  xor     r9d, r9d; lpParameter
0x18000c71e  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18000c726  xor     edx, edx; dwStackSize
0x18000c728  xor     ecx, ecx; lpThreadAttributes
0x18000c72a  call    cs:__imp_CreateThread
0x18000c730  mov     cs:g_hTapiSrvMonitorThread, rax
0x18000c737  test    rax, rax
0x18000c73a  jnz     short loc_18000C780
0x18000c73c  call    cs:__imp_GetLastError
0x18000c742  lea     rcx, aInitializedriv_1; "InitializeDriverIoControl: CreateThread"...
0x18000c749  jmp     short loc_18000C758
0x18000c74b  call    cs:__imp_GetLastError
0x18000c751  lea     rcx, aInitializedriv_5; "InitializeDriverIoControl: QueryService"...
0x18000c758  mov     edx, eax
0x18000c75a  mov     ebx, eax
0x18000c75c  call    RasTapiTrace
0x18000c761  jmp     short loc_18000C797
0x18000c763  call    cs:__imp_GetLastError
0x18000c769  mov     ebx, eax
0x18000c76b  cmp     eax, 424h
0x18000c770  jnz     short loc_18000C7A2
0x18000c772  lea     rcx, aInitializedriv_6; "InitializeDriverIoControl: TapiSrv serv"...
0x18000c779  call    RasTapiTrace
0x18000c77e  xor     ebx, ebx
0x18000c780  mov     edx, cs:g_fTapiSrvRunning
0x18000c786  lea     rcx, aInitializedriv_0; "InitializeDriverIoControl: TapiSrv runn"...
0x18000c78d  call    RasTapiTrace
0x18000c792  test    rdi, rdi
0x18000c795  jz      short loc_18000C7B0
0x18000c797  mov     rcx, rdi; hSCObject
0x18000c79a  call    cs:__imp_CloseServiceHandle
0x18000c7a0  jmp     short loc_18000C7B0
0x18000c7a2  mov     edx, eax
0x18000c7a4  lea     rcx, aInitializedriv_3; "InitializeDriverIoControl: OpenService "...
0x18000c7ab  call    RasTapiTrace
0x18000c7b0  mov     rcx, rsi; hSCObject
0x18000c7b3  call    cs:__imp_CloseServiceHandle
0x18000c7b9  test    ebx, ebx
0x18000c7bb  jz      short loc_18000C7C2
0x18000c7bd  call    CleanupDriverIoControl
0x18000c7c2  mov     eax, ebx
0x18000c7c4  mov     rcx, [rsp+68h+var_18]
0x18000c7c9  xor     rcx, rsp; StackCookie
0x18000c7cc  call    __security_check_cookie
0x18000c7d1  lea     r11, [rsp+68h+var_8]
0x18000c7d6  mov     rbx, [r11+10h]
0x18000c7da  mov     rsi, [r11+20h]
0x18000c7de  mov     rsp, r11
0x18000c7e1  pop     rdi
0x18000c7e2  retn
```
