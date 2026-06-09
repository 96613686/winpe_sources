# SvcIsStarted

- ea: `0x1800264fc`
- end: `0x18002654f`
- name: `SvcIsStarted`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800209f8`
- `0x180026558`
- `0x180029fc0`

## callees

- `0x1800264fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026528`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002651e`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18002651e`

## pseudocode

```c
DWORD __fastcall SvcIsStarted(__int64 a1, _DWORD *a2)
{
  if ( !a1 || !a2 )
    return 87;
  if ( !QueryServiceStatus(*(SC_HANDLE *)(a1 + 8), (LPSERVICE_STATUS)(a1 + 16)) )
    return GetLastError();
  *a2 = *(_DWORD *)(a1 + 20) == 4;
  return 0;
}

```

## disassembly

```asm
0x1800264fc  mov     [rsp+arg_0], rbx
0x180026501  push    rdi
0x180026502  sub     rsp, 20h
0x180026506  mov     rdi, rdx
0x180026509  mov     rbx, rcx
0x18002650c  test    rcx, rcx
0x18002650f  jz      short loc_18002653F
0x180026511  test    rdx, rdx
0x180026514  jz      short loc_18002653F
0x180026516  lea     rdx, [rcx+10h]; lpServiceStatus
0x18002651a  mov     rcx, [rcx+8]; hService
0x18002651e  call    cs:__imp_QueryServiceStatus
0x180026524  test    eax, eax
0x180026526  jnz     short loc_180026530
0x180026528  call    cs:__imp_GetLastError
0x18002652e  jmp     short loc_180026544
0x180026530  xor     eax, eax
0x180026532  cmp     dword ptr [rbx+14h], 4
0x180026536  setz    al
0x180026539  mov     [rdi], eax
0x18002653b  xor     eax, eax
0x18002653d  jmp     short loc_180026544
0x18002653f  mov     eax, 57h ; 'W'
0x180026544  mov     rbx, [rsp+28h+arg_0]
0x180026549  add     rsp, 20h
0x18002654d  pop     rdi
0x18002654e  retn
```
