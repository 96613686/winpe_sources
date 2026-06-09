# DeleteICSRegKeys(void)

- ea: `0x180068088`
- end: `0x180068351`
- name: `?DeleteICSRegKeys@@YAXXZ`
- size: `713`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180065b08`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18002e7a4`
- `0x18004e0c0`
- `0x18004ed64`
- `0x180068088`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800681f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800681f5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006822e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180068248`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006825a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006826c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006827e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180068290`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006822e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180068248`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006825a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006826c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006827e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180068290`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800682ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800682fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800682fa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006815b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006815b`

## string_xrefs

- `0x180068127`: `System\CurrentControlSet\Services\Tcpip6\Parameters`

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
0x180068088  mov     [rsp-8+arg_0], rbx
0x18006808d  mov     [rsp-8+arg_8], r14
0x180068092  push    rbp
0x180068093  lea     rbp, [rsp-190h]
0x18006809b  sub     rsp, 290h
0x1800680a2  mov     rax, cs:__security_cookie
0x1800680a9  xor     rax, rsp
0x1800680ac  mov     [rbp+190h+var_10], rax
0x1800680b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800680ba  lea     r14, WPP_GLOBAL_Control
0x1800680c1  cmp     rcx, r14
0x1800680c4  jz      short loc_1800680E7
0x1800680c6  test    byte ptr [rcx+1Ch], 80h
0x1800680ca  jz      short loc_1800680E7
0x1800680cc  cmp     byte ptr [rcx+19h], 6
0x1800680d0  jb      short loc_1800680E7
0x1800680d2  mov     rcx, [rcx+10h]
0x1800680d6  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x1800680dd  mov     edx, 18h
0x1800680e2  call    WPP_SF_
0x1800680e7  xor     edx, edx; Val
0x1800680e9  mov     dword ptr [rsp+290h+Data], 0
0x1800680f1  mov     r8d, 208h; Size
0x1800680f7  mov     [rsp+290h+cbData], 0
0x1800680ff  lea     rcx, [rsp+290h+ValueName]; void *
0x180068104  mov     [rsp+290h+dwDisposition], 0
0x18006810c  mov     [rsp+290h+hKey], 0
0x180068115  call    memset_0
0x18006811a  lea     rax, [rsp+290h+dwDisposition]
0x18006811f  xor     r9d, r9d; lpClass
0x180068122  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x180068127  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18006812e  lea     rax, [rsp+290h+hKey]
0x180068133  xor     r8d, r8d; Reserved
0x180068136  mov     [rsp+290h+phkResult], rax; phkResult
0x18006813b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068142  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006814b  mov     [rsp+290h+samDesired], 0F003Fh; samDesired
0x180068153  mov     [rsp+290h+dwOptions], 0; dwOptions
0x18006815b  call    cs:__imp_RegCreateKeyExW
0x180068161  test    eax, eax
0x180068163  jz      short loc_1800681C7
0x180068165  mov     rcx, cs:WPP_GLOBAL_Control
0x18006816c  cmp     rcx, r14
0x18006816f  jz      loc_18006832D
0x180068175  test    byte ptr [rcx+1Ch], 80h
0x180068179  jz      short loc_1800681A0
0x18006817b  cmp     byte ptr [rcx+19h], 2
0x18006817f  jb      short loc_1800681A0
0x180068181  mov     rcx, [rcx+10h]
0x180068185  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x18006818c  mov     edx, 19h
0x180068191  mov     r9d, eax
0x180068194  call    WPP_SF_d
0x180068199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800681a0  cmp     rcx, r14
0x1800681a3  jz      loc_18006832D
0x1800681a9  test    byte ptr [rcx+1Ch], 80h
0x1800681ad  jz      loc_18006832D
0x1800681b3  cmp     byte ptr [rcx+19h], 6
0x1800681b7  jb      loc_18006832D
0x1800681bd  mov     edx, 1Ah
0x1800681c2  jmp     loc_18006831D
0x1800681c7  mov     rcx, [rsp+290h+hKey]; hKey
0x1800681cc  lea     rax, [rsp+290h+cbData]
0x1800681d1  mov     qword ptr [rsp+290h+samDesired], rax; lpcbData
0x1800681d6  lea     rdx, ValueName; "NumberOfPrefixes"
0x1800681dd  lea     rax, [rsp+290h+Data]
0x1800681e2  mov     [rsp+290h+cbData], 4
0x1800681ea  xor     r9d, r9d; lpType
0x1800681ed  mov     qword ptr [rsp+290h+dwOptions], rax; lpData
0x1800681f2  xor     r8d, r8d; lpReserved
0x1800681f5  call    cs:__imp_RegQueryValueExW
0x1800681fb  test    eax, eax
0x1800681fd  jnz     loc_1800682F0
0x180068203  xor     ebx, ebx
0x180068205  cmp     dword ptr [rsp+290h+Data], ebx
0x180068209  jbe     short loc_18006823C
0x18006820b  mov     r9d, ebx
0x18006820e  lea     r8, aIcsIpv6PrefixD; "ICS_IPv6_Prefix_%d"
0x180068215  mov     edx, 104h; unsigned __int64
0x18006821a  lea     rcx, [rsp+290h+ValueName]; unsigned __int16 *
0x18006821f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180068224  mov     rcx, [rsp+290h+hKey]; hKey
0x180068229  lea     rdx, [rsp+290h+ValueName]; lpValueName
0x18006822e  call    cs:__imp_RegDeleteValueW
0x180068234  inc     ebx
0x180068236  cmp     ebx, dword ptr [rsp+290h+Data]
0x18006823a  jb      short loc_18006820B
0x18006823c  mov     rcx, [rsp+290h+hKey]; hKey
0x180068241  lea     rdx, ValueName; "NumberOfPrefixes"
0x180068248  call    cs:__imp_RegDeleteValueW
0x18006824e  mov     rcx, [rsp+290h+hKey]; hKey
0x180068253  lea     rdx, aIcsIpv6Iaid; "ICS_IPv6_iaid"
0x18006825a  call    cs:__imp_RegDeleteValueW
0x180068260  mov     rcx, [rsp+290h+hKey]; hKey
0x180068265  lea     rdx, aIcsIpv6T1; "ICS_IPv6_T1"
0x18006826c  call    cs:__imp_RegDeleteValueW
0x180068272  mov     rcx, [rsp+290h+hKey]; hKey
0x180068277  lea     rdx, aIcsIpv6T2; "ICS_IPv6_T2"
0x18006827e  call    cs:__imp_RegDeleteValueW
0x180068284  mov     rcx, [rsp+290h+hKey]; hKey
0x180068289  lea     rdx, aIcsIpv6Nextren; "ICS_IPv6_NextRenewalTime"
0x180068290  call    cs:__imp_RegDeleteValueW
0x180068296  mov     rcx, [rsp+290h+hKey]; hKey
0x18006829b  lea     rdx, aIcsPublicadapt; "ICS_PublicAdapterIndex"
0x1800682a2  call    cs:__imp_RegDeleteValueW
0x1800682a8  mov     rcx, [rsp+290h+hKey]; hKey
0x1800682ad  lea     rdx, aIcsIpv6Dhcpv6s; "ICS_IPv6_Dhcpv6ServerID"
0x1800682b4  call    cs:__imp_RegDeleteValueW
0x1800682ba  mov     rcx, [rsp+290h+hKey]; hKey
0x1800682bf  lea     rdx, aIcsIpv6Dhcpv6s_0; "ICS_IPv6_Dhcpv6ServerIDLen"
0x1800682c6  call    cs:__imp_RegDeleteValueW
0x1800682cc  mov     rcx, [rsp+290h+hKey]; hKey
0x1800682d1  lea     rdx, aIcsIpv6Dhcpv6m; "ICS_IPv6_Dhcpv6MaxLeaseExpirationTime"
0x1800682d8  call    cs:__imp_RegDeleteValueW
0x1800682de  mov     rcx, [rsp+290h+hKey]; hKey
0x1800682e3  lea     rdx, aIcsIpv6Dhcpv6l; "ICS_IPv6_Dhcpv6LastRenewalTime"
0x1800682ea  call    cs:__imp_RegDeleteValueW
0x1800682f0  mov     rcx, [rsp+290h+hKey]; hKey
0x1800682f5  test    rcx, rcx
0x1800682f8  jz      short loc_180068300
0x1800682fa  call    cs:__imp_RegCloseKey
0x180068300  mov     rcx, cs:WPP_GLOBAL_Control
0x180068307  cmp     rcx, r14
0x18006830a  jz      short loc_18006832D
0x18006830c  test    byte ptr [rcx+1Ch], 80h
0x180068310  jz      short loc_18006832D
0x180068312  cmp     byte ptr [rcx+19h], 6
0x180068316  jb      short loc_18006832D
0x180068318  mov     edx, 1Bh
0x18006831d  mov     rcx, [rcx+10h]
0x180068321  lea     r8, WPP_b002d07646b635308a4693336a4759d4_Traceguids
0x180068328  call    WPP_SF_
0x18006832d  mov     rcx, [rbp+190h+var_10]
0x180068334  xor     rcx, rsp; StackCookie
0x180068337  call    __security_check_cookie
0x18006833c  lea     r11, [rsp+290h+var_s0]
0x180068344  mov     rbx, [r11+10h]
0x180068348  mov     r14, [r11+18h]
0x18006834c  mov     rsp, r11
0x18006834f  pop     rbp
0x180068350  retn
```
