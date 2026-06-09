# LogAdapterAddresses(_IP_ADAPTER_ADDRESSES_LH const &)

- ea: `0x180038b08`
- end: `0x18003919d`
- name: `?LogAdapterAddresses@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `1685`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x1800100d8`
- `0x180010100`
- `0x180010124`
- `0x180011614`
- `0x180038b08`
- `0x18003a37c`
- `0x18003a624`
- `0x18003a708`
- `0x18003a79c`
- `0x18003b3f8`
- `0x18003b7cc`

## string_xrefs

- `0x180039157`: `  Flags:\n    IPv4 Enabled: %ws\n    IPv6 Enabled: %ws\n    Dynamic DNS Enabled: %ws\n    Register DNS Suffix: %ws\n    DHCP Enabled: %ws\n    Receive-only adapter: %ws\n    No-Multicast adapter: %ws\n    NetBIOS over TCP Enabled: %ws\n    IPv6 Other Stateful config: %ws\n    IPv6 Managed Address config: %ws\n`
- `0x18003908a`: `  CompartmentID: %u\n  IPv4 Interface Metric: %u\n  IPv6 Interface Metric: %u\n  Max Transmission Unit: %u\n  Receive Link Speed: %llu\n  Transmit Link Speed: %llu\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LogAdapterAddresses(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  const wchar_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r10
  __int64 i; // rdi
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  const wchar_t *v14; // rsi
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 j; // rbx
  __int64 v18; // rax
  __int64 k; // rbx
  __int64 v20; // rax
  __int64 m; // rbx
  __int64 v22; // rax
  __int64 n; // rbx
  __int64 v24; // rax
  __int64 ii; // rbx
  __int64 v26; // rax
  __int64 jj; // rbx
  __int64 v28; // rax
  _QWORD *kk; // rbx
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // r14d
  const wchar_t *v33; // r8
  const wchar_t *v34; // rsi
  const wchar_t *v35; // rdi
  const wchar_t *v36; // rbx
  const wchar_t *v37; // r11
  const wchar_t *v38; // r10
  const wchar_t *v39; // rdx
  const wchar_t *v40; // rcx
  const wchar_t *v41; // rax
  const wchar_t *v42; // r9
  __int64 v44; // [rsp+28h] [rbp-A9h]
  __int64 v45; // [rsp+30h] [rbp-A1h]
  _BYTE v46[32]; // [rsp+78h] [rbp-59h] BYREF
  _BYTE v47[32]; // [rsp+98h] [rbp-39h] BYREF
  int v48; // [rsp+B8h] [rbp-19h]
  _BYTE v49[32]; // [rsp+C0h] [rbp-11h] BYREF
  _BYTE v50[40]; // [rsp+E0h] [rbp+Fh] BYREF

  v48 = 0;
  ToString(v50, a2 + 80, *(unsigned int *)(a2 + 88));
  v4 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v49, a2 + 252);
  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString((const enum _NET_IF_CONNECTION_TYPE *)(a2 + 268));
  ToString((const enum IF_OPER_STATUS *)(a2 + 104));
  v5 = ToString((unsigned int *)(a2 + 100), (const enum TUNNEL_TYPE *)(a2 + 272));
  wil::str_printf<std::wstring>(
    a1,
    (__int64)L"\n"
              " >>>>>> GetAdaptersAddresses Adapter Information <<<<<<\n"
              "  AdapterName: %hs\n"
              "  FriendlyName: %ws\n"
              "  Description: %ws\n"
              "  Luid: %llu\n"
              "  IfIndex: %u\n"
              "  IPv6 IfIndex: %u\n"
              "  IfType: %ws\n"
              "  OperStatus: %ws\n"
              "  ConnectionType: %ws\n"
              "  NetworkGuid: %ws\n"
              "  PhysicalAddress: %ws\n",
    *(_QWORD *)(a2 + 16),
    *(_QWORD *)(a2 + 72),
    *(_QWORD *)(a2 + 64),
    *(_QWORD *)(a2 + 224),
    *(_DWORD *)(a2 + 4),
    *(_DWORD *)(a2 + 108),
    v5,
    v6,
    v7,
    v8,
    v4);
  v48 = 1;
  std::wstring::_Tidy_deallocate((__int64)v49);
  std::wstring::_Tidy_deallocate((__int64)v50);
  if ( *(_DWORD *)(a2 + 104) == 1 )
  {
    std::wstring::append(a1, (__int64)L"  Unicast Addresses:\n");
    for ( i = *(_QWORD *)(a2 + 24); i; i = *(_QWORD *)(i + 8) )
    {
      v10 = *(_DWORD *)(i + 40);
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( v13 == 1 )
                v14 = L"IpDadStatePreferred";
              else
                v14 = L"(unknown IP_DAD_STATE)";
            }
            else
            {
              v14 = L"IpDadStateDeprecated";
            }
          }
          else
          {
            v14 = L"IpDadStateDuplicate";
          }
        }
        else
        {
          v14 = L"IpDadStateTentative";
        }
      }
      else
      {
        v14 = L"IpDadStateInvalid";
      }
      v15 = *(unsigned __int8 *)(i + 56);
      ToString(v46, *(_QWORD *)(i + 16), *(unsigned int *)(i + 24));
      v16 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>((__int64)v47, (__int64)L"    %ws / %u (%ws)\n", v16, v15, v14);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v47);
      std::wstring::_Tidy_deallocate((__int64)v46);
    }
    for ( j = *(_QWORD *)(a2 + 40); j; j = *(_QWORD *)(j + 8) )
    {
      ToString(v47, *(_QWORD *)(j + 16), *(unsigned int *)(j + 24));
      v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>((__int64)v46, (__int64)L"    %ws (multicast)\n", v18);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v46);
      std::wstring::_Tidy_deallocate((__int64)v47);
    }
    for ( k = *(_QWORD *)(a2 + 32); k; k = *(_QWORD *)(k + 8) )
    {
      ToString(v47, *(_QWORD *)(k + 16), *(unsigned int *)(k + 24));
      v20 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>((__int64)v46, (__int64)L"    %ws (anycast)\n", v20);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v46);
      std::wstring::_Tidy_deallocate((__int64)v47);
    }
    for ( m = *(_QWORD *)(a2 + 176); m; m = *(_QWORD *)(m + 8) )
    {
      ToString(v47, *(_QWORD *)(m + 16), *(unsigned int *)(m + 24));
      v22 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>((__int64)v46, (__int64)L"    %ws (prefix)\n", v22);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v46);
      std::wstring::_Tidy_deallocate((__int64)v47);
    }
    std::wstring::append(a1, (__int64)L"  Gateway Addresses:\n");
    for ( n = *(_QWORD *)(a2 + 208); n; n = *(_QWORD *)(n + 8) )
    {
      ToString(v47, *(_QWORD *)(n + 16), *(unsigned int *)(n + 24));
      v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>((__int64)v46, (__int64)L"    %ws\n", v24);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v46);
      std::wstring::_Tidy_deallocate((__int64)v47);
    }
    std::wstring::append(a1, (__int64)L"  WINS Addresses:\n");
    for ( ii = *(_QWORD *)(a2 + 200); ii; ii = *(_QWORD *)(ii + 8) )
    {
      ToString(v47, *(_QWORD *)(ii + 16), *(unsigned int *)(ii + 24));
      v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>((__int64)v46, (__int64)L"    %ws\n", v26);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v46);
      std::wstring::_Tidy_deallocate((__int64)v47);
    }
    std::wstring::append(a1, (__int64)L"  DNS Server Addresses:\n");
    for ( jj = *(_QWORD *)(a2 + 48); jj; jj = *(_QWORD *)(jj + 8) )
    {
      ToString(v47, *(_QWORD *)(jj + 16), *(unsigned int *)(jj + 24));
      v28 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      wil::str_printf<std::wstring>((__int64)v46, (__int64)L"    %ws\n", v28);
      std::wstring::append();
      std::wstring::_Tidy_deallocate((__int64)v46);
      std::wstring::_Tidy_deallocate((__int64)v47);
    }
  }
  wil::str_printf<std::wstring>((__int64)v46, (__int64)L"  Primary DNS Suffix: %ws\n", *(_QWORD *)(a2 + 56));
  std::wstring::append();
  std::wstring::_Tidy_deallocate((__int64)v46);
  std::wstring::append(a1, (__int64)L"  DNS Suffixes:\n");
  for ( kk = *(_QWORD **)(a2 + 440); kk; kk = (_QWORD *)*kk )
  {
    wil::str_printf<std::wstring>((__int64)v46, (__int64)L"    %ws\n", kk + 1);
    std::wstring::append();
    std::wstring::_Tidy_deallocate((__int64)v46);
  }
  ToString(v47, *(_QWORD *)(a2 + 232), *(unsigned int *)(a2 + 240));
  v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>((__int64)v46, (__int64)L"  DHCP IPv4 Server: %ws\n", v30);
  std::wstring::append();
  std::wstring::_Tidy_deallocate((__int64)v46);
  std::wstring::_Tidy_deallocate((__int64)v47);
  ToString(v47, *(_QWORD *)(a2 + 280), *(unsigned int *)(a2 + 288));
  v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>((__int64)v46, (__int64)L"  DHCP IPv6 Server: %ws\n", v31);
  std::wstring::append();
  std::wstring::_Tidy_deallocate((__int64)v46);
  std::wstring::_Tidy_deallocate((__int64)v47);
  LODWORD(v45) = *(_DWORD *)(a2 + 96);
  LODWORD(v44) = *(_DWORD *)(a2 + 220);
  wil::str_printf<std::wstring>(
    (__int64)v46,
    (__int64)L"  CompartmentID: %u\n"
              "  IPv4 Interface Metric: %u\n"
              "  IPv6 Interface Metric: %u\n"
              "  Max Transmission Unit: %u\n"
              "  Receive Link Speed: %llu\n"
              "  Transmit Link Speed: %llu\n",
    *(unsigned int *)(a2 + 248),
    *(unsigned int *)(a2 + 216),
    v44,
    v45,
    *(_QWORD *)(a2 + 192),
    *(_QWORD *)(a2 + 184));
  std::wstring::append();
  std::wstring::_Tidy_deallocate((__int64)v46);
  v32 = *(_DWORD *)(a2 + 92);
  v33 = L"enabled";
  v34 = L"enabled";
  if ( (v32 & 0x200) == 0 )
    v34 = L"disabled";
  v35 = L"enabled";
  if ( (v32 & 0x20) == 0 )
    v35 = L"disabled";
  v36 = L"enabled";
  if ( (v32 & 0x40) == 0 )
    v36 = L"disabled";
  v37 = L"enabled";
  if ( (v32 & 0x10) == 0 )
    v37 = L"disabled";
  v38 = L"enabled";
  if ( (v32 & 8) == 0 )
    v38 = L"disabled";
  v39 = L"enabled";
  if ( (v32 & 4) == 0 )
    v39 = L"disabled";
  v40 = L"enabled";
  if ( (v32 & 2) == 0 )
    v40 = L"disabled";
  v41 = L"enabled";
  if ( (v32 & 1) == 0 )
    v41 = L"disabled";
  v42 = L"enabled";
  if ( (v32 & 0x100) == 0 )
    v42 = L"disabled";
  if ( (v32 & 0x80u) == 0 )
    v33 = L"disabled";
  wil::str_printf<std::wstring>(
    (__int64)v46,
    (__int64)L"  Flags:\n"
              "    IPv4 Enabled: %ws\n"
              "    IPv6 Enabled: %ws\n"
              "    Dynamic DNS Enabled: %ws\n"
              "    Register DNS Suffix: %ws\n"
              "    DHCP Enabled: %ws\n"
              "    Receive-only adapter: %ws\n"
              "    No-Multicast adapter: %ws\n"
              "    NetBIOS over TCP Enabled: %ws\n"
              "    IPv6 Other Stateful config: %ws\n"
              "    IPv6 Managed Address config: %ws\n",
    v33,
    v42,
    v41,
    v40,
    v39,
    v38,
    v37,
    v36,
    v35,
    v34);
  std::wstring::append();
  std::wstring::_Tidy_deallocate((__int64)v46);
  return a1;
}

```

