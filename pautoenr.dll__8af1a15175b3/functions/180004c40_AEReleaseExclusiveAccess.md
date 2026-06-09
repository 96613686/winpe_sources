# AEReleaseExclusiveAccess

- ea: `0x180004c40`
- end: `0x180004cbc`
- name: `AEReleaseExclusiveAccess`
- size: `124`
- prototype: `LSTATUS __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001d90`

## callees

- `0x180004c40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004c60`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180004c60`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004c7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004cb1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004c7c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180004cb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c8c`

## pseudocode

```c
LSTATUS __fastcall AEReleaseExclusiveAccess(int a1)
{
  LSTATUS result; // eax
  HKEY phkResult; // [rsp+38h] [rbp+10h] BYREF

  phkResult = 0;
  if ( a1 )
  {
    phkResult = HKEY_LOCAL_MACHINE;
    return RegDeleteKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Volatile-AutoEnroll-EXCLUSIVE", 0, 0);
  }
  else
  {
    result = RegOpenCurrentUser(0x20006u, &phkResult);
    if ( !result )
    {
      result = RegDeleteKeyExW(phkResult, L"SOFTWARE\\Microsoft\\Volatile-AutoEnroll-EXCLUSIVE", 0, 0);
      if ( phkResult )
        return RegCloseKey(phkResult);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004c40  mov     [rsp+phkResult], rdx
0x180004c45  sub     rsp, 28h
0x180004c49  mov     [rsp+28h+phkResult], 0
0x180004c52  test    ecx, ecx
0x180004c54  jnz     short loc_180004C94
0x180004c56  lea     rdx, [rsp+28h+phkResult]; phkResult
0x180004c5b  mov     ecx, 20006h; samDesired
0x180004c60  call    cs:__imp_RegOpenCurrentUser
0x180004c66  test    eax, eax
0x180004c68  jnz     short loc_180004CB7
0x180004c6a  mov     rcx, [rsp+28h+phkResult]; hKey
0x180004c6f  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Volatile-AutoEnrol"...
0x180004c76  xor     r9d, r9d; Reserved
0x180004c79  xor     r8d, r8d; samDesired
0x180004c7c  call    cs:__imp_RegDeleteKeyExW
0x180004c82  mov     rcx, [rsp+28h+phkResult]; hKey
0x180004c87  test    rcx, rcx
0x180004c8a  jz      short loc_180004CB7
0x180004c8c  call    cs:__imp_RegCloseKey
0x180004c92  jmp     short loc_180004CB7
0x180004c94  xor     r9d, r9d; Reserved
0x180004c97  mov     [rsp+28h+phkResult], 0FFFFFFFF80000002h
0x180004ca0  xor     r8d, r8d; samDesired
0x180004ca3  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Volatile-AutoEnrol"...
0x180004caa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004cb1  call    cs:__imp_RegDeleteKeyExW
0x180004cb7  add     rsp, 28h
0x180004cbb  retn
```
