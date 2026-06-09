# GetClientHierarchy(void)

- ea: `0x180018b74`
- end: `0x180018c19`
- name: `?GetClientHierarchy@@YAKXZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018c20`
- `0x18001bff0`
- `0x18002cb38`

## callees

- `0x180018b74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018bb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018bb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018be6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018be6`

## pseudocode

```c
__int64 GetClientHierarchy(void)
{
  unsigned int v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\uDRM", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Hierarchy", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v0 = Data;
      if ( Data > 2 )
        v0 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180018b74  push    rbp
0x180018b76  push    rbx
0x180018b77  mov     rbp, rsp
0x180018b7a  sub     rsp, 38h
0x180018b7e  xor     ebx, ebx
0x180018b80  mov     [rbp+hKey], 0
0x180018b88  lea     rax, [rbp+hKey]
0x180018b8c  mov     [rbp+Type], ebx
0x180018b8f  mov     r9d, 20019h; samDesired
0x180018b95  mov     [rbp+Data], ebx
0x180018b98  xor     r8d, r8d; ulOptions
0x180018b9b  mov     [rbp+cbData], ebx
0x180018b9e  lea     rdx, ?g_wszReguDRMRoot@@3QBGB; "Software\\Microsoft\\uDRM"
0x180018ba5  mov     [rsp+38h+phkResult], rax; phkResult
0x180018baa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018bb1  call    cs:__imp_RegOpenKeyExW
0x180018bb7  test    eax, eax
0x180018bb9  jnz     short loc_180018C01
0x180018bbb  mov     rcx, [rbp+hKey]; hKey
0x180018bbf  lea     rax, [rbp+cbData]
0x180018bc3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180018bc8  lea     r9, [rbp+Type]; lpType
0x180018bcc  lea     rax, [rbp+Data]
0x180018bd0  mov     [rbp+cbData], 4
0x180018bd7  xor     r8d, r8d; lpReserved
0x180018bda  mov     [rsp+38h+phkResult], rax; lpData
0x180018bdf  lea     rdx, ?g_wszReguDRMHierarchy@@3QBGB; "Hierarchy"
0x180018be6  call    cs:__imp_RegQueryValueExW
0x180018bec  test    eax, eax
0x180018bee  jnz     short loc_180018C01
0x180018bf0  cmp     [rbp+Type], 4
0x180018bf4  jnz     short loc_180018C01
0x180018bf6  mov     ebx, [rbp+Data]
0x180018bf9  xor     ecx, ecx
0x180018bfb  cmp     ebx, 2
0x180018bfe  cmova   ebx, ecx
0x180018c01  mov     rcx, [rbp+hKey]; hKey
0x180018c05  test    rcx, rcx
0x180018c08  jz      short loc_180018C10
0x180018c0a  call    cs:__imp_RegCloseKey
0x180018c10  mov     eax, ebx
0x180018c12  add     rsp, 38h
0x180018c16  pop     rbx
0x180018c17  pop     rbp
0x180018c18  retn
```
