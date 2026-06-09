# SvcReportStatus(ulong,ulong,ulong)

- ea: `0x180008128`
- end: `0x1800081be`
- name: `?SvcReportStatus@@YAXKKK@Z`
- size: `150`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180007e50`

## callees

- `0x180008128`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000819f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000819f`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800081b2`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800081b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800081a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800081a7`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008195`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008195`

## pseudocode

```c
void __fastcall SvcReportStatus(DWORD a1)
{
  UINT LastError; // ebx
  HANDLE CurrentProcess; // rax

  if ( g_hStatus )
  {
    g_status.dwCurrentState = a1;
    g_status.dwWin32ExitCode = 0;
    g_status.dwWaitHint = 0;
    if ( a1 == 2 )
    {
      g_status.dwControlsAccepted = 0;
    }
    else
    {
      g_status.dwControlsAccepted = 4225;
      if ( a1 == 4 || a1 == 1 )
      {
        g_status.dwCheckPoint = 0;
LABEL_8:
        if ( !SetServiceStatus(g_hStatus, &g_status) )
        {
          LastError = GetLastError();
          CurrentProcess = GetCurrentProcess();
          TerminateProcess(CurrentProcess, LastError);
        }
        return;
      }
    }
    g_status.dwCheckPoint = ++dword_18002623C;
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x180008128  push    rbx
0x18000812a  sub     rsp, 20h
0x18000812e  mov     r8, cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_hStatus
0x180008135  xor     ebx, ebx
0x180008137  test    r8, r8
0x18000813a  jz      short loc_1800081B8
0x18000813c  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS g_status ...
0x180008142  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ebx; _SERVICE_STATUS g_status ...
0x180008148  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWaitHint, ebx; _SERVICE_STATUS g_status ...
0x18000814e  cmp     ecx, 2
0x180008151  jnz     short loc_18000815B
0x180008153  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, ebx; _SERVICE_STATUS g_status ...
0x180008159  jmp     short loc_18000816F
0x18000815b  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1081h; _SERVICE_STATUS g_status ...
0x180008165  cmp     ecx, 4
0x180008168  jz      short loc_180008185
0x18000816a  cmp     ecx, 1
0x18000816d  jz      short loc_180008185
0x18000816f  mov     eax, cs:dword_18002623C
0x180008175  inc     eax
0x180008177  mov     cs:dword_18002623C, eax
0x18000817d  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, eax; _SERVICE_STATUS g_status ...
0x180008183  jmp     short loc_18000818B
0x180008185  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, ebx; _SERVICE_STATUS g_status ...
0x18000818b  lea     rdx, ?g_status@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180008192  mov     rcx, r8; hServiceStatus
0x180008195  call    cs:__imp_SetServiceStatus
0x18000819b  test    eax, eax
0x18000819d  jnz     short loc_1800081B8
0x18000819f  call    cs:__imp_GetLastError
0x1800081a5  mov     ebx, eax
0x1800081a7  call    cs:__imp_GetCurrentProcess
0x1800081ad  mov     rcx, rax; hProcess
0x1800081b0  mov     edx, ebx; uExitCode
0x1800081b2  call    cs:__imp_TerminateProcess
0x1800081b8  add     rsp, 20h
0x1800081bc  pop     rbx
0x1800081bd  retn
```
