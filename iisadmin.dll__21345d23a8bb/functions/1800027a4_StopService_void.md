# StopService(void)

- ea: `0x1800027a4`
- end: `0x180002837`
- name: `?StopService@@YAXXZ`
- size: `147`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180001cf0`

## callees

- `0x180001a0c`
- `0x1800027a4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180002830`
- `IisRTL!PuDbgPrint` at `0x1800027f1`
- `IisRTL!PuDbgPrint` at `0x1800027f1`

## string_xrefs

- `0x1800027d8`: `shutting down service %s\n`
- `0x1800027d1`: `StopService`

## pseudocode

```c
void StopService(void)
{
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
      305,
      "StopService",
      "shutting down service %s\n",
      "IISADMIN");
  g_svcStatus.dwCurrentState = 3;
  *(_QWORD *)&g_svcStatus.dwWin32ExitCode = 0;
  g_svcStatus.dwCheckPoint = 1;
  g_svcStatus.dwWaitHint = 10000;
  ReportServiceStatus();
  SetEvent(g_hShutdownEvent);
}

```

## disassembly

```asm
0x1800027a4  sub     rsp, 38h
0x1800027a8  mov     eax, cs:g_dwDebugFlags
0x1800027ae  test    al, 3
0x1800027b0  setnz   cl
0x1800027b3  bt      eax, 15h
0x1800027b7  setb    al
0x1800027ba  test    al, cl
0x1800027bc  jz      short loc_1800027F7
0x1800027be  mov     rcx, cs:g_pDebug
0x1800027c5  lea     rax, ServiceName; "IISADMIN"
0x1800027cc  mov     [rsp+38h+var_10], rax
0x1800027d1  lea     r9, aStopservice; "StopService"
0x1800027d8  lea     rax, aShuttingDownSe; "shutting down service %s\n"
0x1800027df  mov     r8d, 131h
0x1800027e5  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x1800027ec  mov     [rsp+38h+var_18], rax
0x1800027f1  call    cs:__imp_PuDbgPrint
0x1800027f7  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_svcStatus ...
0x180002801  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_svcStatus ...
0x18000280c  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 1; _SERVICE_STATUS g_svcStatus ...
0x180002816  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 2710h; _SERVICE_STATUS g_svcStatus ...
0x180002820  call    ?ReportServiceStatus@@YAKXZ; ReportServiceStatus(void)
0x180002825  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; void * g_hShutdownEvent
0x18000282c  add     rsp, 38h
0x180002830  jmp     cs:__imp_SetEvent
```
