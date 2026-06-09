# int_VpnProfileAutoConnect(bool)

- ea: `0x1800d67a8`
- end: `0x1800d7377`
- name: `?int_VpnProfileAutoConnect@@YAK_N@Z`
- size: `3023`
- prototype: `__int64 __fastcall(unsigned __int8, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cb180`
- `0x1800cb420`
- `0x1800cbb64`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bf70`
- `0x18000e5f0`
- `0x18000e650`
- `0x18003204c`
- `0x180032508`
- `0x1800552a4`
- `0x1800b81fc`
- `0x1800bcf60`
- `0x1800bda40`
- `0x1800bea1c`
- `0x1800bf530`
- `0x1800c0ef0`
- `0x1800c85f8`
- `0x1800c8c88`
- `0x1800cac58`
- `0x1800cad98`
- `0x1800d67a8`
- `0x1800daba4`
- `0x1800e1cd8`
- `0x1800e1d04`
- `0x1800e1e64`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e71e2`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800d6ae5`
- `msvcrt!wcscpy_s` at `0x1800d6ae5`
- `ntdll!RtlIsMultiSessionSku` at `0x1800d6eeb`
- `ntdll!RtlIsMultiSessionSku` at `0x1800d6eeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d72da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d72ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d72da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d72ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6e62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6e62`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800d6e54`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800d6e54`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d6f9d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d6fbb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d708a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d70ad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d6f9d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d6fbb`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d708a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d70ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800d68c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800d68c3`
- `RASAPI32!RasTriggerConnectionWithDetails` at `0x1800d7016`
- `RASAPI32!RasTriggerConnectionWithDetails` at `0x1800d7016`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetConnectStatusW` at `0x1800d6a60`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetConnectStatusW` at `0x1800d6a60`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasTriggerConnection` at `0x1800d703f`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasTriggerConnection` at `0x1800d703f`

## string_xrefs

- `0x1800d6a12`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d6b45`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d6cc3`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d6ec2`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7119`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d71f1`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7344`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d6ed3`: `DuplicateToken`

## pseudocode

