# NetpIncJoinDomainEntryUseCount(void)

- ea: `0x18007d7c8`
- end: `0x18007d919`
- name: `?NetpIncJoinDomainEntryUseCount@@YAXXZ`
- size: `337`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180036230`

## callees

- `0x18007d7c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d856`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d856`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d896`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d8ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d896`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007d8ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d81e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d8c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d81e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d8c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d8fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d90c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d8fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d90c`

## string_xrefs

- `0x18007d7f4`: `SYSTEM\CurrentControlSet\Services\Netlogon\JoinDomain`
- `0x18007d84a`: `DcLocatorCacheReadCount`
- `0x18007d879`: `DcLocatorCacheReadCount`
- `0x18007d8b8`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters`

## pseudocode

```c
void NetpIncJoinDomainEntryUseCount(void)
{
  LSTATUS v0; // eax
  int v1; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF
  int v7; // [rsp+78h] [rbp+30h] BYREF

  hKey = 0;
  phkResult = 0;
  v7 = 1;
  Type = 0;
  cbData = 0;
  Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\JoinDomain",
          0,
          0x2001Bu,
          &hKey) )
  {
    cbData = 4;
    v0 = RegQueryValueExW(hKey, L"DcLocatorCacheReadCount", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v0 )
    {
      if ( v0 != 2 )
        goto LABEL_10;
      v1 = 1;
    }
    else
    {
      v1 = Data + 1;
    }
    Data = v1;
    if ( !RegSetValueExW(hKey, L"DcLocatorCacheReadCount", 0, 4u, (const BYTE *)&Data, 4u)
      && Data > 1
      && !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Parameters",
            0,
            2u,
            &phkResult) )
    {
      RegSetValueExW(phkResult, L"DcLocatorIsDoneWithJoinDomainEntry", 0, 4u, (const BYTE *)&v7, 4u);
    }
  }
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x18007d7c8  push    rbp
0x18007d7ca  push    rsi
0x18007d7cb  mov     rbp, rsp
0x18007d7ce  sub     rsp, 48h
0x18007d7d2  lea     rax, [rbp+hKey]
0x18007d7d6  mov     [rbp+hKey], 0
0x18007d7de  mov     r9d, 2001Bh; samDesired
0x18007d7e4  mov     [rsp+48h+phkResult], rax; phkResult
0x18007d7e9  xor     r8d, r8d; ulOptions
0x18007d7ec  mov     [rbp+var_10], 0
0x18007d7f4  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18007d7fb  mov     [rbp+arg_18], 1
0x18007d802  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d809  mov     [rbp+Type], 0
0x18007d810  mov     [rbp+cbData], 0
0x18007d817  mov     [rbp+Data], 0
0x18007d81e  call    cs:__imp_RegOpenKeyExW
0x18007d824  test    eax, eax
0x18007d826  jnz     loc_18007D8F4
0x18007d82c  mov     rcx, [rbp+hKey]; hKey
0x18007d830  lea     esi, [rax+4]
0x18007d833  lea     rax, [rbp+cbData]
0x18007d837  mov     [rbp+cbData], esi
0x18007d83a  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18007d83f  lea     r9, [rbp+Type]; lpType
0x18007d843  lea     rax, [rbp+Data]
0x18007d847  xor     r8d, r8d; lpReserved
0x18007d84a  lea     rdx, aDclocatorcache; "DcLocatorCacheReadCount"
0x18007d851  mov     [rsp+48h+phkResult], rax; lpData
0x18007d856  call    cs:__imp_RegQueryValueExW
0x18007d85c  test    eax, eax
0x18007d85e  jnz     short loc_18007D867
0x18007d860  mov     eax, [rbp+Data]
0x18007d863  inc     eax
0x18007d865  jmp     short loc_18007D875
0x18007d867  cmp     eax, 2
0x18007d86a  jnz     loc_18007D8F4
0x18007d870  mov     eax, 1
0x18007d875  mov     rcx, [rbp+hKey]; hKey
0x18007d879  lea     rdx, aDclocatorcache; "DcLocatorCacheReadCount"
0x18007d880  mov     [rbp+Data], eax
0x18007d883  mov     r9d, esi; dwType
0x18007d886  lea     rax, [rbp+Data]
0x18007d88a  mov     dword ptr [rsp+48h+lpcbData], esi; cbData
0x18007d88e  xor     r8d, r8d; Reserved
0x18007d891  mov     [rsp+48h+phkResult], rax; lpData
0x18007d896  call    cs:__imp_RegSetValueExW
0x18007d89c  test    eax, eax
0x18007d89e  jnz     short loc_18007D8F4
0x18007d8a0  cmp     [rbp+Data], 1
0x18007d8a4  jbe     short loc_18007D8F4
0x18007d8a6  lea     rax, [rbp+var_10]
0x18007d8aa  mov     r9d, 2; samDesired
0x18007d8b0  xor     r8d, r8d; ulOptions
0x18007d8b3  mov     [rsp+48h+phkResult], rax; phkResult
0x18007d8b8  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18007d8bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d8c6  call    cs:__imp_RegOpenKeyExW
0x18007d8cc  test    eax, eax
0x18007d8ce  jnz     short loc_18007D8F4
0x18007d8d0  mov     rcx, [rbp+var_10]; hKey
0x18007d8d4  lea     rax, [rbp+arg_18]
0x18007d8d8  mov     dword ptr [rsp+48h+lpcbData], esi; cbData
0x18007d8dc  lea     rdx, aDclocatorisdon; "DcLocatorIsDoneWithJoinDomainEntry"
0x18007d8e3  mov     r9d, esi; dwType
0x18007d8e6  mov     [rsp+48h+phkResult], rax; lpData
0x18007d8eb  xor     r8d, r8d; Reserved
0x18007d8ee  call    cs:__imp_RegSetValueExW
0x18007d8f4  mov     rcx, [rbp+hKey]; hKey
0x18007d8f8  test    rcx, rcx
0x18007d8fb  jz      short loc_18007D903
0x18007d8fd  call    cs:__imp_RegCloseKey
0x18007d903  mov     rcx, [rbp+var_10]; hKey
0x18007d907  test    rcx, rcx
0x18007d90a  jz      short loc_18007D912
0x18007d90c  call    cs:__imp_RegCloseKey
0x18007d912  add     rsp, 48h
0x18007d916  pop     rsi
0x18007d917  pop     rbp
0x18007d918  retn
```
