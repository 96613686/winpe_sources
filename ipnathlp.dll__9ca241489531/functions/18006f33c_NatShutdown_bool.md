# NatShutdown(bool)

- ea: `0x18006f33c`
- end: `0x18006f7e8`
- name: `?NatShutdown@@YAX_N@Z`
- size: `1196`
- prototype: `void(bool)`
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003eee0`
- `0x1800697e0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18002d3cc`
- `0x18002d87c`
- `0x180034f2c`
- `0x180038420`
- `0x18003eca4`
- `0x18003f464`
- `0x18003f6c8`
- `0x180041f8c`
- `0x18004215c`
- `0x180043d74`
- `0x1800473f8`
- `0x180047568`
- `0x18004b570`
- `0x18004c068`
- `0x18004e0c0`
- `0x18004ed64`
- `0x18005f460`
- `0x18005f50c`
- `0x18006eca8`
- `0x18006f33c`
- `0x180071358`
- `0x180071498`
- `0x180071d38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f664`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006f664`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f672`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f672`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f652`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f6b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f652`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f6b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f686`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f6c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f686`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f6c4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f5fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006f5fe`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18006f3f1`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18006f3f1`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x18006f468`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x18006f468`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18006f5bc`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18006f5bc`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18006f431`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18006f431`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006f6ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006f6ab`
- `dhcpcsvc!DhcpEnableDhcp` at `0x18006f4a9`
- `dhcpcsvc!DhcpEnableDhcp` at `0x18006f4a9`

## pseudocode

