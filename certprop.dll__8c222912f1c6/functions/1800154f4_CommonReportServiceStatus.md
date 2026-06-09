# CommonReportServiceStatus

- ea: `0x1800154f4`
- end: `0x18001554d`
- name: `CommonReportServiceStatus`
- size: `89`
- prototype: `DWORD __fastcall(LPSERVICE_STATUS lpServiceStatus, SERVICE_STATUS_HANDLE hServiceStatus, DWORD, DWORD, DWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017d90`
- `0x180017f30`
- `0x18001b490`
- `0x18001b5c0`
- `0x18001b808`

## callees

- `0x1800154f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001553f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015531`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180015531`

## pseudocode

```c
DWORD __fastcall CommonReportServiceStatus(
        LPSERVICE_STATUS lpServiceStatus,
        SERVICE_STATUS_HANDLE hServiceStatus,
        DWORD a3,
        DWORD a4,
        DWORD a5)
{
  DWORD v5; // eax

  lpServiceStatus->dwControlsAccepted = a3 != 2 ? 0x85 : 0;
  if ( a4 )
  {
    lpServiceStatus->dwServiceSpecificExitCode = a4;
    v5 = 1066;
  }
  else
  {
    v5 = 0;
  }
  lpServiceStatus->dwWin32ExitCode = v5;
  lpServiceStatus->dwWaitHint = a5;
  lpServiceStatus->dwCurrentState = a3;
  if ( SetServiceStatus(hServiceStatus, lpServiceStatus) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800154f4  sub     rsp, 28h
0x1800154f8  lea     eax, [r8-2]
0x1800154fc  mov     r10, rdx
0x1800154ff  neg     eax
0x180015501  sbb     eax, eax
0x180015503  and     eax, 85h
0x180015508  mov     [rcx+8], eax
0x18001550b  test    r9d, r9d
0x18001550e  jnz     short loc_180015514
0x180015510  xor     eax, eax
0x180015512  jmp     short loc_18001551D
0x180015514  mov     [rcx+10h], r9d
0x180015518  mov     eax, 42Ah
0x18001551d  mov     [rcx+0Ch], eax
0x180015520  mov     rdx, rcx; lpServiceStatus
0x180015523  mov     eax, [rsp+28h+arg_20]
0x180015527  mov     [rcx+18h], eax
0x18001552a  mov     [rcx+4], r8d
0x18001552e  mov     rcx, r10; hServiceStatus
0x180015531  call    cs:__imp_SetServiceStatus
0x180015537  test    eax, eax
0x180015539  jnz     short loc_180015546
0x18001553b  add     rsp, 28h
0x18001553f  jmp     cs:__imp_GetLastError
0x180015546  xor     eax, eax
0x180015548  add     rsp, 28h
0x18001554c  retn
```
