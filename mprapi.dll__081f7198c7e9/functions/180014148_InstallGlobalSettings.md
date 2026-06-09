# InstallGlobalSettings

- ea: `0x180014148`
- end: `0x180014248`
- name: `InstallGlobalSettings`
- size: `256`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180026b90`

## callees

- `0x180014148`
- `0x180016608`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001422a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001422a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800141c0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800141ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014218`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800141c0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800141ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014218`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001418a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001418a`

## string_xrefs

- `0x180014177`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 InstallGlobalSettings()
{
  unsigned int v0; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  int v3; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v3 = 1;
  Data = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters", 0, 0x20006u, &hKey) )
  {
    v0 = 0;
  }
  else
  {
    v0 = RegSetValueExW(hKey, L"EnableICMPRedirect", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v0 )
    {
      v0 = RegSetValueExW(hKey, L"DeadGWDetectDefault", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v0 )
        v0 = RegSetValueExW(hKey, L"DontAddDefaultGatewayDefault", 0, 4u, (const BYTE *)&v3, 4u);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v0 )
    return (unsigned int)SetPerInterfaceRegistrySettings();
  return v0;
}

```

## disassembly

```asm
0x180014148  mov     rax, rsp
0x18001414b  mov     [rax+20h], rbx
0x18001414f  push    rdi
0x180014150  sub     rsp, 30h
0x180014154  mov     dword ptr [rax+10h], 1
0x18001415b  mov     r9d, 20006h; samDesired
0x180014161  mov     dword ptr [rax+8], 0
0x180014168  xor     r8d, r8d; ulOptions
0x18001416b  mov     qword ptr [rax+18h], 0
0x180014173  lea     rax, [rax+18h]
0x180014177  lea     rdx, c_szRegKeyTcpipParameters; "System\\CurrentControlSet\\Services\\Tc"...
0x18001417e  mov     [rsp+38h+phkResult], rax; phkResult
0x180014183  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001418a  call    cs:__imp_RegOpenKeyExW
0x180014190  test    eax, eax
0x180014192  jz      short loc_18001419B
0x180014194  xor     ebx, ebx
0x180014196  jmp     loc_180014220
0x18001419b  mov     rcx, [rsp+38h+hKey]; hKey
0x1800141a0  lea     rax, [rsp+38h+Data]
0x1800141a5  mov     edi, 4
0x1800141aa  lea     rdx, c_szRegValEnableICMPRedirect; "EnableICMPRedirect"
0x1800141b1  mov     [rsp+38h+cbData], edi; cbData
0x1800141b5  mov     r9d, edi; dwType
0x1800141b8  xor     r8d, r8d; Reserved
0x1800141bb  mov     [rsp+38h+phkResult], rax; lpData
0x1800141c0  call    cs:__imp_RegSetValueExW
0x1800141c6  mov     ebx, eax
0x1800141c8  test    eax, eax
0x1800141ca  jnz     short loc_180014220
0x1800141cc  mov     rcx, [rsp+38h+hKey]; hKey
0x1800141d1  lea     rax, [rsp+38h+Data]
0x1800141d6  mov     [rsp+38h+cbData], edi; cbData
0x1800141da  lea     rdx, c_szRegValDeadGWDetectDefault; "DeadGWDetectDefault"
0x1800141e1  mov     r9d, edi; dwType
0x1800141e4  mov     [rsp+38h+phkResult], rax; lpData
0x1800141e9  xor     r8d, r8d; Reserved
0x1800141ec  call    cs:__imp_RegSetValueExW
0x1800141f2  mov     ebx, eax
0x1800141f4  test    eax, eax
0x1800141f6  jnz     short loc_180014220
0x1800141f8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800141fd  lea     rax, [rsp+38h+arg_8]
0x180014202  mov     [rsp+38h+cbData], edi; cbData
0x180014206  lea     rdx, c_szRegValDontAddDefaultGatewayDefault; "DontAddDefaultGatewayDefault"
0x18001420d  mov     r9d, edi; dwType
0x180014210  mov     [rsp+38h+phkResult], rax; lpData
0x180014215  xor     r8d, r8d; Reserved
0x180014218  call    cs:__imp_RegSetValueExW
0x18001421e  mov     ebx, eax
0x180014220  mov     rcx, [rsp+38h+hKey]; hKey
0x180014225  test    rcx, rcx
0x180014228  jz      short loc_180014230
0x18001422a  call    cs:__imp_RegCloseKey
0x180014230  test    ebx, ebx
0x180014232  jnz     short loc_18001423B
0x180014234  call    SetPerInterfaceRegistrySettings
0x180014239  mov     ebx, eax
0x18001423b  mov     eax, ebx
0x18001423d  mov     rbx, [rsp+38h+arg_18]
0x180014242  add     rsp, 30h
0x180014246  pop     rdi
0x180014247  retn
```