```c
void __fastcall NatShutdown(bool a1, __int64 a2, __int64 a3, __int64 a4)
{
  ULONG v5; // edi
  __int64 v6; // rdx
  int v7; // r8d
  unsigned int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int InterfaceTypeByInterfaceIndex; // eax
  unsigned int v15; // eax
  __int64 v16; // rcx
  void *v17; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  bool v22; // [rsp+30h] [rbp-D0h] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[20]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-ACh]
  struct _GUID v26; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+70h] [rbp-90h] BYREF
  GUID v28; // [rsp+74h] [rbp-8Ch]
  unsigned int v29; // [rsp+84h] [rbp-7Ch]
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
  v8 = ConvertInterfaceIndexToLuid(g_PrivIndex, &InterfaceLuid);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 141;
LABEL_36:
      WPP_SF_d(v9[2], v10, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v8);
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
  v11 = ConvertInterfaceLuidToNameW(&InterfaceLuid, InterfaceName, 0x100u);
  if ( v11 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v13 = 142;
LABEL_21:
      WPP_SF_d(v12[2], v13, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v11);
    }
  }
  else
  {
    v11 = DhcpEnableDhcp(InterfaceName, 1);
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v13 = 143;
        goto LABEL_21;
      }
    }
    else
    {
      InterfaceTypeByInterfaceIndex = SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(g_PrivIndex);
      *(_DWORD *)v24 = 26;
      *(GUID *)&v24[4] = g_PrivateConnectionGuid;
      v25 = InterfaceTypeByInterfaceIndex;
      NetworkingTriageScenario::MobileHotspot::SharedAccessTransitionUpdate(
        (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)v24,
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
      v22 = 1;
      v15 = SharedAccessUtils::TryPublishWnfStateData(&g_PrivateConnectionGuid, &Row, &v22);
      if ( v15
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
          v15);
      }
    }
  }
  v8 = DeleteUnicastIpAddressEntry(&Row);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v10 = 146;
      goto LABEL_36;
    }
  }
LABEL_37:
  v16 = (__int64)*(&xmmword_1800A7330 + 1);
  if ( *(&xmmword_1800A7330 + 1) )
    SetEvent(*(&xmmword_1800A7330 + 1));
  if ( a1 )
  {
    NatRemoveDhcpPortExceptions(v16, v6, v7);
    NatCloseGroupExceptionForICS();
  }
  NhpStopAddressChangeNotification();
  DeRegisterAddressNotifyChangeAndCleanup();
  DeRegisterForNetworkMediaConnect();
  NatStopProtocol(NatRmStopProtocol, &NhpStopNatEvent);
  NatStopProtocol((unsigned int (*)(void))AlgRmStopProtocol, &NhpStopAlgEvent);
  EnterCriticalSection(&NhLock);
  NhFreeApplicationSettings();
  v17 = NhpSharedPrivateLanBindingInfo;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v17);
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
  *(_QWORD *)v24 = 0;
  v26 = GUID_NULL;
  v19 = NatMapIndexToAdapterEx(gICSPublicAdapterIndex, &v26, (union _NET_LUID_LH *)v24);
  if ( v19 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x7C4,
      (unsigned int)"onecoreuap\\net\\rras\\ip\\nathlp\\natsvc\\svcmain.cpp",
      (const char *)v19,
      v21);
  v20 = SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(g_PrivIndex);
  v27 = 26;
  v28 = g_PrivateConnectionGuid;
  v29 = v20;
  *(struct _GUID *)v24 = v26;
  NetworkingTriageScenario::MobileHotspot::SharedAccessStopped(
    (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)&v27,
    (struct _GUID *)v24,
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
0x18006f33c  mov     [rsp-8+arg_8], rbx
0x18006f341  mov     [rsp-8+arg_10], rsi
0x18006f346  push    rbp
0x18006f347  push    rdi
0x18006f348  push    r12
0x18006f34a  push    r13
0x18006f34c  push    r15
0x18006f34e  lea     rbp, [rsp-1F0h]
0x18006f356  sub     rsp, 2F0h
0x18006f35d  mov     rax, cs:__security_cookie
0x18006f364  xor     rax, rsp
0x18006f367  mov     [rbp+210h+var_30], rax
0x18006f36e  mov     sil, cl
0x18006f371  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f378  lea     r13, WPP_GLOBAL_Control
0x18006f37f  lea     r12, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006f386  mov     r15d, 200h
0x18006f38c  cmp     rcx, r13
0x18006f38f  jz      short loc_18006F3B1
0x18006f391  test    [rcx+1Ch], r15d
0x18006f395  jz      short loc_18006F3B1
0x18006f397  cmp     byte ptr [rcx+19h], 6
0x18006f39b  jb      short loc_18006F3B1
0x18006f39d  mov     rcx, [rcx+10h]
0x18006f3a1  mov     edx, 8Ch
0x18006f3a6  mov     r9b, sil
0x18006f3a9  mov     r8, r12
0x18006f3ac  call    WPP_SF_c
0x18006f3b1  xor     edx, edx; Val
0x18006f3b3  mov     qword ptr [rsp+310h+InterfaceLuid], 0
0x18006f3bc  lea     rcx, [rbp+210h+Row]; void *
0x18006f3c0  lea     r8d, [rdx+50h]; Size
0x18006f3c4  call    memset_0
0x18006f3c9  mov     edi, cs:?g_PrivAddress@@3KA; ulong g_PrivAddress
0x18006f3cf  lea     rcx, [rbp+210h+InterfaceName]; void *
0x18006f3d3  mov     r8, r15; Size
0x18006f3d6  xor     edx, edx; Val
0x18006f3d8  call    memset_0
0x18006f3dd  mov     ecx, cs:?g_PrivIndex@@3KA; InterfaceIndex
0x18006f3e3  cmp     ecx, 0FFFFFFFFh
0x18006f3e6  jz      loc_18006F5F2
0x18006f3ec  lea     rdx, [rsp+310h+InterfaceLuid]; InterfaceLuid
0x18006f3f1  call    cs:__imp_ConvertInterfaceIndexToLuid
0x18006f3f7  test    eax, eax
0x18006f3f9  jz      short loc_18006F42D
0x18006f3fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f402  cmp     rcx, r13
0x18006f405  jz      loc_18006F5F2
0x18006f40b  test    [rcx+1Ch], r15d
0x18006f40f  jz      loc_18006F5F2
0x18006f415  mov     ebx, 2
0x18006f41a  cmp     [rcx+19h], bl
0x18006f41d  jb      loc_18006F5F2
0x18006f423  mov     edx, 8Dh
0x18006f428  jmp     loc_18006F5E3
0x18006f42d  lea     rcx, [rbp+210h+Row]; Row
0x18006f431  call    cs:__imp_InitializeUnicastIpAddressEntry
0x18006f437  mov     rax, qword ptr [rsp+310h+InterfaceLuid]
0x18006f43c  lea     rdx, [rbp+210h+InterfaceName]; InterfaceName
0x18006f440  mov     qword ptr [rbp+210h+Row.InterfaceLuid], rax
0x18006f444  lea     rcx, [rsp+310h+InterfaceLuid]; InterfaceLuid
0x18006f449  mov     eax, cs:?g_PrivIndex@@3KA; ulong g_PrivIndex
0x18006f44f  mov     ebx, 2
0x18006f454  mov     r8d, 100h; Length
0x18006f45a  mov     [rbp+210h+Row.InterfaceIndex], eax
0x18006f45d  mov     word ptr [rbp+210h+Row.Address], bx
0x18006f461  mov     [rbp+210h+Row.OnLinkPrefixLength], 18h
0x18006f465  mov     dword ptr [rbp+210h+Row.Address+4], edi
0x18006f468  call    cs:__imp_ConvertInterfaceLuidToNameW
0x18006f46e  mov     dil, 3
0x18006f471  test    eax, eax
0x18006f473  jz      short loc_18006F4A0
0x18006f475  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f47c  cmp     rcx, r13
0x18006f47f  jz      loc_18006F5B8
0x18006f485  test    [rcx+1Ch], r15d
0x18006f489  jz      loc_18006F5B8
0x18006f48f  cmp     [rcx+19h], dil
0x18006f493  jb      loc_18006F5B8
0x18006f499  mov     edx, 8Eh
0x18006f49e  jmp     short loc_18006F4DC
0x18006f4a0  mov     edx, 1
0x18006f4a5  lea     rcx, [rbp+210h+InterfaceName]
0x18006f4a9  call    cs:__imp_DhcpEnableDhcp
0x18006f4af  test    eax, eax
0x18006f4b1  jz      short loc_18006F4F0
0x18006f4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f4ba  cmp     rcx, r13
0x18006f4bd  jz      loc_18006F5B8
0x18006f4c3  test    [rcx+1Ch], r15d
0x18006f4c7  jz      loc_18006F5B8
0x18006f4cd  cmp     [rcx+19h], dil
0x18006f4d1  jb      loc_18006F5B8
0x18006f4d7  mov     edx, 8Fh
0x18006f4dc  mov     rcx, [rcx+10h]
0x18006f4e0  mov     r9d, eax
0x18006f4e3  mov     r8, r12
0x18006f4e6  call    WPP_SF_d
0x18006f4eb  jmp     loc_18006F5B8
0x18006f4f0  mov     ecx, cs:?g_PrivIndex@@3KA; unsigned int
0x18006f4f6  call    ?TryGetInterfaceTypeByInterfaceIndex@SharedAccessUtils@@SAKK@Z; SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(ulong)
0x18006f4fb  movups  xmm0, xmmword ptr cs:?g_PrivateConnectionGuid@@3U_GUID@@A.Data1; _GUID g_PrivateConnectionGuid ...
0x18006f502  mov     r8d, cs:?g_PrivIndex@@3KA; unsigned int
0x18006f509  lea     rdx, aHostednetmode; "HostedNetMode"
0x18006f510  lea     rcx, [rsp+310h+var_2D0]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x18006f515  mov     dword ptr [rsp+310h+var_2D0], 1Ah
0x18006f51d  movdqu  xmmword ptr [rsp+310h+var_2D0+4], xmm0
0x18006f523  mov     [rsp+310h+var_2BC], eax
0x18006f527  call    ?SharedAccessTransitionUpdate@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBGK@Z; NetworkingTriageScenario::MobileHotspot::SharedAccessTransitionUpdate(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,ushort const *,ulong)
0x18006f52c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f533  cmp     rcx, r13
0x18006f536  jz      short loc_18006F560
0x18006f538  test    [rcx+1Ch], r15d
0x18006f53c  jz      short loc_18006F560
0x18006f53e  cmp     byte ptr [rcx+19h], 5
0x18006f542  jb      short loc_18006F560
0x18006f544  mov     eax, dword ptr [rbp+210h+Row.Address+4]
0x18006f547  lea     r9, [rbp+210h+InterfaceName]
0x18006f54b  mov     rcx, [rcx+10h]
0x18006f54f  mov     edx, 90h
0x18006f554  mov     r8, r12
0x18006f557  mov     [rsp+310h+var_2F0], eax
0x18006f55b  call    WPP_SF_SD
0x18006f560  lea     r8, [rsp+310h+var_2E0]; bool *
0x18006f565  mov     [rsp+310h+var_2E0], 1
0x18006f56a  lea     rdx, [rbp+210h+Row]; struct _MIB_UNICASTIPADDRESS_ROW *
0x18006f56e  lea     rcx, ?g_PrivateConnectionGuid@@3U_GUID@@A; struct _GUID *
0x18006f575  call    ?TryPublishWnfStateData@SharedAccessUtils@@SAKAEBU_GUID@@AEBU_MIB_UNICASTIPADDRESS_ROW@@AEB_N@Z; SharedAccessUtils::TryPublishWnfStateData(_GUID const &,_MIB_UNICASTIPADDRESS_ROW const &,bool const &)
0x18006f57a  test    eax, eax
0x18006f57c  jz      short loc_18006F5B8
0x18006f57e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f585  cmp     rcx, r13
0x18006f588  jz      short loc_18006F5B8
0x18006f58a  test    [rcx+1Ch], r15d
0x18006f58e  jz      short loc_18006F5B8
0x18006f590  cmp     [rcx+19h], bl
0x18006f593  jb      short loc_18006F5B8
0x18006f595  mov     rcx, [rcx+10h]
0x18006f599  lea     r9, ?g_PrivateConnectionGuid@@3U_GUID@@A; _GUID g_PrivateConnectionGuid
0x18006f5a0  mov     [rsp+310h+var_2E8], eax
0x18006f5a4  mov     edx, 91h
0x18006f5a9  mov     eax, dword ptr [rbp+210h+Row.Address+4]
0x18006f5ac  mov     r8, r12
0x18006f5af  mov     [rsp+310h+var_2F0], eax; unsigned int
0x18006f5b3  call    WPP_SF__guid_DD
0x18006f5b8  lea     rcx, [rbp+210h+Row]; Row
0x18006f5bc  call    cs:__imp_DeleteUnicastIpAddressEntry
0x18006f5c2  test    eax, eax
0x18006f5c4  jz      short loc_18006F5F2
0x18006f5c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f5cd  cmp     rcx, r13
0x18006f5d0  jz      short loc_18006F5F2
0x18006f5d2  test    [rcx+1Ch], r15d
0x18006f5d6  jz      short loc_18006F5F2
0x18006f5d8  cmp     [rcx+19h], dil
0x18006f5dc  jb      short loc_18006F5F2
0x18006f5de  mov     edx, 92h
0x18006f5e3  mov     rcx, [rcx+10h]
0x18006f5e7  mov     r9d, eax
0x18006f5ea  mov     r8, r12
0x18006f5ed  call    WPP_SF_d
0x18006f5f2  mov     rcx, qword ptr cs:xmmword_1800A7330+8; hEvent
0x18006f5f9  test    rcx, rcx
0x18006f5fc  jz      short loc_18006F604
0x18006f5fe  call    cs:__imp_SetEvent
0x18006f604  test    sil, sil
0x18006f607  jz      short loc_18006F613
0x18006f609  call    ?NatRemoveDhcpPortExceptions@@YAJXZ; NatRemoveDhcpPortExceptions(void)
0x18006f60e  call    ?NatCloseGroupExceptionForICS@@YAJXZ; NatCloseGroupExceptionForICS(void)
0x18006f613  call    ?NhpStopAddressChangeNotification@@YAXXZ; NhpStopAddressChangeNotification(void)
0x18006f618  call    ?DeRegisterAddressNotifyChangeAndCleanup@@YAXXZ; DeRegisterAddressNotifyChangeAndCleanup(void)
0x18006f61d  call    ?DeRegisterForNetworkMediaConnect@@YAXXZ; DeRegisterForNetworkMediaConnect(void)
0x18006f622  lea     rdx, ?NhpStopNatEvent@@3PEAXEA; void **
0x18006f629  lea     rcx, ?NatRmStopProtocol@@YAKXZ; unsigned int (*)(void)
0x18006f630  call    ?NatStopProtocol@@YAXP6AKXZPEAPEAX@Z; NatStopProtocol(ulong (*)(void),void * *)
0x18006f635  lea     rdx, ?NhpStopAlgEvent@@3PEAXEA; void **
0x18006f63c  lea     rcx, ?AlgRmStopProtocol@@YAKXZ; unsigned int (*)(void)
0x18006f643  call    ?NatStopProtocol@@YAXP6AKXZPEAPEAX@Z; NatStopProtocol(ulong (*)(void),void * *)
0x18006f648  lea     rdi, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION NhLock
0x18006f64f  mov     rcx, rdi; lpCriticalSection
0x18006f652  call    cs:__imp_EnterCriticalSection
0x18006f658  call    ?NhFreeApplicationSettings@@YAXXZ; NhFreeApplicationSettings(void)
0x18006f65d  mov     rbx, cs:?NhpSharedPrivateLanBindingInfo@@3PEAUIP_ADAPTER_BINDING_INFO@@EA; IP_ADAPTER_BINDING_INFO * NhpSharedPrivateLanBindingInfo
0x18006f664  call    cs:__imp_GetProcessHeap
0x18006f66a  mov     r8, rbx; lpMem
0x18006f66d  xor     edx, edx; dwFlags
0x18006f66f  mov     rcx, rax; hHeap
0x18006f672  call    cs:__imp_HeapFree
0x18006f678  mov     rcx, rdi; lpCriticalSection
0x18006f67b  mov     cs:?NhpSharedPrivateLanBindingInfo@@3PEAUIP_ADAPTER_BINDING_INFO@@EA, 0; IP_ADAPTER_BINDING_INFO * NhpSharedPrivateLanBindingInfo
0x18006f686  call    cs:__imp_LeaveCriticalSection
0x18006f68c  cmp     cs:?NhpComponentModeSet@@3EA, 0; uchar NhpComponentModeSet
0x18006f693  jz      short loc_18006F6A1
0x18006f695  call    ?NhResetComponentMode@@YAXXZ; NhResetComponentMode(void)
0x18006f69a  mov     cs:?NhpComponentModeSet@@3EA, 0; uchar NhpComponentModeSet
0x18006f6a1  call    ?NatNetConnectionRefreshAll@@YAJXZ; NatNetConnectionRefreshAll(void)
0x18006f6a6  mov     ecx, 3E8h; dwMilliseconds
0x18006f6ab  call    cs:__imp_Sleep
0x18006f6b1  mov     rcx, rdi; lpCriticalSection
0x18006f6b4  call    cs:__imp_EnterCriticalSection
0x18006f6ba  mov     rcx, rdi; lpCriticalSection
0x18006f6bd  mov     cs:?g_fIsNatProtocolSet@@3_NA, 0; bool g_fIsNatProtocolSet
0x18006f6c4  call    cs:__imp_LeaveCriticalSection
0x18006f6ca  call    ?GetEnableRebootPersistConnection@@YAHXZ; GetEnableRebootPersistConnection(void)
0x18006f6cf  test    eax, eax
0x18006f6d1  jz      short loc_18006F6FE
0x18006f6d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f6da  cmp     rcx, r13
0x18006f6dd  jz      short loc_18006F703
0x18006f6df  test    [rcx+1Ch], r15d
0x18006f6e3  jz      short loc_18006F703
0x18006f6e5  cmp     byte ptr [rcx+19h], 4
0x18006f6e9  jb      short loc_18006F703
0x18006f6eb  mov     rcx, [rcx+10h]
0x18006f6ef  mov     edx, 93h
0x18006f6f4  mov     r8, r12
0x18006f6f7  call    WPP_SF_
0x18006f6fc  jmp     short loc_18006F703
0x18006f6fe  call    ?ResetIcsRegistrySettings@@YAJXZ; ResetIcsRegistrySettings(void)
0x18006f703  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006f70a  mov     ecx, cs:?gICSPublicAdapterIndex@@3KA; InterfaceIndex
0x18006f710  lea     r8, [rsp+310h+var_2D0]; union _NET_LUID_LH *
0x18006f715  lea     rdx, [rsp+310h+var_2B0]; struct _GUID *
0x18006f71a  mov     qword ptr [rsp+310h+var_2D0], 0
0x18006f723  movdqu  xmmword ptr [rsp+310h+var_2B0.Data1], xmm0
0x18006f729  call    ?NatMapIndexToAdapterEx@@YAKKPEAU_GUID@@PEAT_NET_LUID_LH@@@Z; NatMapIndexToAdapterEx(ulong,_GUID *,_NET_LUID_LH *)
0x18006f72e  test    eax, eax
0x18006f730  jz      short loc_18006F74D
0x18006f732  mov     rcx, [rbp+218h]; this
0x18006f739  lea     r8, aOnecoreuapNetR_3; "onecoreuap\\net\\rras\\ip\\nathlp\\nats"...
0x18006f740  mov     r9d, eax; char *
0x18006f743  mov     edx, 7C4h; void *
0x18006f748  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18006f74d  mov     ecx, cs:?g_PrivIndex@@3KA; unsigned int
0x18006f753  call    ?TryGetInterfaceTypeByInterfaceIndex@SharedAccessUtils@@SAKK@Z; SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(ulong)
0x18006f758  movups  xmm0, xmmword ptr cs:?g_PrivateConnectionGuid@@3U_GUID@@A.Data1; _GUID g_PrivateConnectionGuid ...
0x18006f75f  mov     r8d, cs:?gICSPublicAdapterIndex@@3KA; unsigned int
0x18006f766  lea     rdx, [rsp+310h+var_2D0]; struct _GUID
0x18006f76b  mov     r9b, sil; bool
0x18006f76e  mov     [rsp+310h+var_2A0], 1Ah
0x18006f776  movdqu  [rsp+310h+var_29C], xmm0
0x18006f77c  lea     rcx, [rsp+310h+var_2A0]; struct NetworkingTriageScenario::MobileHotspot::RequiredFields *
0x18006f781  mov     [rbp+210h+var_28C], eax
0x18006f784  movaps  xmm0, xmmword ptr [rsp+310h+var_2B0.Data1]
0x18006f789  movdqa  xmmword ptr [rsp+310h+var_2D0], xmm0
0x18006f78f  call    ?SharedAccessStopped@MobileHotspot@NetworkingTriageScenario@@SAXAEBURequiredFields@12@U_GUID@@K_N@Z; NetworkingTriageScenario::MobileHotspot::SharedAccessStopped(NetworkingTriageScenario::MobileHotspot::RequiredFields const &,_GUID,ulong,bool)
0x18006f794  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f79b  cmp     rcx, r13
0x18006f79e  jz      short loc_18006F7BD
0x18006f7a0  test    [rcx+1Ch], r15d
0x18006f7a4  jz      short loc_18006F7BD
0x18006f7a6  cmp     byte ptr [rcx+19h], 6
0x18006f7aa  jb      short loc_18006F7BD
0x18006f7ac  mov     rcx, [rcx+10h]
0x18006f7b0  mov     edx, 94h
0x18006f7b5  mov     r8, r12
0x18006f7b8  call    WPP_SF_
0x18006f7bd  mov     rcx, [rbp+210h+var_30]
0x18006f7c4  xor     rcx, rsp; StackCookie
0x18006f7c7  call    __security_check_cookie
0x18006f7cc  lea     r11, [rsp+310h+var_20]
0x18006f7d4  mov     rbx, [r11+38h]
0x18006f7d8  mov     rsi, [r11+40h]
0x18006f7dc  mov     rsp, r11
0x18006f7df  pop     r15
0x18006f7e1  pop     r13
0x18006f7e3  pop     r12
0x18006f7e5  pop     rdi
0x18006f7e6  pop     rbp
0x18006f7e7  retn
```
