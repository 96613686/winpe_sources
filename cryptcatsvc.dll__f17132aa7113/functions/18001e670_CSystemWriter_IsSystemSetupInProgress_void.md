# CSystemWriter::IsSystemSetupInProgress(void)

- ea: `0x18001e670`
- end: `0x18001e714`
- name: `?IsSystemSetupInProgress@CSystemWriter@@CAHXZ`
- size: `164`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18001eb28`

## callees

- `0x18000be40`
- `0x18001e670`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e6bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e6bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e6ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e6ed`

## pseudocode

```c
__int64 CSystemWriter::IsSystemSetupInProgress(void)
{
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-1Ch] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, 1u, &hKey) )
  {
    RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, 0, Data, &cbData);
    RegCloseKey(hKey);
  }
  return *(unsigned int *)Data;
}

```

## disassembly

```asm
0x18001e670  sub     rsp, 58h
0x18001e674  mov     rax, cs:__security_cookie
0x18001e67b  xor     rax, rsp
0x18001e67e  mov     [rsp+58h+var_18], rax
0x18001e683  lea     rax, [rsp+58h+hKey]
0x18001e688  mov     [rsp+58h+hKey], 0
0x18001e691  mov     r9d, 1; samDesired
0x18001e697  mov     [rsp+58h+phkResult], rax; phkResult
0x18001e69c  xor     r8d, r8d; ulOptions
0x18001e69f  mov     dword ptr [rsp+58h+Data], 0
0x18001e6a7  lea     rdx, aSystemSetup; "System\\Setup"
0x18001e6ae  mov     [rsp+58h+cbData], 4
0x18001e6b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e6bd  call    cs:__imp_RegOpenKeyExW
0x18001e6c3  test    eax, eax
0x18001e6c5  jnz     short loc_18001E6FE
0x18001e6c7  mov     rcx, [rsp+58h+hKey]; hKey
0x18001e6cc  lea     rax, [rsp+58h+cbData]
0x18001e6d1  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001e6d6  lea     rdx, ValueName; "SystemSetupInProgress"
0x18001e6dd  lea     rax, [rsp+58h+Data]
0x18001e6e2  xor     r9d, r9d; lpType
0x18001e6e5  xor     r8d, r8d; lpReserved
0x18001e6e8  mov     [rsp+58h+phkResult], rax; lpData
0x18001e6ed  call    cs:__imp_RegQueryValueExW
0x18001e6f3  mov     rcx, [rsp+58h+hKey]; hKey
0x18001e6f8  call    cs:__imp_RegCloseKey
0x18001e6fe  mov     eax, dword ptr [rsp+58h+Data]
0x18001e702  mov     rcx, [rsp+58h+var_18]
0x18001e707  xor     rcx, rsp; StackCookie
0x18001e70a  call    __security_check_cookie
0x18001e70f  add     rsp, 58h
0x18001e713  retn
```