## disassembly

```asm
0x180038b08  mov     rax, rsp
0x180038b0b  mov     [rax+10h], rbx
0x180038b0f  mov     [rax+18h], rsi
0x180038b13  mov     [rax+8], rcx
0x180038b17  push    rbp
0x180038b18  push    rdi
0x180038b19  push    r12
0x180038b1b  push    r14
0x180038b1d  push    r15
0x180038b1f  lea     rbp, [rax-5Fh]
0x180038b23  sub     rsp, 100h
0x180038b2a  mov     r14, rdx
0x180038b2d  mov     r15, rcx
0x180038b30  mov     [rbp+57h+var_70], 0
0x180038b37  add     rdx, 50h ; 'P'
0x180038b3b  mov     r8d, [r14+58h]
0x180038b3f  lea     rcx, [rbp+57h+var_48]
0x180038b43  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBEK@Z; ToString(uchar const *,ulong)
0x180038b48  nop
0x180038b49  mov     rcx, rax
0x180038b4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038b51  mov     rbx, rax
0x180038b54  lea     rdx, [r14+0FCh]
0x180038b5b  lea     rcx, [rbp+57h+var_68]
0x180038b5f  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x180038b64  nop
0x180038b65  mov     rcx, rax
0x180038b68  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038b6d  mov     r10, rax
0x180038b70  lea     rcx, [r14+10Ch]; enum _NET_IF_CONNECTION_TYPE *
0x180038b77  call    ?ToString@@YAPEB_WAEBW4_NET_IF_CONNECTION_TYPE@@@Z; ToString(_NET_IF_CONNECTION_TYPE const &)
0x180038b7c  mov     r9, rax
0x180038b7f  lea     rcx, [r14+68h]; enum IF_OPER_STATUS *
0x180038b83  call    ?ToString@@YAPEB_WAEBW4IF_OPER_STATUS@@@Z; ToString(IF_OPER_STATUS const &)
0x180038b88  mov     r8, rax
0x180038b8b  lea     rdx, [r14+110h]; enum TUNNEL_TYPE *
0x180038b92  lea     rcx, [r14+64h]; unsigned int *
0x180038b96  call    ?ToString@@YAPEB_WAEBKAEBW4TUNNEL_TYPE@@@Z; ToString(ulong const &,TUNNEL_TYPE const &)
0x180038b9b  mov     [rsp+120h+var_C0], rbx
0x180038ba0  mov     [rsp+120h+var_C8], r10
0x180038ba5  mov     [rsp+120h+var_D0], r9
0x180038baa  mov     [rsp+120h+var_D8], r8
0x180038baf  mov     [rsp+120h+var_E0], rax
0x180038bb4  mov     eax, [r14+6Ch]
0x180038bb8  mov     dword ptr [rsp+120h+var_E8], eax
0x180038bbc  mov     eax, [r14+4]
0x180038bc0  mov     dword ptr [rsp+120h+var_F0], eax
0x180038bc4  mov     rax, [r14+0E0h]
0x180038bcb  mov     [rsp+120h+var_F8], rax
0x180038bd0  mov     rax, [r14+40h]
0x180038bd4  mov     [rsp+120h+var_100], rax
0x180038bd9  mov     r9, [r14+48h]
0x180038bdd  mov     r8, [r14+10h]
0x180038be1  lea     rdx, aGetadaptersadd_0; "\n >>>>>> GetAdaptersAddresses Adapter "...
0x180038be8  mov     rcx, r15
0x180038beb  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038bf0  mov     [rbp+57h+var_70], 1
0x180038bf7  lea     rcx, [rbp+57h+var_68]
0x180038bfb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038c00  nop
0x180038c01  lea     rcx, [rbp+57h+var_48]
0x180038c05  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038c0a  lea     r12, aWs_1; "    %ws\n"
0x180038c11  cmp     dword ptr [r14+68h], 1
0x180038c16  jnz     loc_180038F3B
0x180038c1c  lea     rdx, aUnicastAddress; "  Unicast Addresses:\n"
0x180038c23  mov     rcx, r15
0x180038c26  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180038c2b  mov     rdi, [r14+18h]
0x180038c2f  jmp     loc_180038CE0
0x180038c34  mov     ecx, [rdi+28h]
0x180038c37  test    ecx, ecx
0x180038c39  jz      short loc_180038C7C
0x180038c3b  sub     ecx, 1
0x180038c3e  jz      short loc_180038C73
0x180038c40  sub     ecx, 1
0x180038c43  jz      short loc_180038C6A
0x180038c45  sub     ecx, 1
0x180038c48  jz      short loc_180038C61
0x180038c4a  cmp     ecx, 1
0x180038c4d  jz      short loc_180038C58
0x180038c4f  lea     rsi, aUnknownIpDadSt; "(unknown IP_DAD_STATE)"
0x180038c56  jmp     short loc_180038C83
0x180038c58  lea     rsi, aIpdadstatepref; "IpDadStatePreferred"
0x180038c5f  jmp     short loc_180038C83
0x180038c61  lea     rsi, aIpdadstatedepr; "IpDadStateDeprecated"
0x180038c68  jmp     short loc_180038C83
0x180038c6a  lea     rsi, aIpdadstatedupl; "IpDadStateDuplicate"
0x180038c71  jmp     short loc_180038C83
0x180038c73  lea     rsi, aIpdadstatetent; "IpDadStateTentative"
0x180038c7a  jmp     short loc_180038C83
0x180038c7c  lea     rsi, aIpdadstateinva; "IpDadStateInvalid"
0x180038c83  movzx   ebx, byte ptr [rdi+38h]
0x180038c87  mov     r8d, [rdi+18h]
0x180038c8b  mov     rdx, [rdi+10h]
0x180038c8f  lea     rcx, [rbp+57h+var_B0]
0x180038c93  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBUsockaddr@@K@Z; ToString(sockaddr const *,ulong)
0x180038c98  nop
0x180038c99  mov     rcx, rax
0x180038c9c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038ca1  mov     [rsp+120h+var_100], rsi
0x180038ca6  mov     r9d, ebx
0x180038ca9  mov     r8, rax
0x180038cac  lea     rdx, aWsUWs; "    %ws / %u (%ws)\n"
0x180038cb3  lea     rcx, [rbp+57h+var_90]
0x180038cb7  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038cbc  nop
0x180038cbd  mov     rdx, rax
0x180038cc0  mov     rcx, r15
0x180038cc3  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038cc8  nop
0x180038cc9  lea     rcx, [rbp+57h+var_90]
0x180038ccd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038cd2  nop
0x180038cd3  lea     rcx, [rbp+57h+var_B0]
0x180038cd7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038cdc  mov     rdi, [rdi+8]
0x180038ce0  test    rdi, rdi
0x180038ce3  jnz     loc_180038C34
0x180038ce9  mov     rbx, [r14+28h]
0x180038ced  jmp     short loc_180038D40
0x180038cef  mov     r8d, [rbx+18h]
0x180038cf3  mov     rdx, [rbx+10h]
0x180038cf7  lea     rcx, [rbp+57h+var_90]
0x180038cfb  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBUsockaddr@@K@Z; ToString(sockaddr const *,ulong)
0x180038d00  nop
0x180038d01  mov     rcx, rax
0x180038d04  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038d09  mov     r8, rax
0x180038d0c  lea     rdx, aWsMulticast; "    %ws (multicast)\n"
0x180038d13  lea     rcx, [rbp+57h+var_B0]
0x180038d17  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038d1c  nop
0x180038d1d  mov     rdx, rax
0x180038d20  mov     rcx, r15
0x180038d23  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038d28  nop
0x180038d29  lea     rcx, [rbp+57h+var_B0]
0x180038d2d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038d32  nop
0x180038d33  lea     rcx, [rbp+57h+var_90]
0x180038d37  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038d3c  mov     rbx, [rbx+8]
0x180038d40  test    rbx, rbx
0x180038d43  jnz     short loc_180038CEF
0x180038d45  mov     rbx, [r14+20h]
0x180038d49  jmp     short loc_180038D9C
0x180038d4b  mov     r8d, [rbx+18h]
0x180038d4f  mov     rdx, [rbx+10h]
0x180038d53  lea     rcx, [rbp+57h+var_90]
0x180038d57  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBUsockaddr@@K@Z; ToString(sockaddr const *,ulong)
0x180038d5c  nop
0x180038d5d  mov     rcx, rax
0x180038d60  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038d65  mov     r8, rax
0x180038d68  lea     rdx, aWsAnycast; "    %ws (anycast)\n"
0x180038d6f  lea     rcx, [rbp+57h+var_B0]
0x180038d73  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038d78  nop
0x180038d79  mov     rdx, rax
0x180038d7c  mov     rcx, r15
0x180038d7f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038d84  nop
0x180038d85  lea     rcx, [rbp+57h+var_B0]
0x180038d89  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038d8e  nop
0x180038d8f  lea     rcx, [rbp+57h+var_90]
0x180038d93  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038d98  mov     rbx, [rbx+8]
0x180038d9c  test    rbx, rbx
0x180038d9f  jnz     short loc_180038D4B
0x180038da1  mov     rbx, [r14+0B0h]
0x180038da8  jmp     short loc_180038DFB
0x180038daa  mov     r8d, [rbx+18h]
0x180038dae  mov     rdx, [rbx+10h]
0x180038db2  lea     rcx, [rbp+57h+var_90]
0x180038db6  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBUsockaddr@@K@Z; ToString(sockaddr const *,ulong)
0x180038dbb  nop
0x180038dbc  mov     rcx, rax
0x180038dbf  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038dc4  mov     r8, rax
0x180038dc7  lea     rdx, aWsPrefix; "    %ws (prefix)\n"
0x180038dce  lea     rcx, [rbp+57h+var_B0]
0x180038dd2  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038dd7  nop
0x180038dd8  mov     rdx, rax
0x180038ddb  mov     rcx, r15
0x180038dde  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038de3  nop
0x180038de4  lea     rcx, [rbp+57h+var_B0]
0x180038de8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038ded  nop
0x180038dee  lea     rcx, [rbp+57h+var_90]
0x180038df2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038df7  mov     rbx, [rbx+8]
0x180038dfb  test    rbx, rbx
0x180038dfe  jnz     short loc_180038DAA
0x180038e00  lea     rdx, aGatewayAddress; "  Gateway Addresses:\n"
0x180038e07  mov     rcx, r15
0x180038e0a  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180038e0f  mov     rbx, [r14+0D0h]
0x180038e16  jmp     short loc_180038E65
0x180038e18  mov     r8d, [rbx+18h]
0x180038e1c  mov     rdx, [rbx+10h]
0x180038e20  lea     rcx, [rbp+57h+var_90]
0x180038e24  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBUsockaddr@@K@Z; ToString(sockaddr const *,ulong)
0x180038e29  nop
0x180038e2a  mov     rcx, rax
0x180038e2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038e32  mov     r8, rax
0x180038e35  mov     rdx, r12
0x180038e38  lea     rcx, [rbp+57h+var_B0]
0x180038e3c  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038e41  nop
0x180038e42  mov     rdx, rax
0x180038e45  mov     rcx, r15
0x180038e48  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038e4d  nop
0x180038e4e  lea     rcx, [rbp+57h+var_B0]
0x180038e52  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038e57  nop
0x180038e58  lea     rcx, [rbp+57h+var_90]
0x180038e5c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038e61  mov     rbx, [rbx+8]
0x180038e65  test    rbx, rbx
0x180038e68  jnz     short loc_180038E18
0x180038e6a  lea     rdx, aWinsAddresses; "  WINS Addresses:\n"
0x180038e71  mov     rcx, r15
0x180038e74  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180038e79  mov     rbx, [r14+0C8h]
0x180038e80  jmp     short loc_180038ECF
0x180038e82  mov     r8d, [rbx+18h]
0x180038e86  mov     rdx, [rbx+10h]
0x180038e8a  lea     rcx, [rbp+57h+var_90]
0x180038e8e  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBUsockaddr@@K@Z; ToString(sockaddr const *,ulong)
0x180038e93  nop
0x180038e94  mov     rcx, rax
0x180038e97  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038e9c  mov     r8, rax
0x180038e9f  mov     rdx, r12
0x180038ea2  lea     rcx, [rbp+57h+var_B0]
0x180038ea6  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038eab  nop
0x180038eac  mov     rdx, rax
0x180038eaf  mov     rcx, r15
0x180038eb2  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038eb7  nop
0x180038eb8  lea     rcx, [rbp+57h+var_B0]
0x180038ebc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038ec1  nop
0x180038ec2  lea     rcx, [rbp+57h+var_90]
0x180038ec6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038ecb  mov     rbx, [rbx+8]
0x180038ecf  test    rbx, rbx
0x180038ed2  jnz     short loc_180038E82
0x180038ed4  lea     rdx, aDnsServerAddre; "  DNS Server Addresses:\n"
0x180038edb  mov     rcx, r15
0x180038ede  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180038ee3  mov     rbx, [r14+30h]
0x180038ee7  jmp     short loc_180038F36
0x180038ee9  mov     r8d, [rbx+18h]
0x180038eed  mov     rdx, [rbx+10h]
0x180038ef1  lea     rcx, [rbp+57h+var_90]
0x180038ef5  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBUsockaddr@@K@Z; ToString(sockaddr const *,ulong)
0x180038efa  nop
0x180038efb  mov     rcx, rax
0x180038efe  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180038f03  mov     r8, rax
0x180038f06  mov     rdx, r12
0x180038f09  lea     rcx, [rbp+57h+var_B0]
0x180038f0d  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038f12  nop
0x180038f13  mov     rdx, rax
0x180038f16  mov     rcx, r15
0x180038f19  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038f1e  nop
0x180038f1f  lea     rcx, [rbp+57h+var_B0]
0x180038f23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038f28  nop
0x180038f29  lea     rcx, [rbp+57h+var_90]
0x180038f2d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038f32  mov     rbx, [rbx+8]
0x180038f36  test    rbx, rbx
0x180038f39  jnz     short loc_180038EE9
0x180038f3b  mov     r8, [r14+38h]
0x180038f3f  lea     rdx, aPrimaryDnsSuff; "  Primary DNS Suffix: %ws\n"
0x180038f46  lea     rcx, [rbp+57h+var_B0]
0x180038f4a  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180038f4f  nop
0x180038f50  mov     rdx, rax
0x180038f53  mov     rcx, r15
0x180038f56  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180038f5b  nop
0x180038f5c  lea     rcx, [rbp+57h+var_B0]
0x180038f60  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038f65  lea     rdx, aDnsSuffixes; "  DNS Suffixes:\n"
0x180038f6c  mov     rcx, r15
0x180038f6f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x180038f74  mov     rbx, [r14+1B8h]
0x180038f7b  jmp     short loc_180038FA6
  ... truncated ...
```
