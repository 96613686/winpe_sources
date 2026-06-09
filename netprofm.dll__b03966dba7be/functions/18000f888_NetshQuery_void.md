# NetshQuery(void *)

- ea: `0x18000f888`
- end: `0x1800100d2`
- name: `?NetshQuery@@YAKPEAX@Z`
- size: `2122`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bc80`

## callees

- `0x18000ef08`
- `0x18000ef20`
- `0x18000f424`
- `0x18000f588`
- `0x18000f700`
- `0x18000f888`
- `0x1800100d8`
- `0x180010100`
- `0x180010124`
- `0x1800104b8`
- `0x180010ce0`
- `0x180010ea8`
- `0x180010f64`
- `0x18001136c`
- `0x1800120d0`
- `0x180012f40`
- `0x18002a3e4`
- `0x18002a928`
- `0x1800340a4`
- `0x180034574`
- `0x1800346d4`
- `0x180034844`
- `0x180034de8`
- `0x18003500c`
- `0x180038b08`
- `0x1800391a4`
- `0x180039b84`
- `0x180039f70`
- `0x18003b89c`
- `0x18003c0b8`
- `0x18003c818`
- `0x18003cd24`
- `0x18003e3bc`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180010030`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x180010030`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A` at `0x18001001a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001000d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001009f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001000d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001009f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f961`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000f961`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f8b5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f8b5`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000fda7`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000fe3d`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000fda7`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000fe3d`
- `WS2_32!__imp_WSAStartup` at `0x18000f909`
- `WS2_32!__imp_WSAStartup` at `0x18000f909`
- `WS2_32!__imp_WSACleanup` at `0x18000ffff`
- `WS2_32!__imp_WSACleanup` at `0x180010091`
- `WS2_32!__imp_WSACleanup` at `0x18000ffff`
- `WS2_32!__imp_WSACleanup` at `0x180010091`

## string_xrefs

