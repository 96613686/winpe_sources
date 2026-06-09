# CEfsService::UpdateServiceStatus(ulong,ulong)

- ea: `0x1800031f4`
- end: `0x18000322b`
- name: `?UpdateServiceStatus@CEfsService@@AEAAJKK@Z`
- size: `55`
- prototype: `__int64 __fastcall(LPSERVICE_STATUS lpServiceStatus, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180002c60`
- `0x180002ee0`
- `0x18000314c`

## callees

- `0x1800031f4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003206`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003210`

## pseudocode

```c
signed int __fastcall CEfsService::UpdateServiceStatus(LPSERVICE_STATUS lpServiceStatus, DWORD a2, DWORD a3)
{
  signed int result; // eax

  lpServiceStatus->dwControlsAccepted = a2;
  lpServiceStatus->dwCurrentState = a3;
  if ( SetServiceStatus(*(SERVICE_STATUS_HANDLE *)&lpServiceStatus[1].dwCurrentState, lpServiceStatus) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800031f4  sub     rsp, 28h
0x1800031f8  mov     [rcx+8], edx
0x1800031fb  mov     rdx, rcx; lpServiceStatus
0x1800031fe  mov     [rcx+4], r8d
0x180003202  mov     rcx, [rcx+20h]; hServiceStatus
0x180003206  call    cs:__imp_SetServiceStatus
0x18000320c  test    eax, eax
0x18000320e  jnz     short loc_180003224
0x180003210  call    cs:__imp_GetLastError
0x180003216  test    eax, eax
0x180003218  jle     short loc_180003226
0x18000321a  movzx   eax, ax
0x18000321d  or      eax, 80070000h
0x180003222  jmp     short loc_180003226
0x180003224  xor     eax, eax
0x180003226  add     rsp, 28h
0x18000322a  retn
```
