# LsapUpdateConfigSettings(void)

- ea: `0x1800b4574`
- end: `0x1800b46af`
- name: `?LsapUpdateConfigSettings@@YAXXZ`
- size: `315`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800adbf0`

## callees

- `0x1800b4574`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b469c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b4687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b469c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b4657`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b4657`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b45bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4622`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b45bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b4622`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b4672`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800b4672`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b45f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b45f2`

## string_xrefs

- `0x1800b4642`: `LsaLookupCacheMaxSize`
- `0x1800b459f`: `Security\SidCache`

## pseudocode

```c
void LsapUpdateConfigSettings(void)
{
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  phkResult = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Security\\SidCache", 0, 0x2000000u, &hKey)
    && !RegQueryValueExW(hKey, L"MaxEntries", 0, 0, (LPBYTE)&Data, &cbData)
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x2000000u, &phkResult)
    && !RegSetValueExW(phkResult, L"LsaLookupCacheMaxSize", 0, 4u, (const BYTE *)&Data, 4u) )
  {
    RegDeleteValueW(hKey, L"MaxEntries");
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x1800b4574  push    rbp
0x1800b4576  mov     rbp, rsp
0x1800b4579  sub     rsp, 30h
0x1800b457d  lea     rax, [rbp+hKey]
0x1800b4581  mov     [rbp+hKey], 0
0x1800b4589  mov     r9d, 2000000h; samDesired
0x1800b458f  mov     [rsp+30h+phkResult], rax; phkResult
0x1800b4594  xor     r8d, r8d; ulOptions
0x1800b4597  mov     [rbp+arg_18], 0
0x1800b459f  lea     rdx, aSecuritySidcac; "Security\\SidCache"
0x1800b45a6  mov     [rbp+cbData], 4
0x1800b45ad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b45b4  mov     [rbp+Data], 0
0x1800b45bb  call    cs:__imp_RegOpenKeyExW
0x1800b45c2  nop     dword ptr [rax+rax+00h]
0x1800b45c7  test    eax, eax
0x1800b45c9  jnz     loc_1800B467E
0x1800b45cf  mov     rcx, [rbp+hKey]; hKey
0x1800b45d3  lea     rax, [rbp+cbData]
0x1800b45d7  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800b45dc  lea     rdx, aMaxentries; "MaxEntries"
0x1800b45e3  lea     rax, [rbp+Data]
0x1800b45e7  xor     r9d, r9d; lpType
0x1800b45ea  xor     r8d, r8d; lpReserved
0x1800b45ed  mov     [rsp+30h+phkResult], rax; lpData
0x1800b45f2  call    cs:__imp_RegQueryValueExW
0x1800b45f9  nop     dword ptr [rax+rax+00h]
0x1800b45fe  test    eax, eax
0x1800b4600  jnz     short loc_1800B467E
0x1800b4602  lea     rax, [rbp+arg_18]
0x1800b4606  mov     r9d, 2000000h; samDesired
0x1800b460c  xor     r8d, r8d; ulOptions
0x1800b460f  mov     [rsp+30h+phkResult], rax; phkResult
0x1800b4614  lea     rdx, aSystemCurrentc_14; "System\\CurrentControlSet\\Control\\Lsa"
0x1800b461b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b4622  call    cs:__imp_RegOpenKeyExW
0x1800b4629  nop     dword ptr [rax+rax+00h]
0x1800b462e  test    eax, eax
0x1800b4630  jnz     short loc_1800B467E
0x1800b4632  mov     rcx, [rbp+arg_18]; hKey
0x1800b4636  lea     rax, [rbp+Data]
0x1800b463a  mov     dword ptr [rsp+30h+lpcbData], 4; cbData
0x1800b4642  lea     rdx, aLsalookupcache_0; "LsaLookupCacheMaxSize"
0x1800b4649  mov     r9d, 4; dwType
0x1800b464f  mov     [rsp+30h+phkResult], rax; lpData
0x1800b4654  xor     r8d, r8d; Reserved
0x1800b4657  call    cs:__imp_RegSetValueExW
0x1800b465e  nop     dword ptr [rax+rax+00h]
0x1800b4663  test    eax, eax
0x1800b4665  jnz     short loc_1800B467E
0x1800b4667  mov     rcx, [rbp+hKey]; hKey
0x1800b466b  lea     rdx, aMaxentries; "MaxEntries"
0x1800b4672  call    cs:__imp_RegDeleteValueW
0x1800b4679  nop     dword ptr [rax+rax+00h]
0x1800b467e  mov     rcx, [rbp+hKey]; hKey
0x1800b4682  test    rcx, rcx
0x1800b4685  jz      short loc_1800B4693
0x1800b4687  call    cs:__imp_RegCloseKey
0x1800b468e  nop     dword ptr [rax+rax+00h]
0x1800b4693  mov     rcx, [rbp+arg_18]; hKey
0x1800b4697  test    rcx, rcx
0x1800b469a  jz      short loc_1800B46A8
0x1800b469c  call    cs:__imp_RegCloseKey
0x1800b46a3  nop     dword ptr [rax+rax+00h]
0x1800b46a8  add     rsp, 30h
0x1800b46ac  pop     rbp
0x1800b46ad  retn
```
