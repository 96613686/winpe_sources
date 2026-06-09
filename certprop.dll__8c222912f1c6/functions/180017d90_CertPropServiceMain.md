# CertPropServiceMain

- ea: `0x180017d90`
- end: `0x180017f28`
- name: `CertPropServiceMain`
- size: `408`
- prototype: `int()`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ec48`
- `0x1800154f4`
- `0x1800178a4`
- `0x180017b08`
- `0x180017cec`
- `0x180017d90`
- `0x180017f30`
- `0x180018f14`
- `0x180023aa8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e15`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180017e43`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180017e43`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180017e0e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180017e0e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e27`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180017db9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180017db9`

## pseudocode

```c
int CertPropServiceMain()
{
  SERVICE_STATUS_HANDLE v0; // rax
  int v1; // ebx
  struct _SERVICE_THREAD_SECURITY_INFO **v2; // rcx

  g_fShutdownInProgress = 0;
  _InterlockedExchange(&g_fBlockServiceHandler, 0);
  v0 = RegisterServiceCtrlHandlerExW(L"CertPropSvc", CertPropServiceHandlerEx, 0);
  g_hCertPropStatus = v0;
  if ( v0 )
  {
    v1 = 0;
    ServiceStatus.dwServiceType = 32;
    ServiceStatus.dwServiceSpecificExitCode = 0;
    LODWORD(v0) = CommonReportServiceStatus(&ServiceStatus, v0, 3000);
    if ( !(_DWORD)v0 )
    {
      InitializeCriticalSection(&g_csSessionList);
      g_hHeap = GetProcessHeap();
      if ( !g_hHeap || (SafeAllocaInitialize(), (g_hCertPropStopEvent = CreateEventA(0, 1, 0, 0)) == 0) )
      {
        LODWORD(v0) = GetLastError();
LABEL_14:
        if ( v1 == 1 )
          LODWORD(v0) = SetEvent(g_hCertPropStopEvent);
        else
          LODWORD(v0) = CertPropTeardownServer((unsigned int)v0);
        return (int)v0;
      }
      LODWORD(v0) = CertPropGetConfiguration();
      if ( (_DWORD)v0 )
        goto LABEL_14;
      if ( g_fEnableCertProp != 1 )
        goto LABEL_14;
      LODWORD(v0) = CertPropInitializeThreadPool();
      if ( (_DWORD)v0 )
        goto LABEL_14;
      ScPnPInitialize();
      LODWORD(v0) = CommonRegisterStopCallback(
                      &g_hCertPropRegisteredWait,
                      L"CertPropSvc",
                      g_hCertPropStopEvent,
                      CertPropTerminationNotify);
      if ( (_DWORD)v0 )
        goto LABEL_14;
      v1 = 1;
      LODWORD(v0) = CommonReportServiceStatus(&ServiceStatus, g_hCertPropStatus, 0);
      if ( (_DWORD)v0 )
        goto LABEL_14;
      LODWORD(v0) = CertPropAddSessionsOnStartup();
      if ( (_DWORD)v0 )
        goto LABEL_14;
      if ( g_fEnableRootCertProp == 1 )
      {
        LODWORD(v0) = RootRpcInitialize(v2);
        if ( (_DWORD)v0 )
          goto LABEL_14;
      }
    }
  }
  return (int)v0;
}

