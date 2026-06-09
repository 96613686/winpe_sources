# NatShutdown(bool)

- ea: `0x180074c04`
- end: `0x1800750ff`
- name: `?NatShutdown@@YAX_N@Z`
- size: `1275`
- prototype: `void __fastcall(bool, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180042360`
- `0x18006eab0`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180031d04`
- `0x1800321b8`
- `0x180037914`
- `0x18003b220`
- `0x180042114`
- `0x180042974`
- `0x180042c18`
- `0x18004561c`
- `0x1800457ec`
- `0x18004774c`
- `0x18004aef8`
- `0x18004b07c`
- `0x18004ef24`
- `0x18004fd9c`
- `0x180051f30`
- `0x180052bf4`
- `0x180063ec4`
- `0x180063f78`
- `0x1800744e4`
- `0x180074c04`
- `0x180076dac`
- `0x180076eec`
- `0x1800777ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074f56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074f56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074f6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074f3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074fbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074f3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074fbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074f84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074fd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074f84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074fd4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180074ee4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180074ee4`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180074cb9`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x180074cb9`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x180074d3c`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x180074d3c`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180074e9c`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180074e9c`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180074cff`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180074cff`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180074faf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180074faf`
- `dhcpcsvc!DhcpEnableDhcp` at `0x180074d83`
- `dhcpcsvc!DhcpEnableDhcp` at `0x180074d83`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NatShutdown(bool a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG v5; // edi
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int InterfaceTypeByInterfaceIndex; // eax
  unsigned int v13; // eax
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v18; // [rsp+20h] [rbp-E0h]
  bool v19; // [rsp+30h] [rbp-D0h] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v21[20]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh]
  struct _GUID v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+70h] [rbp-90h] BYREF
  GUID v25; // [rsp+74h] [rbp-8Ch]
  int v26; // [rsp+84h] [rbp-7Ch]
  struct _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+90h] [rbp-70h] BYREF
  WCHAR InterfaceName[256]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    LOBYTE(a4) = a1;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, a4);
  }
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v5 = g_PrivAddress;
  memset_0(InterfaceName, 0, sizeof(InterfaceName));
  if ( g_PrivIndex == -1 )
    goto LABEL_37;
  v6 = ConvertInterfaceIndexToLuid(g_PrivIndex, &InterfaceLuid);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 141;
LABEL_36:
      WPP_SF_d(v7[2], v8, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v6);
      goto LABEL_37;
    }
    goto LABEL_37;
  }
  InitializeUnicastIpAddressEntry(&Row);
  Row.InterfaceLuid = InterfaceLuid;
  Row.InterfaceIndex = g_PrivIndex;
  Row.Address.Ipv4.sin_family = 2;
  Row.OnLinkPrefixLength = 24;
  Row.Address.Ipv4.sin_addr.S_un.S_addr = v5;
  v9 = ConvertInterfaceLuidToNameW(&InterfaceLuid, InterfaceName, 0x100u);
  if ( v9 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v11 = 142;
LABEL_21:
      WPP_SF_d(v10[2], v11, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v9);
    }
  }
  else
  {
    v9 = DhcpEnableDhcp(InterfaceName, 1);
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v11 = 143;
        goto LABEL_21;
      }
    }
    else
    {
      InterfaceTypeByInterfaceIndex = SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(g_PrivIndex);
      *(_DWORD *)v21 = 26;
      *(GUID *)&v21[4] = g_PrivateConnectionGuid;
      v22 = InterfaceTypeByInterfaceIndex;
      NetworkingTriageScenario::MobileHotspot::SharedAccessTransitionUpdate(
        (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)v21,
        L"HostedNetMode",
        g_PrivIndex);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          144,
          (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          (unsigned int)InterfaceName,
          Row.Address.Ipv4.sin_addr.S_un.S_un_b.s_b1);
      }
      v19 = 1;
      v13 = SharedAccessUtils::TryPublishWnfStateData(&g_PrivateConnectionGuid, &Row, &v19);
      if ( v13
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF__guid_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          145,
          &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          &g_PrivateConnectionGuid,
          Row.Address.Ipv4.sin_addr.S_un.S_addr,
          v13);
      }
    }
  }
  v6 = DeleteUnicastIpAddressEntry(&Row);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v8 = 146;
      goto LABEL_36;
    }
  }