- `0x18000f8d1`: `onecore\net\netprofiles\service\src\netshnlmplugin\netshquery.cpp`
- `0x18000f91e`: `onecore\net\netprofiles\service\src\netshnlmplugin\netshquery.cpp`
- `0x18000fe52`: `onecore\net\netprofiles\service\src\netshnlmplugin\netshquery.cpp`
- `0x18000f976`: `onecore\net\netprofiles\service\src\netshnlmplugin\publicnetworklistmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18 #try_helpers=1
__int64 __fastcall NetshQuery(void *a1)
{
  HRESULT v1; // eax
  unsigned int v2; // eax
  HRESULT v3; // eax
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  PIP_ADAPTER_ADDRESSES v8; // rdi
  IP_ADAPTER_ADDRESSES_LH *v9; // rax
  size_t v10; // rbx
  ULONG AdaptersAddresses; // eax
  PIP_ADAPTER_ADDRESSES i; // rbx
  PIP_ADAPTER_ADDRESSES j; // rbx
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  LPVOID v16; // rcx
  __int64 v18; // rax
  LPVOID v19; // rcx
  LPVOID v20; // rcx
  unsigned int ppv; // [rsp+20h] [rbp-288h]
  int ppva; // [rsp+20h] [rbp-288h]
  unsigned int ppvb; // [rsp+20h] [rbp-288h]
  char v24; // [rsp+30h] [rbp-278h]
  _BYTE v25[32]; // [rsp+38h] [rbp-270h] BYREF
  HANDLE hFile; // [rsp+58h] [rbp-250h]
  const std::exception *v27; // [rsp+60h] [rbp-248h] BYREF
  const std::exception *v28; // [rsp+68h] [rbp-240h] BYREF
  const std::exception *v29; // [rsp+70h] [rbp-238h] BYREF
  const std::exception *v30; // [rsp+78h] [rbp-230h] BYREF
  const std::exception *v31; // [rsp+80h] [rbp-228h] BYREF
  const std::exception *v32; // [rsp+88h] [rbp-220h] BYREF
  ULONG SizePointer; // [rsp+90h] [rbp-218h] BYREF
  PIP_ADAPTER_ADDRESSES AdapterAddresses[2]; // [rsp+98h] [rbp-210h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-200h]
  _BYTE v36[32]; // [rsp+B8h] [rbp-1F0h] BYREF
  LPVOID v37; // [rsp+D8h] [rbp-1D0h] BYREF
  LPVOID v38[2]; // [rsp+E0h] [rbp-1C8h] BYREF
  WSAData WSAData; // [rsp+F0h] [rbp-1B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  hFile = a1;
  v24 = 1;
  v1 = CoInitializeEx(0, 0);
  if ( v1 < 0 )
  {
    if ( v1 != -2147417850 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\netshquery.cpp",
        (const char *)(unsigned int)v1,
        ppv);
    v24 = 0;
  }
  memset_0(&WSAData, 0, sizeof(WSAData));
  v2 = WSAStartup(0x202u, &WSAData);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\netshquery.cpp",
      (const char *)v2,
      ppv);
  v37 = 0;
  v3 = CoCreateInstance(
         &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
         0,
         1u,
         &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
         &v37);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\publicnetworklistmanager.cpp",
      (const char *)(unsigned int)v3,
      ppva);
  v38[0] = 0;
  PrivateNlm::PrivateNlm(v38);
  std::wstring::wstring((__int64)v36);
  try
  {
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManager GetConnectivity ********************\n");
    PublicNlm::GetConnectivity(&v37, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManager EnumerateAllConnections ********************\n");
    PublicNlm::EnumerateAllConnections(&v37, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManager EnumerateNetworks(NLM_ENUM_NETWORK_CONNECTED) ********************\n");
    PublicNlm::EnumerateNetworks(&v37, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManager EnumNetworkConnectionCost ********************\n");
    PublicNlm::EnumNetworkConnectionCost(&v37, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  catch ( const std::exception *v27 )
  {
    std::wstring::append((__int64)v36, (__int64)L"\n\n** ERROR gathering INetworkListManager information\n");
    WriteException(AdapterAddresses, v27);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  try
  {
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManager GetNetworkCost ********************\n");
    PublicNlm::GetNetworkCost(&v37, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  catch ( const std::exception *v28 )
  {
    std::wstring::append((__int64)v36, (__int64)L"\n\n** ERROR gathering INetworkCostManager information\n");
    WriteException(AdapterAddresses, v28);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  try
  {
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManagerPrivate GetConnectivity ********************\n");
    PrivateNlm::GetConnectivity(v38, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManagerPrivate EnumNetworks ********************\n");
    PrivateNlm::EnumConnectedNetworks(v38, (__int64)AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManagerPrivate EnumNetworkInterfaces ********************\n");
    PrivateNlm::EnumNetworkInterfaces(v38, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** INetworkListManagerPrivate EnumNetworkConnectionProfiles ********************\n");
    PrivateNlm::EnumNetworkConnectionProfiles(v38, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  catch ( const std::exception *v29 )
  {
    std::wstring::append((__int64)v36, (__int64)L"\n\n** ERROR gathering INetworkListManagerPrivate information\n");
    WriteException(AdapterAddresses, v29);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  try
  {
    std::wstring::append((__int64)v36, (__int64)L"******************** WLAN API EnumNetworks ********************\n");
    WlanInfo::EnumNetworks(v4, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append((__int64)v36, (__int64)L"******************** WLAN API EnumProfiles ********************\n");
    WlanInfo::EnumProfiles(v5, (__int64)AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
    std::wstring::append(
      (__int64)v36,
      (__int64)L"******************** WLAN API EnumQueryableParameters ********************\n");
    WlanInfo::EnumQueryableParameters(v6, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  catch ( const std::exception *v30 )
  {
    std::wstring::append((__int64)v36, (__int64)L"\n\n** ERROR gathering WLAN information\n");
    WriteException(AdapterAddresses, v30);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  try
  {
    std::wstring::append((__int64)v36, (__int64)L"******************** NLA NSP API Enumerate ********************\n");
    NlaNspInfo::Enumerate(v7, AdapterAddresses);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  catch ( const std::exception *v31 )
  {
    std::wstring::append((__int64)v36, (__int64)L"\n\n** ERROR gathering NLA-NSP information\n");
    WriteException(AdapterAddresses, v31);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)AdapterAddresses);
  }
  *(_OWORD *)AdapterAddresses = 0;
  v35 = 0;
  std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(AdapterAddresses);
  try
  {
    std::vector<unsigned char>::_Construct_n<>(AdapterAddresses);
    SizePointer = LODWORD(AdapterAddresses[1]) - LODWORD(AdapterAddresses[0]);
    if ( GetAdaptersAddresses(0, 0x2D0u, 0, AdapterAddresses[0], &SizePointer) != 111 )
    {
LABEL_21:
      std::wstring::append(
        (__int64)v36,
        (__int64)L"******************** IPHELPER API LogBestInterfaceInfo ********************\n");
      LogBestInterfaceInfo(v25);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v25);
      std::wstring::append(
        (__int64)v36,
        (__int64)L"******************** IPHELPER API LogAdapterAddresses ********************\n");
      for ( i = AdapterAddresses[0]; i; i = i->Next )
      {
        LogAdapterAddresses(v25, i);
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v25);
      }
      std::wstring::append(
        (__int64)v36,
        (__int64)L"******************** IPHELPER API LogIfEntryInformation ********************\n");
      for ( j = AdapterAddresses[0]; j; j = j->Next )
      {
        LogIfEntryInformation(v25, &j->Luid);
        std::wstring::append();
        std::wstring::_Tidy_deallocate((__int64)v25);
      }
      std::wstring::append(
        (__int64)v36,
        (__int64)L"******************** IPHELPER API LogRouteInformation ********************\n");
      LogRouteInformation(v25);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v25);
      std::vector<unsigned char>::_Tidy(AdapterAddresses);
      goto LABEL_76;
    }
    v8 = AdapterAddresses[1];
    if ( (PIP_ADAPTER_ADDRESSES)SizePointer >= (PIP_ADAPTER_ADDRESSES)((char *)AdapterAddresses[1]
                                                                     - (char *)AdapterAddresses[0]) )
    {
      if ( (PIP_ADAPTER_ADDRESSES)SizePointer <= (PIP_ADAPTER_ADDRESSES)((char *)AdapterAddresses[1]
                                                                       - (char *)AdapterAddresses[0]) )
        goto LABEL_19;
      if ( SizePointer > v35 - (unsigned __int64)AdapterAddresses[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(AdapterAddresses, SizePointer);
        goto LABEL_19;
      }
      v10 = SizePointer - (unsigned __int64)((char *)AdapterAddresses[1] - (char *)AdapterAddresses[0]);
      memset_0(AdapterAddresses[1], 0, v10);
      v9 = (PIP_ADAPTER_ADDRESSES)((char *)v8 + v10);
    }
    else
    {
      v9 = (PIP_ADAPTER_ADDRESSES)((char *)AdapterAddresses[0] + SizePointer);
    }
    AdapterAddresses[1] = v9;
LABEL_19:
    AdaptersAddresses = GetAdaptersAddresses(0, 0x2D0u, 0, AdapterAddresses[0], &SizePointer);
    if ( AdaptersAddresses )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\netshquery.cpp",
        (const char *)AdaptersAddresses,
        ppvb);
    goto LABEL_21;
  }
  catch ( const std::exception *v32 )
  {
    std::wstring::append((__int64)v36, (__int64)L"\n\n** ERROR gathering IPHelper API information\n");
    WriteException(v25, v32);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)v25);
  }
LABEL_76:
  if ( hFile )
  {
    v14 = WriteOutput(hFile);
    std::wstring::_Tidy_deallocate((__int64)v36);
    v15 = v38[0];
    if ( v38[0] )
    {
      v38[0] = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v15 + 16LL))(v15, *v15);
    }
    v16 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    }
    WSACleanup();
    if ( v24 )
      CoUninitialize();
    return v14;
  }
  else
  {
    v18 = std::operator<<<wchar_t>(std::wcout, v36);
    std::wostream::operator<<(v18, std::endl<wchar_t,std::char_traits<wchar_t>>);
    std::wstring::_Tidy_deallocate((__int64)v36);
    v19 = v38[0];
    if ( v38[0] )
    {
      v38[0] = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    WSACleanup();
    if ( v24 )
      CoUninitialize();
    return 0;
  }
}

```

