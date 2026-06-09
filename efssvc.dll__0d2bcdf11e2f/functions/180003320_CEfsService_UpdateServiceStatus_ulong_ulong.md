# CEfsService::UpdateServiceStatus(ulong,ulong)

- ea: `0x180003320`
- end: `0x180003364`
- name: `?UpdateServiceStatus@CEfsService@@AEAAJKK@Z`
- size: `68`
- prototype: `signed int __fastcall(LPSERVICE_STATUS lpServiceStatus, DWORD, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180002cd4`
- `0x180002fb0`
- `0x180003250`

## callees

- `0x180003320`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003332`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003342`

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
0x180003320  sub     rsp, 28h
0x180003324  mov     [rcx+8], edx
0x180003327  mov     rdx, rcx; lpServiceStatus
0x18000332a  mov     [rcx+4], r8d
0x18000332e  mov     rcx, [rcx+20h]; hServiceStatus
0x180003332  call    cs:__imp_SetServiceStatus
0x180003339  nop     dword ptr [rax+rax+00h]
0x18000333e  test    eax, eax
0x180003340  jnz     short loc_18000335C
0x180003342  call    cs:__imp_GetLastError
0x180003349  nop     dword ptr [rax+rax+00h]
0x18000334e  test    eax, eax
0x180003350  jle     short loc_18000335E
0x180003352  movzx   eax, ax
0x180003355  or      eax, 80070000h
0x18000335a  jmp     short loc_18000335E
0x18000335c  xor     eax, eax
0x18000335e  add     rsp, 28h
0x180003362  retn
```
