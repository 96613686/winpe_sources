# IPSecSPDUpdateStatus

- ea: `0x180007550`
- end: `0x18000757b`
- name: `IPSecSPDUpdateStatus`
- size: `43`
- prototype: `DWORD()`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180007430`
- `0x18000c564`

## callees

- `0x180007550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000756c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000756c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007562`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180007562`

## pseudocode

```c
DWORD IPSecSPDUpdateStatus()
{
  if ( SetServiceStatus(IPSecSPDStatusHandle, &IPSecSPDStatus) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180007550  sub     rsp, 28h
0x180007554  mov     rcx, cs:IPSecSPDStatusHandle; hServiceStatus
0x18000755b  lea     rdx, IPSecSPDStatus; lpServiceStatus
0x180007562  call    cs:__imp_SetServiceStatus
0x180007568  test    eax, eax
0x18000756a  jnz     short loc_180007574
0x18000756c  call    cs:__imp_GetLastError
0x180007572  jmp     short loc_180007576
0x180007574  xor     eax, eax
0x180007576  add     rsp, 28h
0x18000757a  retn
```
