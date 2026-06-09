# SockGetProviderId

- ea: `0x180010e2c`
- end: `0x180010f43`
- name: `SockGetProviderId`
- size: `279`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPBYTE lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000b3a0`
- `0x180010680`

## callees

- `0x180010e2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010ee8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010ee8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010e82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010eaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010e82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010eaf`

## string_xrefs

- `0x180010e5e`: `SYSTEM\CurrentControlSet\Services\Winsock\Setup Migration\Providers`

## pseudocode

```c
LSTATUS __fastcall SockGetProviderId(LPCWSTR lpSubKey, LPBYTE lpData)
{
  LSTATUS result; // eax
  LSTATUS v5; // ebx
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  phkResult = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\Winsock\\Setup Migration\\Providers",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    v5 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
    if ( !v5 )
    {
      cbData = 16;
      v5 = RegQueryValueExW(phkResult, L"WinSock 2.0 Provider ID", 0, &Type, lpData, &cbData);
      if ( !v5 && Type != 3 )
        v5 = 1804;
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180010e2c  mov     [rsp-8+arg_0], rbx
0x180010e31  mov     [rsp-8+arg_8], rdi
0x180010e36  push    rbp
0x180010e37  mov     rbp, rsp
0x180010e3a  sub     rsp, 40h
0x180010e3e  mov     rdi, rdx
0x180010e41  mov     [rbp+cbData], 0
0x180010e48  mov     rbx, rcx
0x180010e4b  mov     [rbp+Type], 0
0x180010e52  lea     rax, [rbp+hKey]
0x180010e56  mov     [rbp+hKey], 0
0x180010e5e  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Wi"...
0x180010e65  mov     [rsp+40h+phkResult], rax; phkResult
0x180010e6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010e71  mov     [rbp+var_10], 0
0x180010e79  mov     r9d, 20019h; samDesired
0x180010e7f  xor     r8d, r8d; ulOptions
0x180010e82  call    cs:__imp_RegOpenKeyExW
0x180010e89  nop     dword ptr [rax+rax+00h]
0x180010e8e  test    eax, eax
0x180010e90  jnz     loc_180010F32
0x180010e96  mov     rcx, [rbp+hKey]; hKey
0x180010e9a  lea     rax, [rbp+var_10]
0x180010e9e  mov     r9d, 20019h; samDesired
0x180010ea4  mov     [rsp+40h+phkResult], rax; phkResult
0x180010ea9  xor     r8d, r8d; ulOptions
0x180010eac  mov     rdx, rbx; lpSubKey
0x180010eaf  call    cs:__imp_RegOpenKeyExW
0x180010eb6  nop     dword ptr [rax+rax+00h]
0x180010ebb  mov     ebx, eax
0x180010ebd  test    eax, eax
0x180010ebf  jnz     short loc_180010F06
0x180010ec1  mov     rcx, [rbp+var_10]; hKey
0x180010ec5  lea     rax, [rbp+cbData]
0x180010ec9  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180010ece  lea     r9, [rbp+Type]; lpType
0x180010ed2  xor     r8d, r8d; lpReserved
0x180010ed5  mov     [rsp+40h+phkResult], rdi; lpData
0x180010eda  lea     rdx, aWinsock20Provi; "WinSock 2.0 Provider ID"
0x180010ee1  mov     [rbp+cbData], 10h
0x180010ee8  call    cs:__imp_RegQueryValueExW
0x180010eef  nop     dword ptr [rax+rax+00h]
0x180010ef4  mov     ebx, eax
0x180010ef6  test    eax, eax
0x180010ef8  jnz     short loc_180010F06
0x180010efa  cmp     [rbp+Type], 3
0x180010efe  mov     eax, 70Ch
0x180010f03  cmovnz  ebx, eax
0x180010f06  mov     rcx, [rbp+var_10]; hKey
0x180010f0a  test    rcx, rcx
0x180010f0d  jz      short loc_180010F1B
0x180010f0f  call    cs:__imp_RegCloseKey
0x180010f16  nop     dword ptr [rax+rax+00h]
0x180010f1b  mov     rcx, [rbp+hKey]; hKey
0x180010f1f  test    rcx, rcx
0x180010f22  jz      short loc_180010F30
0x180010f24  call    cs:__imp_RegCloseKey
0x180010f2b  nop     dword ptr [rax+rax+00h]
0x180010f30  mov     eax, ebx
0x180010f32  mov     rbx, [rsp+40h+arg_0]
0x180010f37  mov     rdi, [rsp+40h+arg_8]
0x180010f3c  add     rsp, 40h
0x180010f40  pop     rbp
0x180010f41  retn
```
