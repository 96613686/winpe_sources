# StartUpIndicateClientActivity(void)

- ea: `0x180002760`
- end: `0x18000279d`
- name: `?StartUpIndicateClientActivity@@YAXXZ`
- size: `61`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180001e60`

## callees

- `0x180001958`
- `0x180001a0c`
- `0x180002760`

## pseudocode

```c
void StartUpIndicateClientActivity(void)
{
  DWORD StartupWaitHint; // eax

  if ( g_svcStatus.dwCurrentState == 2 )
  {
    StartupWaitHint = GetStartupWaitHint();
    ++g_svcStatus.dwCheckPoint;
    g_svcStatus.dwWaitHint = StartupWaitHint;
    g_svcStatus.dwCurrentState = 2;
    *(_QWORD *)&g_svcStatus.dwWin32ExitCode = 0;
    ReportServiceStatus();
  }
}

```

## disassembly

```asm
0x180002760  sub     rsp, 28h
0x180002764  cmp     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_svcStatus ...
0x18000276b  jnz     short loc_180002798
0x18000276d  call    ?GetStartupWaitHint@@YAKXZ; GetStartupWaitHint(void)
0x180002772  inc     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS g_svcStatus ...
0x180002778  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, eax; _SERVICE_STATUS g_svcStatus ...
0x18000277e  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_svcStatus ...
0x180002788  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_svcStatus ...
0x180002793  call    ?ReportServiceStatus@@YAKXZ; ReportServiceStatus(void)
0x180002798  add     rsp, 28h
0x18000279c  retn
```
