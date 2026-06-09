# DeleteICSRegKeys(void)

- ea: `0x18006d22c`
- end: `0x18006d54a`
- name: `?DeleteICSRegKeys@@YAXXZ`
- size: `798`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18006aab8`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003313c`
- `0x180051f30`
- `0x180052bf4`
- `0x18006d22c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006d39f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006d39f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d3de`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d3fe`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d416`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d42e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d446`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d45e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d476`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d48e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d4a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d4be`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d4d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d3de`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d3fe`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d416`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d42e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d446`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d45e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d476`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d48e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d4a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d4be`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006d4d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d4ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006d4ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d2ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006d2ff`

## string_xrefs

- `0x18006d2cb`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

## pseudocode

```c
void DeleteICSRegKeys(void)
{
  unsigned int v0; // eax
  PVOID *v1; // rcx
  __int64 v2; // rdx
  unsigned int i; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
  }
  *(_DWORD *)Data = 0;
  cbData = 0;
  dwDisposition[0] = 0;
  hKey = 0;
  memset_0(ValueName, 0, 0x208u);
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         dwDisposition);
  if ( v0 )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_b002d07646b635308a4693336a4759d4_Traceguids, v0);
        v1 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v1 != &WPP_GLOBAL_Control && *((char *)v1 + 28) < 0 && *((_BYTE *)v1 + 25) >= 6u )
      {
        v2 = 26;
LABEL_24:
        WPP_SF_(v1[2], v2, WPP_b002d07646b635308a4693336a4759d4_Traceguids);
      }
    }
  }
  else
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"NumberOfPrefixes", 0, 0, Data, &cbData) )
    {
      for ( i = 0; i < *(_DWORD *)Data; ++i )
      {
        StringCchPrintfW(ValueName, 0x104u, L"ICS_IPv6_Prefix_%d", i);
        RegDeleteValueW(hKey, ValueName);
      }
      RegDeleteValueW(hKey, L"NumberOfPrefixes");
      RegDeleteValueW(hKey, L"ICS_IPv6_iaid");
      RegDeleteValueW(hKey, L"ICS_IPv6_T1");
      RegDeleteValueW(hKey, L"ICS_IPv6_T2");
      RegDeleteValueW(hKey, L"ICS_IPv6_NextRenewalTime");
      RegDeleteValueW(hKey, L"ICS_PublicAdapterIndex");
      RegDeleteValueW(hKey, L"ICS_IPv6_Dhcpv6ServerID");
      RegDeleteValueW(hKey, L"ICS_IPv6_Dhcpv6ServerIDLen");
      RegDeleteValueW(hKey, L"ICS_IPv6_Dhcpv6MaxLeaseExpirationTime");
      RegDeleteValueW(hKey, L"ICS_IPv6_Dhcpv6LastRenewalTime");
    }
    if ( hKey )
      RegCloseKey(hKey);
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v2 = 27;
      goto LABEL_24;
    }
  }
}

```

## disassembly

