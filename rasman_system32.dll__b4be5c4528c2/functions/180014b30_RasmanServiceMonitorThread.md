# RasmanServiceMonitorThread

- ea: `0x180014b30`
- end: `0x180014dff`
- name: `RasmanServiceMonitorThread`
- size: `719`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180014b30`
- `0x180023488`
- `0x18002739e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014c79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180014c79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014bef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014bef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014c0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180014d48`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180014d48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014de2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014de2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014dc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d80`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180014b9b`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180014b9b`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x180014c53`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x180014c53`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180014b69`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180014b69`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014cd7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014cf6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014cd7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180014cf6`
- `rtutils!TracePrintfExA` at `0x180014d61`
- `rtutils!TracePrintfExA` at `0x180014daf`
- `rtutils!TracePrintfExA` at `0x180014d61`
- `rtutils!TracePrintfExA` at `0x180014daf`

## string_xrefs

- `0x180014d55`: `RasmanServiceMonitor thread Entered ...`
- `0x180014da0`: `RasmanServiceMonitorThread: NotifyServiceStatusChange failed, Error=%d`
- `0x180014c9f`: `RasmanServiceMonitor: WaitForSingleObjectEx failed, Error= %d`

## pseudocode

```c
void __fastcall __noreturn RasmanServiceMonitorThread(PVOID Parameter)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  SC_HANDLE v3; // rdi
  DWORD v4; // ebx
  DWORD v5; // eax
  DWORD v6; // eax
  HLOCAL *i; // rcx
  SERVICE_NOTIFY_2A pNotifyBuffer; // [rsp+20h] [rbp-68h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasmanServiceMonitor thread Entered ...");
  v1 = OpenSCManagerA(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v3 = OpenServiceA(v1, "RASMAN", 4u);
    if ( v3 )
    {
      v4 = 0;
      while ( 1 )
      {
        *(&pNotifyBuffer.dwVersion + 1) = 0;
        memset_0(&pNotifyBuffer, 0, 0x4Cu);
        EnterCriticalSection(&g_RasCriticalSection);
        if ( !g_fRCNInitialized && g_fRasmanStarted )
        {
          if ( g_pRCNList )
            RasmanAddNotificationForAll();
          g_fRCNInitialized = 1;
        }
        LeaveCriticalSection(&g_RasCriticalSection);
        *(_QWORD *)&pNotifyBuffer.dwVersion = 2;
        memset(&pNotifyBuffer.pContext, 0, 64);
        v4 |= 0xDu;
        pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)RasmanServiceNotify;
        v5 = NotifyServiceStatusChangeA(v3, v4, &pNotifyBuffer);
        if ( v5 )
          break;
        v6 = WaitForSingleObjectEx(g_hEventServiceMonitorTerminate, 0xFFFFFFFF, 1);
        if ( !v6 )
          goto LABEL_16;
        if ( v6 != 192 )
        {
          if ( g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "RasmanServiceMonitor: WaitForSingleObjectEx failed, Error= %d", v6);
          goto LABEL_16;
        }
      }
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasmanServiceMonitorThread: NotifyServiceStatusChange failed, Error=%d", v5);
LABEL_16:
      CloseServiceHandle(v3);
    }
    else
    {
      GetLastError();
    }
    CloseServiceHandle(v2);
  }
  else
  {
    GetLastError();
  }
  if ( g_hEventServiceMonitorTerminate )
  {
    CloseHandle(g_hEventServiceMonitorTerminate);
    g_hEventServiceMonitorTerminate = 0;
  }
  for ( i = (HLOCAL *)g_pRCNList; g_pRCNList; i = (HLOCAL *)g_pRCNList )
  {
    g_pRCNList = *i;
    LocalFree(i);
  }
  g_pRCNList = 0;
  g_fRCNInitialized = 0;
  FreeLibraryAndExitThread(g_hModule, 0);
}

