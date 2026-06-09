# ProvAgent::InUpgrade(void)

- ea: `0x18002a858`
- end: `0x18002a909`
- name: `?InUpgrade@ProvAgent@@SA_NXZ`
- size: `177`
- prototype: `char(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000f8d0`
- `0x180010b40`

## callees

- `0x18002a858`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a8e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a8fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a8e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a8fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a886`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a886`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a8cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a8cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char ProvAgent::InUpgrade(void)
{
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, 0x20019u, &hkey)
    || (pvData = 0, pcbData = 4, RegGetValueW(hkey, 0, L"Upgrade", 0x10u, 0, &pvData, &pcbData))
    || pvData != 1 )
  {
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  else
  {
    if ( hkey )
      RegCloseKey(hkey);
    return 1;
  }
}

```

## disassembly

```asm
0x18002a858  sub     rsp, 48h
0x18002a85c  lea     rax, [rsp+48h+hkey]
0x18002a861  mov     [rsp+48h+hkey], 0
0x18002a86a  mov     r9d, 20019h; samDesired
0x18002a870  mov     [rsp+48h+phkResult], rax; phkResult
0x18002a875  xor     r8d, r8d; ulOptions
0x18002a878  lea     rdx, ?c_provUpgradePath@@3QBGB; "System\\Setup"
0x18002a87f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a886  call    cs:__imp_RegOpenKeyExW
0x18002a88c  test    eax, eax
0x18002a88e  jnz     short loc_18002A8F2
0x18002a890  mov     rcx, [rsp+48h+hkey]; hkey
0x18002a895  lea     r8, ?c_provUpgrade@@3QBGB; "Upgrade"
0x18002a89c  mov     [rsp+48h+arg_0], eax
0x18002a8a0  mov     r9d, 10h; dwFlags
0x18002a8a6  lea     rax, [rsp+48h+arg_8]
0x18002a8ab  mov     [rsp+48h+arg_8], 4
0x18002a8b3  mov     [rsp+48h+pcbData], rax; pcbData
0x18002a8b8  xor     edx, edx; lpSubKey
0x18002a8ba  lea     rax, [rsp+48h+arg_0]
0x18002a8bf  mov     [rsp+48h+pvData], rax; pvData
0x18002a8c4  mov     [rsp+48h+phkResult], 0; pdwType
0x18002a8cd  call    cs:__imp_RegGetValueW
0x18002a8d3  test    eax, eax
0x18002a8d5  jnz     short loc_18002A8F2
0x18002a8d7  cmp     [rsp+48h+arg_0], 1
0x18002a8dc  jnz     short loc_18002A8F2
0x18002a8de  mov     rcx, [rsp+48h+hkey]; hKey
0x18002a8e3  test    rcx, rcx
0x18002a8e6  jz      short loc_18002A8EE
0x18002a8e8  call    cs:__imp_RegCloseKey
0x18002a8ee  mov     al, 1
0x18002a8f0  jmp     short loc_18002A904
0x18002a8f2  mov     rcx, [rsp+48h+hkey]; hKey
0x18002a8f7  test    rcx, rcx
0x18002a8fa  jz      short loc_18002A902
0x18002a8fc  call    cs:__imp_RegCloseKey
0x18002a902  xor     al, al
0x18002a904  add     rsp, 48h
0x18002a908  retn
```