```c
__int64 __fastcall int_VpnProfileAutoConnect(unsigned __int8 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r13d
  DWORD ConnectStatusW; // ebx
  int v6; // esi
  LPCWSTR *v7; // r15
  ULONGLONG TickCount64; // rax
  __int64 v9; // rcx
  bool v10; // di
  struct _LIST_ENTRY *v11; // rcx
  unsigned int v12; // r12d
  HRASCONN *v13; // rsi
  unsigned int EntryHrasconnW; // eax
  unsigned int v15; // ebx
  HRASCONN v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  struct _LIST_ENTRY *v19; // rcx
  int v20; // ebx
  int BestCostNetworkConnectionInternal; // eax
  unsigned int v22; // ebx
  struct _LIST_ENTRY *v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rcx
  DWORD LastError; // edi
  GUID *v27; // rdx
  bool v28; // zf
  unsigned int v29; // eax
  HRASCONN v30; // rcx
  _DWORD *v31; // rax
  __int64 v32; // rcx
  const char *v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rdx
  void *DuplicateTokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+50h] [rbp-B0h]
  struct _GUID v41; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID Buf2; // [rsp+70h] [rbp-90h] BYREF
  __int128 Buf1; // [rsp+80h] [rbp-80h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-70h] BYREF
  struct tagRASCONNSTATUSW v45; // [rsp+A0h] [rbp-60h] BYREF

  v4 = a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a1;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 312, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, a4);
  }
  ConnectStatusW = 0;
  ExistingTokenHandle = 0;
  DuplicateTokenHandle = 0;
  v38 = 0;
  memset_0(&v45, 0, sizeof(v45));
  v6 = g_IsActiveDeviceProfile;
  v39 = 0;
  Buf1 = 0;
  if ( (_BYTE)v4 )
    v6 = g_IsActiveUserProfile;
  Buf2 = 0;
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  v7 = &g_ActiveUserProfile;
  if ( !(_BYTE)v4 )
    v7 = &g_ActiveDeviceProfile;
  if ( g_deviceLastPowerState == 1 || g_CrmIsDisconnectedStandby )
  {
    v12 = 9;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 )
    {
      goto LABEL_168;
    }
    v35 = 313;
LABEL_167:
    WPP_SF_(v11[1].Flink, v35, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    goto LABEL_168;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl'::`2'::impl) )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 12, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    TickCount64 = GetTickCount64();
    v9 = qword_18010E920;
    if ( (_BYTE)v4 )
      v9 = qword_18010E928;
    if ( v9 )
      v10 = TickCount64 - v9 < 0xEA60;
    else
      v10 = 0;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 13, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v10 )
    {
      v12 = 22;
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
        WPP_SF_d(v11[1].Flink, 314, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v4);
      goto LABEL_168;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
  }
  if ( !v6 )
  {
    v12 = 6;
    if ( v11 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v11[1].Blink) & 4) == 0 )
      goto LABEL_168;
    v35 = 337;
    goto LABEL_167;
  }
  v12 = 0;
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
  {
    WPP_SF_(v11[1].Flink, 315, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  v13 = (HRASCONN *)(v7 + 5);
  if ( !v7[5] )
  {
    EntryHrasconnW = RasGetEntryHrasconnW(*v7, v7[1], v7 + 5);
    v15 = EntryHrasconnW;
    if ( EntryHrasconnW )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 316, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, EntryHrasconnW);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v15,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          3261,
          "int_VpnProfileAutoConnect");
    }
    v11 = WPP_GLOBAL_Control;
  }
  ConnectStatusW = 0;
  if ( *v13 )
  {
    if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
      WPP_SF_(v11[1].Flink, 317, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    v16 = *v13;
    v45.dwSize = 608;
    ConnectStatusW = RasGetConnectStatusW(v16, &v45);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        318,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        (unsigned int)v45.rasconnstate);
      v11 = WPP_GLOBAL_Control;
    }
    if ( ConnectStatusW )
    {
      if ( ConnectStatusW != 6 )
      {
        v12 = 17;
        if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 1) != 0 )
          WPP_SF_d(v11[1].Flink, 320, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, ConnectStatusW);
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          goto LABEL_168;
        v17 = 3289;
LABEL_57:
        TraceVpnWppErrorW32Impl(
          ConnectStatusW,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          v17,
          "int_VpnProfileAutoConnect");
