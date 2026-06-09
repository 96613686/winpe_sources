# NetpIncJoinDomainEntryUseCount(void)

- ea: `0x180083478`
- end: `0x1800835f4`
- name: `?NetpIncJoinDomainEntryUseCount@@YAXXZ`
- size: `380`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800382b0`

## callees

- `0x180083478`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008350c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008350c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180083552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800835b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180083552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800835b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800834ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083588`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800834ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083588`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800835cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800835e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800835cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800835e0`

## string_xrefs

- `0x1800834a4`: `SYSTEM\CurrentControlSet\Services\Netlogon\JoinDomain`
- `0x180083500`: `DcLocatorCacheReadCount`
- `0x180083535`: `DcLocatorCacheReadCount`
- `0x18008357a`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters`

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
0x180083478  push    rbp
0x18008347a  push    rsi
0x18008347b  mov     rbp, rsp
0x18008347e  sub     rsp, 48h
0x180083482  lea     rax, [rbp+hKey]
0x180083486  mov     [rbp+hKey], 0
0x18008348e  mov     r9d, 2001Bh; samDesired
0x180083494  mov     [rsp+48h+phkResult], rax; phkResult
0x180083499  xor     r8d, r8d; ulOptions
0x18008349c  mov     [rbp+var_10], 0
0x1800834a4  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800834ab  mov     [rbp+arg_18], 1
0x1800834b2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800834b9  mov     [rbp+Type], 0
0x1800834c0  mov     [rbp+cbData], 0
0x1800834c7  mov     [rbp+Data], 0
0x1800834ce  call    cs:__imp_RegOpenKeyExW
0x1800834d5  nop     dword ptr [rax+rax+00h]
0x1800834da  test    eax, eax
0x1800834dc  jnz     loc_1800835C2
0x1800834e2  mov     rcx, [rbp+hKey]; hKey
0x1800834e6  lea     esi, [rax+4]
0x1800834e9  lea     rax, [rbp+cbData]
0x1800834ed  mov     [rbp+cbData], esi
0x1800834f0  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800834f5  lea     r9, [rbp+Type]; lpType
0x1800834f9  lea     rax, [rbp+Data]
0x1800834fd  xor     r8d, r8d; lpReserved
0x180083500  lea     rdx, aDclocatorcache; "DcLocatorCacheReadCount"
0x180083507  mov     [rsp+48h+phkResult], rax; lpData
0x18008350c  call    cs:__imp_RegQueryValueExW
0x180083513  nop     dword ptr [rax+rax+00h]
0x180083518  test    eax, eax
0x18008351a  jnz     short loc_180083523
0x18008351c  mov     eax, [rbp+Data]
0x18008351f  inc     eax
0x180083521  jmp     short loc_180083531
0x180083523  cmp     eax, 2
0x180083526  jnz     loc_1800835C2
0x18008352c  mov     eax, 1
0x180083531  mov     rcx, [rbp+hKey]; hKey
0x180083535  lea     rdx, aDclocatorcache; "DcLocatorCacheReadCount"
0x18008353c  mov     [rbp+Data], eax
0x18008353f  mov     r9d, esi; dwType
0x180083542  lea     rax, [rbp+Data]
0x180083546  mov     dword ptr [rsp+48h+lpcbData], esi; cbData
0x18008354a  xor     r8d, r8d; Reserved
0x18008354d  mov     [rsp+48h+phkResult], rax; lpData
0x180083552  call    cs:__imp_RegSetValueExW
0x180083559  nop     dword ptr [rax+rax+00h]
0x18008355e  test    eax, eax
0x180083560  jnz     short loc_1800835C2
0x180083562  cmp     [rbp+Data], 1
0x180083566  jbe     short loc_1800835C2
0x180083568  lea     rax, [rbp+var_10]
0x18008356c  mov     r9d, 2; samDesired
0x180083572  xor     r8d, r8d; ulOptions
0x180083575  mov     [rsp+48h+phkResult], rax; phkResult
0x18008357a  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180083581  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180083588  call    cs:__imp_RegOpenKeyExW
0x18008358f  nop     dword ptr [rax+rax+00h]
0x180083594  test    eax, eax
0x180083596  jnz     short loc_1800835C2
0x180083598  mov     rcx, [rbp+var_10]; hKey
0x18008359c  lea     rax, [rbp+arg_18]
0x1800835a0  mov     dword ptr [rsp+48h+lpcbData], esi; cbData
0x1800835a4  lea     rdx, aDclocatorisdon; "DcLocatorIsDoneWithJoinDomainEntry"
0x1800835ab  mov     r9d, esi; dwType
0x1800835ae  mov     [rsp+48h+phkResult], rax; lpData
0x1800835b3  xor     r8d, r8d; Reserved
0x1800835b6  call    cs:__imp_RegSetValueExW
0x1800835bd  nop     dword ptr [rax+rax+00h]
0x1800835c2  mov     rcx, [rbp+hKey]; hKey
0x1800835c6  test    rcx, rcx
0x1800835c9  jz      short loc_1800835D7
0x1800835cb  call    cs:__imp_RegCloseKey
0x1800835d2  nop     dword ptr [rax+rax+00h]
0x1800835d7  mov     rcx, [rbp+var_10]; hKey
0x1800835db  test    rcx, rcx
0x1800835de  jz      short loc_1800835EC
0x1800835e0  call    cs:__imp_RegCloseKey
0x1800835e7  nop     dword ptr [rax+rax+00h]
0x1800835ec  add     rsp, 48h
0x1800835f0  pop     rsi
0x1800835f1  pop     rbp
0x1800835f2  retn
```