## disassembly

```asm
0x18000f888  mov     [rsp+arg_8], rbx
0x18000f88d  push    rdi
0x18000f88e  sub     rsp, 2A0h
0x18000f895  mov     rax, cs:__security_cookie
0x18000f89c  xor     rax, rsp
0x18000f89f  mov     [rsp+2A8h+var_18], rax
0x18000f8a7  mov     [rsp+2A8h+hFile], rcx
0x18000f8ac  mov     [rsp+2A8h+var_278], 1
0x18000f8b1  xor     edx, edx; dwCoInit
0x18000f8b3  xor     ecx, ecx; pvReserved
0x18000f8b5  call    cs:__imp_CoInitializeEx
0x18000f8bb  test    eax, eax
0x18000f8bd  jns     short loc_18000F8E7
0x18000f8bf  cmp     eax, 80010106h
0x18000f8c4  jz      short loc_18000F8E2
0x18000f8c6  mov     rcx, [rsp+2A8h]; this
0x18000f8ce  mov     r9d, eax; char *
0x18000f8d1  lea     r8, aOnecoreNetNetp_1; "onecore\\net\\netprofiles\\service\\src"...
0x18000f8d8  mov     edx, 1Ch; void *
0x18000f8dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f8e2  mov     [rsp+2A8h+var_278], 0
0x18000f8e7  xor     edx, edx; Val
0x18000f8e9  mov     r8d, 198h; Size
0x18000f8ef  lea     rcx, [rsp+2A8h+WSAData]; void *
0x18000f8f7  call    memset_0
0x18000f8fc  mov     ecx, 202h; wVersionRequested
0x18000f901  lea     rdx, [rsp+2A8h+WSAData]; lpWSAData
0x18000f909  call    cs:__imp_WSAStartup
0x18000f90f  mov     rcx, [rsp+2A8h]; this
0x18000f917  test    eax, eax
0x18000f919  jz      short loc_18000F92F
0x18000f91b  mov     r9d, eax; char *
0x18000f91e  lea     r8, aOnecoreNetNetp_1; "onecore\\net\\netprofiles\\service\\src"...
0x18000f925  mov     edx, 23h ; '#'; void *
0x18000f92a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000f92f  mov     [rsp+2A8h+var_273], 1
0x18000f934  mov     [rsp+2A8h+var_1D0], 0
0x18000f940  lea     rax, [rsp+2A8h+var_1D0]
0x18000f948  mov     qword ptr [rsp+2A8h+ppv], rax; int
0x18000f94d  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18000f954  xor     edx, edx; pUnkOuter
0x18000f956  lea     r8d, [rdx+1]; dwClsContext
0x18000f95a  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x18000f961  call    cs:__imp_CoCreateInstance
0x18000f967  mov     rcx, [rsp+2A8h]; this
0x18000f96f  test    eax, eax
0x18000f971  jns     short loc_18000F988
0x18000f973  mov     r9d, eax; char *
0x18000f976  lea     r8, aOnecoreNetNetp_2; "onecore\\net\\netprofiles\\service\\src"...
0x18000f97d  mov     edx, 0B5h; void *
0x18000f982  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f988  mov     [rsp+2A8h+var_1C8], 0
0x18000f994  lea     rcx, [rsp+2A8h+var_1C8]; ppv
0x18000f99c  call    ??0PrivateNlm@@QEAA@XZ; PrivateNlm::PrivateNlm(void)
0x18000f9a1  nop
0x18000f9a2  lea     rcx, [rsp+2A8h+var_1F0]
0x18000f9aa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f9af  nop
0x18000f9b0  lea     rdx, aInetworklistma_7; "******************** INetworkListManage"...
0x18000f9b7  lea     rcx, [rsp+2A8h+var_1F0]
0x18000f9bf  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000f9c4  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000f9cc  lea     rcx, [rsp+2A8h+var_1D0]
0x18000f9d4  call    ?GetConnectivity@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PublicNlm::GetConnectivity(void)
0x18000f9d9  nop
0x18000f9da  mov     rdx, rax
0x18000f9dd  lea     rcx, [rsp+2A8h+var_1F0]
0x18000f9e5  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000f9ea  nop
0x18000f9eb  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000f9f3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f9f8  lea     rdx, aInetworklistma_5; "******************** INetworkListManage"...
0x18000f9ff  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fa07  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fa0c  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fa14  lea     rcx, [rsp+2A8h+var_1D0]
0x18000fa1c  call    ?EnumerateAllConnections@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PublicNlm::EnumerateAllConnections(void)
0x18000fa21  nop
0x18000fa22  mov     rdx, rax
0x18000fa25  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fa2d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fa32  nop
0x18000fa33  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fa3b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fa40  lea     rdx, aInetworklistma_12; "******************** INetworkListManage"...
0x18000fa47  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fa4f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fa54  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fa5c  lea     rcx, [rsp+2A8h+var_1D0]
0x18000fa64  call    ?EnumerateNetworks@PublicNlm@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4NLM_ENUM_NETWORK@@@Z; PublicNlm::EnumerateNetworks(NLM_ENUM_NETWORK)
0x18000fa69  nop
0x18000fa6a  mov     rdx, rax
0x18000fa6d  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fa75  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fa7a  nop
0x18000fa7b  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fa83  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fa88  lea     rdx, aInetworklistma_8; "******************** INetworkListManage"...
0x18000fa8f  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fa97  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fa9c  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000faa4  lea     rcx, [rsp+2A8h+var_1D0]
0x18000faac  call    ?EnumNetworkConnectionCost@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PublicNlm::EnumNetworkConnectionCost(void)
0x18000fab1  nop
0x18000fab2  mov     rdx, rax
0x18000fab5  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fabd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fac2  nop
0x18000fac3  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000facb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fad0  nop
0x18000fad1  jmp     short $+2
0x18000fad3  lea     rdx, aInetworklistma_0; "******************** INetworkListManage"...
0x18000fada  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fae2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fae7  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000faef  lea     rcx, [rsp+2A8h+var_1D0]
0x18000faf7  call    ?GetNetworkCost@PublicNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PublicNlm::GetNetworkCost(void)
0x18000fafc  nop
0x18000fafd  mov     rdx, rax
0x18000fb00  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fb08  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fb0d  nop
0x18000fb0e  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fb16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fb1b  nop
0x18000fb1c  jmp     short $+2
0x18000fb1e  lea     rdx, aInetworklistma_16; "******************** INetworkListManage"...
0x18000fb25  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fb2d  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fb32  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fb3a  lea     rcx, [rsp+2A8h+var_1C8]
0x18000fb42  call    ?GetConnectivity@PrivateNlm@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PrivateNlm::GetConnectivity(void)
0x18000fb47  nop
0x18000fb48  mov     rdx, rax
0x18000fb4b  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fb53  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fb58  nop
0x18000fb59  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fb61  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fb66  lea     rdx, aInetworklistma_10; "******************** INetworkListManage"...
0x18000fb6d  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fb75  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fb7a  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fb82  lea     rcx, [rsp+2A8h+var_1C8]
0x18000fb8a  call    ?EnumConnectedNetworks@PrivateNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PrivateNlm::EnumConnectedNetworks(void)
0x18000fb8f  nop
0x18000fb90  mov     rdx, rax
0x18000fb93  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fb9b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fba0  nop
0x18000fba1  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fba9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fbae  lea     rdx, aInetworklistma_3; "******************** INetworkListManage"...
0x18000fbb5  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fbbd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fbc2  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fbca  lea     rcx, [rsp+2A8h+var_1C8]
0x18000fbd2  call    ?EnumNetworkInterfaces@PrivateNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PrivateNlm::EnumNetworkInterfaces(void)
0x18000fbd7  nop
0x18000fbd8  mov     rdx, rax
0x18000fbdb  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fbe3  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fbe8  nop
0x18000fbe9  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fbf1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fbf6  lea     rdx, aInetworklistma_1; "******************** INetworkListManage"...
0x18000fbfd  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fc05  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fc0a  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fc12  lea     rcx, [rsp+2A8h+var_1C8]
0x18000fc1a  call    ?EnumNetworkConnectionProfiles@PrivateNlm@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; PrivateNlm::EnumNetworkConnectionProfiles(void)
0x18000fc1f  nop
0x18000fc20  mov     rdx, rax
0x18000fc23  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fc2b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fc30  nop
0x18000fc31  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fc39  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc3e  nop
0x18000fc3f  jmp     short $+2
0x18000fc41  lea     rdx, aWlanApiEnumnet; "******************** WLAN API EnumNetwo"...
0x18000fc48  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fc50  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fc55  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fc5d  call    ?EnumNetworks@WlanInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; WlanInfo::EnumNetworks(void)
0x18000fc62  nop
0x18000fc63  mov     rdx, rax
0x18000fc66  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fc6e  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fc73  nop
0x18000fc74  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fc7c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fc81  lea     rdx, aWlanApiEnumpro; "******************** WLAN API EnumProfi"...
0x18000fc88  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fc90  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fc95  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fc9d  call    ?EnumProfiles@WlanInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; WlanInfo::EnumProfiles(void)
0x18000fca2  nop
0x18000fca3  mov     rdx, rax
0x18000fca6  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fcae  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fcb3  nop
0x18000fcb4  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fcbc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fcc1  lea     rdx, aWlanApiEnumque; "******************** WLAN API EnumQuery"...
0x18000fcc8  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fcd0  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fcd5  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fcdd  call    ?EnumQueryableParameters@WlanInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; WlanInfo::EnumQueryableParameters(void)
0x18000fce2  nop
0x18000fce3  mov     rdx, rax
0x18000fce6  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fcee  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fcf3  nop
0x18000fcf4  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fcfc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fd01  nop
0x18000fd02  jmp     short $+2
0x18000fd04  lea     rdx, aNlaNspApiEnume; "******************** NLA NSP API Enumer"...
0x18000fd0b  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fd13  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fd18  lea     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fd20  call    ?Enumerate@NlaNspInfo@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NlaNspInfo::Enumerate(void)
0x18000fd25  nop
0x18000fd26  mov     rdx, rax
0x18000fd29  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fd31  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18000fd36  nop
0x18000fd37  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fd3f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000fd44  nop
0x18000fd45  jmp     short $+2
0x18000fd47  xorps   xmm0, xmm0
0x18000fd4a  xor     eax, eax
0x18000fd4c  movups  xmmword ptr [rsp+2A8h+AdapterAddresses], xmm0
0x18000fd54  mov     [rsp+2A8h+var_200], rax
0x18000fd5c  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fd64  call    ??0?$vector@UWlanAvailableNetworks@@V?$allocator@UWlanAvailableNetworks@@@std@@@std@@QEAA@XZ; std::vector<WlanAvailableNetworks>::vector<WlanAvailableNetworks>(void)
0x18000fd69  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fd71  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x18000fd76  nop
0x18000fd77  mov     eax, dword ptr [rsp+2A8h+AdapterAddresses+8]
0x18000fd7e  mov     r9, [rsp+2A8h+AdapterAddresses]; AdapterAddresses
0x18000fd86  sub     eax, r9d
0x18000fd89  mov     [rsp+2A8h+SizePointer], eax
0x18000fd90  lea     rax, [rsp+2A8h+SizePointer]
0x18000fd98  mov     qword ptr [rsp+2A8h+ppv], rax; SizePointer
0x18000fd9d  xor     r8d, r8d; Reserved
0x18000fda0  mov     edx, 2D0h; Flags
0x18000fda5  xor     ecx, ecx; Family
0x18000fda7  call    cs:__imp_GetAdaptersAddresses
0x18000fdad  cmp     eax, 6Fh ; 'o'
0x18000fdb0  jnz     loc_18000FE63
0x18000fdb6  mov     ebx, [rsp+2A8h+SizePointer]
0x18000fdbd  mov     rdx, [rsp+2A8h+AdapterAddresses]
0x18000fdc5  mov     rdi, [rsp+2A8h+AdapterAddresses+8]
0x18000fdcd  mov     rcx, rdi
0x18000fdd0  sub     rcx, rdx
0x18000fdd3  cmp     rbx, rcx
0x18000fdd6  jnb     short loc_18000FDDE
0x18000fdd8  lea     rax, [rbx+rdx]
0x18000fddc  jmp     short loc_18000FE16
0x18000fdde  jbe     short loc_18000FE1E
0x18000fde0  mov     rax, [rsp+2A8h+var_200]
0x18000fde8  sub     rax, rdx
0x18000fdeb  cmp     rbx, rax
0x18000fdee  jbe     short loc_18000FE02
0x18000fdf0  mov     rdx, rbx
0x18000fdf3  lea     rcx, [rsp+2A8h+AdapterAddresses]
0x18000fdfb  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000fe00  jmp     short loc_18000FE1E
0x18000fe02  sub     rbx, rcx
0x18000fe05  mov     r8, rbx; Size
0x18000fe08  xor     edx, edx; Val
0x18000fe0a  mov     rcx, rdi; void *
0x18000fe0d  call    memset_0
0x18000fe12  lea     rax, [rbx+rdi]
0x18000fe16  mov     [rsp+2A8h+AdapterAddresses+8], rax
0x18000fe1e  lea     rax, [rsp+2A8h+SizePointer]
0x18000fe26  mov     qword ptr [rsp+2A8h+ppv], rax; unsigned int
0x18000fe2b  mov     r9, [rsp+2A8h+AdapterAddresses]; AdapterAddresses
0x18000fe33  xor     r8d, r8d; Reserved
0x18000fe36  mov     edx, 2D0h; Flags
0x18000fe3b  xor     ecx, ecx; Family
0x18000fe3d  call    cs:__imp_GetAdaptersAddresses
0x18000fe43  mov     rcx, [rsp+2A8h]; this
0x18000fe4b  test    eax, eax
0x18000fe4d  jz      short loc_18000FE63
0x18000fe4f  mov     r9d, eax; char *
0x18000fe52  lea     r8, aOnecoreNetNetp_1; "onecore\\net\\netprofiles\\service\\src"...
0x18000fe59  mov     edx, 84h; void *
0x18000fe5e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000fe63  lea     rdx, aIphelperApiLog; "******************** IPHELPER API LogBe"...
0x18000fe6a  lea     rcx, [rsp+2A8h+var_1F0]
0x18000fe72  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18000fe77  lea     rcx, [rsp+2A8h+var_270]
0x18000fe7c  call    ?LogBestInterfaceInfo@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; LogBestInterfaceInfo(void)
0x18000fe81  nop
0x18000fe82  mov     rdx, rax
  ... truncated ...
```