LABEL_168:
        AddVPNCanceledEvent(v12);
        goto LABEL_169;
      }
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
        WPP_SF_(v11[1].Flink, 319, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      *v13 = 0;
      v7[6] = 0;
      *((_DWORD *)v7 + 145) = 0;
      wcscpy_s((wchar_t *)v7 + 28, 0x104u, &Class);
      v11 = WPP_GLOBAL_Control;
      ConnectStatusW = 0;
    }
    else if ( v45.rasconnstate == RASCS_Disconnected )
    {
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
      {
        WPP_SF_(v11[1].Flink, 321, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        v11 = WPP_GLOBAL_Control;
      }
      *v13 = 0;
    }
    else
    {
      v12 = 19;
    }
  }
  if ( *v13 )
    goto LABEL_168;
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
    WPP_SF_(v11[1].Flink, 322, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  NlmHandlerCheckInternetConnectivity(&v38);
  v19 = WPP_GLOBAL_Control;
  v20 = v38;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    LOBYTE(v18) = v38 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 323, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v18);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v20 != 1 )
  {
    ConnectStatusW = 21;
    v12 = 1;
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v19, InternetUnavailableTriggerFailed, v7[1]);
      v19 = WPP_GLOBAL_Control;
    }
    if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v19[1].Blink) & 4) != 0 )
      WPP_SF_d(v19[1].Flink, 324, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 21);
    goto LABEL_168;
  }
  BestCostNetworkConnectionInternal = NlmGetBestCostNetworkConnectionInternal(&Buf1, &Buf2, &v39);
  v22 = BestCostNetworkConnectionInternal;
  v12 = 2;
  if ( BestCostNetworkConnectionInternal < 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        325,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        (unsigned int)BestCostNetworkConnectionInternal);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v22,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        3327,
        "int_VpnProfileAutoConnect");
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF__guid_d(WPP_GLOBAL_Control[1].Flink, 326, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, &Buf2);
    v23 = WPP_GLOBAL_Control;
  }
  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    ConnectStatusW = 21;
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v24, InternetUnavailableTriggerFailed, v7[1]);
      v23 = WPP_GLOBAL_Control;
    }
    if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 1) != 0 )
      WPP_SF_Sd(
        v23[1].Flink,
        327,
        (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        (unsigned int)v7[1],
        21);
    goto LABEL_168;
  }
  if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
  {
    WPP_SF_ddd(
      v23[1].Flink,
      328,
      &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
      *((unsigned int *)v7 + 8),
      1,
      *((_DWORD *)v7 + 145));
    v23 = WPP_GLOBAL_Control;
  }
  *((_DWORD *)v7 + 8) = 1;
  if ( (_BYTE)v4 )
  {
    ConnectStatusW = GetActiveTokenAndSessionId((void *)v7[2]);
    if ( ConnectStatusW )
    {
      v12 = 20;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 329, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, ConnectStatusW);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_168;
      v17 = 3353;
      goto LABEL_57;
    }
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v12 = 12;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 330, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            LastError,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            3361,
            "int_VpnProfileAutoConnect");
        VpnReportError("int_VpnProfileAutoConnect", "DuplicateToken", LastError);
        goto LABEL_168;
      }
    }
    if ( !(unsigned __int8)RtlIsMultiSessionSku(v25) && (unsigned int)IsTokenForDefaultAccount(DuplicateTokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 331, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      ConnectStatusW = 21;
      v12 = 21;
      goto LABEL_168;
    }
    v23 = WPP_GLOBAL_Control;
  }
  if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
    WPP_SF_S(v23[1].Flink, 332, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v7[1]);
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v24, VpnAutoTriggerConnectionAttempt, v7[1]);
  ActivityId = 0;
  EventActivityIdControl(1u, &ActivityId);
  v27 = &::ActivityId;
  if ( !(_BYTE)v4 )
    v27 = &stru_18010E550;
  EventActivityIdControl(2u, v27);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::GetImpl'::`2'::impl) )
  {
    v28 = *((_DWORD *)v7 + 151) == 0;
    *((_DWORD *)v7 + 150) = 2;
    if ( v28 )
      *((_DWORD *)v7 + 151) = 1;
    v29 = RasTriggerConnectionWithDetails(*v7, v7[1], DuplicateTokenHandle, *((unsigned int *)v7 + 6));
  }
  else
  {
    v29 = RasTriggerConnection(*v7, v7[1], DuplicateTokenHandle, *((unsigned int *)v7 + 6));
  }
  v30 = (HRASCONN)v7[5];
  v41 = Buf2;
  ConnectStatusW = v29;
  LogStartPhysicalConnection(v30, v4, &v41, v29);
  VpnCriticalSectionEnter(&g_connMonitorCs);
  v31 = g_pMonitor;
  if ( g_pMonitor )
  {
    if ( !*((_DWORD *)g_pMonitor + 2) )
    {
      EventActivityIdControl(1u, (LPGUID)((char *)g_pMonitor + 56));
      v31 = g_pMonitor;
    }
    v31[2] = 1;
    VpnCriticalSectionLeave(&g_connMonitorCs);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::GetImpl'::`2'::impl) )
  {
    if ( ConnectStatusW )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 333, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, ConnectStatusW);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          ConnectStatusW,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          3424,
          "int_VpnProfileAutoConnect");
      if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(v32, VpnAutoTriggerConnectionAttemptFailed, v7[1]);
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_dq(
        WPP_GLOBAL_Control[1].Flink,
        334,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        ConnectStatusW,
        v7[5]);
    }
    if ( ConnectStatusW )
    {
      v33 = "RasTriggerConnectionWithDetails";
LABEL_147:
      VpnReportError("int_VpnProfileAutoConnect", v33, ConnectStatusW);
    }
  }
  else
  {
    if ( ConnectStatusW )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 335, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, ConnectStatusW);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          ConnectStatusW,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          3436,
          "int_VpnProfileAutoConnect");
      if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(v34, VpnAutoTriggerConnectionAttemptFailed, v7[1]);
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_dq(
        WPP_GLOBAL_Control[1].Flink,
        336,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        ConnectStatusW,
        v7[5]);
    }
    if ( ConnectStatusW )
    {
      v33 = "RasTriggerConnection";
      goto LABEL_147;
    }
  }
