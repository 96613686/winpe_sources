# NatInitialize(ulong)

- ea: `0x18006e294`
- end: `0x18006eca1`
- name: `?NatInitialize@@YAJK@Z`
- size: `2573`
- prototype: `__int64 __fastcall(NET_IFINDEX InterfaceIndex)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003b394`
- `0x180043450`

## callees

- `0x180001ed0`
- `0x18000c110`
- `0x18000c750`
- `0x18001ec08`
- `0x18002cb40`
- `0x18002f690`
- `0x180030b7c`
- `0x180037cf4`
- `0x180039764`
- `0x180039eec`
- `0x18004112c`
- `0x180041e1c`
- `0x18004215c`
- `0x180042370`
- `0x180044890`
- `0x1800471e8`
- `0x1800473f8`
- `0x18004c068`
- `0x18004e0c0`
- `0x18004ed64`
- `0x18005f460`
- `0x18006e294`
- `0x18006eca8`
- `0x180071498`
- `0x1800715b4`
- `0x180071d38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006e7af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006e7af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ea67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006eaec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ea67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006eaec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ea7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eb00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ea7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eb00`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x18006e7eb`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x18006e7eb`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x18006e9cc`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x18006e9cc`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18006e972`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x18006e972`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18006e7be`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x18006e7be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006e361`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18006e361`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006e36e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18006e36e`
- `dhcpcsvc!DhcpEnableDhcp` at `0x18006e865`
- `dhcpcsvc!DhcpEnableDhcp` at `0x18006e865`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006ea86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006ea86`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006e409`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006e409`

## string_xrefs

- `0x18006e47a`: `NatRmStartProtocol`
- `0x18006e4fe`: `AlgRmStartProtocol`
- `0x18006e8c9`: `SharedAccessMode`
- `0x18006eab1`: `SharedAccess (Full ICS)`

## pseudocode

```c
__int64 __fastcall NatInitialize(NET_IFINDEX InterfaceIndex)
{
  unsigned __int8 v2; // al
  __int64 v3; // r9
  ULONG v4; // r14d
  signed int v5; // ebx
  HRESULT v6; // r15d
  int started; // eax
  unsigned int v8; // edx
  unsigned int v9; // r8d
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // r8d
  int v15; // eax
  int *v16; // rcx
  int v17; // eax
  unsigned int v18; // eax
  int AdapterNameByGuid; // eax
  unsigned int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  unsigned int InterfaceTypeByInterfaceIndex; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  ULONG S_addr; // esi
  NTSTATUS v28; // eax
  PVOID *v29; // rcx
  bool v30; // sf
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned int v35; // eax
  bool v36[4]; // [rsp+30h] [rbp-D0h] BYREF
  signed int v37; // [rsp+34h] [rbp-CCh] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  NET_LUID InterfaceLuid; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+58h] [rbp-A8h]
  __int64 v43; // [rsp+5Ch] [rbp-A4h]
  __int64 v44; // [rsp+64h] [rbp-9Ch]
  __int64 v45; // [rsp+6Ch] [rbp-94h]
  struct _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+D0h] [rbp-30h] BYREF
  GUID v48; // [rsp+D4h] [rbp-2Ch]
  unsigned int v49; // [rsp+E4h] [rbp-1Ch]
  struct _GUID v50; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR InterfaceName[256]; // [rsp+100h] [rbp+0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, InterfaceIndex);
  }
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v2 = IsPrivateConnectionPresent();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LOBYTE(v3) = v2 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v3);
  }
  ClearPersistentDhcpExceptions();
  WaitForThreadpoolWorkCallbacks(g_FirewallExceptionBackgroundWork, 1);
  SubmitThreadpoolWork(g_FirewallExceptionBackgroundWork);
  v41 = 1;
  v4 = 25798848;
  v42 = 1;
  v43 = 12;
  v44 = 0;
  v45 = 0;
  v40 = 1;
  if ( !(unsigned __int8)NhSetComponentMode(1) )
  {
    v5 = -2147467259;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, 2147500037LL);
    }
    goto LABEL_120;
  }
  NhpComponentModeSet = 1;
  v6 = CoInitializeEx(0, 0);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147417850 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        115,
        &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
        (unsigned int)v6);
    }
    v5 = v6;
    goto LABEL_120;
  }
  started = NatStartProtocol(NatRmStartProtocol, "NatRmStartProtocol", &v41, 0x24u, &NhpStopNatEvent);
  v5 = started;
  if ( started < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 116;
LABEL_26:
      WPP_SF_d(v10[2], v11, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)started);
      goto LABEL_118;
    }
    goto LABEL_118;
  }
  v12 = NatStartServiceSync(L"ALG", v8, v9);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
        (unsigned int)v12);
    }
