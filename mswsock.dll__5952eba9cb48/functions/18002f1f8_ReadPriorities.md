# ReadPriorities

- ea: `0x18002f1f8`
- end: `0x18002f361`
- name: `ReadPriorities`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18002ef90`

## callees

- `0x18002f1f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f34e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f34e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f2a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f2d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f30b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f33e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f272`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f2a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f2d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f30b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002f33e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f237`

## string_xrefs

- `0x18002f222`: `System\CurrentControlSet\Services\Tcpip\ServiceProvider`
- `0x18002f332`: `MaxHostentCacheSize`

## pseudocode

```c
LSTATUS ReadPriorities()
{
  LSTATUS result; // eax
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  hKey = 0;
  cbData = 4;
  Type = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\Tcpip\\ServiceProvider",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    RegQueryValueExW(hKey, L"LocalPriority", 0, &Type, &LocalPriority, &cbData);
    RegQueryValueExW(hKey, L"HostsPriority", 0, &Type, &HostsPriority, &cbData);
    RegQueryValueExW(hKey, L"DnsPriority", 0, &Type, &DnsPriority, &cbData);
    RegQueryValueExW(hKey, L"NetbtPriority", 0, &Type, &NetbtPriority, &cbData);
    RegQueryValueExW(hKey, L"MaxHostentCacheSize", 0, &Type, &MaxHostentCacheSize, &cbData);
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18002f1f8  push    rbp
0x18002f1fa  mov     rbp, rsp
0x18002f1fd  sub     rsp, 30h
0x18002f201  lea     rax, [rbp+hKey]
0x18002f205  mov     [rbp+hKey], 0
0x18002f20d  mov     r9d, 20019h; samDesired
0x18002f213  mov     [rsp+30h+phkResult], rax; phkResult
0x18002f218  xor     r8d, r8d; ulOptions
0x18002f21b  mov     [rbp+cbData], 4
0x18002f222  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18002f229  mov     [rbp+Type], 0
0x18002f230  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f237  call    cs:__imp_RegOpenKeyExW
0x18002f23e  nop     dword ptr [rax+rax+00h]
0x18002f243  test    eax, eax
0x18002f245  jnz     loc_18002F35A
0x18002f24b  mov     rcx, [rbp+hKey]; hKey
0x18002f24f  lea     rax, [rbp+cbData]
0x18002f253  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002f258  lea     r9, [rbp+Type]; lpType
0x18002f25c  lea     rax, LocalPriority
0x18002f263  xor     r8d, r8d; lpReserved
0x18002f266  lea     rdx, aLocalpriority; "LocalPriority"
0x18002f26d  mov     [rsp+30h+phkResult], rax; lpData
0x18002f272  call    cs:__imp_RegQueryValueExW
0x18002f279  nop     dword ptr [rax+rax+00h]
0x18002f27e  mov     rcx, [rbp+hKey]; hKey
0x18002f282  lea     rax, [rbp+cbData]
0x18002f286  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002f28b  lea     r9, [rbp+Type]; lpType
0x18002f28f  lea     rax, HostsPriority
0x18002f296  xor     r8d, r8d; lpReserved
0x18002f299  lea     rdx, aHostspriority; "HostsPriority"
0x18002f2a0  mov     [rsp+30h+phkResult], rax; lpData
0x18002f2a5  call    cs:__imp_RegQueryValueExW
0x18002f2ac  nop     dword ptr [rax+rax+00h]
0x18002f2b1  mov     rcx, [rbp+hKey]; hKey
0x18002f2b5  lea     rax, [rbp+cbData]
0x18002f2b9  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002f2be  lea     r9, [rbp+Type]; lpType
0x18002f2c2  lea     rax, DnsPriority
0x18002f2c9  xor     r8d, r8d; lpReserved
0x18002f2cc  lea     rdx, aDnspriority; "DnsPriority"
0x18002f2d3  mov     [rsp+30h+phkResult], rax; lpData
0x18002f2d8  call    cs:__imp_RegQueryValueExW
0x18002f2df  nop     dword ptr [rax+rax+00h]
0x18002f2e4  mov     rcx, [rbp+hKey]; hKey
0x18002f2e8  lea     rax, [rbp+cbData]
0x18002f2ec  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002f2f1  lea     r9, [rbp+Type]; lpType
0x18002f2f5  lea     rax, NetbtPriority
0x18002f2fc  xor     r8d, r8d; lpReserved
0x18002f2ff  lea     rdx, aNetbtpriority; "NetbtPriority"
0x18002f306  mov     [rsp+30h+phkResult], rax; lpData
0x18002f30b  call    cs:__imp_RegQueryValueExW
0x18002f312  nop     dword ptr [rax+rax+00h]
0x18002f317  mov     rcx, [rbp+hKey]; hKey
0x18002f31b  lea     rax, [rbp+cbData]
0x18002f31f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002f324  lea     r9, [rbp+Type]; lpType
0x18002f328  lea     rax, MaxHostentCacheSize
0x18002f32f  xor     r8d, r8d; lpReserved
0x18002f332  lea     rdx, aMaxhostentcach; "MaxHostentCacheSize"
0x18002f339  mov     [rsp+30h+phkResult], rax; lpData
0x18002f33e  call    cs:__imp_RegQueryValueExW
0x18002f345  nop     dword ptr [rax+rax+00h]
0x18002f34a  mov     rcx, [rbp+hKey]; hKey
0x18002f34e  call    cs:__imp_RegCloseKey
0x18002f355  nop     dword ptr [rax+rax+00h]
0x18002f35a  add     rsp, 30h
0x18002f35e  pop     rbp
0x18002f35f  retn
```