```asm
0x18006d22c  mov     [rsp-8+arg_0], rbx
0x18006d231  mov     [rsp-8+arg_8], r14
0x18006d236  push    rbp
0x18006d237  lea     rbp, [rsp-190h]
0x18006d23f  sub     rsp, 290h
0x18006d246  mov     rax, cs:__security_cookie
0x18006d24d  xor     rax, rsp
0x18006d250  mov     [rbp+190h+var_10], rax
0x18006d257  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d25e  lea     r14, WPP_GLOBAL_Control
0x18006d265  cmp     rcx, r14
0x18006d268  jz      short loc_18006D28B
0x18006d26a  test    byte ptr [rcx+1Ch], 80h
0x18006d26e  jz      short loc_18006D28B
0x18006d270  cmp     byte ptr [rcx+19h], 6
0x18006d274  jb      short loc_18006D28B
0x18006d276  mov     rcx, [rcx+10h]
0x18006d27a  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18006d281  mov     edx, 18h
0x18006d286  call    WPP_SF_
0x18006d28b  xor     edx, edx; Val
0x18006d28d  mov     dword ptr [rsp+290h+Data], 0
0x18006d295  mov     r8d, 208h; Size
0x18006d29b  mov     [rsp+290h+cbData], 0
0x18006d2a3  lea     rcx, [rsp+290h+ValueName]; void *
0x18006d2a8  mov     [rsp+290h+dwDisposition], 0
0x18006d2b0  mov     [rsp+290h+hKey], 0
0x18006d2b9  call    memset_0
0x18006d2be  lea     rax, [rsp+290h+dwDisposition]
0x18006d2c3  xor     r9d, r9d; lpClass
0x18006d2c6  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x18006d2cb  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006d2d2  lea     rax, [rsp+290h+hKey]
0x18006d2d7  xor     r8d, r8d; Reserved
0x18006d2da  mov     [rsp+290h+phkResult], rax; phkResult
0x18006d2df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006d2e6  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006d2ef  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x18006d2f7  mov     [rsp+290h+dwOptions], 0; dwOptions
0x18006d2ff  call    cs:__imp_RegCreateKeyExW
0x18006d306  nop     dword ptr [rax+rax+00h]
0x18006d30b  test    eax, eax
0x18006d30d  jz      short loc_18006D371
0x18006d30f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d316  cmp     rcx, r14
0x18006d319  jz      loc_18006D525
0x18006d31f  test    byte ptr [rcx+1Ch], 80h
0x18006d323  jz      short loc_18006D34A
0x18006d325  cmp     byte ptr [rcx+19h], 2
0x18006d329  jb      short loc_18006D34A
0x18006d32b  mov     rcx, [rcx+10h]
0x18006d32f  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18006d336  mov     edx, 19h
0x18006d33b  mov     r9d, eax
0x18006d33e  call    WPP_SF_d
0x18006d343  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d34a  cmp     rcx, r14
0x18006d34d  jz      loc_18006D525
0x18006d353  test    byte ptr [rcx+1Ch], 80h
0x18006d357  jz      loc_18006D525
0x18006d35d  cmp     byte ptr [rcx+19h], 6
0x18006d361  jb      loc_18006D525
0x18006d367  mov     edx, 1Ah
0x18006d36c  jmp     loc_18006D515
0x18006d371  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d376  lea     rax, [rsp+290h+cbData]
0x18006d37b  mov     qword ptr [rsp+290h+samDesired], rax; lpcbData
0x18006d380  lea     rdx, ValueName; "NumberOfPrefixes"
0x18006d387  lea     rax, [rsp+290h+Data]
0x18006d38c  mov     [rsp+290h+cbData], 4
0x18006d394  xor     r9d, r9d; lpType
0x18006d397  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x18006d39c  xor     r8d, r8d; lpReserved
0x18006d39f  call    cs:__imp_RegQueryValueExW
0x18006d3a6  nop     dword ptr [rax+rax+00h]
0x18006d3ab  test    eax, eax
0x18006d3ad  jnz     loc_18006D4E2
0x18006d3b3  xor     ebx, ebx
0x18006d3b5  cmp     dword ptr [rsp+290h+Data], ebx
0x18006d3b9  jbe     short loc_18006D3F2
0x18006d3bb  mov     r9d, ebx
0x18006d3be  lea     r8, aIcsIpv6PrefixD; "ICS_IPv6_Prefix_%d"
0x18006d3c5  mov     edx, 104h; unsigned __int64
0x18006d3ca  lea     rcx, [rsp+290h+ValueName]; unsigned __int16 *
0x18006d3cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d3d4  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d3d9  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x18006d3de  call    cs:__imp_RegDeleteValueW
0x18006d3e5  nop     dword ptr [rax+rax+00h]
0x18006d3ea  inc     ebx
0x18006d3ec  cmp     ebx, dword ptr [rsp+290h+Data]
0x18006d3f0  jb      short loc_18006D3BB
0x18006d3f2  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d3f7  lea     rdx, ValueName; "NumberOfPrefixes"
0x18006d3fe  call    cs:__imp_RegDeleteValueW
0x18006d405  nop     dword ptr [rax+rax+00h]
0x18006d40a  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d40f  lea     rdx, aIcsIpv6Iaid; "ICS_IPv6_iaid"
0x18006d416  call    cs:__imp_RegDeleteValueW
0x18006d41d  nop     dword ptr [rax+rax+00h]
0x18006d422  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d427  lea     rdx, aIcsIpv6T1; "ICS_IPv6_T1"
0x18006d42e  call    cs:__imp_RegDeleteValueW
0x18006d435  nop     dword ptr [rax+rax+00h]
0x18006d43a  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d43f  lea     rdx, aIcsIpv6T2; "ICS_IPv6_T2"
0x18006d446  call    cs:__imp_RegDeleteValueW
0x18006d44d  nop     dword ptr [rax+rax+00h]
0x18006d452  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d457  lea     rdx, aIcsIpv6Nextren; "ICS_IPv6_NextRenewalTime"
0x18006d45e  call    cs:__imp_RegDeleteValueW
0x18006d465  nop     dword ptr [rax+rax+00h]
0x18006d46a  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d46f  lea     rdx, aIcsPublicadapt; "ICS_PublicAdapterIndex"
0x18006d476  call    cs:__imp_RegDeleteValueW
0x18006d47d  nop     dword ptr [rax+rax+00h]
0x18006d482  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d487  lea     rdx, aIcsIpv6Dhcpv6s; "ICS_IPv6_Dhcpv6ServerID"
0x18006d48e  call    cs:__imp_RegDeleteValueW
0x18006d495  nop     dword ptr [rax+rax+00h]
0x18006d49a  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d49f  lea     rdx, aIcsIpv6Dhcpv6s_0; "ICS_IPv6_Dhcpv6ServerIDLen"
0x18006d4a6  call    cs:__imp_RegDeleteValueW
0x18006d4ad  nop     dword ptr [rax+rax+00h]
0x18006d4b2  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d4b7  lea     rdx, aIcsIpv6Dhcpv6m; "ICS_IPv6_Dhcpv6MaxLeaseExpirationTime"
0x18006d4be  call    cs:__imp_RegDeleteValueW
0x18006d4c5  nop     dword ptr [rax+rax+00h]
0x18006d4ca  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d4cf  lea     rdx, aIcsIpv6Dhcpv6l; "ICS_IPv6_Dhcpv6LastRenewalTime"
0x18006d4d6  call    cs:__imp_RegDeleteValueW
0x18006d4dd  nop     dword ptr [rax+rax+00h]
0x18006d4e2  mov     rcx, [rsp+290h+hKey]; hKey
0x18006d4e7  test    rcx, rcx
0x18006d4ea  jz      short loc_18006D4F8
0x18006d4ec  call    cs:__imp_RegCloseKey
0x18006d4f3  nop     dword ptr [rax+rax+00h]
0x18006d4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d4ff  cmp     rcx, r14
0x18006d502  jz      short loc_18006D525
0x18006d504  test    byte ptr [rcx+1Ch], 80h
0x18006d508  jz      short loc_18006D525
0x18006d50a  cmp     byte ptr [rcx+19h], 6
0x18006d50e  jb      short loc_18006D525
0x18006d510  mov     edx, 1Bh
0x18006d515  mov     rcx, [rcx+10h]
0x18006d519  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18006d520  call    WPP_SF_
0x18006d525  mov     rcx, [rbp+190h+var_10]
0x18006d52c  xor     rcx, rsp; StackCookie
0x18006d52f  call    __security_check_cookie
0x18006d534  lea     r11, [rsp+290h+var_s0]
0x18006d53c  mov     rbx, [r11+10h]
0x18006d540  mov     r14, [r11+18h]
0x18006d544  mov     rsp, r11
0x18006d547  pop     rbp
0x18006d548  retn
```