```

## disassembly

```asm
0x180017d90  push    rbx
0x180017d92  sub     rsp, 30h
0x180017d96  mov     cs:g_fShutdownInProgress, 0
0x180017da0  xor     eax, eax
0x180017da2  xchg    eax, cs:g_fBlockServiceHandler
0x180017da8  xor     r8d, r8d; lpContext
0x180017dab  lea     rdx, CertPropServiceHandlerEx; lpHandlerProc
0x180017db2  lea     rcx, ServiceName; "CertPropSvc"
0x180017db9  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180017dbf  mov     cs:g_hCertPropStatus, rax
0x180017dc6  test    rax, rax
0x180017dc9  jz      loc_180017F22
0x180017dcf  xor     ebx, ebx
0x180017dd1  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180017ddb  mov     cs:ServiceStatus.dwServiceSpecificExitCode, ebx
0x180017de1  mov     [rsp+38h+var_18], 0BB8h; int
0x180017de9  xor     r9d, r9d
0x180017dec  lea     r8d, [rbx+2]
0x180017df0  mov     rdx, rax; hServiceStatus
0x180017df3  lea     rcx, ServiceStatus; lpServiceStatus
0x180017dfa  call    CommonReportServiceStatus
0x180017dff  test    eax, eax
0x180017e01  jnz     loc_180017F22
0x180017e07  lea     rcx, g_csSessionList; lpCriticalSection
0x180017e0e  call    cs:__imp_InitializeCriticalSection
0x180017e14  nop
0x180017e15  call    cs:__imp_GetProcessHeap
0x180017e1b  mov     cs:g_hHeap, rax
0x180017e22  test    rax, rax
0x180017e25  jnz     short loc_180017E32
0x180017e27  call    cs:__imp_GetLastError
0x180017e2d  jmp     loc_180017ED9
0x180017e32  call    SafeAllocaInitialize
0x180017e37  xor     r9d, r9d; lpName
0x180017e3a  xor     r8d, r8d; bInitialState
0x180017e3d  lea     edx, [r9+1]; bManualReset
0x180017e41  xor     ecx, ecx; lpEventAttributes
0x180017e43  call    cs:__imp_CreateEventA
0x180017e49  mov     cs:g_hCertPropStopEvent, rax
0x180017e50  test    rax, rax
0x180017e53  jz      short loc_180017E27
0x180017e55  call    CertPropGetConfiguration
0x180017e5a  test    eax, eax
0x180017e5c  jnz     short loc_180017ED9
0x180017e5e  cmp     cs:g_fEnableCertProp, 1
0x180017e65  jnz     short loc_180017ED9
0x180017e67  call    CertPropInitializeThreadPool
0x180017e6c  test    eax, eax
0x180017e6e  jnz     short loc_180017ED9
0x180017e70  call    ScPnPInitialize
0x180017e75  lea     r9, CertPropTerminationNotify
0x180017e7c  mov     r8, cs:g_hCertPropStopEvent
0x180017e83  lea     rdx, ServiceName; "CertPropSvc"
0x180017e8a  lea     rcx, g_hCertPropRegisteredWait
0x180017e91  call    CommonRegisterStopCallback
0x180017e96  test    eax, eax
0x180017e98  jnz     short loc_180017ED9
0x180017e9a  lea     ebx, [rax+1]
0x180017e9d  mov     [rsp+38h+var_18], eax; int
0x180017ea1  xor     r9d, r9d
0x180017ea4  lea     r8d, [rax+4]
0x180017ea8  mov     rdx, cs:g_hCertPropStatus; hServiceStatus
0x180017eaf  lea     rcx, ServiceStatus; lpServiceStatus
0x180017eb6  call    CommonReportServiceStatus
0x180017ebb  test    eax, eax
0x180017ebd  jnz     short loc_180017ED9
0x180017ebf  call    CertPropAddSessionsOnStartup
0x180017ec4  test    eax, eax
0x180017ec6  jnz     short loc_180017ED9
0x180017ec8  cmp     cs:g_fEnableRootCertProp, ebx
0x180017ece  jnz     short loc_180017F22
0x180017ed0  call    RootRpcInitialize
0x180017ed5  test    eax, eax
0x180017ed7  jz      short loc_180017F22
0x180017ed9  cmp     ebx, 1
0x180017edc  jnz     short loc_180017EF1
0x180017ede  mov     rcx, cs:g_hCertPropStopEvent
0x180017ee5  add     rsp, 30h
0x180017ee9  pop     rbx
0x180017eea  jmp     cs:__imp_SetEvent
0x180017ef1  mov     ecx, eax
0x180017ef3  add     rsp, 30h
0x180017ef7  pop     rbx
0x180017ef8  jmp     CertPropTeardownServer
0x180017efd  mov     r9d, eax
0x180017f00  mov     [rsp+38h+var_18], 0; int
0x180017f08  mov     r8d, 1
0x180017f0e  mov     rdx, cs:g_hCertPropStatus; hServiceStatus
0x180017f15  lea     rcx, ServiceStatus; lpServiceStatus
0x180017f1c  call    CommonReportServiceStatus
0x180017f21  nop
0x180017f22  add     rsp, 30h
0x180017f26  pop     rbx
0x180017f27  retn
```