LABEL_37:
  if ( *(&xmmword_1800AE3F0 + 1) )
    SetEvent(*(&xmmword_1800AE3F0 + 1));
  if ( a1 )
  {
    NatRemoveDhcpPortExceptions();
    NatCloseGroupExceptionForICS();
  }
  NhpStopAddressChangeNotification();
  DeRegisterAddressNotifyChangeAndCleanup();
  DeRegisterForNetworkMediaConnect();
  NatStopProtocol(NatRmStopProtocol, &NhpStopNatEvent);
  NatStopProtocol(AlgRmStopProtocol, &NhpStopAlgEvent);
  EnterCriticalSection(&NhLock);
  NhFreeApplicationSettings();
  v14 = NhpSharedPrivateLanBindingInfo;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v14);
  NhpSharedPrivateLanBindingInfo = 0;
  LeaveCriticalSection(&NhLock);
  if ( NhpComponentModeSet )
  {
    NhResetComponentMode();
    NhpComponentModeSet = 0;
  }
  NatNetConnectionRefreshAll();
  Sleep(0x3E8u);
  EnterCriticalSection(&NhLock);
  g_fIsNatProtocolSet = 0;
  LeaveCriticalSection(&NhLock);
  if ( (unsigned int)GetEnableRebootPersistConnection() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    }
  }
  else
  {
    ResetIcsRegistrySettings();
  }
  *(_QWORD *)v21 = 0;
  v23 = GUID_NULL;
  v16 = NatMapIndexToAdapterEx(gICSPublicAdapterIndex, &v23, (union _NET_LUID_LH *)v21);
  if ( v16 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x7C4,
      (unsigned int)"onecoreuap\\net\\rras\\ip\\nathlp\\natsvc\\svcmain.cpp",
      (const char *)v16,
      v18);
  v17 = SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(g_PrivIndex);
  v24 = 26;
  v25 = g_PrivateConnectionGuid;
  v26 = v17;
  *(struct _GUID *)v21 = v23;
  NetworkingTriageScenario::MobileHotspot::SharedAccessStopped(
    (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)&v24,
    (struct _GUID *)v21,
    gICSPublicAdapterIndex,
    a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
}

