# LogBestInterfaceInfo(void)

- ea: `0x1800391a4`
- end: `0x180039b7e`
- name: `?LogBestInterfaceInfo@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `2522`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f888`

## callees

- `0x18000c650`
- `0x18000ef08`
- `0x18000f388`
- `0x18000f700`
- `0x1800100d8`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x180012f40`
- `0x180013fad`
- `0x18002a3e4`
- `0x1800389f0`
- `0x1800391a4`
- `0x18003a210`
- `0x18003a37c`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180039469`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180039905`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180039469`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180039905`
- `IPHLPAPI!GetIpInterfaceTable` at `0x1800393c9`
- `IPHLPAPI!GetIpInterfaceTable` at `0x180039872`
- `IPHLPAPI!GetIpInterfaceTable` at `0x1800393c9`
- `IPHLPAPI!GetIpInterfaceTable` at `0x180039872`
- `IPHLPAPI!GetBestRoute2` at `0x18003938c`
- `IPHLPAPI!GetBestRoute2` at `0x180039835`
- `IPHLPAPI!GetBestRoute2` at `0x18003938c`
- `IPHLPAPI!GetBestRoute2` at `0x180039835`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x1800394aa`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x180039946`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x1800394aa`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x180039946`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18003930f`
- `IPHLPAPI!GetBestInterfaceEx` at `0x1800397b8`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18003930f`
- `IPHLPAPI!GetBestInterfaceEx` at `0x1800397b8`
- `IPHLPAPI!FreeMibTable` at `0x180039652`
- `IPHLPAPI!FreeMibTable` at `0x180039ae1`
- `IPHLPAPI!FreeMibTable` at `0x180039652`
- `IPHLPAPI!FreeMibTable` at `0x180039ae1`
- `WS2_32!GetAddrInfoW` at `0x180039240`
- `WS2_32!GetAddrInfoW` at `0x1800396db`
- `WS2_32!GetAddrInfoW` at `0x180039240`
- `WS2_32!GetAddrInfoW` at `0x1800396db`
- `WS2_32!FreeAddrInfoW` at `0x1800392c5`
- `WS2_32!FreeAddrInfoW` at `0x180039760`
- `WS2_32!FreeAddrInfoW` at `0x1800392c5`
- `WS2_32!FreeAddrInfoW` at `0x180039760`

## string_xrefs

- `0x180039239`: `ipv4.google.com`
- `0x180039255`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x180039324`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x1800393a1`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x1800393de`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x18003947e`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x1800394bf`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x1800396f0`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x1800397cd`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x18003984a`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x180039887`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x18003991a`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x18003995b`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x1800395e3`: `\n>>>>>> GetBestInterfaceEx(ipv4.google.com) <<<<<<\n  Returning the interface for the IPv4 address %ws\n    Interface Index: %u\n    Interface LUID: %I64u\n    Interface GUID: %ws\n    Interface Metric: %u (%ws)\n  Using Route:\n    Destination Prefix: %ws / %u\n    Next Hop: %ws\n    Route Metric: %u\n`
- `0x180039a72`: `\n>>>>>> GetBestInterfaceEx(ipv6.google.com) <<<<<<\n  Returning the interface for the IPv6 address %ws\n    Interface Index: %u\n    Interface LUID: %I64u\n    Interface GUID: %ws\n    Interface Metric: %u (%ws)\n  Using Route:\n    Destination Prefix: %ws / %u\n    Next Hop: %ws\n    Route Metric: %u\n`
- `0x1800396d4`: `ipv6.google.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall LogBestInterfaceInfo(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int AddrInfoW; // eax
  PADDRINFOW i; // r14
  size_t ai_addrlen; // r8
  DWORD BestInterface; // eax
  unsigned int BestRoute2; // eax
  unsigned int IpInterfaceTable; // eax
  int v8; // r15d
  unsigned int k; // ecx
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned int v12; // eax
  const wchar_t *v13; // r12
  unsigned int Value; // r13d
  __int64 v15; // rax
  struct sockaddr *j; // rbx
  unsigned int v17; // eax
  NET_LUID v18; // r14
  size_t v19; // r8
  DWORD v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  bool v23; // r13
  unsigned int n; // edx
  __int64 v25; // r8
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // r13
  __int64 v29; // rax
  struct sockaddr *m; // rbx
  void *v31; // r14
  __int64 v33; // rax
  __int64 v34; // rax
  unsigned int AddressSortOptions; // [rsp+20h] [rbp-268h]
  unsigned int AddressSortOptionsa; // [rsp+20h] [rbp-268h]
  unsigned int AddressSortOptionsb; // [rsp+20h] [rbp-268h]
  SOCKADDR_INET *BestSourceAddress; // [rsp+30h] [rbp-258h]
  DWORD v40; // [rsp+68h] [rbp-220h]
  DWORD v41; // [rsp+6Ch] [rbp-21Ch]
  int SitePrefixLength; // [rsp+6Ch] [rbp-21Ch]
  NET_LUID v43; // [rsp+78h] [rbp-210h]
  __int64 v44; // [rsp+80h] [rbp-208h]
  __int64 v45; // [rsp+88h] [rbp-200h]
  _BYTE v46[32]; // [rsp+A0h] [rbp-1E8h] BYREF
  _BYTE v47[32]; // [rsp+C0h] [rbp-1C8h] BYREF
  _BYTE v48[32]; // [rsp+E0h] [rbp-1A8h] BYREF
  _BYTE v49[32]; // [rsp+100h] [rbp-188h] BYREF
  _BYTE v50[32]; // [rsp+120h] [rbp-168h] BYREF
  PADDRINFOW ppResult[2]; // [rsp+140h] [rbp-148h] BYREF
  struct _MIB_IPFORWARD_ROW2 BestRoute; // [rsp+150h] [rbp-138h] BYREF
  DWORD pdwBestIfIndex; // [rsp+1C0h] [rbp-C8h] BYREF
  NET_LUID InterfaceLuid; // [rsp+1C8h] [rbp-C0h] BYREF
  SOCKADDR_INET v55; // [rsp+1D0h] [rbp-B8h] BYREF
  struct sockaddr *pDestAddr[2]; // [rsp+1F0h] [rbp-98h] BYREF
  __int64 v57; // [rsp+200h] [rbp-88h]
  GUID InterfaceGuid[2]; // [rsp+208h] [rbp-80h] BYREF
  SOCKADDR_INET v59; // [rsp+228h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v1 = a1;
  std::wstring::wstring(a1);
  *(_OWORD *)pDestAddr = 0;
  v57 = 0;
  std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(pDestAddr);
  ppResult[0] = 0;
  *(_QWORD *)&InterfaceGuid[0].Data1 = ppResult;
  InterfaceGuid[0].Data4[0] = 1;
  AddrInfoW = GetAddrInfoW(L"ipv4.google.com", 0, 0, ppResult);
  try
  {
    if ( AddrInfoW )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4BE,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
        (const char *)AddrInfoW,
        AddressSortOptions);
    for ( i = ppResult[0]; i; i = i->ai_next )
    {
      ai_addrlen = i->ai_addrlen;
      if ( ai_addrlen <= 0x1C )
      {
        memset(&v55, 0, sizeof(v55));
        memcpy_0(&v55, i->ai_addr, ai_addrlen);
        std::vector<_SOCKADDR_INET>::emplace_back<_SOCKADDR_INET &>(pDestAddr, &v55);
      }
    }
    if ( ppResult[0] )
      FreeAddrInfoW(ppResult[0]);
  }
  catch ( ... )
  {
    std::wstring::append(a1, (__int64)L"\n!! Failed to resolve the name ipv4.google.com\n");
    v1 = a1;
  }
  try
  {
    for ( j = pDestAddr[0]; ; j = (struct sockaddr *)((char *)j + 28) )
    {
      if ( j == pDestAddr[1] )
      {
        v8 = -1;
        v13 = L"used automatic metric";
        goto LABEL_78;
      }
      if ( j->sa_family == 2 )
        break;
    }
    pdwBestIfIndex = 0;
    BestInterface = GetBestInterfaceEx(j, &pdwBestIfIndex);
    if ( BestInterface )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4D5,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
        (const char *)BestInterface,
        AddressSortOptions);
    memset_0(&BestRoute, 0, sizeof(BestRoute));
    memset(&v55, 0, sizeof(v55));
    BestRoute2 = GetBestRoute2(0, pdwBestIfIndex, 0, (const SOCKADDR_INET *)j, 0, &BestRoute, &v55);
    if ( BestRoute2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4D9,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
        (const char *)BestRoute2,
        AddressSortOptionsa);
    ppResult[0] = 0;
    IpInterfaceTable = GetIpInterfaceTable(2u, (PMIB_IPINTERFACE_TABLE *)ppResult);
    if ( IpInterfaceTable )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4DC,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
        (const char *)IpInterfaceTable,
        AddressSortOptionsa);
    v8 = -1;
    for ( k = 0; k < ppResult[0]->ai_flags; ++k )
    {
      v10 = 168LL * k;
      if ( *(_DWORD *)((char *)&ppResult[0]->ai_canonname + v10) == pdwBestIfIndex )
        break;
    }
    InterfaceLuid.Value = 0;
    v11 = ConvertInterfaceIndexToLuid(pdwBestIfIndex, &InterfaceLuid);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4EF,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
        (const char *)v11,
        AddressSortOptionsa);
    InterfaceGuid[0] = 0;
    v12 = ConvertInterfaceLuidToGuid(&InterfaceLuid, InterfaceGuid);
    if ( v12 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4F1,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
        (const char *)v12,
        AddressSortOptionsa);
    ToString(v46, &BestRoute.NextHop);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    ToString(v47, &BestRoute.DestinationPrefix);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v13 = L"used automatic metric";
    ToString(v49, InterfaceGuid);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    Value = InterfaceLuid.Value;
    v41 = pdwBestIfIndex;
    ToString(v48, j);
    v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    AddressSortOptions = Value;
    wil::str_printf<std::wstring>(
      (__int64)&v59,
      (__int64)L"\n"
                ">>>>>> GetBestInterfaceEx(ipv4.google.com) <<<<<<\n"
                "  Returning the interface for the IPv4 address %ws\n"
                "    Interface Index: %u\n"
                "    Interface LUID: %I64u\n"
                "    Interface GUID: %ws\n"
                "    Interface Metric: %u (%ws)\n"
                "  Using Route:\n"
                "    Destination Prefix: %ws / %u\n"
                "    Next Hop: %ws\n"
                "    Route Metric: %u\n",
      v15,
      v41);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)&v59);
    std::wstring::_Tidy_deallocate((__int64)v48);
    std::wstring::_Tidy_deallocate((__int64)v49);
    std::wstring::_Tidy_deallocate((__int64)v47);
    std::wstring::_Tidy_deallocate((__int64)v46);
    FreeMibTable(ppResult[0]);
  }
  catch ( ... )
  {
    if ( pDestAddr[0] != pDestAddr[1] )
    {
      ToString(v47, pDestAddr[0]);
      v33 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>(
        (__int64)v46,
        (__int64)L"\n!! IPHelper APIs failed to test the IPv4 address %ws to find the preferred interface\n",
        v33);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v46);
      std::wstring::_Tidy_deallocate((__int64)v47);
    }
    v8 = -1;
    v13 = L"used automatic metric";
    v1 = a1;
  }
