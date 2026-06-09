# SvcUpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x1800082d8`
- end: `0x18000834f`
- name: `?SvcUpdateServiceStatus@@YAXKKK@Z`
- size: `119`
- prototype: `void __fastcall(unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180007eb0`

## callees

- `0x1800082d8`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008344`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180008344`

## pseudocode

```c
void __fastcall SvcUpdateServiceStatus(DWORD a1, DWORD a2, DWORD a3)
{
  if ( g_hStatus )
  {
    if ( a1 == 2 )
      g_status.dwControlsAccepted &= ~1u;
    else
      g_status.dwControlsAccepted |= 1u;
    g_status.dwCurrentState = a1;
    g_status.dwWin32ExitCode = a2;
    g_status.dwWaitHint = a3;
    if ( a1 == 4 || a1 == 1 )
      g_status.dwCheckPoint = 0;
    else
      g_status.dwCheckPoint = dword_180026240++;
    SetServiceStatus(g_hStatus, &g_status);
  }
}

```

## disassembly

```asm
0x1800082d8  sub     rsp, 28h
0x1800082dc  mov     r9, cs:?g_hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_hStatus
0x1800082e3  test    r9, r9
0x1800082e6  jz      short loc_18000834A
0x1800082e8  cmp     ecx, 2
0x1800082eb  jnz     short loc_1800082F6
0x1800082ed  and     cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 0FFFFFFFEh; _SERVICE_STATUS g_status ...
0x1800082f4  jmp     short loc_1800082FD
0x1800082f6  or      cs:?g_status@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 1; _SERVICE_STATUS g_status ...
0x1800082fd  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCurrentState, ecx; _SERVICE_STATUS g_status ...
0x180008303  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, edx; _SERVICE_STATUS g_status ...
0x180008309  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwWaitHint, r8d; _SERVICE_STATUS g_status ...
0x180008310  cmp     ecx, 4
0x180008313  jz      short loc_180008330
0x180008315  cmp     ecx, 1
0x180008318  jz      short loc_180008330
0x18000831a  mov     eax, cs:dword_180026240
0x180008320  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, eax; _SERVICE_STATUS g_status ...
0x180008326  inc     eax
0x180008328  mov     cs:dword_180026240, eax
0x18000832e  jmp     short loc_18000833A
0x180008330  mov     cs:?g_status@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_status ...
0x18000833a  lea     rdx, ?g_status@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180008341  mov     rcx, r9; hServiceStatus
0x180008344  call    cs:__imp_SetServiceStatus
0x18000834a  add     rsp, 28h
0x18000834e  retn
```
