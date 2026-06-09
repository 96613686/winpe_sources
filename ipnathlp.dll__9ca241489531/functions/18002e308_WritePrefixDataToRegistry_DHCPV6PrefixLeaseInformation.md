# WritePrefixDataToRegistry(_DHCPV6PrefixLeaseInformation *)

- ea: `0x18002e308`
- end: `0x18002e5cb`
- name: `?WritePrefixDataToRegistry@@YAKPEAU_DHCPV6PrefixLeaseInformation@@@Z`
- size: `707`
- prototype: `unsigned int __fastcall(BYTE *lpData)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000d6a0`
- `0x180066244`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18002e308`
- `0x18002e7a4`
- `0x18004e0c0`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e422`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e45a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e480`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e514`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e539`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e55a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e422`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e45a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e480`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4ef`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e514`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e539`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e55a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e56c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e56c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e3d1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e3d1`

## string_xrefs

- `0x18002e39d`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
__int64 __fastcall WritePrefixDataToRegistry(BYTE *lpData)
{
  unsigned int v2; // ebx
  const BYTE *v3; // rsi
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
  }
  hKey = 0;
  dwDisposition = 0;
  memset_0(ValueName, 0, 0x208u);
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &dwDisposition);
  if ( !v2 )
  {
    v3 = (const BYTE *)*((_QWORD *)lpData + 1);
    if ( *(_DWORD *)lpData )
    {
      do
      {
        StringCchPrintfW(ValueName, 0x104u, L"ICS_IPv6_Prefix_%d", v2);
        RegSetValueExW(hKey, ValueName, 0, 3u, v3, 0x20u);
        v3 += 32;
        ++v2;
      }
      while ( v2 < *(_DWORD *)lpData );
    }
    RegSetValueExW(hKey, L"ICS_IPv6_Dhcpv6ServerID", 0, 3u, *((const BYTE **)lpData + 8), *((_DWORD *)lpData + 18));
    RegSetValueExW(hKey, L"ICS_IPv6_Dhcpv6ServerIDLen", 0, 4u, lpData + 72, 4u);
    RegSetValueExW(hKey, L"ICS_IPv6_iaid", 0, 4u, lpData + 16, 4u);
    RegSetValueExW(hKey, L"ICS_IPv6_T1", 0, 4u, lpData + 24, 4u);
    RegSetValueExW(hKey, L"ICS_IPv6_T2", 0, 4u, lpData + 32, 4u);
    RegSetValueExW(hKey, L"ICS_IPv6_Dhcpv6MaxLeaseExpirationTime", 0, 4u, lpData + 40, 4u);
    RegSetValueExW(hKey, L"ICS_IPv6_Dhcpv6LastRenewalTime", 0, 4u, lpData + 48, 4u);
    v2 = RegSetValueExW(hKey, L"NumberOfPrefixes", 0, 4u, lpData, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b002d07646b635308a4693336a4759d4_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18002e308  mov     [rsp-8+arg_8], rbx
0x18002e30d  mov     [rsp-8+arg_10], rsi
0x18002e312  push    rbp
0x18002e313  push    rdi
0x18002e314  push    r15
0x18002e316  lea     rbp, [rsp-180h]
0x18002e31e  sub     rsp, 280h
0x18002e325  mov     rax, cs:__security_cookie
0x18002e32c  xor     rax, rsp
0x18002e32f  mov     [rbp+190h+var_20], rax
0x18002e336  mov     rdi, rcx
0x18002e339  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e340  lea     r15, WPP_GLOBAL_Control
0x18002e347  cmp     rcx, r15
0x18002e34a  jz      short loc_18002E36D
0x18002e34c  test    byte ptr [rcx+1Ch], 80h
0x18002e350  jz      short loc_18002E36D
0x18002e352  cmp     byte ptr [rcx+19h], 6
0x18002e356  jb      short loc_18002E36D
0x18002e358  mov     rcx, [rcx+10h]
0x18002e35c  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18002e363  mov     edx, 10h
0x18002e368  call    WPP_SF_
0x18002e36d  xor     edx, edx; Val
0x18002e36f  mov     [rsp+290h+hKey], 0
0x18002e378  mov     r8d, 208h; Size
0x18002e37e  mov     [rsp+290h+dwDisposition], 0
0x18002e386  lea     rcx, [rsp+290h+ValueName]; void *
0x18002e38b  call    memset_0
0x18002e390  lea     rax, [rsp+290h+dwDisposition]
0x18002e395  xor     r9d, r9d; lpClass
0x18002e398  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x18002e39d  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18002e3a4  lea     rax, [rsp+290h+hKey]
0x18002e3a9  xor     r8d, r8d; Reserved
0x18002e3ac  mov     [rsp+290h+phkResult], rax; phkResult
0x18002e3b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e3b8  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002e3c1  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18002e3c9  mov     [rsp+290h+dwOptions], 0; dwOptions
0x18002e3d1  call    cs:__imp_RegCreateKeyExW
0x18002e3d7  mov     ebx, eax
0x18002e3d9  test    eax, eax
0x18002e3db  jnz     loc_18002E562
0x18002e3e1  mov     rsi, [rdi+8]
0x18002e3e5  cmp     [rdi], eax
0x18002e3e7  jbe     short loc_18002E432
0x18002e3e9  mov     r9d, ebx
0x18002e3ec  lea     r8, aIcsIpv6PrefixD; "ICS_IPv6_Prefix_%d"
0x18002e3f3  mov     edx, 104h; unsigned __int64
0x18002e3f8  lea     rcx, [rsp+290h+ValueName]; unsigned __int16 *
0x18002e3fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002e402  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e407  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x18002e40c  mov     r9d, 3; dwType
0x18002e412  mov     [rsp+290h+samDesired], 20h ; ' '; cbData
0x18002e41a  xor     r8d, r8d; Reserved
0x18002e41d  mov     qword ptr [rsp+290h+dwOptions], rsi; lpData
0x18002e422  call    cs:__imp_RegSetValueExW
0x18002e428  add     rsi, 20h ; ' '
0x18002e42c  inc     ebx
0x18002e42e  cmp     ebx, [rdi]
0x18002e430  jb      short loc_18002E3E9
0x18002e432  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e437  lea     rbx, [rdi+48h]
0x18002e43b  mov     eax, [rbx]
0x18002e43d  lea     rdx, aIcsIpv6Dhcpv6s; "ICS_IPv6_Dhcpv6ServerID"
0x18002e444  mov     [rsp+290h+samDesired], eax; cbData
0x18002e448  mov     r9d, 3; dwType
0x18002e44e  mov     rax, [rdi+40h]
0x18002e452  xor     r8d, r8d; Reserved
0x18002e455  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18002e45a  call    cs:__imp_RegSetValueExW
0x18002e460  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e465  lea     rdx, aIcsIpv6Dhcpv6s_0; "ICS_IPv6_Dhcpv6ServerIDLen"
0x18002e46c  mov     esi, 4
0x18002e471  xor     r8d, r8d; Reserved
0x18002e474  mov     [rsp+290h+samDesired], esi; cbData
0x18002e478  mov     r9d, esi; dwType
0x18002e47b  mov     qword ptr [rsp+290h+dwOptions], rbx; lpData
0x18002e480  call    cs:__imp_RegSetValueExW
0x18002e486  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e48b  lea     rax, [rdi+10h]
0x18002e48f  mov     [rsp+290h+samDesired], esi; cbData
0x18002e493  lea     rdx, aIcsIpv6Iaid; "ICS_IPv6_iaid"
0x18002e49a  mov     r9d, esi; dwType
0x18002e49d  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18002e4a2  xor     r8d, r8d; Reserved
0x18002e4a5  call    cs:__imp_RegSetValueExW
0x18002e4ab  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e4b0  lea     rax, [rdi+18h]
0x18002e4b4  mov     [rsp+290h+samDesired], esi; cbData
0x18002e4b8  lea     rdx, aIcsIpv6T1; "ICS_IPv6_T1"
0x18002e4bf  mov     r9d, esi; dwType
0x18002e4c2  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18002e4c7  xor     r8d, r8d; Reserved
0x18002e4ca  call    cs:__imp_RegSetValueExW
0x18002e4d0  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e4d5  lea     rax, [rdi+20h]
0x18002e4d9  mov     [rsp+290h+samDesired], esi; cbData
0x18002e4dd  lea     rdx, aIcsIpv6T2; "ICS_IPv6_T2"
0x18002e4e4  mov     r9d, esi; dwType
0x18002e4e7  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18002e4ec  xor     r8d, r8d; Reserved
0x18002e4ef  call    cs:__imp_RegSetValueExW
0x18002e4f5  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e4fa  lea     rax, [rdi+28h]
0x18002e4fe  mov     [rsp+290h+samDesired], esi; cbData
0x18002e502  lea     rdx, aIcsIpv6Dhcpv6m; "ICS_IPv6_Dhcpv6MaxLeaseExpirationTime"
0x18002e509  mov     r9d, esi; dwType
0x18002e50c  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18002e511  xor     r8d, r8d; Reserved
0x18002e514  call    cs:__imp_RegSetValueExW
0x18002e51a  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e51f  lea     rax, [rdi+30h]
0x18002e523  mov     [rsp+290h+samDesired], esi; cbData
0x18002e527  lea     rdx, aIcsIpv6Dhcpv6l; "ICS_IPv6_Dhcpv6LastRenewalTime"
0x18002e52e  mov     r9d, esi; dwType
0x18002e531  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18002e536  xor     r8d, r8d; Reserved
0x18002e539  call    cs:__imp_RegSetValueExW
0x18002e53f  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e544  lea     rdx, ValueName; "NumberOfPrefixes"
0x18002e54b  mov     r9d, esi; dwType
0x18002e54e  mov     [rsp+290h+samDesired], esi; cbData
0x18002e552  xor     r8d, r8d; Reserved
0x18002e555  mov     qword ptr [rsp+290h+dwOptions], rdi; lpData
0x18002e55a  call    cs:__imp_RegSetValueExW
0x18002e560  mov     ebx, eax
0x18002e562  mov     rcx, [rsp+290h+hKey]; hKey
0x18002e567  test    rcx, rcx
0x18002e56a  jz      short loc_18002E572
0x18002e56c  call    cs:__imp_RegCloseKey
0x18002e572  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e579  cmp     rcx, r15
0x18002e57c  jz      short loc_18002E5A2
0x18002e57e  test    byte ptr [rcx+1Ch], 80h
0x18002e582  jz      short loc_18002E5A2
0x18002e584  cmp     byte ptr [rcx+19h], 6
0x18002e588  jb      short loc_18002E5A2
0x18002e58a  mov     rcx, [rcx+10h]
0x18002e58e  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18002e595  mov     edx, 11h
0x18002e59a  mov     r9d, ebx
0x18002e59d  call    WPP_SF_d
0x18002e5a2  mov     eax, ebx
0x18002e5a4  mov     rcx, [rbp+190h+var_20]
0x18002e5ab  xor     rcx, rsp; StackCookie
0x18002e5ae  call    __security_check_cookie
0x18002e5b3  lea     r11, [rsp+290h+var_10]
0x18002e5bb  mov     rbx, [r11+28h]
0x18002e5bf  mov     rsi, [r11+30h]
0x18002e5c3  mov     rsp, r11
0x18002e5c6  pop     r15
0x18002e5c8  pop     rdi
0x18002e5c9  pop     rbp
0x18002e5ca  retn
```