LABEL_78:
  try
  {
    memset(&v55, 0, 24);
    std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(&v55);
    InterfaceLuid.Value = 0;
    v17 = GetAddrInfoW(L"ipv6.google.com", 0, 0, (PADDRINFOW *)&InterfaceLuid);
    if ( v17 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x521,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
        (const char *)v17,
        AddressSortOptions);
    for ( v18.Value = InterfaceLuid.Value; v18.Value; v18.Value = *(ULONG64 *)(v18.Value + 40) )
    {
      v19 = *(_QWORD *)(v18.Value + 16);
      if ( v19 <= 0x1C )
      {
        memset(InterfaceGuid, 0, 28);
        memcpy_0(InterfaceGuid, *(const void **)(v18.Value + 32), v19);
        std::vector<_SOCKADDR_INET>::emplace_back<_SOCKADDR_INET &>(pDestAddr, InterfaceGuid);
      }
    }
    if ( InterfaceLuid.Value )
      FreeAddrInfoW((PADDRINFOW)InterfaceLuid.Value);
  }
  catch ( ... )
  {
    std::wstring::append(a1, (__int64)L"\n!! Failed to resolve the name ipv6.google.com\n");
    v8 = -1;
    v13 = L"used automatic metric";
    v1 = a1;
  }
  try
  {
    v31 = *(void **)&v55.Ipv4.sin_family;
    for ( m = *(struct sockaddr **)&v55.Ipv4.sin_family;
          m != *((struct sockaddr **)&v55.si_family + 1);
          m = (struct sockaddr *)((char *)m + 28) )
    {
      if ( m->sa_family == 23 )
      {
        pdwBestIfIndex = 0;
        v20 = GetBestInterfaceEx(m, &pdwBestIfIndex);
        if ( v20 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x538,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
            (const char *)v20,
            AddressSortOptions);
        memset_0(&BestRoute, 0, sizeof(BestRoute));
        memset(&v59, 0, sizeof(v59));
        v21 = GetBestRoute2(0, pdwBestIfIndex, 0, (const SOCKADDR_INET *)m, 0, &BestRoute, &v59);
        if ( v21 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x53C,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
            (const char *)v21,
            AddressSortOptionsb);
        ppResult[0] = 0;
        v22 = GetIpInterfaceTable(0x17u, (PMIB_IPINTERFACE_TABLE *)ppResult);
        if ( v22 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x53F,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
            (const char *)v22,
            AddressSortOptionsb);
        v23 = 0;
        for ( n = 0; n < ppResult[0]->ai_flags; ++n )
        {
          v25 = 168LL * n;
          if ( *(_DWORD *)((char *)&ppResult[0]->ai_canonname + v25) == pdwBestIfIndex )
          {
            v8 = *(int *)((char *)&ppResult[0][3].ai_protocol + v25);
            v23 = *((_BYTE *)&ppResult[0][1].ai_family + v25) != 0;
            break;
          }
        }
        InterfaceLuid.Value = 0;
        v26 = ConvertInterfaceIndexToLuid(pdwBestIfIndex, &InterfaceLuid);
        if ( v26 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x552,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
            (const char *)v26,
            AddressSortOptionsb);
        InterfaceGuid[0] = 0;
        v27 = ConvertInterfaceLuidToGuid(&InterfaceLuid, InterfaceGuid);
        if ( v27 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x554,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
            (const char *)v27,
            AddressSortOptionsb);
        ToString(v50, &BestRoute.NextHop);
        v45 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        SitePrefixLength = BestRoute.SitePrefixLength;
        ToString(v48, &BestRoute.DestinationPrefix);
        v44 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        if ( !v23 )
          v13 = L"did not use automatic metric";
        ToString(v49, InterfaceGuid);
        v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        v43.Value = InterfaceLuid.Value;
        v40 = pdwBestIfIndex;
        ToString(v47, m);
        v29 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        LODWORD(BestSourceAddress) = v8;
        wil::str_printf<std::wstring>(
          (__int64)v46,
          (__int64)L"\n"
                    ">>>>>> GetBestInterfaceEx(ipv6.google.com) <<<<<<\n"
                    "  Returning the interface for the IPv6 address %ws\n"
                    "    Interface Index: %u\n"
                    "    Interface LUID: %I64u\n"
                    "    Interface GUID: %ws\n"
                    "    Interface Metric: %u (%ws)\n"
                    "  Using Route:\n"
                    "    Destination Prefix: %ws / %u\n"
                    "    Next Hop: %ws\n"
                    "    Route Metric: %u\n",
          v29,
          v40,
          v43.Value,
          v28,
          BestSourceAddress,
          v13,
          v44,
          SitePrefixLength,
          v45,
          BestRoute.Metric);
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v46);
        std::wstring::_Tidy_deallocate((__int64)v47);
        std::wstring::_Tidy_deallocate((__int64)v49);
        std::wstring::_Tidy_deallocate((__int64)v48);
        std::wstring::_Tidy_deallocate((__int64)v50);
        FreeMibTable(ppResult[0]);
        goto LABEL_88;
      }
    }
  }
  catch ( ... )
  {
    if ( *(_QWORD *)&v55.Ipv4.sin_family != *((_QWORD *)&v55.si_family + 1) )
    {
      ToString(v46, *(_QWORD *)&v55.Ipv4.sin_family);
      v34 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>(
        (__int64)v50,
        (__int64)L"\n!! IPHelper APIs failed to test the IPv6 address %ws to find the preferred interface\n",
        v34);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v50);
      std::wstring::_Tidy_deallocate((__int64)v46);
    }
    v31 = *(void **)&v55.Ipv4.sin_family;
    v1 = a1;
  }