LABEL_37:
    v15 = NatStartServiceSync(L"NLA", v13, v14);
    v5 = v15;
    if ( v15 < 0 )
    {
      v16 = (int *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          119,
          &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          (unsigned int)v15);
      }
      v5 = 0;
    }
    NatGetPolicy(v16, &NhPolicyAllowsSharing);
    v17 = NatStartConnectionManagement();
    if ( v17 )
    {
      if ( v17 > 0 )
        v5 = (unsigned __int16)v17 | 0x80070000;
      else
        v5 = v17;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          (unsigned int)v17,
          v5);
      }
      goto LABEL_118;
    }
    StartAddressChangeNotification();
    NatNetConnectionRefreshAll();
    if ( InterfaceIndex == -1 )
      goto LABEL_117;
    v50 = GUID_NULL;
    memset_0(InterfaceName, 0, sizeof(InterfaceName));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
    }
    g_PrivIndex = InterfaceIndex;
    v18 = NatMapIndexToAdapterEx(InterfaceIndex, &v50, &InterfaceLuid);
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v18);
      }
      goto LABEL_118;
    }
    v37 = 0;
    Block = 0;
    AdapterNameByGuid = FindAdapterNameByGuid(
                          &g_PrivateConnectionGuid,
                          (unsigned __int16 **)&Block,
                          (enum NAT_IF_TYPE *)&v37);
    if ( AdapterNameByGuid >= 0 )
    {
      if ( v37 == 4 )
        v4 = 25864384;
      g_PrivAddress = v4;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          124,
          &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          g_PrivIndex,
          v4);
      }
      if ( Block )
      {
        free(Block);
        Block = 0;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
        (unsigned int)AdapterNameByGuid);
    }
    InitializeUnicastIpAddressEntry(&Row);
    Row.InterfaceLuid = InterfaceLuid;
    Row.Address.Ipv4.sin_family = 2;
    Row.InterfaceIndex = InterfaceIndex;
    Row.OnLinkPrefixLength = 24;
    Row.Address.Ipv4.sin_addr.S_un.S_addr = v4;
    v20 = ConvertInterfaceLuidToNameW(&InterfaceLuid, InterfaceName, 0x100u);
    if ( v20 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v22 = 125;
LABEL_88:
        WPP_SF_d(v21[2], v22, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v20);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          InterfaceName);
      }
      v20 = DhcpEnableDhcp(InterfaceName, 0);
      if ( v20 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v22 = 127;
          goto LABEL_88;
        }
      }
      else
      {
        InterfaceTypeByInterfaceIndex = SharedAccessUtils::TryGetInterfaceTypeByInterfaceIndex(g_PrivIndex);
        v47 = 26;
        v48 = g_PrivateConnectionGuid;
        v49 = InterfaceTypeByInterfaceIndex;
        NetworkingTriageScenario::MobileHotspot::SharedAccessTransitionUpdate(
          (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)&v47,
          L"SharedAccessMode",
          g_PrivIndex);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
            InterfaceName);
        }
        v36[0] = 0;
        v24 = SharedAccessUtils::TryPublishWnfStateData(&g_PrivateConnectionGuid, &Row, v36);
        if ( v24
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF__guid_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            129,
            &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
            &g_PrivateConnectionGuid,
            Row.Address.Ipv4.sin_addr.S_un.S_addr,
            v24);
        }
      }
    }
    v25 = DeleteUnicastIpAddressEntry(&Row);
    if ( v25
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v25);
    }
    v26 = SharedAccessUtils::TryAcquirePrivateIPAddress(&Row);
    v5 = v26;
    if ( v26 )
    {
      v29 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_109;
      }
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v4, v26);
    }
    else
    {
      S_addr = Row.Address.Ipv4.sin_addr.S_un.S_addr;
      g_PrivAddress = Row.Address.Ipv4.sin_addr.S_un.S_addr;
      v28 = CreateUnicastIpAddressEntry(&Row);
      v5 = v28;
      if ( v28 )
      {
        v29 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            131,
            &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
            S_addr,
            v28);
          v29 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_109;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          132,
          &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
          g_PrivIndex,
          g_PrivAddress);
      }
      v36[0] = 1;
      v35 = SharedAccessUtils::TryPublishWnfStateData(&g_PrivateConnectionGuid, &Row, v36);
      if ( !v35 )
      {
        v29 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_111;
      }
      v29 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_111;
      }
      WPP_SF__guid_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        133,
        &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
        &g_PrivateConnectionGuid,
        Row.Address.Ipv4.sin_addr.S_un.S_addr,
        v35);
    }
    v29 = (PVOID *)WPP_GLOBAL_Control;
