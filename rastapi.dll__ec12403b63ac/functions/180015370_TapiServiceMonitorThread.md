# TapiServiceMonitorThread

- ea: `0x180015370`
- end: `0x1800154dc`
- name: `TapiServiceMonitorThread`
- size: `364`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000d92c`
- `0x180015370`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015487`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x180015438`
- `api-ms-win-service-winsvc-l1-1-0!NotifyServiceStatusChangeA` at `0x180015438`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800153ee`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x1800153ee`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800153b5`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x1800153b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001545f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001545f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800154a9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800154b2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800154a9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800154b2`

## string_xrefs

- `0x1800153a1`: `TapiServiceMonitorThread: Thread started`
- `0x1800153cb`: `TapiServiceMonitorThread: OpenSCManager failed (0x%x)`
- `0x180015404`: `TapiServiceMonitorThread: OpenService failed (0x%x)`
- `0x180015446`: `TapiServiceMonitorThread: NotifyServiceStatusChange failed (0x%x)`
- `0x18001546b`: `TapiServiceMonitorThread: Tapi Service monitor terminate signaled`
- `0x180015491`: `TapiServiceMonitorThread: WaitForSingleObjectEx failed (0x%x)`
- `0x18001549a`: `TapiServiceMonitorThread: Exiting with return code (0x%x)`

## pseudocode

```c
__int64 __fastcall TapiServiceMonitorThread(PVOID Parameter)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v4; // rdi
  const CHAR *v5; // rcx
  DWORD v6; // eax
  SERVICE_NOTIFY_2A pNotifyBuffer; // [rsp+20h] [rbp-68h] BYREF

  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  RasTapiTrace("TapiServiceMonitorThread: Thread started");
  v1 = OpenSCManagerA(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v4 = OpenServiceA(v1, "TapiSrv", 4u);
    if ( !v4 )
    {
      LastError = GetLastError();
      RasTapiTrace("TapiServiceMonitorThread: OpenService failed (0x%x)");
LABEL_16:
      CloseServiceHandle(v2);
      return LastError;
    }
    pNotifyBuffer.dwVersion = 2;
    pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)TapiServiceNotify;
    LastError = NotifyServiceStatusChangeA(v4, 8u, &pNotifyBuffer);
    if ( LastError )
    {
      v5 = "TapiServiceMonitorThread: NotifyServiceStatusChange failed (0x%x)";
    }
    else
    {
      v6 = WaitForSingleObjectEx(g_hTapiSrvMonitorTerminate, 0xFFFFFFFF, 1);
      LastError = v6;
      if ( !v6 )
      {
        RasTapiTrace("TapiServiceMonitorThread: Tapi Service monitor terminate signaled");
LABEL_15:
        CloseServiceHandle(v4);
        goto LABEL_16;
      }
      if ( v6 == 192 )
      {
        v5 = "TapiServiceMonitorThread: Exiting with return code (0x%x)";
      }
      else
      {
        if ( v6 == -1 )
          LastError = GetLastError();
        v5 = "TapiServiceMonitorThread: WaitForSingleObjectEx failed (0x%x)";
      }
    }
    RasTapiTrace(v5);
    goto LABEL_15;
  }
  LastError = GetLastError();
  RasTapiTrace("TapiServiceMonitorThread: OpenSCManager failed (0x%x)");
  return LastError;
}