```

## disassembly

```asm
0x180014b30  push    rbp
0x180014b32  sub     rsp, 80h
0x180014b39  mov     rax, cs:__security_cookie
0x180014b40  xor     rax, rsp
0x180014b43  mov     [rsp+88h+var_18], rax
0x180014b48  mov     ecx, cs:g_dwTraceId
0x180014b4e  mov     [rsp+88h+arg_8], rsi
0x180014b56  cmp     ecx, 0FFFFFFFFh
0x180014b59  jnz     loc_180014D55
0x180014b5f  xor     edx, edx; lpDatabaseName
0x180014b61  xor     ecx, ecx; lpMachineName
0x180014b63  mov     r8d, 1; dwDesiredAccess
0x180014b69  call    cs:__imp_OpenSCManagerA
0x180014b70  nop     dword ptr [rax+rax+00h]
0x180014b75  xor     ebp, ebp
0x180014b77  mov     rsi, rax
0x180014b7a  test    rax, rax
0x180014b7d  jz      loc_180014D72
0x180014b83  mov     r8d, 4; dwDesiredAccess
0x180014b89  mov     [rsp+88h+arg_10], rdi
0x180014b91  lea     rdx, aRasman; "RASMAN"
0x180014b98  mov     rcx, rax; hSCManager
0x180014b9b  call    cs:__imp_OpenServiceA
0x180014ba2  nop     dword ptr [rax+rax+00h]
0x180014ba7  mov     rdi, rax
0x180014baa  test    rax, rax
0x180014bad  jz      loc_180014D80
0x180014bb3  mov     [rsp+88h+arg_0], rbx
0x180014bbb  mov     ebx, ebp
0x180014bbd  mov     [rsp+88h+arg_18], r14
0x180014bc5  lea     r14, RasmanServiceNotify
0x180014bcc  nop     dword ptr [rax+00h]
0x180014bd0  xor     eax, eax
0x180014bd2  lea     rcx, [rsp+88h+pNotifyBuffer]; void *
0x180014bd7  xor     edx, edx; Val
0x180014bd9  mov     dword ptr [rsp+88h+pNotifyBuffer+4], eax
0x180014bdd  mov     r8d, 4Ch ; 'L'; Size
0x180014be3  call    memset_0
0x180014be8  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180014bef  call    cs:__imp_EnterCriticalSection
0x180014bf6  nop     dword ptr [rax+rax+00h]
0x180014bfb  cmp     cs:g_fRCNInitialized, ebp
0x180014c01  jz      loc_180014CAB
0x180014c07  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180014c0e  call    cs:__imp_LeaveCriticalSection
0x180014c15  nop     dword ptr [rax+rax+00h]
0x180014c1a  xorps   xmm0, xmm0
0x180014c1d  mov     qword ptr [rsp+88h+pNotifyBuffer.dwVersion], 2
0x180014c26  xorps   xmm1, xmm1
0x180014c29  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.pContext], xmm0
0x180014c2f  or      ebx, 0Dh
0x180014c32  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.ServiceStatus.dwCurrentState], xmm1
0x180014c38  mov     edx, ebx; dwNotifyMask
0x180014c3a  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.ServiceStatus.dwCheckPoint], xmm0
0x180014c40  lea     r8, [rsp+88h+pNotifyBuffer]; pNotifyBuffer
0x180014c45  movdqa  xmmword ptr [rsp+88h+pNotifyBuffer.dwNotificationTriggered], xmm1
0x180014c4b  mov     rcx, rdi; hService
0x180014c4e  mov     [rsp+88h+pNotifyBuffer.pfnNotifyCallback], r14
0x180014c53  call    cs:__imp_NotifyServiceStatusChangeA
0x180014c5a  nop     dword ptr [rax+rax+00h]
0x180014c5f  test    eax, eax
0x180014c61  jnz     loc_180014D91
0x180014c67  mov     rcx, cs:g_hEventServiceMonitorTerminate; hHandle
0x180014c6e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180014c73  mov     r8d, 1; bAlertable
0x180014c79  call    cs:__imp_WaitForSingleObjectEx
0x180014c80  nop     dword ptr [rax+rax+00h]
0x180014c85  test    eax, eax
0x180014c87  jz      short loc_180014CD4
0x180014c89  cmp     eax, 0C0h
0x180014c8e  jz      loc_180014BD0
0x180014c94  mov     ecx, cs:g_dwTraceId
0x180014c9a  cmp     ecx, 0FFFFFFFFh
0x180014c9d  jz      short loc_180014CD4
0x180014c9f  lea     r8, aRasmanservicem; "RasmanServiceMonitor: WaitForSingleObje"...
0x180014ca6  jmp     loc_180014DA7
0x180014cab  cmp     cs:g_fRasmanStarted, ebp
0x180014cb1  jz      loc_180014C07
0x180014cb7  cmp     cs:g_pRCNList, rbp
0x180014cbe  jz      short loc_180014CC5
0x180014cc0  call    RasmanAddNotificationForAll
0x180014cc5  mov     cs:g_fRCNInitialized, 1
0x180014ccf  jmp     loc_180014C07
0x180014cd4  mov     rcx, rdi; hSCObject
0x180014cd7  call    cs:__imp_CloseServiceHandle
0x180014cde  nop     dword ptr [rax+rax+00h]
0x180014ce3  mov     r14, [rsp+88h+arg_18]
0x180014ceb  mov     rbx, [rsp+88h+arg_0]
0x180014cf3  mov     rcx, rsi; hSCObject
0x180014cf6  call    cs:__imp_CloseServiceHandle
0x180014cfd  nop     dword ptr [rax+rax+00h]
0x180014d02  mov     rdi, [rsp+88h+arg_10]
0x180014d0a  mov     rcx, cs:g_hEventServiceMonitorTerminate; hObject
0x180014d11  mov     rsi, [rsp+88h+arg_8]
0x180014d19  test    rcx, rcx
0x180014d1c  jnz     loc_180014DC0
0x180014d22  mov     rcx, cs:g_pRCNList; hMem
0x180014d29  test    rcx, rcx
0x180014d2c  jnz     loc_180014DD8
0x180014d32  mov     rcx, cs:g_hModule; hLibModule
0x180014d39  xor     edx, edx; dwExitCode
0x180014d3b  mov     cs:g_pRCNList, rbp
0x180014d42  mov     cs:g_fRCNInitialized, ebp
0x180014d48  call    cs:__imp_FreeLibraryAndExitThread
0x180014d4f  nop     dword ptr [rax+rax+00h]
0x180014d54  int     3; Trap to Debugger
0x180014d55  lea     r8, aRasmanservicem_0; "RasmanServiceMonitor thread Entered ..."
0x180014d5c  mov     edx, 0Ch; dwFlags
0x180014d61  call    cs:__imp_TracePrintfExA
0x180014d68  nop     dword ptr [rax+rax+00h]
0x180014d6d  jmp     loc_180014B5F
0x180014d72  call    cs:__imp_GetLastError
0x180014d79  nop     dword ptr [rax+rax+00h]
0x180014d7e  jmp     short loc_180014D0A
0x180014d80  call    cs:__imp_GetLastError
0x180014d87  nop     dword ptr [rax+rax+00h]
0x180014d8c  jmp     loc_180014CF3
0x180014d91  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014d97  cmp     ecx, 0FFFFFFFFh
0x180014d9a  jz      loc_180014CD4
0x180014da0  lea     r8, aRasmanservicem_1; "RasmanServiceMonitorThread: NotifyServi"...
0x180014da7  mov     r9d, eax
0x180014daa  mov     edx, 0Ch; dwFlags
0x180014daf  call    cs:__imp_TracePrintfExA
0x180014db6  nop     dword ptr [rax+rax+00h]
0x180014dbb  jmp     loc_180014CD4
0x180014dc0  call    cs:__imp_CloseHandle
0x180014dc7  nop     dword ptr [rax+rax+00h]
0x180014dcc  mov     cs:g_hEventServiceMonitorTerminate, rbp
0x180014dd3  jmp     loc_180014D22
0x180014dd8  mov     rax, [rcx]
0x180014ddb  mov     cs:g_pRCNList, rax
0x180014de2  call    cs:__imp_LocalFree
0x180014de9  nop     dword ptr [rax+rax+00h]
0x180014dee  mov     rcx, cs:g_pRCNList
0x180014df5  test    rcx, rcx
0x180014df8  jnz     short loc_180014DD8
0x180014dfa  jmp     loc_180014D32
```