LABEL_169:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( ExistingTokenHandle )
    CloseHandle(ExistingTokenHandle);
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( (ConnectStatusW & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 338, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, ConnectStatusW);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        ConnectStatusW,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        3473,
        "int_VpnProfileAutoConnect");
  }
  return ConnectStatusW;
}

```

## disassembly

```asm
0x1800d67a8  push    rbp
0x1800d67aa  push    rbx
0x1800d67ab  push    rsi
0x1800d67ac  push    rdi
0x1800d67ad  push    r12
0x1800d67af  push    r13
0x1800d67b1  push    r14
0x1800d67b3  push    r15
0x1800d67b5  lea     rbp, [rsp-218h]
0x1800d67bd  sub     rsp, 318h
0x1800d67c4  mov     rax, cs:__security_cookie
0x1800d67cb  xor     rax, rsp
0x1800d67ce  mov     [rbp+250h+var_50], rax
0x1800d67d5  movzx   r13d, cl
0x1800d67d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d67e0  lea     rdi, WPP_GLOBAL_Control
0x1800d67e7  lea     r14, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d67ee  mov     r12b, 8
0x1800d67f1  cmp     rcx, rdi
0x1800d67f4  jz      short loc_1800D6810
0x1800d67f6  test    [rcx+1Ch], r12b
0x1800d67fa  jz      short loc_1800D6810
0x1800d67fc  mov     rcx, [rcx+10h]
0x1800d6800  mov     edx, 138h
0x1800d6805  mov     r9b, r13b
0x1800d6808  mov     r8, r14
0x1800d680b  call    WPP_SF_c
0x1800d6810  xor     ebx, ebx
0x1800d6812  lea     rcx, [rbp+250h+var_2B0]; void *
0x1800d6816  xor     edx, edx; Val
0x1800d6818  mov     [rsp+350h+ExistingTokenHandle], rbx
0x1800d681d  mov     r8d, 260h; Size
0x1800d6823  mov     [rsp+350h+DuplicateTokenHandle], rbx
0x1800d6828  mov     [rsp+350h+var_308], ebx
0x1800d682c  call    memset_0
0x1800d6831  mov     esi, cs:?g_IsActiveDeviceProfile@@3HA; int g_IsActiveDeviceProfile
0x1800d6837  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800d683e  xorps   xmm0, xmm0
0x1800d6841  mov     [rsp+350h+var_304], ebx
0x1800d6845  xorps   xmm1, xmm1
0x1800d6848  test    r13b, r13b
0x1800d684b  movups  [rbp+250h+Buf1], xmm0
0x1800d684f  cmovnz  esi, cs:?g_IsActiveUserProfile@@3HA; int g_IsActiveUserProfile
0x1800d6856  movups  [rsp+350h+Buf2], xmm1
0x1800d685b  call    VpnCriticalSectionEnter
0x1800d6860  test    r13b, r13b
0x1800d6863  lea     rax, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800d686a  lea     r15, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d6871  cmovz   r15, rax
0x1800d6875  cmp     cs:?g_deviceLastPowerState@@3W4_VPNPROFILEDEVICESTATE@@A, 1; _VPNPROFILEDEVICESTATE g_deviceLastPowerState
0x1800d687c  jz      loc_1800D727F
0x1800d6882  cmp     cs:?g_CrmIsDisconnectedStandby@@3HA, ebx; int g_CrmIsDisconnectedStandby
0x1800d6888  jnz     loc_1800D727F
0x1800d688e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl(void)'::`2'::impl
0x1800d6895  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(void)
0x1800d689a  test    al, al
0x1800d689c  jz      loc_1800D6968
0x1800d68a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d68a9  cmp     rcx, rdi
0x1800d68ac  jz      short loc_1800D68C3
0x1800d68ae  test    [rcx+1Ch], r12b
0x1800d68b2  jz      short loc_1800D68C3
0x1800d68b4  mov     rcx, [rcx+10h]
0x1800d68b8  lea     edx, [rbx+0Ch]
0x1800d68bb  mov     r8, r14
0x1800d68be  call    WPP_SF_
0x1800d68c3  call    cs:__imp_GetTickCount64
0x1800d68c9  mov     rcx, cs:qword_18010E920
0x1800d68d0  test    r13b, r13b
0x1800d68d3  cmovnz  rcx, cs:qword_18010E928
0x1800d68db  test    rcx, rcx
0x1800d68de  jnz     short loc_1800D68E5
0x1800d68e0  xor     dil, dil
0x1800d68e3  jmp     short loc_1800D68F2
0x1800d68e5  sub     rax, rcx
0x1800d68e8  cmp     rax, 0EA60h
0x1800d68ee  setb    dil
0x1800d68f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d68f9  lea     rax, WPP_GLOBAL_Control
0x1800d6900  cmp     rcx, rax
0x1800d6903  jz      short loc_1800D692A
0x1800d6905  test    [rcx+1Ch], r12b
0x1800d6909  jz      short loc_1800D692A
0x1800d690b  mov     rcx, [rcx+10h]
0x1800d690f  mov     edx, 0Dh
0x1800d6914  mov     r8, r14
0x1800d6917  call    WPP_SF_
0x1800d691c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6923  lea     rax, WPP_GLOBAL_Control
0x1800d692a  test    dil, dil
0x1800d692d  jz      short loc_1800D6971
0x1800d692f  mov     r12d, 16h
0x1800d6935  cmp     rcx, rax
0x1800d6938  jz      loc_1800D72AF
0x1800d693e  mov     r14b, 4
0x1800d6941  test    [rcx+1Ch], r14b
0x1800d6945  jz      loc_1800D72AF
0x1800d694b  mov     rcx, [rcx+10h]
0x1800d694f  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6956  mov     r9d, r13d
0x1800d6959  mov     edx, 13Ah
0x1800d695e  call    WPP_SF_d
0x1800d6963  jmp     loc_1800D72AF
0x1800d6968  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d696f  jmp     short loc_1800D6978
0x1800d6971  lea     rdi, WPP_GLOBAL_Control
0x1800d6978  test    esi, esi
0x1800d697a  jz      loc_1800D7264
0x1800d6980  xor     r12d, r12d
0x1800d6983  mov     r14b, 4
0x1800d6986  cmp     rcx, rdi
0x1800d6989  jz      short loc_1800D69AD
0x1800d698b  test    [rcx+1Ch], r14b
0x1800d698f  jz      short loc_1800D69AD
0x1800d6991  mov     rcx, [rcx+10h]
0x1800d6995  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d699c  mov     edx, 13Bh
0x1800d69a1  call    WPP_SF_
0x1800d69a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d69ad  lea     rsi, [r15+28h]
0x1800d69b1  cmp     [rsi], rbx
0x1800d69b4  jnz     short loc_1800D6A27
0x1800d69b6  mov     rdx, [r15+8]
0x1800d69ba  mov     r8, rsi
0x1800d69bd  mov     rcx, [r15]
0x1800d69c0  call    RasGetEntryHrasconnW
0x1800d69c5  mov     ebx, eax
0x1800d69c7  test    eax, eax
0x1800d69c9  jz      short loc_1800D6A20
0x1800d69cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d69d2  cmp     rcx, rdi
0x1800d69d5  jz      short loc_1800D69F5
0x1800d69d7  test    byte ptr [rcx+1Ch], 1
0x1800d69db  jz      short loc_1800D69F5
0x1800d69dd  mov     rcx, [rcx+10h]
0x1800d69e1  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d69e8  mov     edx, 13Ch
0x1800d69ed  mov     r9d, eax
0x1800d69f0  call    WPP_SF_d
0x1800d69f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d69fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d6a01  test    al, al
0x1800d6a03  jz      short loc_1800D6A20
0x1800d6a05  lea     r9, aIntVpnprofilea; "int_VpnProfileAutoConnect"
0x1800d6a0c  mov     r8d, 0CBDh
0x1800d6a12  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d6a19  mov     ecx, ebx
0x1800d6a1b  call    TraceVpnWppErrorW32Impl
0x1800d6a20  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6a27  xor     ebx, ebx
0x1800d6a29  cmp     [rsi], rbx
0x1800d6a2c  jz      loc_1800D6B91
0x1800d6a32  cmp     rcx, rdi
0x1800d6a35  jz      short loc_1800D6A52
0x1800d6a37  test    [rcx+1Ch], r14b
0x1800d6a3b  jz      short loc_1800D6A52
0x1800d6a3d  mov     rcx, [rcx+10h]
0x1800d6a41  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6a48  mov     edx, 13Dh
0x1800d6a4d  call    WPP_SF_
0x1800d6a52  mov     rcx, [rsi]; HRASCONN
0x1800d6a55  lea     rdx, [rbp+250h+var_2B0]; struct tagRASCONNSTATUSW *
0x1800d6a59  mov     [rbp+250h+var_2B0.dwSize], 260h
0x1800d6a60  call    cs:__imp_RasGetConnectStatusW
0x1800d6a66  mov     ebx, eax
0x1800d6a68  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6a6f  cmp     rcx, rdi
0x1800d6a72  jz      short loc_1800D6A9A
0x1800d6a74  test    [rcx+1Ch], r14b
0x1800d6a78  jz      short loc_1800D6A9A
0x1800d6a7a  mov     r9d, [rbp+250h+var_2B0.rasconnstate]
0x1800d6a7e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6a85  mov     rcx, [rcx+10h]
0x1800d6a89  mov     edx, 13Eh
0x1800d6a8e  call    WPP_SF_d
0x1800d6a93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6a9a  test    ebx, ebx
0x1800d6a9c  jz      loc_1800D6B56
0x1800d6aa2  cmp     ebx, 6
0x1800d6aa5  jnz     short loc_1800D6AF9
0x1800d6aa7  cmp     rcx, rdi
0x1800d6aaa  jz      short loc_1800D6AC7
0x1800d6aac  test    [rcx+1Ch], r14b
0x1800d6ab0  jz      short loc_1800D6AC7
0x1800d6ab2  mov     rcx, [rcx+10h]
0x1800d6ab6  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6abd  mov     edx, 13Fh
0x1800d6ac2  call    WPP_SF_
0x1800d6ac7  lea     rcx, [r15+38h]; Destination
0x1800d6acb  mov     [rsi], r12
0x1800d6ace  lea     r8, Class; Source
0x1800d6ad5  mov     [r15+30h], r12
0x1800d6ad9  mov     edx, 104h; SizeInWords
0x1800d6ade  mov     [r15+244h], r12d
0x1800d6ae5  call    cs:__imp_wcscpy_s
0x1800d6aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6af2  xor     ebx, ebx
0x1800d6af4  jmp     loc_1800D6B91
0x1800d6af9  mov     r12d, 11h
0x1800d6aff  cmp     rcx, rdi
0x1800d6b02  jz      short loc_1800D6B22
0x1800d6b04  test    byte ptr [rcx+1Ch], 1
0x1800d6b08  jz      short loc_1800D6B22
0x1800d6b0a  mov     rcx, [rcx+10h]
0x1800d6b0e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6b15  mov     edx, 140h
0x1800d6b1a  mov     r9d, ebx
0x1800d6b1d  call    WPP_SF_d
0x1800d6b22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d6b29  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d6b2e  test    al, al
0x1800d6b30  jz      loc_1800D72AF
0x1800d6b36  mov     r8d, 0CD9h
0x1800d6b3c  lea     r9, aIntVpnprofilea; "int_VpnProfileAutoConnect"
0x1800d6b43  mov     ecx, ebx
0x1800d6b45  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d6b4c  call    TraceVpnWppErrorW32Impl
0x1800d6b51  jmp     loc_1800D72AF
0x1800d6b56  cmp     [rbp+250h+var_2B0.rasconnstate], 2001h
0x1800d6b5d  jnz     short loc_1800D6B8B
0x1800d6b5f  cmp     rcx, rdi
0x1800d6b62  jz      short loc_1800D6B86
0x1800d6b64  test    [rcx+1Ch], r14b
0x1800d6b68  jz      short loc_1800D6B86
0x1800d6b6a  mov     rcx, [rcx+10h]
0x1800d6b6e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6b75  mov     edx, 141h
0x1800d6b7a  call    WPP_SF_
0x1800d6b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6b86  mov     [rsi], r12
0x1800d6b89  jmp     short loc_1800D6B91
0x1800d6b8b  mov     r12d, 13h
0x1800d6b91  cmp     qword ptr [rsi], 0
0x1800d6b95  jnz     loc_1800D72AF
0x1800d6b9b  cmp     rcx, rdi
0x1800d6b9e  jz      short loc_1800D6BBB
0x1800d6ba0  test    [rcx+1Ch], r14b
0x1800d6ba4  jz      short loc_1800D6BBB
0x1800d6ba6  mov     rcx, [rcx+10h]
0x1800d6baa  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6bb1  mov     edx, 142h
0x1800d6bb6  call    WPP_SF_
0x1800d6bbb  lea     rcx, [rsp+350h+var_308]
0x1800d6bc0  call    NlmHandlerCheckInternetConnectivity
0x1800d6bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6bcc  mov     ebx, [rsp+350h+var_308]
0x1800d6bd0  cmp     rcx, rdi
0x1800d6bd3  jz      short loc_1800D6BFD
0x1800d6bd5  test    [rcx+1Ch], r14b
0x1800d6bd9  jz      short loc_1800D6BFD
0x1800d6bdb  mov     rcx, [rcx+10h]
0x1800d6bdf  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6be6  test    ebx, ebx
0x1800d6be8  mov     edx, 143h
0x1800d6bed  setnz   r9b
0x1800d6bf1  call    WPP_SF_c
0x1800d6bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6bfd  cmp     ebx, 1
0x1800d6c00  jz      short loc_1800D6C5D
0x1800d6c02  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800d6c09  mov     esi, 15h
0x1800d6c0e  mov     ebx, esi
0x1800d6c10  lea     r12d, [rsi-14h]
0x1800d6c14  jz      short loc_1800D6C2D
0x1800d6c16  mov     r8, [r15+8]
0x1800d6c1a  lea     rdx, InternetUnavailableTriggerFailed
0x1800d6c21  call    McTemplateU0z_EventWriteTransfer
0x1800d6c26  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6c2d  cmp     rcx, rdi
0x1800d6c30  jz      loc_1800D72AF
0x1800d6c36  test    [rcx+1Ch], r14b
0x1800d6c3a  jz      loc_1800D72AF
0x1800d6c40  mov     rcx, [rcx+10h]
0x1800d6c44  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6c4b  mov     edx, 144h
0x1800d6c50  mov     r9d, esi
0x1800d6c53  call    WPP_SF_d
0x1800d6c58  jmp     loc_1800D72AF
0x1800d6c5d  lea     r8, [rsp+350h+var_304]
0x1800d6c62  lea     rdx, [rsp+350h+Buf2]
0x1800d6c67  lea     rcx, [rbp+250h+Buf1]
0x1800d6c6b  call    NlmGetBestCostNetworkConnectionInternal
0x1800d6c70  mov     ebx, eax
0x1800d6c72  mov     r12d, 2
0x1800d6c78  test    eax, eax
0x1800d6c7a  jns     short loc_1800D6CD1
0x1800d6c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6c83  cmp     rcx, rdi
0x1800d6c86  jz      short loc_1800D6CA6
0x1800d6c88  test    [rcx+1Ch], r12b
0x1800d6c8c  jz      short loc_1800D6CA6
0x1800d6c8e  mov     rcx, [rcx+10h]
0x1800d6c92  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6c99  mov     edx, 145h
0x1800d6c9e  mov     r9d, eax
0x1800d6ca1  call    WPP_SF_d
0x1800d6ca6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d6cad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d6cb2  test    al, al
0x1800d6cb4  jz      short loc_1800D6CD1
  ... truncated ...
```
