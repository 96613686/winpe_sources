# LogIfEntryInformation(_NET_LUID_LH const &)

- ea: `0x180039b84`
- end: `0x180039f6a`
- name: `?LogIfEntryInformation@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBT_NET_LUID_LH@@@Z`
- size: `998`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task`

## callers

- `0x18000f888`

## callees

- `0x18000f388`
- `0x180010124`
- `0x180011614`
- `0x1800120d0`
- `0x180012f40`
- `0x18002a3e4`
- `0x180039b84`
- `0x18003a37c`
- `0x18003a624`
- `0x18003a79c`
- `0x18003b3f8`
- `0x18003b570`
- `0x18003b694`
- `0x18003b7cc`

## import_xrefs

- `IPHLPAPI!GetIfEntry2Ex` at `0x180039bdd`
- `IPHLPAPI!GetIfEntry2Ex` at `0x180039bdd`

## string_xrefs

- `0x180039ced`: `NET_IF_ACCESS_BROADCAST`
- `0x180039ce4`: `NET_IF_ACCESS_POINT_TO_POINT`
- `0x180039cf6`: `NET_IF_ACCESS_LOOPBACK`
- `0x180039cdb`: `NET_IF_ACCESS_POINT_TO_MULTI_POINT`
- `0x180039cd2`: `(unknown NET_IF_ACCESS_TYPE)`
- `0x180039bf1`: `onecore\net\netprofiles\service\src\netshnlmplugin\log.cpp`
- `0x180039f04`: `\n >>>>>> GetIfEntry2Ex Information <<<<<<\n  Alias: %ws\n  Description: %ws\n  NetworkGuid: %ws\n  InterfaceGuid: %ws\n  InterfaceLuid: 0x%I64x\n  InterfaceIndex: %u\n  IfType: %ws\n  OperStatus: %ws\n  AdminStatus: %ws\n  MediaConnectState: %ws\n  AccessType: %ws\n  DirectionType: %ws\n  ConnectionType: %ws\n  MediaType: %ws\n  PhysicalMediumType: %ws\n  HardwareInterface: %u\n  FilterInterface: %u\n  ConnectorPresent: %u\n  NotAuthenticated: %u\n  NotMediaConnected: %u\n  Paused: %u\n  LowPow`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LogIfEntryInformation(__int64 a1, __int64 *a2)
{
  unsigned int IfEntry2; // eax
  const wchar_t *v4; // rdx
  const wchar_t *v5; // r13
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rax
  const wchar_t *v8; // r12
  const wchar_t *v9; // r15
  __int64 v10; // r14
  __int64 v11; // rax
  unsigned int v13; // [rsp+20h] [rbp-150h]
  const wchar_t *v14; // [rsp+F0h] [rbp-80h]
  const wchar_t *v15; // [rsp+F8h] [rbp-78h]
  const wchar_t *v16; // [rsp+100h] [rbp-70h]
  const wchar_t *v17; // [rsp+108h] [rbp-68h]
  __int64 v18; // [rsp+118h] [rbp-58h]
  __int64 v19; // [rsp+120h] [rbp-50h]
  const wchar_t *v20; // [rsp+128h] [rbp-48h]
  const wchar_t *v21; // [rsp+130h] [rbp-40h]
  _BYTE v23[32]; // [rsp+140h] [rbp-30h] BYREF
  _BYTE v24[32]; // [rsp+160h] [rbp-10h] BYREF
  _BYTE v25[32]; // [rsp+180h] [rbp+10h] BYREF
  _BYTE v26[32]; // [rsp+1A0h] [rbp+30h] BYREF
  __int64 v27; // [rsp+1C0h] [rbp+50h] BYREF
  int v28; // [rsp+1C8h] [rbp+58h] BYREF
  _BYTE v29[16]; // [rsp+1CCh] [rbp+5Ch] BYREF
  _BYTE v30[514]; // [rsp+1DCh] [rbp+6Ch] BYREF
  _BYTE v31[514]; // [rsp+3DEh] [rbp+26Eh] BYREF
  unsigned int v32; // [rsp+5E0h] [rbp+470h]
  _BYTE v33[32]; // [rsp+5E4h] [rbp+474h] BYREF
  _BYTE v34[32]; // [rsp+604h] [rbp+494h] BYREF
  int v35; // [rsp+624h] [rbp+4B4h]
  unsigned int v36; // [rsp+628h] [rbp+4B8h] BYREF
  enum TUNNEL_TYPE v37; // [rsp+62Ch] [rbp+4BCh] BYREF
  enum _NDIS_MEDIUM v38; // [rsp+630h] [rbp+4C0h] BYREF
  enum _NDIS_PHYSICAL_MEDIUM v39; // [rsp+634h] [rbp+4C4h] BYREF
  int v40; // [rsp+638h] [rbp+4C8h]
  int v41; // [rsp+63Ch] [rbp+4CCh]
  unsigned __int8 v42; // [rsp+640h] [rbp+4D0h]
  enum IF_OPER_STATUS v43; // [rsp+644h] [rbp+4D4h] BYREF
  int v44; // [rsp+648h] [rbp+4D8h]
  int v45; // [rsp+64Ch] [rbp+4DCh]
  _BYTE v46[16]; // [rsp+650h] [rbp+4E0h] BYREF
  enum _NET_IF_CONNECTION_TYPE v47; // [rsp+660h] [rbp+4F0h] BYREF
  __int64 v48; // [rsp+668h] [rbp+4F8h]
  __int64 v49; // [rsp+670h] [rbp+500h]
  wil::details::in1diag3 *retaddr; // [rsp+758h] [rbp+5E8h]

  memset_0(&v28, 0, 0x540u);
  v27 = *a2;
  IfEntry2 = GetIfEntry2Ex(0, &v27);
  if ( IfEntry2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\log.cpp",
      (const char *)IfEntry2,
      v13);
  ToString(v26, v34, 32);
  v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v25, v33, v32);
  v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v20 = ToString(&v39);
  v21 = ToString(&v38);
  v17 = ToString(&v47);
  if ( v41 )
  {
    if ( v41 == 1 )
    {
      v4 = L"NET_IF_DIRECTION_SENDONLY";
    }
    else if ( v41 == 2 )
    {
      v4 = L"NET_IF_DIRECTION_RECEIVEONLY";
    }
    else
    {
      v4 = L"(unknown NET_IF_DIRECTION_TYPE)";
    }
    v14 = v4;
  }
  else
  {
    v14 = L"NET_IF_DIRECTION_SENDRECEIVE";
  }
  switch ( v40 )
  {
    case 1:
      v5 = L"NET_IF_ACCESS_LOOPBACK";
      break;
    case 2:
      v5 = L"NET_IF_ACCESS_BROADCAST";
      break;
    case 3:
      v5 = L"NET_IF_ACCESS_POINT_TO_POINT";
      break;
    case 4:
      v5 = L"NET_IF_ACCESS_POINT_TO_MULTI_POINT";
      break;
    default:
      v5 = L"(unknown NET_IF_ACCESS_TYPE)";
      break;
  }
  if ( v45 )
  {
    if ( v45 == 1 )
    {
      v6 = L"MediaConnectStateConnected";
    }
    else if ( v45 == 2 )
    {
      v6 = L"MediaConnectStateDisconnected";
    }
    else
    {
      v6 = L"(unknown NET_IF_MEDIA_CONNECT_STATE)";
    }
    v15 = v6;
  }
  else
  {
    v15 = L"MediaConnectStateUnknown";
  }
  switch ( v44 )
  {
    case 1:
      v7 = L"NET_IF_ADMIN_STATUS_UP";
      break;
    case 2:
      v7 = L"NET_IF_ADMIN_STATUS_DOWN";
      break;
    case 3:
      v7 = L"NET_IF_ADMIN_STATUS_TESTING";
      break;
    default:
      v7 = L"(unknown NET_IF_ADMIN_STATUS)";
      break;
  }
  v16 = v7;
  v8 = ToString(&v43);
  v9 = ToString(&v36, &v37);
  ToString(v24, v29);
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  ToString(v23, v46);
  v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  wil::str_printf<std::wstring>(
    a1,
    (__int64)L"\n"
              " >>>>>> GetIfEntry2Ex Information <<<<<<\n"
              "  Alias: %ws\n"
              "  Description: %ws\n"
              "  NetworkGuid: %ws\n"
              "  InterfaceGuid: %ws\n"
              "  InterfaceLuid: 0x%I64x\n"
              "  InterfaceIndex: %u\n"
              "  IfType: %ws\n"
              "  OperStatus: %ws\n"
              "  AdminStatus: %ws\n"
              "  MediaConnectState: %ws\n"
              "  AccessType: %ws\n"
              "  DirectionType: %ws\n"
              "  ConnectionType: %ws\n"
              "  MediaType: %ws\n"
              "  PhysicalMediumType: %ws\n"
              "  HardwareInterface: %u\n"
              "  FilterInterface: %u\n"
              "  ConnectorPresent: %u\n"
              "  NotAuthenticated: %u\n"
              "  NotMediaConnected: %u\n"
              "  Paused: %u\n"
              "  LowPower: %u\n"
              "  EndPointInterface: %u\n"
              "  TransmitLinkSpeed: %llu\n"
              "  ReceiveLinkSpeed: %llu\n"
              "  Mtu: %u\n"
              "  PhysicalAddress: %ws\n"
              "  PermanentPhysicalAddress: %ws\n",
    v30,
    v31,
    v11,
    v10,
    v27,
    v28,
    v9,
    v8,
    v16,
    v15,
    v5,
    v14,
    v17,
    v21,
    v20,
    v42 & 1,
    (v42 >> 1) & 1,
    (v42 >> 2) & 1,
    (v42 >> 3) & 1,
    (v42 >> 4) & 1,
    (v42 >> 5) & 1,
    (v42 >> 6) & 1,
    v42 >> 7,
    v48,
    v49,
    v35,
    v19,
    v18);
  std::wstring::_Tidy_deallocate((__int64)v23);
  std::wstring::_Tidy_deallocate((__int64)v24);
  std::wstring::_Tidy_deallocate((__int64)v25);
  std::wstring::_Tidy_deallocate((__int64)v26);
  return a1;
}

```

