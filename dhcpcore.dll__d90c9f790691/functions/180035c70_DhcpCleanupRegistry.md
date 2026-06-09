# DhcpCleanupRegistry

- ea: `0x180035c70`
- end: `0x180035eeb`
- name: `DhcpCleanupRegistry`
- size: `635`
- prototype: `int()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001c660`

## callees

- `0x1800057f0`
- `0x180007248`
- `0x18001cef0`
- `0x180035c70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ebb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035ebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035d8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035d8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035e7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035e7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035dbd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035dcf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035de1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035df3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035e17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035e29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035e3b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035dbd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035dcf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035de1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035df3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035e17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035e29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180035e3b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035d61`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180035d61`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180035d21`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180035d21`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180035e05`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180035e05`

## pseudocode

```c
int DhcpCleanupRegistry()
{
  void *v0; // rax
  __int64 v1; // rcx
  _QWORD *v2; // rax
  DWORD i; // ebx
  __int64 j; // rbx
  HKEY *v5; // rcx
  HKEY v6; // rcx
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-94h] BYREF
  void *v11; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[104]; // [rsp+80h] [rbp-80h] BYREF

  cSubKeys = 0;
  cchName = 0;
  phkResult = 0;
  while ( 1 )
  {
    v0 = DhcpGlobalOptionDefList;
    if ( DhcpGlobalOptionDefList == (_UNKNOWN *)&DhcpGlobalOptionDefList )
      break;
    if ( *((_UNKNOWN ***)DhcpGlobalOptionDefList + 1) != &DhcpGlobalOptionDefList
      || (v1 = *(_QWORD *)DhcpGlobalOptionDefList,
          *(_UNKNOWN **)(*(_QWORD *)DhcpGlobalOptionDefList + 8LL) != DhcpGlobalOptionDefList) )
    {
      __fastfail(3u);
    }
    DhcpGlobalOptionDefList = *(_UNKNOWN **)DhcpGlobalOptionDefList;
    *(_QWORD *)(v1 + 8) = &DhcpGlobalOptionDefList;
    v11 = v0;
    DhcpPunycodeFree(&v11);
  }
  LODWORD(v2) = RegQueryInfoKeyW(DhcpGlobalInterfacesKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 100;
    LODWORD(v2) = RegEnumKeyExW(DhcpGlobalInterfacesKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( !(_DWORD)v2 )
    {
      LODWORD(v2) = RegOpenKeyExW(DhcpGlobalInterfacesKey, Name, 0, 0x2001Bu, &phkResult);
      if ( !(_DWORD)v2 )
      {
        if ( !(unsigned int)DhcpV4IsEnabledDHCPRegistryValue(Name) )
        {
          RegDeleteValueW(phkResult, L"DhcpIPAddress");
          RegDeleteValueW(phkResult, L"DhcpSubnetMask");
          RegDeleteValueW(phkResult, L"DhcpDefaultGateway");
          RegDeleteValueW(phkResult, L"DhcpNameServer");
          RegDeleteValueA(phkResult, "DhcpDomainSearchList");
          RegDeleteValueW(phkResult, L"DhcpDomain");
          RegDeleteValueW(phkResult, L"DhcpSubnetMaskOpt");
          RegDeleteValueW(phkResult, L"DhcpIsMeteredDetected");
          wcscpy(Name, L"255.255.255.255");
          RegSetValueExW(phkResult, L"DhcpServer", 0, 1u, (const BYTE *)Name, 0x20u);
        }
        LODWORD(v2) = RegCloseKey(phkResult);
      }
    }
  }
  for ( j = 0; j != 4; ++j )
  {
    v5 = (HKEY *)off_180061110[2 * j];
    if ( v5 )
    {
      v6 = *v5;
      if ( v6 )
      {
        RegCloseKey(v6);
        v2 = (_QWORD *)off_180061110[2 * j];
        *v2 = 0;
      }
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x180035c70  push    rbp
0x180035c72  push    rbx
0x180035c73  push    rsi
0x180035c74  push    rdi
0x180035c75  push    r14
0x180035c77  lea     rbp, [rsp-60h]
0x180035c7c  sub     rsp, 160h
0x180035c83  mov     rax, cs:__security_cookie
0x180035c8a  xor     rax, rsp
0x180035c8d  mov     [rbp+80h+var_30], rax
0x180035c91  xor     esi, esi
0x180035c93  lea     rbx, DhcpGlobalOptionDefList
0x180035c9a  mov     [rsp+180h+cSubKeys], esi
0x180035c9e  mov     [rsp+180h+cchName], esi
0x180035ca2  mov     [rsp+180h+phkResult], rsi
0x180035ca7  mov     rax, cs:DhcpGlobalOptionDefList
0x180035cae  cmp     rax, rbx
0x180035cb1  jz      short loc_180035CE5
0x180035cb3  cmp     [rax+8], rbx
0x180035cb7  jnz     short loc_180035CDE
0x180035cb9  mov     rcx, [rax]
0x180035cbc  cmp     [rcx+8], rax
0x180035cc0  jnz     short loc_180035CDE
0x180035cc2  mov     cs:DhcpGlobalOptionDefList, rcx
0x180035cc9  mov     [rcx+8], rbx
0x180035ccd  lea     rcx, [rsp+180h+var_110]
0x180035cd2  mov     [rsp+180h+var_110], rax
0x180035cd7  call    DhcpPunycodeFree
0x180035cdc  jmp     short loc_180035CA7
0x180035cde  mov     ecx, 3
0x180035ce3  int     29h; Win8: RtlFailFast(ecx)
0x180035ce5  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x180035cec  lea     rax, [rsp+180h+cSubKeys]
0x180035cf1  mov     [rsp+180h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180035cf6  xor     r9d, r9d; lpReserved
0x180035cf9  mov     [rsp+180h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180035cfe  xor     r8d, r8d; lpcchClass
0x180035d01  mov     [rsp+180h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180035d06  xor     edx, edx; lpClass
0x180035d08  mov     [rsp+180h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180035d0d  mov     [rsp+180h+lpcValues], rsi; lpcValues
0x180035d12  mov     [rsp+180h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180035d17  mov     [rsp+180h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180035d1c  mov     [rsp+180h+lpcSubKeys], rax; lpcSubKeys
0x180035d21  call    cs:__imp_RegQueryInfoKeyW
0x180035d27  mov     ebx, esi
0x180035d29  cmp     [rsp+180h+cSubKeys], esi
0x180035d2d  jbe     loc_180035E9A
0x180035d33  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x180035d3a  lea     r9, [rsp+180h+cchName]; lpcchName
0x180035d3f  mov     [rsp+180h+lpcValues], rsi; lpftLastWriteTime
0x180035d44  lea     r8, [rbp+80h+Name]; lpName
0x180035d48  mov     [rsp+180h+lpcbMaxClassLen], rsi; lpcchClass
0x180035d4d  mov     edx, ebx; dwIndex
0x180035d4f  mov     [rsp+180h+lpcbMaxSubKeyLen], rsi; lpClass
0x180035d54  mov     [rsp+180h+lpcSubKeys], rsi; lpReserved
0x180035d59  mov     [rsp+180h+cchName], 64h ; 'd'
0x180035d61  call    cs:__imp_RegEnumKeyExW
0x180035d67  test    eax, eax
0x180035d69  jnz     loc_180035E8E
0x180035d6f  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x180035d76  lea     rax, [rsp+180h+phkResult]
0x180035d7b  mov     r9d, 2001Bh; samDesired
0x180035d81  mov     [rsp+180h+lpcSubKeys], rax; phkResult
0x180035d86  xor     r8d, r8d; ulOptions
0x180035d89  lea     rdx, [rbp+80h+Name]; lpSubKey
0x180035d8d  call    cs:__imp_RegOpenKeyExW
0x180035d93  test    eax, eax
0x180035d95  jnz     loc_180035E8E
0x180035d9b  lea     rdx, [rsp+180h+var_110]
0x180035da0  lea     rcx, [rbp+80h+Name]; LPCWSTR
0x180035da4  call    DhcpV4IsEnabledDHCPRegistryValue
0x180035da9  test    eax, eax
0x180035dab  jnz     loc_180035E83
0x180035db1  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035db6  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x180035dbd  call    cs:__imp_RegDeleteValueW
0x180035dc3  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035dc8  lea     rdx, aDhcpsubnetmask_0; "DhcpSubnetMask"
0x180035dcf  call    cs:__imp_RegDeleteValueW
0x180035dd5  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035dda  lea     rdx, aDhcpdefaultgat; "DhcpDefaultGateway"
0x180035de1  call    cs:__imp_RegDeleteValueW
0x180035de7  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035dec  lea     rdx, aDhcpnameserver; "DhcpNameServer"
0x180035df3  call    cs:__imp_RegDeleteValueW
0x180035df9  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035dfe  lea     rdx, aDhcpdomainsear; "DhcpDomainSearchList"
0x180035e05  call    cs:__imp_RegDeleteValueA
0x180035e0b  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035e10  lea     rdx, aDhcpdomain; "DhcpDomain"
0x180035e17  call    cs:__imp_RegDeleteValueW
0x180035e1d  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035e22  lea     rdx, aDhcpsubnetmask; "DhcpSubnetMaskOpt"
0x180035e29  call    cs:__imp_RegDeleteValueW
0x180035e2f  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035e34  lea     rdx, aDhcpismeteredd; "DhcpIsMeteredDetected"
0x180035e3b  call    cs:__imp_RegDeleteValueW
0x180035e41  movups  xmm0, xmmword ptr cs:a255255255255; "255.255.255.255"
0x180035e48  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035e4d  lea     rax, [rbp+80h+Name]
0x180035e51  movups  xmm1, xmmword ptr cs:a255255255255+10h; "255.255"
0x180035e58  mov     dword ptr [rsp+180h+lpcbMaxSubKeyLen], 20h ; ' '; cbData
0x180035e60  lea     rdx, aDhcpserver; "DhcpServer"
0x180035e67  mov     r9d, 1; dwType
0x180035e6d  movaps  xmmword ptr [rbp+80h+Name], xmm0
0x180035e71  xor     r8d, r8d; Reserved
0x180035e74  movaps  [rbp+80h+var_F0], xmm1
0x180035e78  mov     [rsp+180h+lpcSubKeys], rax; lpData
0x180035e7d  call    cs:__imp_RegSetValueExW
0x180035e83  mov     rcx, [rsp+180h+phkResult]; hKey
0x180035e88  call    cs:__imp_RegCloseKey
0x180035e8e  inc     ebx
0x180035e90  cmp     ebx, [rsp+180h+cSubKeys]
0x180035e94  jb      loc_180035D33
0x180035e9a  mov     rbx, rsi
0x180035e9d  mov     rdi, rbx
0x180035ea0  lea     r14, off_180061110
0x180035ea7  add     rdi, rdi
0x180035eaa  mov     rcx, [r14+rdi*8]
0x180035eae  test    rcx, rcx
0x180035eb1  jz      short loc_180035EC8
0x180035eb3  mov     rcx, [rcx]; hKey
0x180035eb6  test    rcx, rcx
0x180035eb9  jz      short loc_180035EC8
0x180035ebb  call    cs:__imp_RegCloseKey
0x180035ec1  mov     rax, [r14+rdi*8]
0x180035ec5  mov     [rax], rsi
0x180035ec8  inc     rbx
0x180035ecb  cmp     rbx, 4
0x180035ecf  jnz     short loc_180035E9D
0x180035ed1  mov     rcx, [rbp+80h+var_30]
0x180035ed5  xor     rcx, rsp; StackCookie
0x180035ed8  call    __security_check_cookie
0x180035edd  add     rsp, 160h
0x180035ee4  pop     r14
0x180035ee6  pop     rdi
0x180035ee7  pop     rsi
0x180035ee8  pop     rbx
0x180035ee9  pop     rbp
0x180035eea  retn
```
