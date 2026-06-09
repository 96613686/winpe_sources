# NatInitialize(ulong)

- ea: `0x180073a7c`
- end: `0x1800744de`
- name: `?NatInitialize@@YAJK@Z`
- size: `2658`
- prototype: `__int64 __fastcall(NET_IFINDEX InterfaceIndex)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003e574`
- `0x180046db0`

## callees

- `0x180001ef0`
- `0x18000ca20`
- `0x18000d090`
- `0x1800202e0`
- `0x18002259c`
- `0x180023bac`
- `0x1800313f0`
- `0x18003a66c`
- `0x18003c63c`
- `0x18003ce70`
- `0x180044858`
- `0x18004561c`
- `0x180045660`
- `0x180045d00`
- `0x1800482ec`
- `0x18004ace0`
- `0x18004aef8`
- `0x18004fd9c`
- `0x180051f30`
- `0x180052bf4`
- `0x180063ec4`
- `0x180073a7c`
- `0x1800744e4`
- `0x180076eec`
- `0x180077008`
- `0x1800777ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180073fa9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180073fa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007431c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074285`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007431c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007429f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007429f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074336`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x180073ff1`
- `IPHLPAPI!ConvertInterfaceLuidToNameW` at `0x180073ff1`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x1800741e4`
- `IPHLPAPI!CreateUnicastIpAddressEntry` at `0x1800741e4`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180074184`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x180074184`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180073fbe`
- `IPHLPAPI!InitializeUnicastIpAddressEntry` at `0x180073fbe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180073b49`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180073b49`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073b5c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073b5c`
- `dhcpcsvc!DhcpEnableDhcp` at `0x180074071`
- `dhcpcsvc!DhcpEnableDhcp` at `0x180074071`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800742b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800742b0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180073bfd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180073bfd`

## string_xrefs

- `0x180073c74`: `NatRmStartProtocol`
- `0x180073cf8`: `AlgRmStartProtocol`
- `0x1800740db`: `SharedAccessMode`
- `0x1800742e1`: `SharedAccess (Full ICS)`

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
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
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
  if ( (unsigned int)dword_1800AD208 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800AD208, 0x200000000000LL) )
  {
    v37 = v5;
    Block = "SharedAccess (Full ICS)";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v31,
      (unsigned int)&unk_1800A34E8,
      v32,
      v33,
      (__int64)&v37,
      (__int64)&Block);
  }
  if ( v5 < 0 )
  {
    EnterCriticalSection(&gNatMain);
    byte_1800AE402 = 1;
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
0x180073a7c  push    rbp
0x180073a7e  push    rbx
0x180073a7f  push    rsi
0x180073a80  push    rdi
0x180073a81  push    r12
0x180073a83  push    r13
0x180073a85  push    r14
0x180073a87  push    r15
0x180073a89  lea     rbp, [rsp-218h]
0x180073a91  sub     rsp, 318h
0x180073a98  mov     rax, cs:__security_cookie
0x180073a9f  xor     rax, rsp
0x180073aa2  mov     [rbp+250h+var_50], rax
0x180073aa9  mov     esi, ecx
0x180073aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180073ab2  lea     rdi, WPP_GLOBAL_Control
0x180073ab9  mov     r13d, 200h
0x180073abf  cmp     rcx, rdi
0x180073ac2  jz      short loc_180073AE8
0x180073ac4  test    [rcx+1Ch], r13d
0x180073ac8  jz      short loc_180073AE8
0x180073aca  cmp     byte ptr [rcx+19h], 6
0x180073ace  jb      short loc_180073AE8
0x180073ad0  mov     rcx, [rcx+10h]
0x180073ad4  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073adb  mov     edx, 70h ; 'p'
0x180073ae0  mov     r9d, esi
0x180073ae3  call    WPP_SF_d
0x180073ae8  xor     r12d, r12d
0x180073aeb  lea     rcx, [rbp+250h+Row]; void *
0x180073aef  xor     edx, edx; Val
0x180073af1  mov     qword ptr [rsp+350h+InterfaceLuid], r12
0x180073af6  lea     r8d, [r12+50h]; Size
0x180073afb  call    memset_0
0x180073b00  call    ?IsPrivateConnectionPresent@@YAEXZ; IsPrivateConnectionPresent(void)
0x180073b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180073b0c  cmp     rcx, rdi
0x180073b0f  jz      short loc_180073B38
0x180073b11  test    [rcx+1Ch], r13d
0x180073b15  jz      short loc_180073B38
0x180073b17  cmp     byte ptr [rcx+19h], 5
0x180073b1b  jb      short loc_180073B38
0x180073b1d  mov     rcx, [rcx+10h]
0x180073b21  lea     edx, [r12+71h]
0x180073b26  test    al, al
0x180073b28  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073b2f  setnz   r9b
0x180073b33  call    WPP_SF_c
0x180073b38  call    ?ClearPersistentDhcpExceptions@@YAXXZ; ClearPersistentDhcpExceptions(void)
0x180073b3d  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180073b44  mov     edx, 1; fCancelPendingCallbacks
0x180073b49  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180073b50  nop     dword ptr [rax+rax+00h]
0x180073b55  mov     rcx, cs:?g_FirewallExceptionBackgroundWork@@3PEAU_TP_WORK@@EA; pwk
0x180073b5c  call    cs:__imp_SubmitThreadpoolWork
0x180073b63  nop     dword ptr [rax+rax+00h]
0x180073b68  mov     ecx, 1
0x180073b6d  mov     [rsp+350h+var_300], 1
0x180073b76  mov     r14d, 189A8C0h
0x180073b7c  mov     [rsp+350h+var_2F8], 1
0x180073b84  mov     [rsp+350h+var_2F4], 0Ch
0x180073b8d  mov     [rsp+350h+var_2EC], r12
0x180073b92  mov     [rsp+350h+var_2E4], r12
0x180073b97  mov     [rsp+350h+var_308], 1
0x180073ba0  call    ?NhSetComponentMode@@YAEW4NH_COMPONENT_MODE@@@Z; NhSetComponentMode(NH_COMPONENT_MODE)
0x180073ba5  test    al, al
0x180073ba7  jnz     short loc_180073BF2
0x180073ba9  mov     ebx, 80004005h
0x180073bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180073bb5  cmp     rcx, rdi
0x180073bb8  jz      loc_1800742BC
0x180073bbe  test    [rcx+1Ch], r13d
0x180073bc2  jz      loc_1800742BC
0x180073bc8  mov     edi, 2
0x180073bcd  cmp     [rcx+19h], dil
0x180073bd1  jb      loc_1800742BC
0x180073bd7  mov     rcx, [rcx+10h]
0x180073bdb  lea     edx, [rdi+70h]
0x180073bde  mov     r9d, ebx
0x180073be1  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073be8  call    WPP_SF_d
0x180073bed  jmp     loc_1800742BC
0x180073bf2  xor     edx, edx; dwCoInit
0x180073bf4  mov     cs:?NhpComponentModeSet@@3EA, 1; uchar NhpComponentModeSet
0x180073bfb  xor     ecx, ecx; pvReserved
0x180073bfd  call    cs:__imp_CoInitializeEx
0x180073c04  nop     dword ptr [rax+rax+00h]
0x180073c09  mov     r15d, eax
0x180073c0c  mov     eax, 80000000h
0x180073c11  lea     ecx, [r15+rax]
0x180073c15  test    eax, ecx
0x180073c17  jnz     short loc_180073C5D
0x180073c19  cmp     r15d, 80010106h
0x180073c20  jz      short loc_180073C5D
0x180073c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c29  cmp     rcx, rdi
0x180073c2c  jz      short loc_180073C55
0x180073c2e  test    [rcx+1Ch], r13d
0x180073c32  jz      short loc_180073C55
0x180073c34  mov     edi, 2
0x180073c39  cmp     [rcx+19h], dil
0x180073c3d  jb      short loc_180073C55
0x180073c3f  mov     rcx, [rcx+10h]
0x180073c43  lea     edx, [rdi+71h]
0x180073c46  mov     r9d, r15d
0x180073c49  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073c50  call    WPP_SF_d
0x180073c55  mov     ebx, r15d
0x180073c58  jmp     loc_1800742BC
0x180073c5d  lea     rax, ?NhpStopNatEvent@@3PEAXEA; void * NhpStopNatEvent
0x180073c64  mov     r9d, 24h ; '$'; unsigned int
0x180073c6a  lea     r8, [rsp+350h+var_300]; void *
0x180073c6f  mov     [rsp+350h+var_330], rax; void **
0x180073c74  lea     rdx, aNatrmstartprot; "NatRmStartProtocol"
0x180073c7b  lea     rcx, ?NatRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; unsigned int (*)(void *, struct _SUPPORT_FUNCTIONS_50 *, void *, unsigned int, unsigned int, unsigned int)
0x180073c82  call    ?NatStartProtocol@@YAJP6AKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@ZPEBD0KPEAPEAX@Z; NatStartProtocol(ulong (*)(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong),char const *,void *,ulong,void * *)
0x180073c87  mov     ebx, eax
0x180073c89  test    eax, eax
0x180073c8b  jns     short loc_180073CD1
0x180073c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180073c94  cmp     rcx, rdi
0x180073c97  jz      loc_1800742AB
0x180073c9d  test    [rcx+1Ch], r13d
0x180073ca1  jz      loc_1800742AB
0x180073ca7  mov     edi, 2
0x180073cac  cmp     [rcx+19h], dil
0x180073cb0  jb      loc_1800742AB
0x180073cb6  lea     edx, [rdi+72h]
0x180073cb9  mov     rcx, [rcx+10h]
0x180073cbd  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073cc4  mov     r9d, eax
0x180073cc7  call    WPP_SF_d
0x180073ccc  jmp     loc_1800742AB
0x180073cd1  lea     rcx, aAlg; "ALG"
0x180073cd8  call    ?NatStartServiceSync@@YAJPEBGKK@Z; NatStartServiceSync(ushort const *,ulong,ulong)
0x180073cdd  test    eax, eax
0x180073cdf  js      short loc_180073D42
0x180073ce1  lea     rax, ?NhpStopAlgEvent@@3PEAXEA; void * NhpStopAlgEvent
0x180073ce8  mov     r9d, 8; unsigned int
0x180073cee  lea     r8, [rsp+350h+var_308]; void *
0x180073cf3  mov     [rsp+350h+var_330], rax; void **
0x180073cf8  lea     rdx, aAlgrmstartprot; "AlgRmStartProtocol"
0x180073cff  lea     rcx, ?AlgRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z; unsigned int (*)(void *, struct _SUPPORT_FUNCTIONS_50 *, void *, unsigned int, unsigned int, unsigned int)
0x180073d06  call    ?NatStartProtocol@@YAJP6AKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@ZPEBD0KPEAPEAX@Z; NatStartProtocol(ulong (*)(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong),char const *,void *,ulong,void * *)
0x180073d0b  mov     ebx, eax
0x180073d0d  test    eax, eax
0x180073d0f  jns     short loc_180073D72
0x180073d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d18  cmp     rcx, rdi
0x180073d1b  jz      loc_1800742AB
0x180073d21  test    [rcx+1Ch], r13d
0x180073d25  jz      loc_1800742AB
0x180073d2b  mov     edi, 2
0x180073d30  cmp     [rcx+19h], dil
0x180073d34  jb      loc_1800742AB
0x180073d3a  lea     edx, [rdi+73h]
0x180073d3d  jmp     loc_180073CB9
0x180073d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d49  cmp     rcx, rdi
0x180073d4c  jz      short loc_180073D72
0x180073d4e  test    [rcx+1Ch], r13d
0x180073d52  jz      short loc_180073D72
0x180073d54  cmp     byte ptr [rcx+19h], 3
0x180073d58  jb      short loc_180073D72
0x180073d5a  mov     rcx, [rcx+10h]
0x180073d5e  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073d65  mov     edx, 76h ; 'v'
0x180073d6a  mov     r9d, eax
0x180073d6d  call    WPP_SF_d
0x180073d72  lea     rcx, aNla; "NLA"
0x180073d79  call    ?NatStartServiceSync@@YAJPEBGKK@Z; NatStartServiceSync(ushort const *,ulong,ulong)
0x180073d7e  mov     ebx, eax
0x180073d80  test    eax, eax
0x180073d82  jns     short loc_180073DB7
0x180073d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180073d8b  cmp     rcx, rdi
0x180073d8e  jz      short loc_180073DB4
0x180073d90  test    [rcx+1Ch], r13d
0x180073d94  jz      short loc_180073DB4
0x180073d96  cmp     byte ptr [rcx+19h], 3
0x180073d9a  jb      short loc_180073DB4
0x180073d9c  mov     rcx, [rcx+10h]
0x180073da0  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073da7  mov     edx, 77h ; 'w'
0x180073dac  mov     r9d, eax
0x180073daf  call    WPP_SF_d
0x180073db4  mov     ebx, r12d
0x180073db7  lea     rdx, ?NhPolicyAllowsSharing@@3HA; int *
0x180073dbe  call    ?NatGetPolicy@@YAXPEAH0@Z; NatGetPolicy(int *,int *)
0x180073dc3  call    NatStartConnectionManagement
0x180073dc8  test    eax, eax
0x180073dca  jz      short loc_180073E23
0x180073dcc  jg      short loc_180073DD2
0x180073dce  mov     ebx, eax
0x180073dd0  jmp     short loc_180073DDB
0x180073dd2  movzx   ebx, ax
0x180073dd5  or      ebx, 80070000h
0x180073ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180073de2  cmp     rcx, rdi
0x180073de5  jz      loc_1800742AB
0x180073deb  test    [rcx+1Ch], r13d
0x180073def  jz      loc_1800742AB
0x180073df5  mov     edi, 2
0x180073dfa  cmp     [rcx+19h], dil
0x180073dfe  jb      loc_1800742AB
0x180073e04  mov     rcx, [rcx+10h]
0x180073e08  lea     edx, [rdi+76h]
0x180073e0b  mov     r9d, eax
0x180073e0e  mov     dword ptr [rsp+350h+var_330], ebx
0x180073e12  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073e19  call    WPP_SF_Dd
0x180073e1e  jmp     loc_1800742AB
0x180073e23  call    ?StartAddressChangeNotification@@YAXXZ; StartAddressChangeNotification(void)
0x180073e28  call    ?NatNetConnectionRefreshAll@@YAJXZ; NatNetConnectionRefreshAll(void)
0x180073e2d  cmp     esi, 0FFFFFFFFh
0x180073e30  jz      loc_18007427E
0x180073e36  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180073e3d  mov     r8, r13; Size
0x180073e40  lea     rcx, [rbp+250h+InterfaceName]; void *
0x180073e44  xor     edx, edx; Val
0x180073e46  movdqu  xmmword ptr [rbp+250h+var_268.Data1], xmm0
0x180073e4b  call    memset_0
0x180073e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180073e57  cmp     rcx, rdi
0x180073e5a  jz      short loc_180073E7D
0x180073e5c  test    [rcx+1Ch], r13d
0x180073e60  jz      short loc_180073E7D
0x180073e62  cmp     byte ptr [rcx+19h], 5
0x180073e66  jb      short loc_180073E7D
0x180073e68  mov     rcx, [rcx+10h]
0x180073e6c  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073e73  mov     edx, 79h ; 'y'
0x180073e78  call    WPP_SF_
0x180073e7d  lea     r8, [rsp+350h+InterfaceLuid]; union _NET_LUID_LH *
0x180073e82  mov     cs:?g_PrivIndex@@3KA, esi; ulong g_PrivIndex
0x180073e88  lea     rdx, [rbp+250h+var_268]; struct _GUID *
0x180073e8c  mov     ecx, esi; InterfaceIndex
0x180073e8e  call    ?NatMapIndexToAdapterEx@@YAKKPEAU_GUID@@PEAT_NET_LUID_LH@@@Z; NatMapIndexToAdapterEx(ulong,_GUID *,_NET_LUID_LH *)
0x180073e93  test    eax, eax
0x180073e95  jz      short loc_180073EDB
0x180073e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180073e9e  cmp     rcx, rdi
0x180073ea1  jz      loc_1800742AB
0x180073ea7  test    [rcx+1Ch], r13d
0x180073eab  jz      loc_1800742AB
0x180073eb1  mov     edi, 2
0x180073eb6  cmp     [rcx+19h], dil
0x180073eba  jb      loc_1800742AB
0x180073ec0  mov     rcx, [rcx+10h]
0x180073ec4  lea     edx, [rdi+78h]
0x180073ec7  mov     r9d, eax
0x180073eca  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073ed1  call    WPP_SF_d
0x180073ed6  jmp     loc_1800742AB
0x180073edb  lea     rbx, ?g_PrivateConnectionGuid@@3U_GUID@@A; _GUID g_PrivateConnectionGuid
0x180073ee2  mov     [rsp+350h+var_31C], r12d
0x180073ee7  mov     rcx, rbx; struct _GUID *
0x180073eea  mov     [rsp+350h+Block], r12
0x180073eef  lea     r8, [rsp+350h+var_31C]; enum NAT_IF_TYPE *
0x180073ef4  lea     rdx, [rsp+350h+Block]; unsigned __int16 **
0x180073ef9  call    ?FindAdapterNameByGuid@@YAJPEAU_GUID@@PEAPEAGPEAW4NAT_IF_TYPE@@@Z; FindAdapterNameByGuid(_GUID *,ushort * *,NAT_IF_TYPE *)
0x180073efe  mov     edi, 2
0x180073f03  test    eax, eax
0x180073f05  jns     short loc_180073F4A
0x180073f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180073f0e  lea     rdx, WPP_GLOBAL_Control
0x180073f15  cmp     rcx, rdx
0x180073f18  jz      loc_180073FBA
0x180073f1e  test    [rcx+1Ch], r13d
0x180073f22  jz      loc_180073FBA
0x180073f28  cmp     [rcx+19h], dil
0x180073f2c  jb      loc_180073FBA
0x180073f32  mov     rcx, [rcx+10h]
0x180073f36  lea     edx, [rdi+79h]
0x180073f39  mov     r9d, eax
0x180073f3c  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073f43  call    WPP_SF_d
0x180073f48  jmp     short loc_180073FBA
0x180073f4a  cmp     [rsp+350h+var_31C], 4
0x180073f4f  mov     eax, 18AA8C0h
0x180073f54  cmovz   r14d, eax
0x180073f58  mov     cs:?g_PrivAddress@@3KA, r14d; ulong g_PrivAddress
0x180073f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073f66  lea     rdx, WPP_GLOBAL_Control
0x180073f6d  cmp     rcx, rdx
0x180073f70  jz      short loc_180073F9F
0x180073f72  test    [rcx+1Ch], r13d
0x180073f76  jz      short loc_180073F9F
0x180073f78  cmp     byte ptr [rcx+19h], 5
0x180073f7c  jb      short loc_180073F9F
0x180073f7e  mov     r9d, cs:?g_PrivIndex@@3KA; ulong g_PrivIndex
0x180073f85  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180073f8c  mov     rcx, [rcx+10h]
0x180073f90  mov     edx, 7Ch ; '|'
0x180073f95  mov     dword ptr [rsp+350h+var_330], r14d
0x180073f9a  call    WPP_SF_Dd
0x180073f9f  mov     rcx, [rsp+350h+Block]; Block
0x180073fa4  test    rcx, rcx
0x180073fa7  jz      short loc_180073FBA
0x180073fa9  call    cs:__imp_free
  ... truncated ...
```
