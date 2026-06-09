# GetPreFetchDebugFlags(void)

- ea: `0x18000c6d4`
- end: `0x18000c78f`
- name: `?GetPreFetchDebugFlags@@YAKXZ`
- size: `187`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000c46c`

## callees

- `0x18000c6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c77f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c77f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c777`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c777`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000c723`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000c723`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000c751`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000c751`

## string_xrefs

- `0x18000c707`: `SYSTEM\CurrentControlSet\Services\crypt32`

## pseudocode

```c
__int64 GetPreFetchDebugFlags(void)
{
  DWORD LastError; // ebx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  LastError = GetLastError();
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\crypt32", 0, 0x20019u, &hKey)
    || RegQueryValueExA(hKey, "DebugFlags", 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4
    || cbData != 4 )
  {
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return Data;
}

```

## disassembly

```asm
0x18000c6d4  push    rbp
0x18000c6d6  push    rbx
0x18000c6d7  mov     rbp, rsp
0x18000c6da  sub     rsp, 38h
0x18000c6de  mov     [rbp+hKey], 0
0x18000c6e6  mov     [rbp+Type], 0
0x18000c6ed  mov     [rbp+Data], 0
0x18000c6f4  mov     [rbp+cbData], 4
0x18000c6fb  call    cs:__imp_GetLastError
0x18000c701  mov     r9d, 20019h; samDesired
0x18000c707  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\cr"...
0x18000c70e  mov     ebx, eax
0x18000c710  xor     r8d, r8d; ulOptions
0x18000c713  lea     rax, [rbp+hKey]
0x18000c717  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c71e  mov     [rsp+38h+phkResult], rax; phkResult
0x18000c723  call    cs:__imp_RegOpenKeyExA
0x18000c729  test    eax, eax
0x18000c72b  jnz     short loc_18000C767
0x18000c72d  mov     rcx, [rbp+hKey]; hKey
0x18000c731  lea     rax, [rbp+cbData]
0x18000c735  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000c73a  lea     r9, [rbp+Type]; lpType
0x18000c73e  lea     rax, [rbp+Data]
0x18000c742  xor     r8d, r8d; lpReserved
0x18000c745  lea     rdx, aDebugflags; "DebugFlags"
0x18000c74c  mov     [rsp+38h+phkResult], rax; lpData
0x18000c751  call    cs:__imp_RegQueryValueExA
0x18000c757  test    eax, eax
0x18000c759  jnz     short loc_18000C767
0x18000c75b  cmp     [rbp+Type], 4
0x18000c75f  jnz     short loc_18000C767
0x18000c761  cmp     [rbp+cbData], 4
0x18000c765  jz      short loc_18000C76E
0x18000c767  mov     [rbp+Data], 0
0x18000c76e  mov     rcx, [rbp+hKey]; hKey
0x18000c772  test    rcx, rcx
0x18000c775  jz      short loc_18000C77D
0x18000c777  call    cs:__imp_RegCloseKey
0x18000c77d  mov     ecx, ebx; dwErrCode
0x18000c77f  call    cs:__imp_SetLastError
0x18000c785  mov     eax, [rbp+Data]
0x18000c788  add     rsp, 38h
0x18000c78c  pop     rbx
0x18000c78d  pop     rbp
0x18000c78e  retn
```