## disassembly

```asm
0x180039b84  mov     [rsp-8+arg_10], rbx
0x180039b89  push    rbp
0x180039b8a  push    rsi
0x180039b8b  push    rdi
0x180039b8c  push    r12
0x180039b8e  push    r13
0x180039b90  push    r14
0x180039b92  push    r15
0x180039b94  lea     rbp, [rsp-5B0h]
0x180039b9c  sub     rsp, 720h
0x180039ba3  mov     rax, cs:__security_cookie
0x180039baa  xor     rax, rsp
0x180039bad  mov     [rbp+5E0h+var_40], rax
0x180039bb4  mov     rbx, rdx
0x180039bb7  mov     [rbp+5E0h+var_618], rcx
0x180039bbb  mov     [rbp+5E0h+var_648], rcx
0x180039bbf  xor     edx, edx; Val
0x180039bc1  mov     r8d, 540h; Size
0x180039bc7  lea     rcx, [rbp+5E0h+var_588]; void *
0x180039bcb  call    memset_0
0x180039bd0  mov     rax, [rbx]
0x180039bd3  mov     [rbp+5E0h+var_590], rax
0x180039bd7  lea     rdx, [rbp+5E0h+var_590]
0x180039bdb  xor     ecx, ecx
0x180039bdd  call    cs:__imp_GetIfEntry2Ex
0x180039be3  mov     rcx, [rbp+5E8h]; this
0x180039bea  test    eax, eax
0x180039bec  jz      short loc_180039C03
0x180039bee  mov     r9d, eax; char *
0x180039bf1  lea     r8, aOnecoreNetNetp_0; "onecore\\net\\netprofiles\\service\\src"...
0x180039bf8  mov     edx, 42Dh; void *
0x180039bfd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180039c03  mov     r8d, 20h ; ' '
0x180039c09  lea     rdx, [rbp+5E0h+var_14C]
0x180039c10  lea     rcx, [rbp+5E0h+var_5B0]
0x180039c14  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBEK@Z; ToString(uchar const *,ulong)
0x180039c19  nop
0x180039c1a  mov     rcx, rax
0x180039c1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180039c22  mov     [rbp+5E0h+var_638], rax
0x180039c26  mov     r8d, [rbp+5E0h+var_170]
0x180039c2d  lea     rdx, [rbp+5E0h+var_16C]
0x180039c34  lea     rcx, [rbp+5E0h+var_5D0]
0x180039c38  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBEK@Z; ToString(uchar const *,ulong)
0x180039c3d  nop
0x180039c3e  mov     rcx, rax
0x180039c41  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180039c46  mov     [rbp+5E0h+var_630], rax
0x180039c4a  lea     rcx, [rbp+5E0h+var_11C]; enum _NDIS_PHYSICAL_MEDIUM *
0x180039c51  call    ?ToString@@YAPEB_WAEBW4_NDIS_PHYSICAL_MEDIUM@@@Z; ToString(_NDIS_PHYSICAL_MEDIUM const &)
0x180039c56  mov     [rbp+5E0h+var_628], rax
0x180039c5a  lea     rcx, [rbp+5E0h+var_120]; enum _NDIS_MEDIUM *
0x180039c61  call    ?ToString@@YAPEB_WAEBW4_NDIS_MEDIUM@@@Z; ToString(_NDIS_MEDIUM const &)
0x180039c66  mov     [rbp+5E0h+var_620], rax
0x180039c6a  lea     rcx, [rbp+5E0h+var_F0]; enum _NET_IF_CONNECTION_TYPE *
0x180039c71  call    ?ToString@@YAPEB_WAEBW4_NET_IF_CONNECTION_TYPE@@@Z; ToString(_NET_IF_CONNECTION_TYPE const &)
0x180039c76  mov     [rbp+5E0h+var_648], rax
0x180039c7a  mov     ecx, [rbp+5E0h+var_114]
0x180039c80  test    ecx, ecx
0x180039c82  jz      short loc_180039CAD
0x180039c84  sub     ecx, 1
0x180039c87  jz      short loc_180039CA0
0x180039c89  cmp     ecx, 1
0x180039c8c  jz      short loc_180039C97
0x180039c8e  lea     rdx, aUnknownNetIfDi; "(unknown NET_IF_DIRECTION_TYPE)"
0x180039c95  jmp     short loc_180039CA7
0x180039c97  lea     rdx, aNetIfDirection; "NET_IF_DIRECTION_RECEIVEONLY"
0x180039c9e  jmp     short loc_180039CA7
0x180039ca0  lea     rdx, aNetIfDirection_1; "NET_IF_DIRECTION_SENDONLY"
0x180039ca7  mov     [rbp+5E0h+var_660], rdx
0x180039cab  jmp     short loc_180039CB8
0x180039cad  lea     rax, aNetIfDirection_0; "NET_IF_DIRECTION_SENDRECEIVE"
0x180039cb4  mov     [rbp+5E0h+var_660], rax
0x180039cb8  mov     ecx, [rbp+5E0h+var_118]
0x180039cbe  sub     ecx, 1
0x180039cc1  jz      short loc_180039CF6
0x180039cc3  sub     ecx, 1
0x180039cc6  jz      short loc_180039CED
0x180039cc8  sub     ecx, 1
0x180039ccb  jz      short loc_180039CE4
0x180039ccd  cmp     ecx, 1
0x180039cd0  jz      short loc_180039CDB
0x180039cd2  lea     r13, aUnknownNetIfAc; "(unknown NET_IF_ACCESS_TYPE)"
0x180039cd9  jmp     short loc_180039CFD
0x180039cdb  lea     r13, aNetIfAccessPoi_0; "NET_IF_ACCESS_POINT_TO_MULTI_POINT"
0x180039ce2  jmp     short loc_180039CFD
0x180039ce4  lea     r13, aNetIfAccessPoi; "NET_IF_ACCESS_POINT_TO_POINT"
0x180039ceb  jmp     short loc_180039CFD
0x180039ced  lea     r13, aNetIfAccessBro; "NET_IF_ACCESS_BROADCAST"
0x180039cf4  jmp     short loc_180039CFD
0x180039cf6  lea     r13, aNetIfAccessLoo; "NET_IF_ACCESS_LOOPBACK"
0x180039cfd  mov     ecx, [rbp+5E0h+var_104]
0x180039d03  test    ecx, ecx
0x180039d05  jz      short loc_180039D30
0x180039d07  sub     ecx, 1
0x180039d0a  jz      short loc_180039D23
0x180039d0c  cmp     ecx, 1
0x180039d0f  jz      short loc_180039D1A
0x180039d11  lea     rdx, aUnknownNetIfMe; "(unknown NET_IF_MEDIA_CONNECT_STATE)"
0x180039d18  jmp     short loc_180039D2A
0x180039d1a  lea     rdx, aMediaconnectst; "MediaConnectStateDisconnected"
0x180039d21  jmp     short loc_180039D2A
0x180039d23  lea     rdx, aMediaconnectst_0; "MediaConnectStateConnected"
0x180039d2a  mov     [rbp+5E0h+var_658], rdx
0x180039d2e  jmp     short loc_180039D3B
0x180039d30  lea     rax, aMediaconnectst_1; "MediaConnectStateUnknown"
0x180039d37  mov     [rbp+5E0h+var_658], rax
0x180039d3b  mov     ecx, [rbp+5E0h+var_108]
0x180039d41  sub     ecx, 1
0x180039d44  jz      short loc_180039D6B
0x180039d46  sub     ecx, 1
0x180039d49  jz      short loc_180039D62
0x180039d4b  cmp     ecx, 1
0x180039d4e  jz      short loc_180039D59
0x180039d50  lea     rax, aUnknownNetIfAd; "(unknown NET_IF_ADMIN_STATUS)"
0x180039d57  jmp     short loc_180039D72
0x180039d59  lea     rax, aNetIfAdminStat_1; "NET_IF_ADMIN_STATUS_TESTING"
0x180039d60  jmp     short loc_180039D72
0x180039d62  lea     rax, aNetIfAdminStat_0; "NET_IF_ADMIN_STATUS_DOWN"
0x180039d69  jmp     short loc_180039D72
0x180039d6b  lea     rax, aNetIfAdminStat; "NET_IF_ADMIN_STATUS_UP"
0x180039d72  mov     [rbp+5E0h+var_650], rax
0x180039d76  lea     rcx, [rbp+5E0h+var_10C]; enum IF_OPER_STATUS *
0x180039d7d  call    ?ToString@@YAPEB_WAEBW4IF_OPER_STATUS@@@Z; ToString(IF_OPER_STATUS const &)
0x180039d82  mov     r12, rax
0x180039d85  lea     rdx, [rbp+5E0h+var_124]; enum TUNNEL_TYPE *
0x180039d8c  lea     rcx, [rbp+5E0h+var_128]; unsigned int *
0x180039d93  call    ?ToString@@YAPEB_WAEBKAEBW4TUNNEL_TYPE@@@Z; ToString(ulong const &,TUNNEL_TYPE const &)
0x180039d98  mov     r15, rax
0x180039d9b  lea     rdx, [rbp+5E0h+var_584]
0x180039d9f  lea     rcx, [rbp+5E0h+var_5F0]
0x180039da3  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x180039da8  nop
0x180039da9  mov     rcx, rax
0x180039dac  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180039db1  mov     r14, rax
0x180039db4  lea     rdx, [rbp+5E0h+var_100]
0x180039dbb  lea     rcx, [rbp+5E0h+var_610]
0x180039dbf  call    ?ToString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@@Z; ToString(_GUID const &)
0x180039dc4  nop
0x180039dc5  mov     rcx, rax
0x180039dc8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180039dcd  mov     rsi, rax
0x180039dd0  movzx   edi, [rbp+5E0h+var_110]
0x180039dd7  mov     ebx, edi
0x180039dd9  shr     ebx, 7
0x180039ddc  mov     r11d, edi
0x180039ddf  shr     r11d, 6
0x180039de3  mov     eax, 1
0x180039de8  and     r11d, eax
0x180039deb  mov     r10d, edi
0x180039dee  shr     r10d, 5
0x180039df2  and     r10d, eax
0x180039df5  mov     r9d, edi
0x180039df8  shr     r9d, 4
0x180039dfc  and     r9d, eax
0x180039dff  mov     r8d, edi
0x180039e02  shr     r8d, 3
0x180039e06  and     r8d, eax
0x180039e09  mov     edx, edi
0x180039e0b  shr     edx, 2
0x180039e0e  and     edx, eax
0x180039e10  mov     ecx, edi
0x180039e12  shr     ecx, 1
0x180039e14  and     ecx, eax
0x180039e16  and     edi, eax
0x180039e18  mov     rax, [rbp+5E0h+var_638]
0x180039e1c  mov     [rsp+750h+var_668], rax
0x180039e24  mov     rax, [rbp+5E0h+var_630]
0x180039e28  mov     [rsp+750h+var_670], rax
0x180039e30  mov     eax, [rbp+5E0h+var_12C]
0x180039e36  mov     [rsp+750h+var_678], eax
0x180039e3d  mov     rax, [rbp+5E0h+var_E0]
0x180039e44  mov     [rsp+750h+var_680], rax
0x180039e4c  mov     rax, [rbp+5E0h+var_E8]
0x180039e53  mov     [rsp+750h+var_688], rax
0x180039e5b  mov     [rsp+750h+var_690], ebx
0x180039e62  mov     [rsp+750h+var_698], r11d
0x180039e6a  mov     [rsp+750h+var_6A0], r10d
0x180039e72  mov     [rsp+750h+var_6A8], r9d
0x180039e7a  mov     [rsp+750h+var_6B0], r8d
0x180039e82  mov     [rsp+750h+var_6B8], edx
0x180039e89  mov     [rsp+750h+var_6C0], ecx
0x180039e90  mov     [rsp+750h+var_6C8], edi
0x180039e97  mov     rax, [rbp+5E0h+var_628]
0x180039e9b  mov     [rsp+750h+var_6D0], rax
0x180039ea3  mov     rax, [rbp+5E0h+var_620]
0x180039ea7  mov     [rsp+750h+var_6D8], rax
0x180039eac  mov     rax, [rbp+5E0h+var_648]
0x180039eb0  mov     [rsp+750h+var_6E0], rax
0x180039eb5  mov     rax, [rbp+5E0h+var_660]
0x180039eb9  mov     [rsp+750h+var_6E8], rax
0x180039ebe  mov     [rsp+750h+var_6F0], r13
0x180039ec3  mov     rax, [rbp+5E0h+var_658]
0x180039ec7  mov     [rsp+750h+var_6F8], rax
0x180039ecc  mov     rax, [rbp+5E0h+var_650]
0x180039ed0  mov     [rsp+750h+var_700], rax
0x180039ed5  mov     [rsp+750h+var_708], r12
0x180039eda  mov     [rsp+750h+var_710], r15
0x180039edf  mov     eax, [rbp+5E0h+var_588]
0x180039ee2  mov     [rsp+750h+var_718], eax
0x180039ee6  mov     rax, [rbp+5E0h+var_590]
0x180039eea  mov     [rsp+750h+var_720], rax
0x180039eef  mov     [rsp+750h+var_728], r14
0x180039ef4  mov     [rsp+750h+var_730], rsi
0x180039ef9  lea     r9, [rbp+5E0h+var_372]
0x180039f00  lea     r8, [rbp+5E0h+var_574]
0x180039f04  lea     rdx, aGetifentry2exI; "\n >>>>>> GetIfEntry2Ex Information <<<"...
0x180039f0b  mov     rcx, [rbp+5E0h+var_618]
0x180039f0f  call    ??$str_printf@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WZZ; wil::str_printf<std::wstring>(wchar_t const *,...)
0x180039f14  nop
0x180039f15  lea     rcx, [rbp+5E0h+var_610]
0x180039f19  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039f1e  nop
0x180039f1f  lea     rcx, [rbp+5E0h+var_5F0]
0x180039f23  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039f28  nop
0x180039f29  lea     rcx, [rbp+5E0h+var_5D0]
0x180039f2d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039f32  nop
0x180039f33  lea     rcx, [rbp+5E0h+var_5B0]
0x180039f37  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039f3c  mov     rax, [rbp+5E0h+var_618]
0x180039f40  mov     rcx, [rbp+5E0h+var_40]
0x180039f47  xor     rcx, rsp; StackCookie
0x180039f4a  call    __security_check_cookie
0x180039f4f  mov     rbx, [rsp+750h+arg_10]
0x180039f57  add     rsp, 720h
0x180039f5e  pop     r15
0x180039f60  pop     r14
0x180039f62  pop     r13
0x180039f64  pop     r12
0x180039f66  pop     rdi
0x180039f67  pop     rsi
0x180039f68  pop     rbp
0x180039f69  retn
```