```

## disassembly

```asm
0x180015370  mov     [rsp+arg_0], rbx
0x180015375  mov     [rsp+arg_8], rsi
0x18001537a  push    rdi
0x18001537b  sub     rsp, 80h
0x180015382  mov     rax, cs:__security_cookie
0x180015389  xor     rax, rsp
0x18001538c  mov     [rsp+88h+var_18], rax
0x180015391  xor     edx, edx; Val
0x180015393  lea     rcx, [rsp+88h+pNotifyBuffer]; void *
0x180015398  lea     r8d, [rdx+50h]; Size
0x18001539c  call    memset_0
0x1800153a1  lea     rcx, aTapiservicemon_3; "TapiServiceMonitorThread: Thread starte"...
0x1800153a8  call    RasTapiTrace
0x1800153ad  xor     edx, edx; lpDatabaseName
0x1800153af  xor     ecx, ecx; lpMachineName
0x1800153b1  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800153b5  call    cs:__imp_OpenSCManagerA
0x1800153bb  mov     rsi, rax
0x1800153be  test    rax, rax
0x1800153c1  jnz     short loc_1800153DE
0x1800153c3  call    cs:__imp_GetLastError
0x1800153c9  mov     edx, eax
0x1800153cb  lea     rcx, aTapiservicemon_1; "TapiServiceMonitorThread: OpenSCManager"...
0x1800153d2  mov     ebx, eax
0x1800153d4  call    RasTapiTrace
0x1800153d9  jmp     loc_1800154B8
0x1800153de  mov     r8d, 4; dwDesiredAccess
0x1800153e4  lea     rdx, ServiceName; "TapiSrv"
0x1800153eb  mov     rcx, rsi; hSCManager
0x1800153ee  call    cs:__imp_OpenServiceA
0x1800153f4  mov     rdi, rax
0x1800153f7  test    rax, rax
0x1800153fa  jnz     short loc_180015417
0x1800153fc  call    cs:__imp_GetLastError
0x180015402  mov     edx, eax
0x180015404  lea     rcx, aTapiservicemon_5; "TapiServiceMonitorThread: OpenService f"...
0x18001540b  mov     ebx, eax
0x18001540d  call    RasTapiTrace
0x180015412  jmp     loc_1800154AF
0x180015417  lea     rax, TapiServiceNotify
0x18001541e  mov     [rsp+88h+pNotifyBuffer.dwVersion], 2
0x180015426  lea     r8, [rsp+88h+pNotifyBuffer]; pNotifyBuffer
0x18001542b  mov     [rsp+88h+pNotifyBuffer.pfnNotifyCallback], rax
0x180015430  mov     edx, 8; dwNotifyMask
0x180015435  mov     rcx, rdi; hService
0x180015438  call    cs:__imp_NotifyServiceStatusChangeA
0x18001543e  mov     ebx, eax
0x180015440  test    eax, eax
0x180015442  jz      short loc_18001544F
0x180015444  mov     edx, eax
0x180015446  lea     rcx, aTapiservicemon_0; "TapiServiceMonitorThread: NotifyService"...
0x18001544d  jmp     short loc_1800154A1
0x18001544f  mov     rcx, cs:g_hTapiSrvMonitorTerminate; hHandle
0x180015456  mov     r8d, 1; bAlertable
0x18001545c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001545f  call    cs:__imp_WaitForSingleObjectEx
0x180015465  mov     ebx, eax
0x180015467  test    eax, eax
0x180015469  jnz     short loc_180015479
0x18001546b  lea     rcx, aTapiservicemon; "TapiServiceMonitorThread: Tapi Service "...
0x180015472  call    RasTapiTrace
0x180015477  jmp     short loc_1800154A6
0x180015479  mov     edx, 0C0h
0x18001547e  cmp     eax, edx
0x180015480  jz      short loc_18001549A
0x180015482  cmp     eax, 0FFFFFFFFh
0x180015485  jnz     short loc_18001548F
0x180015487  call    cs:__imp_GetLastError
0x18001548d  mov     ebx, eax
0x18001548f  mov     edx, ebx
0x180015491  lea     rcx, aTapiservicemon_4; "TapiServiceMonitorThread: WaitForSingle"...
0x180015498  jmp     short loc_1800154A1
0x18001549a  lea     rcx, aTapiservicemon_2; "TapiServiceMonitorThread: Exiting with "...
0x1800154a1  call    RasTapiTrace
0x1800154a6  mov     rcx, rdi; hSCObject
0x1800154a9  call    cs:__imp_CloseServiceHandle
0x1800154af  mov     rcx, rsi; hSCObject
0x1800154b2  call    cs:__imp_CloseServiceHandle
0x1800154b8  mov     eax, ebx
0x1800154ba  mov     rcx, [rsp+88h+var_18]
0x1800154bf  xor     rcx, rsp; StackCookie
0x1800154c2  call    __security_check_cookie
0x1800154c7  lea     r11, [rsp+88h+var_8]
0x1800154cf  mov     rbx, [r11+10h]
0x1800154d3  mov     rsi, [r11+18h]
0x1800154d7  mov     rsp, r11
0x1800154da  pop     rdi
0x1800154db  retn
```
