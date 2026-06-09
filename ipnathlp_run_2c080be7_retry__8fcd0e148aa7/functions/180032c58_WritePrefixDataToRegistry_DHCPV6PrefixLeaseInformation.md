# WritePrefixDataToRegistry(_DHCPV6PrefixLeaseInformation *)

- ea: `0x180032c58`
- end: `0x180032f5e`
- name: `?WritePrefixDataToRegistry@@YAKPEAU_DHCPV6PrefixLeaseInformation@@@Z`
- size: `774`
- prototype: `unsigned int __fastcall(BYTE *lpData)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000e0b0`
- `0x18006b29c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180032c58`
- `0x18003313c`
- `0x180051f30`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032d78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032db6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032de2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e38`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032eb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032ee0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032d78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032db6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032de2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e38`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e63`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032e8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032eb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180032ee0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032ef8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032ef8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032d21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180032d21`

## string_xrefs

- `0x180032ced`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
0x180032c58  mov     [rsp-8+arg_8], rbx
0x180032c5d  mov     [rsp-8+arg_10], rsi
0x180032c62  push    rbp
0x180032c63  push    rdi
0x180032c64  push    r15
0x180032c66  lea     rbp, [rsp-180h]
0x180032c6e  sub     rsp, 280h
0x180032c75  mov     rax, cs:__security_cookie
0x180032c7c  xor     rax, rsp
0x180032c7f  mov     [rbp+190h+var_20], rax
0x180032c86  mov     rdi, rcx
0x180032c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c90  lea     r15, WPP_GLOBAL_Control
0x180032c97  cmp     rcx, r15
0x180032c9a  jz      short loc_180032CBD
0x180032c9c  test    byte ptr [rcx+1Ch], 80h
0x180032ca0  jz      short loc_180032CBD
0x180032ca2  cmp     byte ptr [rcx+19h], 6
0x180032ca6  jb      short loc_180032CBD
0x180032ca8  mov     rcx, [rcx+10h]
0x180032cac  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x180032cb3  mov     edx, 10h
0x180032cb8  call    WPP_SF_
0x180032cbd  xor     edx, edx; Val
0x180032cbf  mov     [rsp+290h+hKey], 0
0x180032cc8  mov     r8d, 208h; Size
0x180032cce  mov     [rsp+290h+dwDisposition], 0
0x180032cd6  lea     rcx, [rsp+290h+ValueName]; void *
0x180032cdb  call    memset_0
0x180032ce0  lea     rax, [rsp+290h+dwDisposition]
0x180032ce5  xor     r9d, r9d; lpClass
0x180032ce8  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x180032ced  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x180032cf4  lea     rax, [rsp+290h+hKey]
0x180032cf9  xor     r8d, r8d; Reserved
0x180032cfc  mov     [rsp+290h+phkResult], rax; phkResult
0x180032d01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032d08  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180032d11  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x180032d19  mov     [rsp+290h+dwOptions], 0; dwOptions
0x180032d21  call    cs:__imp_RegCreateKeyExW
0x180032d28  nop     dword ptr [rax+rax+00h]
0x180032d2d  mov     ebx, eax
0x180032d2f  test    eax, eax
0x180032d31  jnz     loc_180032EEE
0x180032d37  mov     rsi, [rdi+8]
0x180032d3b  cmp     [rdi], eax
0x180032d3d  jbe     short loc_180032D8E
0x180032d3f  mov     r9d, ebx
0x180032d42  lea     r8, aIcsIpv6PrefixD; "ICS_IPv6_Prefix_%d"
0x180032d49  mov     edx, 104h; unsigned __int64
0x180032d4e  lea     rcx, [rsp+290h+ValueName]; unsigned __int16 *
0x180032d53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032d58  mov     rcx, [rsp+290h+hKey]; hKey
0x180032d5d  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x180032d62  mov     r9d, 3; dwType
0x180032d68  mov     [rsp+290h+samDesired], 20h ; ' '; cbData
0x180032d70  xor     r8d, r8d; Reserved
0x180032d73  mov     qword ptr [rsp+290h+dwOptions], rsi; lpData
0x180032d78  call    cs:__imp_RegSetValueExW
0x180032d7f  nop     dword ptr [rax+rax+00h]
0x180032d84  add     rsi, 20h ; ' '
0x180032d88  inc     ebx
0x180032d8a  cmp     ebx, [rdi]
0x180032d8c  jb      short loc_180032D3F
0x180032d8e  mov     rcx, [rsp+290h+hKey]; hKey
0x180032d93  lea     rbx, [rdi+48h]
0x180032d97  mov     eax, [rbx]
0x180032d99  lea     rdx, aIcsIpv6Dhcpv6s; "ICS_IPv6_Dhcpv6ServerID"
0x180032da0  mov     [rsp+290h+samDesired], eax; cbData
0x180032da4  mov     r9d, 3; dwType
0x180032daa  mov     rax, [rdi+40h]
0x180032dae  xor     r8d, r8d; Reserved
0x180032db1  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180032db6  call    cs:__imp_RegSetValueExW
0x180032dbd  nop     dword ptr [rax+rax+00h]
0x180032dc2  mov     rcx, [rsp+290h+hKey]; hKey
0x180032dc7  lea     rdx, aIcsIpv6Dhcpv6s_0; "ICS_IPv6_Dhcpv6ServerIDLen"
0x180032dce  mov     esi, 4
0x180032dd3  xor     r8d, r8d; Reserved
0x180032dd6  mov     [rsp+290h+samDesired], esi; cbData
0x180032dda  mov     r9d, esi; dwType
0x180032ddd  mov     qword ptr [rsp+290h+dwOptions], rbx; lpData
0x180032de2  call    cs:__imp_RegSetValueExW
0x180032de9  nop     dword ptr [rax+rax+00h]
0x180032dee  mov     rcx, [rsp+290h+hKey]; hKey
0x180032df3  lea     rax, [rdi+10h]
0x180032df7  mov     [rsp+290h+samDesired], esi; cbData
0x180032dfb  lea     rdx, aIcsIpv6Iaid; "ICS_IPv6_iaid"
0x180032e02  mov     r9d, esi; dwType
0x180032e05  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180032e0a  xor     r8d, r8d; Reserved
0x180032e0d  call    cs:__imp_RegSetValueExW
0x180032e14  nop     dword ptr [rax+rax+00h]
0x180032e19  mov     rcx, [rsp+290h+hKey]; hKey
0x180032e1e  lea     rax, [rdi+18h]
0x180032e22  mov     [rsp+290h+samDesired], esi; cbData
0x180032e26  lea     rdx, aIcsIpv6T1; "ICS_IPv6_T1"
0x180032e2d  mov     r9d, esi; dwType
0x180032e30  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180032e35  xor     r8d, r8d; Reserved
0x180032e38  call    cs:__imp_RegSetValueExW
0x180032e3f  nop     dword ptr [rax+rax+00h]
0x180032e44  mov     rcx, [rsp+290h+hKey]; hKey
0x180032e49  lea     rax, [rdi+20h]
0x180032e4d  mov     [rsp+290h+samDesired], esi; cbData
0x180032e51  lea     rdx, aIcsIpv6T2; "ICS_IPv6_T2"
0x180032e58  mov     r9d, esi; dwType
0x180032e5b  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180032e60  xor     r8d, r8d; Reserved
0x180032e63  call    cs:__imp_RegSetValueExW
0x180032e6a  nop     dword ptr [rax+rax+00h]
0x180032e6f  mov     rcx, [rsp+290h+hKey]; hKey
0x180032e74  lea     rax, [rdi+28h]
0x180032e78  mov     [rsp+290h+samDesired], esi; cbData
0x180032e7c  lea     rdx, aIcsIpv6Dhcpv6m; "ICS_IPv6_Dhcpv6MaxLeaseExpirationTime"
0x180032e83  mov     r9d, esi; dwType
0x180032e86  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180032e8b  xor     r8d, r8d; Reserved
0x180032e8e  call    cs:__imp_RegSetValueExW
0x180032e95  nop     dword ptr [rax+rax+00h]
0x180032e9a  mov     rcx, [rsp+290h+hKey]; hKey
0x180032e9f  lea     rax, [rdi+30h]
0x180032ea3  mov     [rsp+290h+samDesired], esi; cbData
0x180032ea7  lea     rdx, aIcsIpv6Dhcpv6l; "ICS_IPv6_Dhcpv6LastRenewalTime"
0x180032eae  mov     r9d, esi; dwType
0x180032eb1  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x180032eb6  xor     r8d, r8d; Reserved
0x180032eb9  call    cs:__imp_RegSetValueExW
0x180032ec0  nop     dword ptr [rax+rax+00h]
0x180032ec5  mov     rcx, [rsp+290h+hKey]; hKey
0x180032eca  lea     rdx, ValueName; "NumberOfPrefixes"
0x180032ed1  mov     r9d, esi; dwType
0x180032ed4  mov     [rsp+290h+samDesired], esi; cbData
0x180032ed8  xor     r8d, r8d; Reserved
0x180032edb  mov     qword ptr [rsp+290h+dwOptions], rdi; lpData
0x180032ee0  call    cs:__imp_RegSetValueExW
0x180032ee7  nop     dword ptr [rax+rax+00h]
0x180032eec  mov     ebx, eax
0x180032eee  mov     rcx, [rsp+290h+hKey]; hKey
0x180032ef3  test    rcx, rcx
0x180032ef6  jz      short loc_180032F04
0x180032ef8  call    cs:__imp_RegCloseKey
0x180032eff  nop     dword ptr [rax+rax+00h]
0x180032f04  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f0b  cmp     rcx, r15
0x180032f0e  jz      short loc_180032F34
0x180032f10  test    byte ptr [rcx+1Ch], 80h
0x180032f14  jz      short loc_180032F34
0x180032f16  cmp     byte ptr [rcx+19h], 6
0x180032f1a  jb      short loc_180032F34
0x180032f1c  mov     rcx, [rcx+10h]
0x180032f20  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x180032f27  mov     edx, 11h
0x180032f2c  mov     r9d, ebx
0x180032f2f  call    WPP_SF_d
0x180032f34  mov     eax, ebx
0x180032f36  mov     rcx, [rbp+190h+var_20]
0x180032f3d  xor     rcx, rsp; StackCookie
0x180032f40  call    __security_check_cookie
0x180032f45  lea     r11, [rsp+290h+var_10]
0x180032f4d  mov     rbx, [r11+28h]
0x180032f51  mov     rsi, [r11+30h]
0x180032f55  mov     rsp, r11
0x180032f58  pop     r15
0x180032f5a  pop     rdi
0x180032f5b  pop     rbp
0x180032f5c  retn
```