LABEL_109:
    v30 = v5 < 0;
    if ( v5 <= 0 )
    {
LABEL_112:
      if ( v30 )
      {
        if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x200) != 0 && *((_BYTE *)v29 + 25) >= 2u )
          WPP_SF_(v29[2], 136, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
        goto LABEL_118;
      }
      if ( v29 != &WPP_GLOBAL_Control && (*((_DWORD *)v29 + 7) & 0x200) != 0 && *((_BYTE *)v29 + 25) >= 4u )
        WPP_SF_(v29[2], 135, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
LABEL_117:
      EnterCriticalSection(&NhLock);
      g_fIsNatProtocolSet = 1;
      LeaveCriticalSection(&NhLock);
      goto LABEL_118;
    }
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_111:
    v30 = v5 < 0;
    goto LABEL_112;
  }
  started = NatStartProtocol(
              (unsigned int (*)(void *, struct _SUPPORT_FUNCTIONS_50 *, void *, unsigned int, unsigned int, unsigned int))AlgRmStartProtocol,
              "AlgRmStartProtocol",
              &v40,
              8u,
              &NhpStopAlgEvent);
  v5 = started;
  if ( started >= 0 )
    goto LABEL_37;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 117;
    goto LABEL_26;
  }
LABEL_118:
  if ( v6 >= 0 )
    CoUninitialize();
