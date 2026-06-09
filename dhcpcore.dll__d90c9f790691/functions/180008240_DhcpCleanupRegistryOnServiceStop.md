# DhcpCleanupRegistryOnServiceStop

- ea: `0x180008240`
- end: `0x1800083b2`
- name: `DhcpCleanupRegistryOnServiceStop`
- size: `370`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001c660`

## callees

- `0x1800069d0`
- `0x18000761c`
- `0x180008240`
- `0x18001bcac`
- `0x18001cef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000836b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000836b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008318`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008318`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008360`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000838b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008360`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000838b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800082f0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800082f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800082b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800082b0`

## string_xrefs

- `0x180008344`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
LSTATUS DhcpCleanupRegistryOnServiceStop()
{
  DWORD i; // ebx
  __int64 v1; // rdx
  __int64 v2; // rcx
  int EnabledDhcpFromMultipleLocations; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v7[8]; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[104]; // [rsp+80h] [rbp-80h] BYREF

  cSubKeys = 0;
  cchName = 0;
  phkResult = 0;
  RegQueryInfoKeyW(DhcpGlobalInterfacesKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 100;
    if ( !RegEnumKeyExW(DhcpGlobalInterfacesKey, i, Name, &cchName, 0, 0, 0, 0)
      && !RegOpenKeyExW(DhcpGlobalInterfacesKey, Name, 0, 0x2001Bu, &phkResult) )
    {
      if ( (unsigned int)DhcpIsWCOSSystem() )
        EnabledDhcpFromMultipleLocations = DhcpRegReadEnabledDhcpFromMultipleLocations(v2, v1, Name, v7);
      else
        EnabledDhcpFromMultipleLocations = DhcpRegReadEnabledDhcp(
                                             L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
                                             Name);
      if ( !EnabledDhcpFromMultipleLocations )
        RegDeleteValueW(phkResult, L"SoHRequest");
      RegCloseKey(phkResult);
    }
  }
  return RegDeleteValueW(DhcpGlobalTcpipParametersKey, L"SoHRequest");
}

```

## disassembly

```asm
0x180008240  mov     [rsp-8+arg_0], rbx
0x180008245  mov     [rsp-8+arg_8], rdi
0x18000824a  push    rbp
0x18000824b  lea     rbp, [rsp-60h]
0x180008250  sub     rsp, 160h
0x180008257  mov     rax, cs:__security_cookie
0x18000825e  xor     rax, rsp
0x180008261  mov     [rbp+60h+var_10], rax
0x180008265  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x18000826c  lea     rax, [rsp+160h+cSubKeys]
0x180008271  xor     edi, edi
0x180008273  xor     r9d, r9d; lpReserved
0x180008276  mov     [rsp+160h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18000827b  xor     r8d, r8d; lpcchClass
0x18000827e  mov     [rsp+160h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180008283  xor     edx, edx; lpClass
0x180008285  mov     [rsp+160h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18000828a  mov     [rsp+160h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18000828f  mov     [rsp+160h+lpcValues], rdi; lpcValues
0x180008294  mov     [rsp+160h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180008299  mov     [rsp+160h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x18000829e  mov     [rsp+160h+lpcSubKeys], rax; lpcSubKeys
0x1800082a3  mov     [rsp+160h+cSubKeys], edi
0x1800082a7  mov     [rsp+160h+cchName], edi
0x1800082ab  mov     [rsp+160h+phkResult], rdi
0x1800082b0  call    cs:__imp_RegQueryInfoKeyW
0x1800082b6  mov     ebx, edi
0x1800082b8  cmp     [rsp+160h+cSubKeys], edi
0x1800082bc  jbe     loc_18000837D
0x1800082c2  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x1800082c9  lea     r9, [rsp+160h+cchName]; lpcchName
0x1800082ce  mov     [rsp+160h+lpcValues], rdi; lpftLastWriteTime
0x1800082d3  lea     r8, [rbp+60h+Name]; lpName
0x1800082d7  mov     [rsp+160h+lpcbMaxClassLen], rdi; lpcchClass
0x1800082dc  mov     edx, ebx; dwIndex
0x1800082de  mov     [rsp+160h+lpcbMaxSubKeyLen], rdi; lpClass
0x1800082e3  mov     [rsp+160h+lpcSubKeys], rdi; lpReserved
0x1800082e8  mov     [rsp+160h+cchName], 64h ; 'd'
0x1800082f0  call    cs:__imp_RegEnumKeyExW
0x1800082f6  test    eax, eax
0x1800082f8  jnz     short loc_180008371
0x1800082fa  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x180008301  lea     rax, [rsp+160h+phkResult]
0x180008306  mov     r9d, 2001Bh; samDesired
0x18000830c  mov     [rsp+160h+lpcSubKeys], rax; phkResult
0x180008311  xor     r8d, r8d; ulOptions
0x180008314  lea     rdx, [rbp+60h+Name]; lpSubKey
0x180008318  call    cs:__imp_RegOpenKeyExW
0x18000831e  test    eax, eax
0x180008320  jnz     short loc_180008371
0x180008322  call    DhcpIsWCOSSystem
0x180008327  test    eax, eax
0x180008329  jz      short loc_18000833B
0x18000832b  lea     r9, [rsp+160h+var_F8]
0x180008330  lea     r8, [rbp+60h+Name]
0x180008334  call    DhcpRegReadEnabledDhcpFromMultipleLocations
0x180008339  jmp     short loc_180008350
0x18000833b  lea     r8, [rsp+160h+var_F8]
0x180008340  lea     rdx, [rbp+60h+Name]; LPCWSTR
0x180008344  lea     rcx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Tc"...
0x18000834b  call    DhcpRegReadEnabledDhcp
0x180008350  test    eax, eax
0x180008352  jnz     short loc_180008366
0x180008354  mov     rcx, [rsp+160h+phkResult]; hKey
0x180008359  lea     rdx, aSohrequest; "SoHRequest"
0x180008360  call    cs:__imp_RegDeleteValueW
0x180008366  mov     rcx, [rsp+160h+phkResult]; hKey
0x18000836b  call    cs:__imp_RegCloseKey
0x180008371  inc     ebx
0x180008373  cmp     ebx, [rsp+160h+cSubKeys]
0x180008377  jb      loc_1800082C2
0x18000837d  mov     rcx, cs:DhcpGlobalTcpipParametersKey; hKey
0x180008384  lea     rdx, aSohrequest; "SoHRequest"
0x18000838b  call    cs:__imp_RegDeleteValueW
0x180008391  mov     rcx, [rbp+60h+var_10]
0x180008395  xor     rcx, rsp; StackCookie
0x180008398  call    __security_check_cookie
0x18000839d  lea     r11, [rsp+160h+var_s0]
0x1800083a5  mov     rbx, [r11+10h]
0x1800083a9  mov     rdi, [r11+18h]
0x1800083ad  mov     rsp, r11
0x1800083b0  pop     rbp
0x1800083b1  retn
```
