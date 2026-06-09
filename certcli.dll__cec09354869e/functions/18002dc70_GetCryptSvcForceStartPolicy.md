# GetCryptSvcForceStartPolicy

- ea: `0x18002dc70`
- end: `0x18002dd15`
- name: `GetCryptSvcForceStartPolicy`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002de54`

## callees

- `0x18002dc70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dcbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002dcbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dcea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002dcea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd06`

## pseudocode

```c
__int64 GetCryptSvcForceStartPolicy()
{
  unsigned int v0; // ebx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  v0 = 1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\CatalogDB", 0, 0x20019u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"CryptSvcForceStartPolicy", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && Data <= 2 )
    {
      v0 = Data;
    }
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x18002dc70  push    rbp
0x18002dc72  push    rbx
0x18002dc73  mov     rbp, rsp
0x18002dc76  sub     rsp, 38h
0x18002dc7a  lea     rax, [rbp+hKey]
0x18002dc7e  mov     [rbp+hKey], 0
0x18002dc86  mov     r9d, 20019h; samDesired
0x18002dc8c  mov     [rsp+38h+phkResult], rax; phkResult
0x18002dc91  xor     r8d, r8d; ulOptions
0x18002dc94  mov     [rbp+Type], 0
0x18002dc9b  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Cryptography\\Cata"...
0x18002dca2  mov     [rbp+Data], 0
0x18002dca9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002dcb0  mov     [rbp+cbData], 4
0x18002dcb7  mov     ebx, 1
0x18002dcbc  call    cs:__imp_RegOpenKeyExW
0x18002dcc2  test    eax, eax
0x18002dcc4  jnz     short loc_18002DD0C
0x18002dcc6  mov     rcx, [rbp+hKey]; hKey
0x18002dcca  lea     rax, [rbp+cbData]
0x18002dcce  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002dcd3  lea     r9, [rbp+Type]; lpType
0x18002dcd7  lea     rax, [rbp+Data]
0x18002dcdb  xor     r8d, r8d; lpReserved
0x18002dcde  lea     rdx, aCryptsvcforces; "CryptSvcForceStartPolicy"
0x18002dce5  mov     [rsp+38h+phkResult], rax; lpData
0x18002dcea  call    cs:__imp_RegQueryValueExW
0x18002dcf0  test    eax, eax
0x18002dcf2  jnz     short loc_18002DD02
0x18002dcf4  cmp     [rbp+Type], 4
0x18002dcf8  jnz     short loc_18002DD02
0x18002dcfa  cmp     [rbp+Data], 2
0x18002dcfe  cmovbe  ebx, [rbp+Data]
0x18002dd02  mov     rcx, [rbp+hKey]; hKey
0x18002dd06  call    cs:__imp_RegCloseKey
0x18002dd0c  mov     eax, ebx
0x18002dd0e  add     rsp, 38h
0x18002dd12  pop     rbx
0x18002dd13  pop     rbp
0x18002dd14  retn
```