```

## disassembly

```asm
0x180074c04  mov     [rsp-8+arg_8], rbx
0x180074c09  mov     [rsp-8+arg_10], rsi
0x180074c0e  push    rbp
0x180074c0f  push    rdi
0x180074c10  push    r12
0x180074c12  push    r13
0x180074c14  push    r15
0x180074c16  lea     rbp, [rsp-1F0h]
0x180074c1e  sub     rsp, 2F0h
0x180074c25  mov     rax, cs:__security_cookie
0x180074c2c  xor     rax, rsp
0x180074c2f  mov     [rbp+210h+var_30], rax
0x180074c36  mov     sil, cl
0x180074c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180074c40  lea     r13, WPP_GLOBAL_Control
0x180074c47  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180074c4e  mov     r15d, 200h
0x180074c54  cmp     rcx, r13
0x180074c57  jz      short loc_180074C79
0x180074c59  test    [rcx+1Ch], r15d
0x180074c5d  jz      short loc_180074C79
0x180074c5f  cmp     byte ptr [rcx+19h], 6
0x180074c63  jb      short loc_180074C79
0x180074c65  mov     rcx, [rcx+10h]
0x180074c69  mov     edx, 8Ch
0x180074c6e  mov     r9b, sil
0x180074c71  mov     r8, r12
0x180074c74  call    WPP_SF_c
0x180074c79  xor     edx, edx; Val
0x180074c7b  mov     qword ptr [rsp+310h+InterfaceLuid], 0
0x180074c84  lea     rcx, [rbp+210h+Row]; void *
0x180074c88  lea     r8d, [rdx+50h]; Size
0x180074c8c  call    memset_0
0x180074c91  mov     edi, cs:?g_PrivAddress@@3KA; ulong g_PrivAddress
0x180074c97  lea     rcx, [rbp+210h+InterfaceName]; void *
0x180074c9b  mov     r8, r15; Size
0x180074c9e  xor     edx, edx; Val
0x180074ca0  call    memset_0
0x180074ca5  mov     ecx, cs:?g_PrivIndex@@3KA; InterfaceIndex
0x180074cab  cmp     ecx, 0FFFFFFFFh
0x180074cae  jz      loc_180074ED8
0x180074cb4  lea     rdx, [rsp+310h+InterfaceLuid]; InterfaceLuid
0x180074cb9  call    cs:__imp_ConvertInterfaceIndexToLuid
0x180074cc0  nop     dword ptr [rax+rax+00h]
0x180074cc5  test    eax, eax
0x180074cc7  jz      short loc_180074CFB
0x180074cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180074cd0  cmp     rcx, r13
0x180074cd3  jz      loc_180074ED8
0x180074cd9  test    [rcx+1Ch], r15d
0x180074cdd  jz      loc_180074ED8
0x180074ce3  mov     ebx, 2
0x180074ce8  cmp     [rcx+19h], bl
0x180074ceb  jb      loc_180074ED8
0x180074cf1  mov     edx, 8Dh
0x180074cf6  jmp     loc_180074EC9
0x180074cfb  lea     rcx, [rbp+210h+Row]; Row
0x180074cff  call    cs:__imp_InitializeUnicastIpAddressEntry
0x180074d06  nop     dword ptr [rax+rax+00h]
0x180074d0b  mov     rax, qword ptr [rsp+310h+InterfaceLuid]
0x180074d10  lea     rdx, [rbp+210h+InterfaceName]; InterfaceName
0x180074d14  mov     qword ptr [rbp+210h+Row.InterfaceLuid], rax
0x180074d18  lea     rcx, [rsp+310h+InterfaceLuid]; InterfaceLuid
0x180074d1d  mov     eax, cs:?g_PrivIndex@@3KA; ulong g_PrivIndex
0x180074d23  mov     ebx, 2
0x180074d28  mov     r8d, 100h; Length
0x180074d2e  mov     [rbp+210h+Row.InterfaceIndex], eax
0x180074d31  mov     word ptr [rbp+210h+Row.Address], bx
0x180074d35  mov     [rbp+210h+Row.OnLinkPrefixLength], 18h
0x180074d39  mov     dword ptr [rbp+210h+Row.Address+4], edi
0x180074d3c  call    cs:__imp_ConvertInterfaceLuidToNameW
0x180074d43  nop     dword ptr [rax+rax+00h]
0x180074d48  mov     dil, 3
0x180074d4b  test    eax, eax
0x180074d4d  jz      short loc_180074D7A
0x180074d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d56  cmp     rcx, r13
0x180074d59  jz      loc_180074E98
0x180074d5f  test    [rcx+1Ch], r15d
0x180074d63  jz      loc_180074E98
0x180074d69  cmp     [rcx+19h], dil
0x180074d6d  jb      loc_180074E98
0x180074d73  mov     edx, 8Eh
0x180074d78  jmp     short loc_180074DBC
0x180074d7a  mov     edx, 1
0x180074d7f  lea     rcx, [rbp+210h+InterfaceName]
0x180074d83  call    cs:__imp_DhcpEnableDhcp
0x180074d8a  nop     dword ptr [rax+rax+00h]
0x180074d8f  test    eax, eax
0x180074d91  jz      short loc_180074DD0
0x180074d93  mov     rcx, cs:WPP_GLOBAL_Control
0x180074d9a  cmp     rcx, r13
0x180074d9d  jz      loc_180074E98
0x180074da3  test    [rcx+1Ch], r15d
0x180074da7  jz      loc_180074E98
0x180074dad  cmp     [rcx+19h], dil
0x180074db1  jb      loc_180074E98
0x180074db7  mov     edx, 8Fh
0x180074dbc  mov     rcx, [rcx+10h]
0x180074dc0  mov     r9d, eax
0x180074dc3  mov     r8, r12
0x180074dc6  call    WPP_SF_d
0x180074dcb  jmp     loc_180074E98
0x180074dd0  mov     ecx, cs:?g_PrivIndex@@3KA; unsigned int
0x180074dd6  call    ?TryGetInterfaceTypeByInterfaceIndex@SharedAccessUtils@@SAKK@Z; SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(ulong)
0x180074ddb  movups  xmm0, xmmword ptr cs:?g_PrivateConnectionGuid@@3U_GUID@@A.Data1; _GUID g_PrivateConnectionGuid ...
0x180074de2  mov     r8d, cs:?g_PrivIndex@@3KA; unsigned int
0x180074de9  lea     rdx, aHostednetmode; "HostedNetMode"
0x180074df0  lea     rcx, [rsp+310h+var_2D0]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x180074df5  mov     dword ptr [rsp+310h+var_2D0], 1Ah
0x180074dfd  movdqu  xmmword ptr [rsp+310h+var_2D0+4], xmm0
0x180074e03  mov     [rsp+310h+var_2BC], eax
0x180074e07  call    ?SharedAccessTransitionUpdate@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBGK@Z; NetworkingTriageScenario::MobileHotspot::SharedAccessTransitionUpdate(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,ushort const *,ulong)
0x180074e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e13  cmp     rcx, r13
0x180074e16  jz      short loc_180074E40
0x180074e18  test    [rcx+1Ch], r15d
0x180074e1c  jz      short loc_180074E40
0x180074e1e  cmp     byte ptr [rcx+19h], 5
0x180074e22  jb      short loc_180074E40
0x180074e24  mov     eax, dword ptr [rbp+210h+Row.Address+4]
0x180074e27  lea     r9, [rbp+210h+InterfaceName]
0x180074e2b  mov     rcx, [rcx+10h]
0x180074e2f  mov     edx, 90h
0x180074e34  mov     r8, r12
0x180074e37  mov     [rsp+310h+var_2F0], eax
0x180074e3b  call    WPP_SF_SD
0x180074e40  lea     r8, [rsp+310h+var_2E0]; bool *
0x180074e45  mov     [rsp+310h+var_2E0], 1
0x180074e4a  lea     rdx, [rbp+210h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x180074e4e  lea     rcx, ?g_PrivateConnectionGuid@@3U_GUID@@A; struct _GUID *
0x180074e55  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x180074e5a  test    eax, eax
0x180074e5c  jz      short loc_180074E98
0x180074e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180074e65  cmp     rcx, r13
0x180074e68  jz      short loc_180074E98
0x180074e6a  test    [rcx+1Ch], r15d
0x180074e6e  jz      short loc_180074E98
0x180074e70  cmp     [rcx+19h], bl
0x180074e73  jb      short loc_180074E98
0x180074e75  mov     rcx, [rcx+10h]
0x180074e79  lea     r9, ?g_PrivateConnectionGuid@@3U_GUID@@A; _GUID g_PrivateConnectionGuid
0x180074e80  mov     [rsp+310h+var_2E8], eax
0x180074e84  mov     edx, 91h
0x180074e89  mov     eax, dword ptr [rbp+210h+Row.Address+4]
0x180074e8c  mov     r8, r12
0x180074e8f  mov     [rsp+310h+var_2F0], eax; unsigned int
0x180074e93  call    WPP_SF__guid_DD
0x180074e98  lea     rcx, [rbp+210h+Row]; Row
0x180074e9c  call    cs:__imp_DeleteUnicastIpAddressEntry
0x180074ea3  nop     dword ptr [rax+rax+00h]
0x180074ea8  test    eax, eax
0x180074eaa  jz      short loc_180074ED8
0x180074eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180074eb3  cmp     rcx, r13
0x180074eb6  jz      short loc_180074ED8
0x180074eb8  test    [rcx+1Ch], r15d
0x180074ebc  jz      short loc_180074ED8
0x180074ebe  cmp     [rcx+19h], dil
0x180074ec2  jb      short loc_180074ED8
0x180074ec4  mov     edx, 92h
0x180074ec9  mov     rcx, [rcx+10h]
0x180074ecd  mov     r9d, eax
0x180074ed0  mov     r8, r12
0x180074ed3  call    WPP_SF_d
0x180074ed8  mov     rcx, qword ptr cs:xmmword_1800AE3F0+8; hEvent
0x180074edf  test    rcx, rcx
0x180074ee2  jz      short loc_180074EF0
0x180074ee4  call    cs:__imp_SetEvent
0x180074eeb  nop     dword ptr [rax+rax+00h]
0x180074ef0  test    sil, sil
0x180074ef3  jz      short loc_180074EFF
0x180074ef5  call    ?NatRemoveDhcpPortExceptions@@YAJXZ; NatRemoveDhcpPortExceptions(void)
0x180074efa  call    ?NatCloseGroupExceptionForICS@@YAJXZ; NatCloseGroupExceptionForICS(void)
0x180074eff  call    ?NhpStopAddressChangeNotification@@YAXXZ; NhpStopAddressChangeNotification(void)
0x180074f04  call    ?DeRegisterAddressNotifyChangeAndCleanup@@YAXXZ; DeRegisterAddressNotifyChangeAndCleanup(void)
0x180074f09  call    ?DeRegisterForNetworkMediaConnect@@YAXXZ; DeRegisterForNetworkMediaConnect(void)
0x180074f0e  lea     rdx, ?NhpStopNatEvent@@3PEAXEA; void **
0x180074f15  lea     rcx, ?NatRmStopProtocol@@YAKXZ; unsigned int (*)(void)
0x180074f1c  call    ?NatStopProtocol@@YAXP6AKXZPEAPEAX@Z; NatStopProtocol(ulong (*)(void),void * *)
0x180074f21  lea     rdx, ?NhpStopAlgEvent@@3PEAXEA; void **
0x180074f28  lea     rcx, ?AlgRmStopProtocol@@YAKXZ; unsigned int (*)(void)
0x180074f2f  call    ?NatStopProtocol@@YAXP6AKXZPEAPEAX@Z; NatStopProtocol(ulong (*)(void),void * *)
0x180074f34  lea     rdi, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION NhLock
0x180074f3b  mov     rcx, rdi; lpCriticalSection
0x180074f3e  call    cs:__imp_EnterCriticalSection
0x180074f45  nop     dword ptr [rax+rax+00h]
0x180074f4a  call    ?NhFreeApplicationSettings@@YAXXZ; NhFreeApplicationSettings(void)
0x180074f4f  mov     rbx, cs:?NhpSharedPrivateLanBindingInfo@@3PEAUIP_ADAPTER_BINDING_INFO@@EA; IP_ADAPTER_BINDING_INFO * NhpSharedPrivateLanBindingInfo
0x180074f56  call    cs:__imp_GetProcessHeap
0x180074f5d  nop     dword ptr [rax+rax+00h]
0x180074f62  mov     r8, rbx; lpMem
0x180074f65  xor     edx, edx; dwFlags
0x180074f67  mov     rcx, rax; hHeap
0x180074f6a  call    cs:__imp_HeapFree
0x180074f71  nop     dword ptr [rax+rax+00h]
0x180074f76  mov     rcx, rdi; lpCriticalSection
0x180074f79  mov     cs:?NhpSharedPrivateLanBindingInfo@@3PEAUIP_ADAPTER_BINDING_INFO@@EA, 0; IP_ADAPTER_BINDING_INFO * NhpSharedPrivateLanBindingInfo
0x180074f84  call    cs:__imp_LeaveCriticalSection
0x180074f8b  nop     dword ptr [rax+rax+00h]
0x180074f90  cmp     cs:?NhpComponentModeSet@@3EA, 0; uchar NhpComponentModeSet
0x180074f97  jz      short loc_180074FA5
0x180074f99  call    ?NhResetComponentMode@@YAXXZ; NhResetComponentMode(void)
0x180074f9e  mov     cs:?NhpComponentModeSet@@3EA, 0; uchar NhpComponentModeSet
0x180074fa5  call    ?NatNetConnectionRefreshAll@@YAJXZ; NatNetConnectionRefreshAll(void)
0x180074faa  mov     ecx, 3E8h; dwMilliseconds
0x180074faf  call    cs:__imp_Sleep
0x180074fb6  nop     dword ptr [rax+rax+00h]
0x180074fbb  mov     rcx, rdi; lpCriticalSection
0x180074fbe  call    cs:__imp_EnterCriticalSection
0x180074fc5  nop     dword ptr [rax+rax+00h]
0x180074fca  mov     rcx, rdi; lpCriticalSection
0x180074fcd  mov     cs:?g_fIsNatProtocolSet@@3_NA, 0; bool g_fIsNatProtocolSet
0x180074fd4  call    cs:__imp_LeaveCriticalSection
0x180074fdb  nop     dword ptr [rax+rax+00h]
0x180074fe0  call    ?GetEnableRebootPersistConnection@@YAHXZ; GetEnableRebootPersistConnection(void)
0x180074fe5  test    eax, eax
0x180074fe7  jz      short loc_180075014
0x180074fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180074ff0  cmp     rcx, r13
0x180074ff3  jz      short loc_180075019
0x180074ff5  test    [rcx+1Ch], r15d
0x180074ff9  jz      short loc_180075019
0x180074ffb  cmp     byte ptr [rcx+19h], 4
0x180074fff  jb      short loc_180075019
0x180075001  mov     rcx, [rcx+10h]
0x180075005  mov     edx, 93h
0x18007500a  mov     r8, r12
0x18007500d  call    WPP_SF_
0x180075012  jmp     short loc_180075019
0x180075014  call    ?ResetIcsRegistrySettings@@YAJXZ; ResetIcsRegistrySettings(void)
0x180075019  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180075020  mov     ecx, cs:?gICSPublicAdapterIndex@@3KA; InterfaceIndex
0x180075026  lea     r8, [rsp+310h+var_2D0]; union _NET_LUID_LH *
0x18007502b  lea     rdx, [rsp+310h+var_2B0]; struct _GUID *
0x180075030  mov     qword ptr [rsp+310h+var_2D0], 0
0x180075039  movdqu  xmmword ptr [rsp+310h+var_2B0.Data1], xmm0
0x18007503f  call    ?NatMapIndexToAdapterEx@@YAKKPEAU_GUID@@PEAT_NET_LUID_LH@@@Z; NatMapIndexToAdapterEx(ulong,_GUID *,_NET_LUID_LH *)
0x180075044  test    eax, eax
0x180075046  jz      short loc_180075063
0x180075048  mov     rcx, [rbp+218h]; this
0x18007504f  lea     r8, aOnecoreuapNetR_3; "onecoreuap\\net\\rras\\ip\\nathlp\\nats"...
0x180075056  mov     r9d, eax; char *
0x180075059  mov     edx, 7C4h; void *
0x18007505e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180075063  mov     ecx, cs:?g_PrivIndex@@3KA; unsigned int
0x180075069  call    ?TryGetInterfaceTypeByInterfaceIndex@SharedAccessUtils@@SAKK@Z; SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(ulong)
0x18007506e  movups  xmm0, xmmword ptr cs:?g_PrivateConnectionGuid@@3U_GUID@@A.Data1; _GUID g_PrivateConnectionGuid ...
0x180075075  mov     r8d, cs:?gICSPublicAdapterIndex@@3KA; unsigned int
0x18007507c  lea     rdx, [rsp+310h+var_2D0]; struct _GUID
0x180075081  mov     r9b, sil; bool
0x180075084  mov     [rsp+310h+var_2A0], 1Ah
0x18007508c  movdqu  [rsp+310h+var_29C], xmm0
0x180075092  lea     rcx, [rsp+310h+var_2A0]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x180075097  mov     [rbp+210h+var_28C], eax
0x18007509a  movaps  xmm0, xmmword ptr [rsp+310h+var_2B0.Data1]
0x18007509f  movdqa  xmmword ptr [rsp+310h+var_2D0], xmm0
0x1800750a5  call    ?SharedAccessStopped@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@U_GUID@@K_N@Z; NetworkingTriageScenario::MobileHotspot::SharedAccessStopped(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,_GUID,ulong,bool)
0x1800750aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800750b1  cmp     rcx, r13
0x1800750b4  jz      short loc_1800750D3
0x1800750b6  test    [rcx+1Ch], r15d
0x1800750ba  jz      short loc_1800750D3
0x1800750bc  cmp     byte ptr [rcx+19h], 6
0x1800750c0  jb      short loc_1800750D3
0x1800750c2  mov     rcx, [rcx+10h]
0x1800750c6  mov     edx, 94h
0x1800750cb  mov     r8, r12
0x1800750ce  call    WPP_SF_
0x1800750d3  mov     rcx, [rbp+210h+var_30]
0x1800750da  xor     rcx, rsp; StackCookie
0x1800750dd  call    __security_check_cookie
0x1800750e2  lea     r11, [rsp+310h+var_20]
0x1800750ea  mov     rbx, [r11+38h]
0x1800750ee  mov     rsi, [r11+40h]
0x1800750f2  mov     rsp, r11
0x1800750f5  pop     r15
0x1800750f7  pop     r13
0x1800750f9  pop     r12
0x1800750fb  pop     rdi
0x1800750fc  pop     rbp
0x1800750fd  retn
```
