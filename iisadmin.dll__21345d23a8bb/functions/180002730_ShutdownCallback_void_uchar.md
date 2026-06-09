# ShutdownCallback(void *,uchar)

- ea: `0x180002730`
- end: `0x18000275a`
- name: `?ShutdownCallback@@YAXPEAXE@Z`
- size: `42`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180001a0c`

## pseudocode

```c
void __fastcall ShutdownCallback(PVOID a1)
{
  ++g_svcStatus.dwCheckPoint;
  g_svcStatus.dwCurrentState = 3;
  *(_QWORD *)&g_svcStatus.dwWin32ExitCode = 0;
  g_svcStatus.dwWaitHint = 10000;
  ReportServiceStatus();
}

```

## disassembly

```asm
0x180002730  inc     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS g_svcStatus ...
0x180002736  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_svcStatus ...
0x180002740  mov     qword ptr cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_svcStatus ...
0x18000274b  mov     cs:?g_svcStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 2710h; _SERVICE_STATUS g_svcStatus ...
0x180002755  jmp     ?ReportServiceStatus@@YAKXZ; ReportServiceStatus(void)
```