LABEL_88:
  if ( v31 )
    std::_Deallocate<16>(v31, 4 * ((__int64)(*((_QWORD *)&v55.si_family + 2) - (_QWORD)v31) >> 2));
  if ( pDestAddr[0] )
    std::_Deallocate<16>(pDestAddr[0], 4 * ((signed __int64)(v57 - (unsigned __int64)pDestAddr[0]) >> 2));
  return v1;
}

```

## disassembly

```asm
0x1800391a4  push    rbx
0x1800391a6  push    rsi
0x1800391a7  push    r12
0x1800391a9  push    r13
0x1800391ab  push    r14
0x1800391ad  push    r15
0x1800391af  sub     rsp, 258h
0x1800391b6  mov     rax, cs:__security_cookie
0x1800391bd  xor     rax, rsp
0x1800391c0  mov     [rsp+288h+var_40], rax
0x1800391c8  mov     rsi, rcx
0x1800391cb  mov     [rsp+288h+var_228], rcx
0x1800391d0  mov     [rsp+288h+var_214], 0
0x1800391d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800391dd  mov     [rsp+288h+var_214], 1
0x1800391e5  xorps   xmm0, xmm0
0x1800391e8  xor     eax, eax
0x1800391ea  movups  xmmword ptr [rsp+288h+pDestAddr], xmm0
0x1800391f2  mov     [rsp+288h+var_88], rax
0x1800391fa  lea     rcx, [rsp+288h+pDestAddr]
0x180039202  call    ??0?$vector@UWlanAvailableNetworks@@V?$allocator@UWlanAvailableNetworks@@@std@@@std@@QEAA@XZ; std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(void)
0x180039207  nop
0x180039208  mov     [rsp+288h+ppResult], 0
0x180039214  lea     rbx, [rsp+288h+ppResult]
0x18003921c  mov     qword ptr [rsp+288h+InterfaceGuid.Data1], rbx
0x180039224  mov     [rsp+288h+InterfaceGuid.Data4], 1
0x18003922c  lea     r9, [rsp+288h+ppResult]; ppResult
0x180039234  xor     r8d, r8d; pHints
0x180039237  xor     edx, edx; pServiceName
0x180039239  lea     rcx, pNodeName; "ipv4.google.com"
0x180039240  call    cs:__imp_GetAddrInfoW
0x180039246  mov     rcx, [rsp+288h]; this
0x18003924e  test    eax, eax
0x180039250  jz      short loc_180039266
0x180039252  mov     r9d, eax; char *
0x180039255  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x18003925c  mov     edx, 4BEh; void *
0x180039261  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180039266  mov     r14, [rsp+288h+ppResult]
0x18003926e  test    r14, r14
0x180039271  jz      short loc_1800392BC
0x180039273  mov     r8, [r14+10h]; Size
0x180039277  cmp     r8, 1Ch
0x18003927b  ja      short loc_1800392B6
0x18003927d  xorps   xmm0, xmm0
0x180039280  movups  xmmword ptr [rsp+288h+var_B8], xmm0
0x180039288  movups  xmmword ptr [rsp+288h+var_B8+0Ch], xmm0
0x180039290  mov     rdx, [r14+20h]; Src
0x180039294  lea     rcx, [rsp+288h+var_B8]; void *
0x18003929c  call    memcpy_0
0x1800392a1  lea     rdx, [rsp+288h+var_B8]
0x1800392a9  lea     rcx, [rsp+288h+pDestAddr]
0x1800392b1  call    ??$emplace_back@AEAT_SOCKADDR_INET@@@?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@QEAAAEAT_SOCKADDR_INET@@AEAT2@@Z; std::vector<_SOCKADDR_INET>::emplace_back<_SOCKADDR_INET &>(_SOCKADDR_INET &)
0x1800392b6  mov     r14, [r14+28h]
0x1800392ba  jmp     short loc_18003926E
0x1800392bc  cmp     qword ptr [rbx], 0
0x1800392c0  jz      short loc_1800392CC
0x1800392c2  mov     rcx, [rbx]; pAddrInfo
0x1800392c5  call    cs:__imp_FreeAddrInfoW
0x1800392cb  nop
0x1800392cc  jmp     short loc_1800392D3
0x1800392ce  mov     rsi, [rsp+288h+var_228]
0x1800392d3  mov     rbx, [rsp+288h+pDestAddr]
0x1800392db  mov     r14d, 2
0x1800392e1  cmp     rbx, [rsp+288h+pDestAddr+8]
0x1800392e9  jz      loc_180039663
0x1800392ef  cmp     [rbx], r14w
0x1800392f3  jnz     loc_18003965A
0x1800392f9  mov     [rsp+288h+pdwBestIfIndex], 0
0x180039304  lea     rdx, [rsp+288h+pdwBestIfIndex]; pdwBestIfIndex
0x18003930c  mov     rcx, rbx; pDestAddr
0x18003930f  call    cs:__imp_GetBestInterfaceEx
0x180039315  mov     rcx, [rsp+288h]; this
0x18003931d  test    eax, eax
0x18003931f  jz      short loc_180039335
0x180039321  mov     r9d, eax; char *
0x180039324  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x18003932b  mov     edx, 4D5h; void *
0x180039330  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180039335  xor     edx, edx; Val
0x180039337  lea     r8d, [rdx+68h]; Size
0x18003933b  lea     rcx, [rsp+288h+var_138]; void *
0x180039343  call    memset_0
0x180039348  xorps   xmm0, xmm0
0x18003934b  movups  xmmword ptr [rsp+288h+var_B8], xmm0
0x180039353  movups  xmmword ptr [rsp+288h+var_B8+0Ch], xmm0
0x18003935b  lea     rax, [rsp+288h+var_B8]
0x180039363  mov     [rsp+288h+BestSourceAddress], rax; BestSourceAddress
0x180039368  lea     rax, [rsp+288h+var_138]
0x180039370  mov     [rsp+288h+BestRoute], rax; BestRoute
0x180039375  mov     [rsp+288h+AddressSortOptions], 0; unsigned int
0x18003937d  mov     r9, rbx; DestinationAddress
0x180039380  xor     r8d, r8d; SourceAddress
0x180039383  mov     edx, [rsp+288h+pdwBestIfIndex]; InterfaceIndex
0x18003938a  xor     ecx, ecx; InterfaceLuid
0x18003938c  call    cs:__imp_GetBestRoute2
0x180039392  mov     rcx, [rsp+288h]; this
0x18003939a  test    eax, eax
0x18003939c  jz      short loc_1800393B2
0x18003939e  mov     r9d, eax; char *
0x1800393a1  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800393a8  mov     edx, 4D9h; void *
0x1800393ad  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800393b2  mov     [rsp+288h+ppResult], 0
0x1800393be  mov     ecx, r14d; Family
0x1800393c1  lea     rdx, [rsp+288h+ppResult]; Table
0x1800393c9  call    cs:__imp_GetIpInterfaceTable
0x1800393cf  mov     rcx, [rsp+288h]; this
0x1800393d7  test    eax, eax
0x1800393d9  jz      short loc_1800393EF
0x1800393db  mov     r9d, eax; char *
0x1800393de  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800393e5  mov     edx, 4DCh; void *
0x1800393ea  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800393ef  lea     rax, [rsp+288h+ppResult]
0x1800393f7  mov     [rsp+288h+var_1F8], rax
0x1800393ff  mov     [rsp+288h+var_1F0], 1
0x180039407  or      r15d, 0FFFFFFFFh
0x18003940b  mov     [rsp+288h+var_218], r15d
0x180039410  xor     r14b, r14b
0x180039413  xor     ecx, ecx
0x180039415  mov     rdx, [rsp+288h+ppResult]
0x18003941d  mov     r9d, [rsp+288h+pdwBestIfIndex]
0x180039425  cmp     ecx, [rdx]
0x180039427  jnb     short loc_180039452
0x180039429  mov     eax, ecx
0x18003942b  imul    r8, rax, 0A8h
0x180039432  cmp     [r8+rdx+18h], r9d
0x180039437  jz      short loc_18003943D
0x180039439  inc     ecx
0x18003943b  jmp     short loc_180039425
0x18003943d  mov     eax, [r8+rdx+9Ch]
0x180039445  mov     [rsp+288h+var_218], eax
0x180039449  cmp     [r8+rdx+34h], r14b
0x18003944e  setnz   r14b
0x180039452  mov     qword ptr [rsp+288h+InterfaceLuid], 0
0x18003945e  lea     rdx, [rsp+288h+InterfaceLuid]; InterfaceLuid
0x180039466  mov     ecx, r9d; InterfaceIndex
0x180039469  call    cs:__imp_ConvertInterfaceIndexToLuid
0x18003946f  mov     rcx, [rsp+288h]; this
0x180039477  test    eax, eax
0x180039479  jz      short loc_18003948F
0x18003947b  mov     r9d, eax; char *
0x18003947e  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180039485  mov     edx, 4EFh; void *
0x18003948a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003948f  xorps   xmm0, xmm0
0x180039492  movups  xmmword ptr [rsp+288h+InterfaceGuid.Data1], xmm0
0x18003949a  lea     rdx, [rsp+288h+InterfaceGuid]; InterfaceGuid
0x1800394a2  lea     rcx, [rsp+288h+InterfaceLuid]; InterfaceLuid
0x1800394aa  call    cs:__imp_ConvertInterfaceLuidToGuid
0x1800394b0  mov     rcx, [rsp+288h]; this
0x1800394b8  test    eax, eax
0x1800394ba  jz      short loc_1800394D0
0x1800394bc  mov     r9d, eax; char *
0x1800394bf  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800394c6  mov     edx, 4F1h; void *
0x1800394cb  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800394d0  lea     rdx, [rsp+288h+var_138.NextHop]
0x1800394d8  lea     rcx, [rsp+288h+var_1E8]
0x1800394e0  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBT_SOCKADDR_INET@@@Z; ToString(_SOCKADDR_INET const &)
0x1800394e5  nop
0x1800394e6  mov     rcx, rax
0x1800394e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800394ee  mov     [rsp+288h+var_210], rax
0x1800394f3  movzx   eax, [rsp+288h+var_138.SitePrefixLength]
0x1800394fb  mov     [rsp+288h+var_220], eax
0x1800394ff  lea     rdx, [rsp+288h+var_138.DestinationPrefix]
0x180039507  lea     rcx, [rsp+288h+var_1C8]
0x18003950f  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBT_SOCKADDR_INET@@@Z; ToString(_SOCKADDR_INET const &)
0x180039514  nop
0x180039515  mov     rcx, rax
0x180039518  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003951d  mov     [rsp+288h+var_208], rax
0x180039525  lea     r13, aDidNotUseAutom; "did not use automatic metric"
0x18003952c  lea     r12, aUsedAutomaticM; "used automatic metric"
0x180039533  mov     rax, r12
0x180039536  test    r14b, r14b
0x180039539  cmovz   rax, r13
0x18003953d  mov     [rsp+288h+var_200], rax
0x180039545  lea     rdx, [rsp+288h+InterfaceGuid]
0x18003954d  lea     rcx, [rsp+288h+var_188]
0x180039555  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x18003955a  nop
0x18003955b  mov     rcx, rax
0x18003955e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180039563  mov     r14, rax
0x180039566  mov     r13, qword ptr [rsp+288h+InterfaceLuid]
0x18003956e  mov     eax, [rsp+288h+pdwBestIfIndex]
0x180039575  mov     [rsp+288h+var_21C], eax
0x180039579  mov     rdx, rbx
0x18003957c  lea     rcx, [rsp+288h+var_1A8]
0x180039584  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBT_SOCKADDR_INET@@@Z; ToString(_SOCKADDR_INET const &)
0x180039589  nop
0x18003958a  mov     rcx, rax
0x18003958d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180039592  mov     r8, rax
0x180039595  mov     eax, [rsp+288h+var_138.Metric]
0x18003959c  mov     [rsp+288h+var_230], eax
0x1800395a0  mov     rax, [rsp+288h+var_210]
0x1800395a5  mov     [rsp+288h+var_238], rax
0x1800395aa  mov     eax, [rsp+288h+var_220]
0x1800395ae  mov     [rsp+288h+var_240], eax
0x1800395b2  mov     rax, [rsp+288h+var_208]
0x1800395ba  mov     [rsp+288h+var_248], rax
0x1800395bf  mov     rax, [rsp+288h+var_200]
0x1800395c7  mov     [rsp+288h+var_250], rax
0x1800395cc  mov     eax, [rsp+288h+var_218]
0x1800395d0  mov     dword ptr [rsp+288h+BestSourceAddress], eax
0x1800395d4  mov     [rsp+288h+BestRoute], r14
0x1800395d9  mov     qword ptr [rsp+288h+AddressSortOptions], r13
0x1800395de  mov     r9d, [rsp+288h+var_21C]
0x1800395e3  lea     rdx, aGetbestinterfa_1; "\n>>>>>> GetBestInterfaceEx(ipv4.google"...
0x1800395ea  lea     rcx, [rsp+288h+var_60]
0x1800395f2  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x1800395f7  nop
0x1800395f8  mov     rdx, rax
0x1800395fb  mov     rcx, rsi
0x1800395fe  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180039603  nop
0x180039604  lea     rcx, [rsp+288h+var_60]
0x18003960c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039611  nop
0x180039612  lea     rcx, [rsp+288h+var_1A8]
0x18003961a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003961f  nop
0x180039620  lea     rcx, [rsp+288h+var_188]
0x180039628  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003962d  nop
0x18003962e  lea     rcx, [rsp+288h+var_1C8]
0x180039636  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003963b  nop
0x18003963c  lea     rcx, [rsp+288h+var_1E8]
0x180039644  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039649  nop
0x18003964a  mov     rcx, [rsp+288h+ppResult]; Memory
0x180039652  call    cs:__imp_FreeMibTable
0x180039658  jmp     short loc_18003966E
0x18003965a  add     rbx, 1Ch
0x18003965e  jmp     loc_1800392E1
0x180039663  or      r15d, 0FFFFFFFFh
0x180039667  lea     r12, aUsedAutomaticM; "used automatic metric"
0x18003966e  jmp     short loc_180039680
0x180039670  or      r15d, 0FFFFFFFFh
0x180039674  lea     r12, aUsedAutomaticM; "used automatic metric"
0x18003967b  mov     rsi, [rsp+288h+var_228]
0x180039680  xorps   xmm0, xmm0
0x180039683  xor     eax, eax
0x180039685  movups  xmmword ptr [rsp+288h+var_B8], xmm0
0x18003968d  mov     qword ptr [rsp+288h+var_B8+10h], rax
0x180039695  lea     rcx, [rsp+288h+var_B8]
0x18003969d  call    ??0?$vector@UWlanAvailableNetworks@@V?$allocator@UWlanAvailableNetworks@@@std@@@std@@QEAA@XZ; std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(void)
0x1800396a2  nop
0x1800396a3  mov     qword ptr [rsp+288h+InterfaceLuid], 0
0x1800396af  lea     rbx, [rsp+288h+InterfaceLuid]
0x1800396b7  mov     [rsp+288h+var_1F8], rbx
0x1800396bf  mov     [rsp+288h+var_1F0], 1
0x1800396c7  lea     r9, [rsp+288h+InterfaceLuid]; ppResult
0x1800396cf  xor     r8d, r8d; pHints
0x1800396d2  xor     edx, edx; pServiceName
0x1800396d4  lea     rcx, aIpv6GoogleCom; "ipv6.google.com"
0x1800396db  call    cs:__imp_GetAddrInfoW
0x1800396e1  mov     rcx, [rsp+288h]; this
0x1800396e9  test    eax, eax
0x1800396eb  jz      short loc_180039701
0x1800396ed  mov     r9d, eax; char *
0x1800396f0  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x1800396f7  mov     edx, 521h; void *
0x1800396fc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180039701  mov     r14, qword ptr [rsp+288h+InterfaceLuid]
0x180039709  test    r14, r14
0x18003970c  jz      short loc_180039757
0x18003970e  mov     r8, [r14+10h]; Size
0x180039712  cmp     r8, 1Ch
0x180039716  ja      short loc_180039751
0x180039718  xorps   xmm0, xmm0
0x18003971b  movups  xmmword ptr [rsp+288h+InterfaceGuid.Data1], xmm0
0x180039723  movups  xmmword ptr [rsp+288h+InterfaceGuid.Data4+4], xmm0
0x18003972b  mov     rdx, [r14+20h]; Src
0x18003972f  lea     rcx, [rsp+288h+InterfaceGuid]; void *
0x180039737  call    memcpy_0
0x18003973c  lea     rdx, [rsp+288h+InterfaceGuid]
0x180039744  lea     rcx, [rsp+288h+pDestAddr]
0x18003974c  call    ??$emplace_back@AEAT_SOCKADDR_INET@@@?$vector@T_SOCKADDR_INET@@V?$allocator@T_SOCKADDR_INET@@@std@@@std@@QEAAAEAT_SOCKADDR_INET@@AEAT2@@Z; std::vector<_SOCKADDR_INET>::emplace_back<_SOCKADDR_INET &>(_SOCKADDR_INET &)
0x180039751  mov     r14, [r14+28h]
0x180039755  jmp     short loc_180039709
0x180039757  cmp     qword ptr [rbx], 0
0x18003975b  jz      short loc_180039767
0x18003975d  mov     rcx, [rbx]; pAddrInfo
0x180039760  call    cs:__imp_FreeAddrInfoW
0x180039766  nop
0x180039767  jmp     short loc_180039779
0x180039769  or      r15d, 0FFFFFFFFh
0x18003976d  lea     r12, aUsedAutomaticM; "used automatic metric"
0x180039774  mov     rsi, [rsp+288h+var_228]
0x180039779  mov     r14, qword ptr [rsp+288h+var_B8]
0x180039781  mov     rbx, r14
0x180039784  mov     r13d, 17h
0x18003978a  cmp     rbx, qword ptr [rsp+288h+var_B8+8]
0x180039792  jz      loc_180039AE8
  ... truncated ...
```
