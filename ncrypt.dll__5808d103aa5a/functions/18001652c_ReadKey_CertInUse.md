# ReadKey_CertInUse

- ea: `0x18001652c`
- end: `0x18001661a`
- name: `ReadKey_CertInUse`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019608`
- `0x18001e970`

## callees

- `0x18001652c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800165b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800165f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800165b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800165f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016571`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001660d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001660d`

## string_xrefs

- `0x1800165a8`: `ClientSideEventThrottlingMinutes`

## pseudocode

```c
LSTATUS ReadKey_CertInUse()
{
  int v0; // ebx
  LSTATUS result; // eax
  int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  cbData = 4;
  Type = 4;
  v0 = 3600000;
  Data = 3600000;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\CertInUse",
             0,
             1u,
             &hKey);
  if ( result )
  {
    g_dwClientSideEventThrottlingMilliseconds = 3600000;
    *(_DWORD *)&g_dwClientEnabled = 0;
  }
  else
  {
    if ( !RegQueryValueExW(hKey, L"ClientSideEventThrottlingMinutes", 0, &Type, (LPBYTE)&Data, &cbData) )
      v0 = 60000 * Data;
    Data = v0;
    g_dwClientSideEventThrottlingMilliseconds = v0;
    if ( RegQueryValueExW(hKey, L"ClientEnable", 0, &Type, &g_dwClientEnabled, &cbData) )
      *(_DWORD *)&g_dwClientEnabled = 0;
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18001652c  push    rbp
0x18001652e  push    rbx
0x18001652f  mov     rbp, rsp
0x180016532  sub     rsp, 38h
0x180016536  mov     eax, 4
0x18001653b  mov     [rbp+hKey], 0
0x180016543  mov     [rbp+cbData], eax
0x180016546  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18001654d  mov     [rbp+Type], eax
0x180016550  mov     ebx, 36EE80h
0x180016555  lea     rax, [rbp+hKey]
0x180016559  mov     [rbp+Data], ebx
0x18001655c  mov     r9d, 1; samDesired
0x180016562  mov     [rsp+38h+phkResult], rax; phkResult
0x180016567  xor     r8d, r8d; ulOptions
0x18001656a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016571  call    cs:__imp_RegOpenKeyExW
0x180016577  test    eax, eax
0x180016579  jz      short loc_180016590
0x18001657b  mov     cs:g_dwClientSideEventThrottlingMilliseconds, ebx
0x180016581  mov     cs:g_dwClientEnabled, 0
0x18001658b  jmp     loc_180016613
0x180016590  mov     rcx, [rbp+hKey]; hKey
0x180016594  lea     rax, [rbp+cbData]
0x180016598  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18001659d  lea     r9, [rbp+Type]; lpType
0x1800165a1  lea     rax, [rbp+Data]
0x1800165a5  xor     r8d, r8d; lpReserved
0x1800165a8  lea     rdx, ValueName; "ClientSideEventThrottlingMinutes"
0x1800165af  mov     [rsp+38h+phkResult], rax; lpData
0x1800165b4  call    cs:__imp_RegQueryValueExW
0x1800165ba  test    eax, eax
0x1800165bc  jnz     short loc_1800165C5
0x1800165be  imul    ebx, [rbp+Data], 0EA60h
0x1800165c5  mov     rcx, [rbp+hKey]; hKey
0x1800165c9  lea     rax, [rbp+cbData]
0x1800165cd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800165d2  lea     r9, [rbp+Type]; lpType
0x1800165d6  lea     rax, g_dwClientEnabled
0x1800165dd  mov     [rbp+Data], ebx
0x1800165e0  xor     r8d, r8d; lpReserved
0x1800165e3  mov     [rsp+38h+phkResult], rax; lpData
0x1800165e8  lea     rdx, aClientenable; "ClientEnable"
0x1800165ef  mov     cs:g_dwClientSideEventThrottlingMilliseconds, ebx
0x1800165f5  call    cs:__imp_RegQueryValueExW
0x1800165fb  test    eax, eax
0x1800165fd  jz      short loc_180016609
0x1800165ff  mov     cs:g_dwClientEnabled, 0
0x180016609  mov     rcx, [rbp+hKey]; hKey
0x18001660d  call    cs:__imp_RegCloseKey
0x180016613  add     rsp, 38h
0x180016617  pop     rbx
0x180016618  pop     rbp
0x180016619  retn
```