LABEL_120:
  if ( (unsigned int)dword_1800A6208 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800A6208, 0x200000000000LL) )
  {
    v37 = v5;
    Block = "SharedAccess (Full ICS)";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v31,
      (__int64)&unk_18009C4E8,
      v32,
      v33,
      (__int64)&v37,
      (const unsigned __int16 **)&Block);
  }
  if ( v5 < 0 )
  {
    EnterCriticalSection(&gNatMain);
    byte_1800A7342 = 1;
    LeaveCriticalSection(&gNatMain);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      137,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006e294  push    rbp
0x18006e296  push    rbx
0x18006e297  push    rsi
0x18006e298  push    rdi
0x18006e299  push    r12
0x18006e29b  push    r13
0x18006e29d  push    r14
0x18006e29f  push    r15
0x18006e2a1  lea     rbp, [rsp-218h]
0x18006e2a9  sub     rsp, 318h
0x18006e2b0  mov     rax, cs:__security_cookie
0x18006e2b7  xor     rax, rsp
0x18006e2ba  mov     [rbp+250h+var_50], rax
0x18006e2c1  mov     esi, ecx
0x18006e2c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e2ca  lea     rdi, WPP_GLOBAL_Control
0x18006e2d1  mov     r13d, 200h
0x18006e2d7  cmp     rcx, rdi
0x18006e2da  jz      short loc_18006E300
0x18006e2dc  test    [rcx+1Ch], r13d
0x18006e2e0  jz      short loc_18006E300
0x18006e2e2  cmp     byte ptr [rcx+19h], 6
0x18006e2e6  jb      short loc_18006E300
0x18006e2e8  mov     rcx, [rcx+10h]
0x18006e2ec  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e2f3  mov     edx, 70h ; 'p'
0x18006e2f8  mov     r9d, esi
0x18006e2fb  call    WPP_SF_d
0x18006e300  xor     r12d, r12d
0x18006e303  lea     rcx, [rbp+250h+Row]; void *
0x18006e307  xor     edx, edx; Val
0x18006e309  mov     qword ptr [rsp+350h+InterfaceLuid], r12
0x18006e30e  lea     r8d, [r12+50h]; Size
0x18006e313  call    memset_0
0x18006e318  call    ?IsPrivateConnectionPresent@@YAEXZ; IsPrivateConnectionPresent(void)
0x18006e31d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e324  cmp     rcx, rdi
0x18006e327  jz      short loc_18006E350
0x18006e329  test    [rcx+1Ch], r13d
0x18006e32d  jz      short loc_18006E350
0x18006e32f  cmp     byte ptr [rcx+19h], 5
0x18006e333  jb      short loc_18006E350
0x18006e335  mov     rcx, [rcx+10h]
0x18006e339  lea     edx, [r12+71h]
0x18006e33e  test    al, al
0x18006e340  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e347  setnz   r9b
0x18006e34b  call    WPP_SF_c
0x18006e350  call    ?ClearPersistentDhcpExceptions@@YAXXZ; ClearPersistentDhcpExceptions(void)
0x18006e355  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006e35c  mov     edx, 1; fCancelPendingCallbacks
0x18006e361  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18006e367  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x18006e36e  call    cs:__imp_SubmitThreadpoolWork
0x18006e374  mov     ecx, 1
0x18006e379  mov     [rsp+350h+var_300], 1
0x18006e382  mov     r14d, 189A8C0h
0x18006e388  mov     [rsp+350h+var_2F8], 1
0x18006e390  mov     [rsp+350h+var_2F4], 0Ch
0x18006e399  mov     [rsp+350h+var_2EC], r12
0x18006e39e  mov     [rsp+350h+var_2E4], r12
0x18006e3a3  mov     [rsp+350h+var_308], 1
0x18006e3ac  call    ?NhSetComponentMode@@YAEW4NH_COMPONENT_MODE@@@Z; NhSetComponentMode(NH_COMPONENT_MODE)
0x18006e3b1  test    al, al
0x18006e3b3  jnz     short loc_18006E3FE
0x18006e3b5  mov     ebx, 80004005h
0x18006e3ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e3c1  cmp     rcx, rdi
0x18006e3c4  jz      loc_18006EA8C
0x18006e3ca  test    [rcx+1Ch], r13d
0x18006e3ce  jz      loc_18006EA8C
0x18006e3d4  mov     edi, 2
0x18006e3d9  cmp     [rcx+19h], dil
0x18006e3dd  jb      loc_18006EA8C
0x18006e3e3  mov     rcx, [rcx+10h]
0x18006e3e7  lea     edx, [rdi+70h]
0x18006e3ea  mov     r9d, ebx
0x18006e3ed  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e3f4  call    WPP_SF_d
0x18006e3f9  jmp     loc_18006EA8C
0x18006e3fe  xor     edx, edx; dwCoInit
0x18006e400  mov     cs:?NhpComponentModeSet@@3EA, 1; uchar NhpComponentModeSet
0x18006e407  xor     ecx, ecx; pvReserved
0x18006e409  call    cs:__imp_CoInitializeEx
0x18006e40f  mov     r15d, eax
0x18006e412  mov     eax, 80000000h
0x18006e417  lea     ecx, [r15+rax]
0x18006e41b  test    eax, ecx
0x18006e41d  jnz     short loc_18006E463
0x18006e41f  cmp     r15d, 80010106h
0x18006e426  jz      short loc_18006E463
0x18006e428  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e42f  cmp     rcx, rdi
0x18006e432  jz      short loc_18006E45B
0x18006e434  test    [rcx+1Ch], r13d
0x18006e438  jz      short loc_18006E45B
0x18006e43a  mov     edi, 2
0x18006e43f  cmp     [rcx+19h], dil
0x18006e443  jb      short loc_18006E45B
0x18006e445  mov     rcx, [rcx+10h]
0x18006e449  lea     edx, [rdi+71h]
0x18006e44c  mov     r9d, r15d
0x18006e44f  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e456  call    WPP_SF_d
0x18006e45b  mov     ebx, r15d
0x18006e45e  jmp     loc_18006EA8C
0x18006e463  lea     rax, ?NhpStopNatEvent@@3PEAXEA; void * NhpStopNatEvent
0x18006e46a  mov     r9d, 24h ; '$'; unsigned int
0x18006e470  lea     r8, [rsp+350h+var_300]; void *
0x18006e475  mov     [rsp+350h+var_330], rax; void **
0x18006e47a  lea     rdx, aNatrmstartprot; "NatRmStartProtocol"
0x18006e481  lea     rcx, ?NatRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; unsigned int (*)(void *, struct _SUPPORT_FUNCTIONS_50 *, void *, unsigned int, unsigned int, unsigned int)
0x18006e488  call    ?NatStartProtocol@@YAJP6AKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@ZPEBD0KPEAPEAX@Z; NatStartProtocol(ulong (*)(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong),char const *,void *,ulong,void * *)
0x18006e48d  mov     ebx, eax
0x18006e48f  test    eax, eax
0x18006e491  jns     short loc_18006E4D7
0x18006e493  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e49a  cmp     rcx, rdi
0x18006e49d  jz      loc_18006EA81
0x18006e4a3  test    [rcx+1Ch], r13d
0x18006e4a7  jz      loc_18006EA81
0x18006e4ad  mov     edi, 2
0x18006e4b2  cmp     [rcx+19h], dil
0x18006e4b6  jb      loc_18006EA81
0x18006e4bc  lea     edx, [rdi+72h]
0x18006e4bf  mov     rcx, [rcx+10h]
0x18006e4c3  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e4ca  mov     r9d, eax
0x18006e4cd  call    WPP_SF_d
0x18006e4d2  jmp     loc_18006EA81
0x18006e4d7  lea     rcx, aAlg; "ALG"
0x18006e4de  call    ?NatStartServiceSync@@YAJPEBGKK@Z; NatStartServiceSync(ushort const *,ulong,ulong)
0x18006e4e3  test    eax, eax
0x18006e4e5  js      short loc_18006E548
0x18006e4e7  lea     rax, ?NhpStopAlgEvent@@3PEAXEA; void * NhpStopAlgEvent
0x18006e4ee  mov     r9d, 8; unsigned int
0x18006e4f4  lea     r8, [rsp+350h+var_308]; void *
0x18006e4f9  mov     [rsp+350h+var_330], rax; void **
0x18006e4fe  lea     rdx, aAlgrmstartprot; "AlgRmStartProtocol"
0x18006e505  lea     rcx, ?AlgRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; unsigned int (*)(void *, struct _SUPPORT_FUNCTIONS_50 *, void *, unsigned int, unsigned int, unsigned int)
0x18006e50c  call    ?NatStartProtocol@@YAJP6AKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@ZPEBD0KPEAPEAX@Z; NatStartProtocol(ulong (*)(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong),char const *,void *,ulong,void * *)
0x18006e511  mov     ebx, eax
0x18006e513  test    eax, eax
0x18006e515  jns     short loc_18006E578
0x18006e517  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e51e  cmp     rcx, rdi
0x18006e521  jz      loc_18006EA81
0x18006e527  test    [rcx+1Ch], r13d
0x18006e52b  jz      loc_18006EA81
0x18006e531  mov     edi, 2
0x18006e536  cmp     [rcx+19h], dil
0x18006e53a  jb      loc_18006EA81
0x18006e540  lea     edx, [rdi+73h]
0x18006e543  jmp     loc_18006E4BF
0x18006e548  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e54f  cmp     rcx, rdi
0x18006e552  jz      short loc_18006E578
0x18006e554  test    [rcx+1Ch], r13d
0x18006e558  jz      short loc_18006E578
0x18006e55a  cmp     byte ptr [rcx+19h], 3
0x18006e55e  jb      short loc_18006E578
0x18006e560  mov     rcx, [rcx+10h]
0x18006e564  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e56b  mov     edx, 76h ; 'v'
0x18006e570  mov     r9d, eax
0x18006e573  call    WPP_SF_d
0x18006e578  lea     rcx, aNla; "NLA"
0x18006e57f  call    ?NatStartServiceSync@@YAJPEBGKK@Z; NatStartServiceSync(ushort const *,ulong,ulong)
0x18006e584  mov     ebx, eax
0x18006e586  test    eax, eax
0x18006e588  jns     short loc_18006E5BD
0x18006e58a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e591  cmp     rcx, rdi
0x18006e594  jz      short loc_18006E5BA
0x18006e596  test    [rcx+1Ch], r13d
0x18006e59a  jz      short loc_18006E5BA
0x18006e59c  cmp     byte ptr [rcx+19h], 3
0x18006e5a0  jb      short loc_18006E5BA
0x18006e5a2  mov     rcx, [rcx+10h]
0x18006e5a6  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e5ad  mov     edx, 77h ; 'w'
0x18006e5b2  mov     r9d, eax
0x18006e5b5  call    WPP_SF_d
0x18006e5ba  mov     ebx, r12d
0x18006e5bd  lea     rdx, ?NhPolicyAllowsSharing@@3HA; int *
0x18006e5c4  call    ?NatGetPolicy@@YAXPEAH0@Z; NatGetPolicy(int *,int *)
0x18006e5c9  call    NatStartConnectionManagement
0x18006e5ce  test    eax, eax
0x18006e5d0  jz      short loc_18006E629
0x18006e5d2  jg      short loc_18006E5D8
0x18006e5d4  mov     ebx, eax
0x18006e5d6  jmp     short loc_18006E5E1
0x18006e5d8  movzx   ebx, ax
0x18006e5db  or      ebx, 80070000h
0x18006e5e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e5e8  cmp     rcx, rdi
0x18006e5eb  jz      loc_18006EA81
0x18006e5f1  test    [rcx+1Ch], r13d
0x18006e5f5  jz      loc_18006EA81
0x18006e5fb  mov     edi, 2
0x18006e600  cmp     [rcx+19h], dil
0x18006e604  jb      loc_18006EA81
0x18006e60a  mov     rcx, [rcx+10h]
0x18006e60e  lea     edx, [rdi+76h]
0x18006e611  mov     r9d, eax
0x18006e614  mov     dword ptr [rsp+350h+var_330], ebx
0x18006e618  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e61f  call    WPP_SF_Dd
0x18006e624  jmp     loc_18006EA81
0x18006e629  call    ?StartAddressChangeNotification@@YAXXZ; StartAddressChangeNotification(void)
0x18006e62e  call    ?NatNetConnectionRefreshAll@@YAJXZ; NatNetConnectionRefreshAll(void)
0x18006e633  cmp     esi, 0FFFFFFFFh
0x18006e636  jz      loc_18006EA60
0x18006e63c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006e643  mov     r8, r13; Size
0x18006e646  lea     rcx, [rbp+250h+InterfaceName]; void *
0x18006e64a  xor     edx, edx; Val
0x18006e64c  movdqu  xmmword ptr [rbp+250h+var_268.Data1], xmm0
0x18006e651  call    memset_0
0x18006e656  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e65d  cmp     rcx, rdi
0x18006e660  jz      short loc_18006E683
0x18006e662  test    [rcx+1Ch], r13d
0x18006e666  jz      short loc_18006E683
0x18006e668  cmp     byte ptr [rcx+19h], 5
0x18006e66c  jb      short loc_18006E683
0x18006e66e  mov     rcx, [rcx+10h]
0x18006e672  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e679  mov     edx, 79h ; 'y'
0x18006e67e  call    WPP_SF_
0x18006e683  lea     r8, [rsp+350h+InterfaceLuid]; union _NET_LUID_LH *
0x18006e688  mov     cs:?g_PrivIndex@@3KA, esi; ulong g_PrivIndex
0x18006e68e  lea     rdx, [rbp+250h+var_268]; struct _GUID *
0x18006e692  mov     ecx, esi; InterfaceIndex
0x18006e694  call    ?NatMapIndexToAdapterEx@@YAKKPEAU_GUID@@PEAT_NET_LUID_LH@@@Z; NatMapIndexToAdapterEx(ulong,_GUID *,_NET_LUID_LH *)
0x18006e699  test    eax, eax
0x18006e69b  jz      short loc_18006E6E1
0x18006e69d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e6a4  cmp     rcx, rdi
0x18006e6a7  jz      loc_18006EA81
0x18006e6ad  test    [rcx+1Ch], r13d
0x18006e6b1  jz      loc_18006EA81
0x18006e6b7  mov     edi, 2
0x18006e6bc  cmp     [rcx+19h], dil
0x18006e6c0  jb      loc_18006EA81
0x18006e6c6  mov     rcx, [rcx+10h]
0x18006e6ca  lea     edx, [rdi+78h]
0x18006e6cd  mov     r9d, eax
0x18006e6d0  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e6d7  call    WPP_SF_d
0x18006e6dc  jmp     loc_18006EA81
0x18006e6e1  lea     rbx, ?g_PrivateConnectionGuid@@3U_GUID@@A; _GUID g_PrivateConnectionGuid
0x18006e6e8  mov     [rsp+350h+var_31C], r12d
0x18006e6ed  mov     rcx, rbx; struct _GUID *
0x18006e6f0  mov     [rsp+350h+Block], r12
0x18006e6f5  lea     r8, [rsp+350h+var_31C]; enum NAT_IF_TYPE *
0x18006e6fa  lea     rdx, [rsp+350h+Block]; unsigned __int16 **
0x18006e6ff  call    ?FindAdapterNameByGuid@@YAJPEAU_GUID@@PEAPEAGPEAW4NAT_IF_TYPE@@@Z; FindAdapterNameByGuid(_GUID *,ushort * *,NAT_IF_TYPE *)
0x18006e704  mov     edi, 2
0x18006e709  test    eax, eax
0x18006e70b  jns     short loc_18006E750
0x18006e70d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e714  lea     rdx, WPP_GLOBAL_Control
0x18006e71b  cmp     rcx, rdx
0x18006e71e  jz      loc_18006E7BA
0x18006e724  test    [rcx+1Ch], r13d
0x18006e728  jz      loc_18006E7BA
0x18006e72e  cmp     [rcx+19h], dil
0x18006e732  jb      loc_18006E7BA
0x18006e738  mov     rcx, [rcx+10h]
0x18006e73c  lea     edx, [rdi+79h]
0x18006e73f  mov     r9d, eax
0x18006e742  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e749  call    WPP_SF_d
0x18006e74e  jmp     short loc_18006E7BA
0x18006e750  cmp     [rsp+350h+var_31C], 4
0x18006e755  mov     eax, 18AA8C0h
0x18006e75a  cmovz   r14d, eax
0x18006e75e  mov     cs:?g_PrivAddress@@3KA, r14d; ulong g_PrivAddress
0x18006e765  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e76c  lea     rdx, WPP_GLOBAL_Control
0x18006e773  cmp     rcx, rdx
0x18006e776  jz      short loc_18006E7A5
0x18006e778  test    [rcx+1Ch], r13d
0x18006e77c  jz      short loc_18006E7A5
0x18006e77e  cmp     byte ptr [rcx+19h], 5
0x18006e782  jb      short loc_18006E7A5
0x18006e784  mov     r9d, cs:?g_PrivIndex@@3KA; ulong g_PrivIndex
0x18006e78b  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006e792  mov     rcx, [rcx+10h]
0x18006e796  mov     edx, 7Ch ; '|'
0x18006e79b  mov     dword ptr [rsp+350h+var_330], r14d
0x18006e7a0  call    WPP_SF_Dd
0x18006e7a5  mov     rcx, [rsp+350h+Block]; Block
0x18006e7aa  test    rcx, rcx
0x18006e7ad  jz      short loc_18006E7BA
0x18006e7af  call    cs:__imp_free
0x18006e7b5  mov     [rsp+350h+Block], r12
0x18006e7ba  lea     rcx, [rbp+250h+Row]; Row
0x18006e7be  call    cs:__imp_InitializeUnicastIpAddressEntry
  ... truncated ...
```
