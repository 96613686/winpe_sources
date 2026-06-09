# IsCachePWAllowed

- ea: `0x180004f2c`
- end: `0x180004fda`
- name: `IsCachePWAllowed`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004350`

## callees

- `0x180004f2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004fa8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004fa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004fb4`

## string_xrefs

- `0x180004fa1`: `AllowCachePW`

## pseudocode

```c
_BOOL8 IsCachePWAllowed()
{
  LSTATUS v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Cryptography\\Protect", 0, 1u, &hKey) )
    return 1;
  cbData = 4;
  v0 = RegQueryValueExW(hKey, L"AllowCachePW", 0, &Type, (LPBYTE)&Data, &cbData);
  RegCloseKey(hKey);
  return v0 || Type != 4 || Data != 0;
}

```

## disassembly

```asm
0x180004f2c  push    rbp
0x180004f2e  push    rbx
0x180004f2f  mov     rbp, rsp
0x180004f32  sub     rsp, 38h
0x180004f36  lea     rax, [rbp+hKey]
0x180004f3a  mov     [rbp+hKey], 0
0x180004f42  mov     r9d, 1; samDesired
0x180004f48  mov     [rsp+38h+phkResult], rax; phkResult
0x180004f4d  xor     r8d, r8d; ulOptions
0x180004f50  mov     [rbp+Type], 0
0x180004f57  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Cryptogr"...
0x180004f5e  mov     [rbp+Data], 0
0x180004f65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004f6c  mov     [rbp+cbData], 0
0x180004f73  call    cs:__imp_RegOpenKeyExW
0x180004f79  test    eax, eax
0x180004f7b  jnz     short loc_180004FCE
0x180004f7d  mov     rcx, [rbp+hKey]; hKey
0x180004f81  lea     rax, [rbp+cbData]
0x180004f85  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180004f8a  lea     r9, [rbp+Type]; lpType
0x180004f8e  lea     rax, [rbp+Data]
0x180004f92  mov     [rbp+cbData], 4
0x180004f99  xor     r8d, r8d; lpReserved
0x180004f9c  mov     [rsp+38h+phkResult], rax; lpData
0x180004fa1  lea     rdx, ValueName; "AllowCachePW"
0x180004fa8  call    cs:__imp_RegQueryValueExW
0x180004fae  mov     rcx, [rbp+hKey]; hKey
0x180004fb2  mov     ebx, eax
0x180004fb4  call    cs:__imp_RegCloseKey
0x180004fba  test    ebx, ebx
0x180004fbc  jnz     short loc_180004FCE
0x180004fbe  cmp     [rbp+Type], 4
0x180004fc2  jnz     short loc_180004FCE
0x180004fc4  xor     eax, eax
0x180004fc6  cmp     [rbp+Data], eax
0x180004fc9  setnz   al
0x180004fcc  jmp     short loc_180004FD3
0x180004fce  mov     eax, 1
0x180004fd3  add     rsp, 38h
0x180004fd7  pop     rbx
0x180004fd8  pop     rbp
0x180004fd9  retn
```
