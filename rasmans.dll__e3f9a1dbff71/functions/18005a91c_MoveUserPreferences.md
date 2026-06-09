# MoveUserPreferences

- ea: `0x18005a91c`
- end: `0x18005aa06`
- name: `MoveUserPreferences`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005a480`

## callees

- `0x18005a55c`
- `0x18005a91c`
- `0x18005aa0c`
- `0x18005b240`
- `0x18005dabc`
- `0x1800e7206`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a95a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a9cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a95a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a9cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a9f7`

## string_xrefs

- `0x18005a94c`: `Software\Microsoft\Windows NT\CurrentVersion\Network\RemoteAccess`
- `0x18005a9dd`: `RemoteAccess`

## pseudocode

```c
LSTATUS MoveUserPreferences()
{
  LSTATUS result; // eax
  char v1[180]; // [rsp+30h] [rbp-69h] BYREF
  int v2; // [rsp+E4h] [rbp+4Bh]
  HKEY hKey; // [rsp+100h] [rbp+67h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp+6Fh] BYREF

  phkResult = 0;
  hKey = 0;
  result = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Network\\RemoteAccess",
             0,
             0x20019u,
             &phkResult);
  if ( !result )
  {
    memset_0(v1, 0, 0xB8u);
    if ( !(unsigned int)SetDefaultUserPreferences(v1) && !(unsigned int)ReadUserPreferences(phkResult, v1) )
    {
      v2 = 1;
      if ( !(unsigned int)DwSetUserPreferences(v1, 0)
        && !RegOpenKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Network",
              0,
              0x20006u,
              &hKey) )
      {
        MyRegDeleteTree(hKey, L"RemoteAccess");
        RegCloseKey(hKey);
      }
    }
    return RegCloseKey(phkResult);
  }
  return result;
}

```

## disassembly

```asm
0x18005a91c  push    rbp
0x18005a91e  lea     rbp, [rsp-57h]
0x18005a923  sub     rsp, 0F0h
0x18005a92a  lea     rax, [rbp+57h+arg_8]
0x18005a92e  mov     [rbp+57h+arg_8], 0
0x18005a936  mov     r9d, 20019h; samDesired
0x18005a93c  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005a941  xor     r8d, r8d; ulOptions
0x18005a944  mov     [rbp+57h+hKey], 0
0x18005a94c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005a953  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005a95a  call    cs:__imp_RegOpenKeyExW
0x18005a960  test    eax, eax
0x18005a962  jnz     loc_18005A9FD
0x18005a968  xor     edx, edx; Val
0x18005a96a  lea     rcx, [rbp+57h+var_C0]; void *
0x18005a96e  mov     r8d, 0B8h; Size
0x18005a974  call    memset_0
0x18005a979  xor     edx, edx
0x18005a97b  lea     rcx, [rbp+57h+var_C0]; void *
0x18005a97f  call    SetDefaultUserPreferences
0x18005a984  test    eax, eax
0x18005a986  jnz     short loc_18005A9F3
0x18005a988  mov     rcx, [rbp+57h+arg_8]; hKey
0x18005a98c  lea     rdx, [rbp+57h+var_C0]; void *
0x18005a990  call    ReadUserPreferences
0x18005a995  test    eax, eax
0x18005a997  jnz     short loc_18005A9F3
0x18005a999  xor     edx, edx
0x18005a99b  mov     [rbp+57h+var_C], 1
0x18005a9a2  lea     rcx, [rbp+57h+var_C0]
0x18005a9a6  call    DwSetUserPreferences
0x18005a9ab  test    eax, eax
0x18005a9ad  jnz     short loc_18005A9F3
0x18005a9af  lea     rax, [rbp+57h+hKey]
0x18005a9b3  mov     r9d, 20006h; samDesired
0x18005a9b9  xor     r8d, r8d; ulOptions
0x18005a9bc  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18005a9c1  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005a9c8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005a9cf  call    cs:__imp_RegOpenKeyExW
0x18005a9d5  test    eax, eax
0x18005a9d7  jnz     short loc_18005A9F3
0x18005a9d9  mov     rcx, [rbp+57h+hKey]
0x18005a9dd  lea     rdx, aRemoteaccess; "RemoteAccess"
0x18005a9e4  call    MyRegDeleteTree
0x18005a9e9  mov     rcx, [rbp+57h+hKey]; hKey
0x18005a9ed  call    cs:__imp_RegCloseKey
0x18005a9f3  mov     rcx, [rbp+57h+arg_8]; hKey
0x18005a9f7  call    cs:__imp_RegCloseKey
0x18005a9fd  add     rsp, 0F0h
0x18005aa04  pop     rbp
0x18005aa05  retn
```
