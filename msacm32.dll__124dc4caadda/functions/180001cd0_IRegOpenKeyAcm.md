# IRegOpenKeyAcm

- ea: `0x180001cd0`
- end: `0x180001dba`
- name: `IRegOpenKeyAcm`
- size: `234`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001570`
- `0x180001ad0`
- `0x180005e70`
- `0x180007cf0`

## callees

- `0x180001cd0`

## import_xrefs

- `ntdll!RtlOpenCurrentUser` at `0x180001cf8`
- `ntdll!RtlOpenCurrentUser` at `0x180001cf8`
- `ntdll!NtClose` at `0x180001d3f`
- `ntdll!NtClose` at `0x180001d3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001daa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001daa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001d34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001d9b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001d34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180001d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001db2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001db2`

## string_xrefs

- `0x180001d11`: `Software\Microsoft\Multimedia\Audio Compression Manager\`

## pseudocode

```c
HKEY __fastcall IRegOpenKeyAcm(LPCWSTR lpSubKey)
{
  void *KeyHandle; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  phkResult = 0;
  KeyHandle = 0;
  if ( RtlOpenCurrentUser(0x2000000u, &KeyHandle) < 0 )
  {
    GetLastError();
    return 0;
  }
  else
  {
    RegCreateKeyExW(
      (HKEY)KeyHandle,
      L"Software\\Microsoft\\Multimedia\\Audio Compression Manager\\",
      0,
      0,
      0,
      0x20006u,
      0,
      &hKey,
      0);
    NtClose(KeyHandle);
    if ( hKey )
    {
      if ( RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0) )
        GetLastError();
      RegCloseKey(hKey);
    }
    return phkResult;
  }
}

```

## disassembly

```asm
0x180001cd0  mov     [rsp+arg_0], rbx
0x180001cd5  push    rdi
0x180001cd6  sub     rsp, 50h
0x180001cda  xor     edi, edi
0x180001cdc  lea     rdx, [rsp+58h+KeyHandle]; KeyHandle
0x180001ce1  mov     rbx, rcx
0x180001ce4  mov     [rsp+58h+hKey], rdi
0x180001ce9  mov     ecx, 2000000h; DesiredAccess
0x180001cee  mov     [rsp+58h+arg_18], rdi
0x180001cf3  mov     [rsp+58h+KeyHandle], rdi
0x180001cf8  call    cs:__imp_RtlOpenCurrentUser
0x180001cfe  test    eax, eax
0x180001d00  js      short loc_180001D5F
0x180001d02  mov     rcx, [rsp+58h+KeyHandle]; hKey
0x180001d07  lea     rax, [rsp+58h+hKey]
0x180001d0c  mov     [rsp+58h+lpdwDisposition], rdi; lpdwDisposition
0x180001d11  lea     rdx, gszAcmProfileKey; "Software\\Microsoft\\Multimedia\\Audio "...
0x180001d18  mov     [rsp+58h+phkResult], rax; phkResult
0x180001d1d  xor     r9d, r9d; lpClass
0x180001d20  mov     [rsp+58h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001d25  xor     r8d, r8d; Reserved
0x180001d28  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180001d30  mov     [rsp+58h+dwOptions], edi; dwOptions
0x180001d34  call    cs:__imp_RegCreateKeyExW
0x180001d3a  mov     rcx, [rsp+58h+KeyHandle]; Handle
0x180001d3f  call    cs:__imp_NtClose
0x180001d45  mov     rcx, [rsp+58h+hKey]; hKey
0x180001d4a  test    rcx, rcx
0x180001d4d  jnz     short loc_180001D72
0x180001d4f  mov     rax, [rsp+58h+arg_18]
0x180001d54  mov     rbx, [rsp+58h+arg_0]
0x180001d59  add     rsp, 50h
0x180001d5d  pop     rdi
0x180001d5e  retn
0x180001d5f  call    cs:__imp_GetLastError
0x180001d65  mov     rbx, [rsp+58h+arg_0]
0x180001d6a  xor     eax, eax
0x180001d6c  add     rsp, 50h
0x180001d70  pop     rdi
0x180001d71  retn
0x180001d72  mov     [rsp+58h+lpdwDisposition], rdi; lpdwDisposition
0x180001d77  lea     rax, [rsp+58h+arg_18]
0x180001d7c  mov     [rsp+58h+phkResult], rax; phkResult
0x180001d81  xor     r9d, r9d; lpClass
0x180001d84  mov     [rsp+58h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180001d89  xor     r8d, r8d; Reserved
0x180001d8c  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180001d94  mov     rdx, rbx; lpSubKey
0x180001d97  mov     [rsp+58h+dwOptions], edi; dwOptions
0x180001d9b  call    cs:__imp_RegCreateKeyExW
0x180001da1  test    eax, eax
0x180001da3  jnz     short loc_180001DB2
0x180001da5  mov     rcx, [rsp+58h+hKey]; hKey
0x180001daa  call    cs:__imp_RegCloseKey
0x180001db0  jmp     short loc_180001D4F
0x180001db2  call    cs:__imp_GetLastError
0x180001db8  jmp     short loc_180001DA5
```
