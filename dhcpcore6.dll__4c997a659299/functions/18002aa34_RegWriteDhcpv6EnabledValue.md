# RegWriteDhcpv6EnabledValue

- ea: `0x18002aa34`
- end: `0x18002ab6c`
- name: `RegWriteDhcpv6EnabledValue`
- size: `312`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001be30`

## callees

- `0x180009f58`
- `0x18002aa34`
- `0x1800338c0`
- `0x180033a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aab5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aab5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab2c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002aae9`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002aae9`

## string_xrefs

- `0x18002aa89`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall RegWriteDhcpv6EnabledValue(LPCWSTR lpSubKey, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  unsigned int v5; // ebx
  int IsWCOSSystem; // eax
  const WCHAR *v7; // rdx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  v3 = (unsigned int)a2;
  if ( !lpSubKey )
  {
    v5 = 87;
LABEL_14:
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 107, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v5);
    return v5;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_DS(1028, 105, (unsigned int)WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, a2, (__int64)lpSubKey);
  IsWCOSSystem = DhcpIsWCOSSystem(lpSubKey, a2, a3, v3);
  v7 = L"OSDATA\\Networking\\Dhcp\\Client6";
  if ( !IsWCOSSystem )
    v7 = L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces";
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 2u, &hKey);
  if ( !v5 )
  {
    v5 = RegSetKeyValueW(hKey, lpSubKey, L"EnableDhcp", 4u, &Data, 4u);
    if ( !v5 && (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_DS(1028, 106, (unsigned int)WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, Data, (__int64)lpSubKey);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    goto LABEL_14;
  return v5;
}

```

## disassembly

```asm
0x18002aa34  mov     [rsp+arg_10], rbx
0x18002aa39  mov     [rsp+Data], edx
0x18002aa3d  push    rdi
0x18002aa3e  sub     rsp, 30h
0x18002aa42  mov     [rsp+38h+hKey], 0
0x18002aa4b  mov     r9d, edx
0x18002aa4e  mov     rdi, rcx
0x18002aa51  test    rcx, rcx
0x18002aa54  jnz     short loc_18002AA5E
0x18002aa56  lea     ebx, [rcx+57h]
0x18002aa59  jmp     loc_18002AB3C
0x18002aa5e  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002aa65  jz      short loc_18002AA82
0x18002aa67  mov     edx, 69h ; 'i'
0x18002aa6c  mov     [rsp+38h+phkResult], rdi
0x18002aa71  mov     ecx, 404h
0x18002aa76  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002aa7d  call    WPP_SF_DS
0x18002aa82  call    DhcpIsWCOSSystem
0x18002aa87  test    eax, eax
0x18002aa89  lea     rcx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Tc"...
0x18002aa90  lea     rax, [rsp+38h+hKey]
0x18002aa95  mov     r9d, 2; samDesired
0x18002aa9b  lea     rdx, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client6"
0x18002aaa2  mov     [rsp+38h+phkResult], rax; phkResult
0x18002aaa7  cmovz   rdx, rcx; lpSubKey
0x18002aaab  xor     r8d, r8d; ulOptions
0x18002aaae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002aab5  call    cs:__imp_RegOpenKeyExW
0x18002aabc  nop     dword ptr [rax+rax+00h]
0x18002aac1  mov     ebx, eax
0x18002aac3  test    eax, eax
0x18002aac5  jnz     short loc_18002AB22
0x18002aac7  mov     rcx, [rsp+38h+hKey]; hKey
0x18002aacc  lea     r9d, [rax+4]; dwType
0x18002aad0  lea     rax, [rsp+38h+Data]
0x18002aad5  mov     [rsp+38h+cbData], r9d; cbData
0x18002aada  lea     r8, aEnabledhcp; "EnableDhcp"
0x18002aae1  mov     [rsp+38h+phkResult], rax; lpData
0x18002aae6  mov     rdx, rdi; lpSubKey
0x18002aae9  call    cs:__imp_RegSetKeyValueW
0x18002aaf0  nop     dword ptr [rax+rax+00h]
0x18002aaf5  mov     ebx, eax
0x18002aaf7  test    eax, eax
0x18002aaf9  jnz     short loc_18002AB22
0x18002aafb  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002ab02  jz      short loc_18002AB22
0x18002ab04  mov     r9d, [rsp+38h+Data]
0x18002ab09  lea     edx, [rax+6Ah]
0x18002ab0c  mov     ecx, 404h
0x18002ab11  mov     [rsp+38h+phkResult], rdi
0x18002ab16  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002ab1d  call    WPP_SF_DS
0x18002ab22  mov     rcx, [rsp+38h+hKey]; hKey
0x18002ab27  test    rcx, rcx
0x18002ab2a  jz      short loc_18002AB38
0x18002ab2c  call    cs:__imp_RegCloseKey
0x18002ab33  nop     dword ptr [rax+rax+00h]
0x18002ab38  test    ebx, ebx
0x18002ab3a  jz      short loc_18002AB5E
0x18002ab3c  test    byte ptr cs:xmmword_1800423E0, 2
0x18002ab43  jz      short loc_18002AB5E
0x18002ab45  mov     edx, 6Bh ; 'k'
0x18002ab4a  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18002ab51  mov     ecx, 401h
0x18002ab56  mov     r9d, ebx
0x18002ab59  call    WPP_SF_D
0x18002ab5e  mov     eax, ebx
0x18002ab60  mov     rbx, [rsp+38h+arg_10]
0x18002ab65  add     rsp, 30h
0x18002ab69  pop     rdi
0x18002ab6a  retn
```
