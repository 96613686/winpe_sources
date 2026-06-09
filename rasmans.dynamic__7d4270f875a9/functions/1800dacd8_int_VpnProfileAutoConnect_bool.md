# int_VpnProfileAutoConnect(bool)

- ea: `0x1800dacd8`
- end: `0x1800db732`
- name: `?int_VpnProfileAutoConnect@@YAK_N@Z`
- size: `2650`
- prototype: `unsigned int __fastcall(bool)`
- caller_count: `3`
- callee_count: `26`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d0260`
- `0x1800d04b0`
- `0x1800d0af0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c37c`
- `0x18000ebe8`
- `0x18000ec50`
- `0x180033654`
- `0x180033b38`
- `0x180057bc8`
- `0x1800c2f5c`
- `0x1800c3a50`
- `0x1800c4964`
- `0x1800c5464`
- `0x1800c6be8`
- `0x1800c8cd8`
- `0x1800cdd38`
- `0x1800ce360`
- `0x1800cfd18`
- `0x1800cfe58`
- `0x1800dacd8`
- `0x1800de658`
- `0x1800e3e00`
- `0x1800e3e30`
- `0x1800e3fac`
- `0x1800e8e72`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800daf72`
- `msvcrt!wcscpy_s` at `0x1800daf72`
- `ntdll!RtlIsMultiSessionSku` at `0x1800db2db`
- `ntdll!RtlIsMultiSessionSku` at `0x1800db2db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db6b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db6c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db6b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db277`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800db267`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800db267`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db395`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db3b9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db498`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db4c1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db395`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db3b9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db498`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800db4c1`
- `RASAPI32!RasTriggerConnectionWithDetails` at `0x1800db418`
- `RASAPI32!RasTriggerConnectionWithDetails` at `0x1800db418`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetConnectStatusW` at `0x1800daee7`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetConnectStatusW` at `0x1800daee7`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasTriggerConnection` at `0x1800db447`
- `ext-ms-win-ras-rasapi32-l1-1-1!RasTriggerConnection` at `0x1800db447`

## string_xrefs

- `0x1800db2c3`: `DuplicateToken`

## pseudocode

```c
__int64 __fastcall int_VpnProfileAutoConnect(unsigned __int8 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r13d
  unsigned int ConnectStatusW; // ebx
  int v6; // edi
  LPCWSTR *v7; // rsi
  unsigned int v8; // r12d
  struct _LIST_ENTRY *v9; // rcx
  HRASCONN *v10; // r15
  unsigned int EntryHrasconnW; // eax
  HRASCONN v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r9
  int v16; // ebx
  int BestCostNetworkConnectionInternal; // eax
  struct _LIST_ENTRY *v18; // rdi
  __int64 v19; // rcx
  DWORD LastError; // edi
  GUID *v21; // rdx
  bool v22; // zf
  unsigned int v23; // eax
  HRASCONN v24; // rcx
  _DWORD *v25; // rax
  struct _LIST_ENTRY *v26; // rcx
  const char *v27; // rdx
  struct _LIST_ENTRY *v28; // rcx
  struct _LIST_ENTRY *v29; // rcx
  __int64 v30; // rdx
  void *DuplicateTokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v36; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID Buf2; // [rsp+70h] [rbp-90h] BYREF
  __int128 Buf1; // [rsp+80h] [rbp-80h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-70h] BYREF
  struct tagRASCONNSTATUSW v40; // [rsp+A0h] [rbp-60h] BYREF

  v4 = a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a1;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 291, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, a4);
  }
  ExistingTokenHandle = 0;
  DuplicateTokenHandle = 0;
  ConnectStatusW = 0;
  v33 = 0;
  memset_0(&v40, 0, sizeof(v40));
  v6 = g_IsActiveDeviceProfile;
  v34 = 0;
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
    v8 = 9;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 )
    {
      goto LABEL_146;
    }
    v30 = 292;
LABEL_145:
    WPP_SF_(v29[1].Flink, v30, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    goto LABEL_146;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl'::`2'::impl)
    && IsAutoConnectInDebounceWindow(v4) )
  {
    v8 = 22;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 293, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v4);
    }
    goto LABEL_146;
  }
  if ( !v6 )
  {
    v8 = 6;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0 )
    {
      goto LABEL_146;
    }
    v30 = 316;
    goto LABEL_145;
  }
  v8 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 294, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = (HRASCONN *)(v7 + 5);
  if ( !v7[5] )
  {
    EntryHrasconnW = RasGetEntryHrasconnW(*v7, v7[1], v7 + 5);
    if ( EntryHrasconnW )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
LABEL_25:
        if ( !*v10 )
          goto LABEL_49;
        goto LABEL_26;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 295, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, EntryHrasconnW);
    }
    v9 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
LABEL_26:
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 4) != 0 )
    WPP_SF_(v9[1].Flink, 296, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  v12 = *v10;
  v40.dwSize = 608;
  ConnectStatusW = RasGetConnectStatusW(v12, &v40);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      297,
      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
      (unsigned int)v40.rasconnstate);
    v9 = WPP_GLOBAL_Control;
  }
  if ( ConnectStatusW )
  {
    if ( ConnectStatusW != 6 )
    {
      v8 = 17;
      if ( v9 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v9[1].Blink) & 1) == 0 )
        goto LABEL_146;
      v13 = 299;
LABEL_41:
      v14 = ConnectStatusW;
LABEL_42:
      WPP_SF_d(v9[1].Flink, v13, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v14);
LABEL_146:
      AddVPNCanceledEvent(v8, v4);
      goto LABEL_147;
    }
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 4) != 0 )
      WPP_SF_(v9[1].Flink, 298, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
    *v10 = 0;
    v7[6] = 0;
    *((_DWORD *)v7 + 145) = 0;
    wcscpy_s((wchar_t *)v7 + 28, 0x104u, &Class);
    v9 = WPP_GLOBAL_Control;
    ConnectStatusW = 0;
  }
  else if ( v40.rasconnstate == RASCS_Disconnected )
  {
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 4) != 0 )
    {
      WPP_SF_(v9[1].Flink, 300, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    *v10 = 0;
  }
  else
  {
    v8 = 19;
  }
LABEL_49:
  if ( *v10 )
    goto LABEL_146;
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 4) != 0 )
    WPP_SF_(v9[1].Flink, 301, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
  NlmHandlerCheckInternetConnectivity(&v33);
  v9 = WPP_GLOBAL_Control;
  v16 = v33;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    LOBYTE(v15) = v33 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 302, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v15);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v16 != 1 )
  {
    ConnectStatusW = 21;
    v8 = 1;
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v9, InternetUnavailableTriggerFailed, v7[1]);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v9[1].Blink) & 4) == 0 )
      goto LABEL_146;
    v13 = 303;
    v14 = 21;
    goto LABEL_42;
  }
  BestCostNetworkConnectionInternal = NlmGetBestCostNetworkConnectionInternal(&Buf1, &Buf2, &v34);
  v8 = 2;
  if ( BestCostNetworkConnectionInternal >= 0 )
    goto LABEL_66;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    goto LABEL_70;
  if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 2) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      304,
      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
      (unsigned int)BestCostNetworkConnectionInternal);
LABEL_66:
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
  {
    WPP_SF__guid_d(v18[1].Flink, 305, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, &Buf2, v34);
    v18 = WPP_GLOBAL_Control;
  }
LABEL_70:
  if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
  {
    ConnectStatusW = 21;
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v19, InternetUnavailableTriggerFailed, v7[1]);
      v18 = WPP_GLOBAL_Control;
    }
    if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 1) != 0 )
      WPP_SF_Sd(
        v18[1].Flink,
        306,
        (unsigned int)&WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
        (unsigned int)v7[1],
        21);
    goto LABEL_146;
  }
  if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
  {
    WPP_SF_ddd(
      v18[1].Flink,
      307,
      &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids,
      *((unsigned int *)v7 + 8),
      1,
      *((_DWORD *)v7 + 145));
    v18 = WPP_GLOBAL_Control;
  }
  *((_DWORD *)v7 + 8) = 1;
  if ( (_BYTE)v4 )
  {
    ConnectStatusW = GetActiveTokenAndSessionId((void *)v7[2], 0, &ExistingTokenHandle);
    if ( ConnectStatusW )
    {
      v8 = 20;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_146;
      }
      v13 = 308;
      goto LABEL_41;
    }
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v8 = 12;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 309, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
        }
        VpnReportError("int_VpnProfileAutoConnect", "DuplicateToken", LastError);
        goto LABEL_146;
      }
    }
    if ( !(unsigned __int8)RtlIsMultiSessionSku()
      && (unsigned int)IsTokenForDefaultAccount((__int64)DuplicateTokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 310, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids);
      }
      ConnectStatusW = 21;
      v8 = 21;
      goto LABEL_146;
    }
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v18[1].Blink) & 4) != 0 )
    WPP_SF_S(v18[1].Flink, 311, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v7[1]);
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v19, VpnAutoTriggerConnectionAttempt, v7[1]);
  ActivityId = 0;
  EventActivityIdControl(1u, &ActivityId);
  v21 = &::ActivityId;
  if ( !(_BYTE)v4 )
    v21 = &stru_18010F458;
  EventActivityIdControl(2u, v21);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::GetImpl'::`2'::impl) )
  {
    v22 = *((_DWORD *)v7 + 151) == 0;
    *((_DWORD *)v7 + 150) = 2;
    if ( v22 )
      *((_DWORD *)v7 + 151) = 1;
    v23 = RasTriggerConnectionWithDetails(
            *v7,
            v7[1],
            DuplicateTokenHandle,
            *((unsigned int *)v7 + 6),
            v7[75],
            v7 + 5,
            int_RasTriggerConnectionCallback);
  }
  else
  {
    v23 = RasTriggerConnection(
            *v7,
            v7[1],
            DuplicateTokenHandle,
            *((unsigned int *)v7 + 6),
            v7 + 5,
            int_RasTriggerConnectionCallback);
  }
  v24 = (HRASCONN)v7[5];
  v36 = Buf2;
  ConnectStatusW = v23;
  LogStartPhysicalConnection(v24, v4, &v36, v23);
  VpnCriticalSectionEnter(&g_connMonitorCs);
  v25 = g_pMonitor;
  if ( g_pMonitor )
  {
    if ( !*((_DWORD *)g_pMonitor + 2) )
    {
      EventActivityIdControl(1u, (LPGUID)((char *)g_pMonitor + 56));
      v25 = g_pMonitor;
    }
    v25[2] = 1;
    VpnCriticalSectionLeave(&g_connMonitorCs);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_Differentiate_Connection_Type>::GetImpl'::`2'::impl) )
  {
    if ( ConnectStatusW )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 312, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, ConnectStatusW);
        v26 = WPP_GLOBAL_Control;
      }
      if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) == 0 )
      {
LABEL_121:
        if ( v26 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v26[1].Blink) & 4) != 0 )
          WPP_SF_dq(v26[1].Flink, 313, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, ConnectStatusW, v7[5]);
        if ( ConnectStatusW )
        {
          v27 = "RasTriggerConnectionWithDetails";
LABEL_126:
          VpnReportError("int_VpnProfileAutoConnect", v27, ConnectStatusW);
          goto LABEL_147;
        }
        goto LABEL_147;
      }
      McTemplateU0z_EventWriteTransfer(v26, VpnAutoTriggerConnectionAttemptFailed, v7[1]);
    }
    v26 = WPP_GLOBAL_Control;
    goto LABEL_121;
  }
  if ( !ConnectStatusW )
    goto LABEL_133;
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 314, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, ConnectStatusW);
    v28 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v28, VpnAutoTriggerConnectionAttemptFailed, v7[1]);
LABEL_133:
    v28 = WPP_GLOBAL_Control;
  }
  if ( v28 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v28[1].Blink) & 4) != 0 )
    WPP_SF_dq(v28[1].Flink, 315, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, ConnectStatusW, v7[5]);
  if ( ConnectStatusW )
  {
    v27 = "RasTriggerConnection";
    goto LABEL_126;
  }
LABEL_147:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( ExistingTokenHandle )
    CloseHandle(ExistingTokenHandle);
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( (ConnectStatusW & 0x80000000) != 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 317, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, ConnectStatusW);
  }
  return ConnectStatusW;
}

```

## disassembly

```asm
0x1800dacd8  push    rbp
0x1800dacda  push    rbx
0x1800dacdb  push    rsi
0x1800dacdc  push    rdi
0x1800dacdd  push    r12
0x1800dacdf  push    r13
0x1800dace1  push    r14
0x1800dace3  push    r15
0x1800dace5  lea     rbp, [rsp-218h]
0x1800daced  sub     rsp, 318h
0x1800dacf4  mov     rax, cs:__security_cookie
0x1800dacfb  xor     rax, rsp
0x1800dacfe  mov     [rbp+250h+var_50], rax
0x1800dad05  movzx   r13d, cl
0x1800dad09  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dad10  lea     r15, WPP_GLOBAL_Control
0x1800dad17  cmp     rcx, r15
0x1800dad1a  jz      short loc_1800DAD3A
0x1800dad1c  test    byte ptr [rcx+1Ch], 8
0x1800dad20  jz      short loc_1800DAD3A
0x1800dad22  mov     rcx, [rcx+10h]
0x1800dad26  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dad2d  mov     edx, 123h
0x1800dad32  mov     r9b, r13b
0x1800dad35  call    WPP_SF_c
0x1800dad3a  xor     r14d, r14d
0x1800dad3d  lea     rcx, [rbp+250h+var_2B0]; void *
0x1800dad41  xor     edx, edx; Val
0x1800dad43  mov     [rsp+350h+ExistingTokenHandle], r14
0x1800dad48  mov     r8d, 260h; Size
0x1800dad4e  mov     [rsp+350h+DuplicateTokenHandle], r14
0x1800dad53  mov     ebx, r14d
0x1800dad56  mov     [rsp+350h+var_308], r14d
0x1800dad5b  call    memset_0
0x1800dad60  mov     edi, cs:?g_IsActiveDeviceProfile@@3HA; int g_IsActiveDeviceProfile
0x1800dad66  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800dad6d  xorps   xmm0, xmm0
0x1800dad70  mov     [rsp+350h+var_304], r14d
0x1800dad75  xorps   xmm1, xmm1
0x1800dad78  test    r13b, r13b
0x1800dad7b  movups  [rbp+250h+Buf1], xmm0
0x1800dad7f  cmovnz  edi, cs:?g_IsActiveUserProfile@@3HA; int g_IsActiveUserProfile
0x1800dad86  movups  [rsp+350h+Buf2], xmm1
0x1800dad8b  call    VpnCriticalSectionEnter
0x1800dad90  test    r13b, r13b
0x1800dad93  lea     rax, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800dad9a  lea     rsi, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800dada1  cmovz   rsi, rax
0x1800dada5  cmp     cs:?g_deviceLastPowerState@@3W4_VPNPROFILEDEVICESTATE@@A, 1; _VPNPROFILEDEVICESTATE g_deviceLastPowerState
0x1800dadac  jz      loc_1800DB658
0x1800dadb2  cmp     cs:?g_CrmIsDisconnectedStandby@@3HA, r14d; int g_CrmIsDisconnectedStandby
0x1800dadb9  jnz     loc_1800DB658
0x1800dadbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::GetImpl(void)'::`2'::impl
0x1800dadc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AudoConnect_Debounce>::__private_IsEnabled(void)
0x1800dadcb  test    al, al
0x1800dadcd  jz      short loc_1800DAE20
0x1800dadcf  mov     cl, r13b; bool
0x1800dadd2  call    ?IsAutoConnectInDebounceWindow@@YA_N_N@Z; IsAutoConnectInDebounceWindow(bool)
0x1800dadd7  test    al, al
0x1800dadd9  jz      short loc_1800DAE20
0x1800daddb  lea     r12d, [r14+16h]
0x1800daddf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dade6  lea     rdi, WPP_GLOBAL_Control
0x1800daded  cmp     rcx, rdi
0x1800dadf0  jz      loc_1800DB688
0x1800dadf6  mov     r14b, 4
0x1800dadf9  test    [rcx+1Ch], r14b
0x1800dadfd  jz      loc_1800DB688
0x1800dae03  mov     rcx, [rcx+10h]
0x1800dae07  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dae0e  mov     r9d, r13d
0x1800dae11  mov     edx, 125h
0x1800dae16  call    WPP_SF_d
0x1800dae1b  jmp     loc_1800DB688
0x1800dae20  test    edi, edi
0x1800dae22  jz      loc_1800DB636
0x1800dae28  xor     r12d, r12d
0x1800dae2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dae32  lea     rdi, WPP_GLOBAL_Control
0x1800dae39  mov     r14b, 4
0x1800dae3c  cmp     rcx, rdi
0x1800dae3f  jz      short loc_1800DAE63
0x1800dae41  test    [rcx+1Ch], r14b
0x1800dae45  jz      short loc_1800DAE63
0x1800dae47  mov     rcx, [rcx+10h]
0x1800dae4b  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dae52  mov     edx, 126h
0x1800dae57  call    WPP_SF_
0x1800dae5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dae63  lea     r15, [rsi+28h]
0x1800dae67  cmp     [r15], rbx
0x1800dae6a  jnz     short loc_1800DAEB9
0x1800dae6c  mov     rdx, [rsi+8]
0x1800dae70  mov     r8, r15
0x1800dae73  mov     rcx, [rsi]
0x1800dae76  call    RasGetEntryHrasconnW
0x1800dae7b  test    eax, eax
0x1800dae7d  jz      short loc_1800DAEA9
0x1800dae7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dae86  cmp     rcx, rdi
0x1800dae89  jz      short loc_1800DAEB0
0x1800dae8b  test    byte ptr [rcx+1Ch], 1
0x1800dae8f  jz      short loc_1800DAEB0
0x1800dae91  mov     rcx, [rcx+10h]
0x1800dae95  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dae9c  mov     edx, 127h
0x1800daea1  mov     r9d, eax
0x1800daea4  call    WPP_SF_d
0x1800daea9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daeb0  cmp     [r15], rbx
0x1800daeb3  jz      loc_1800DAFFA
0x1800daeb9  cmp     rcx, rdi
0x1800daebc  jz      short loc_1800DAED9
0x1800daebe  test    [rcx+1Ch], r14b
0x1800daec2  jz      short loc_1800DAED9
0x1800daec4  mov     rcx, [rcx+10h]
0x1800daec8  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800daecf  mov     edx, 128h
0x1800daed4  call    WPP_SF_
0x1800daed9  mov     rcx, [r15]; HRASCONN
0x1800daedc  lea     rdx, [rbp+250h+var_2B0]; struct tagRASCONNSTATUSW *
0x1800daee0  mov     [rbp+250h+var_2B0.dwSize], 260h
0x1800daee7  call    cs:__imp_RasGetConnectStatusW
0x1800daeee  nop     dword ptr [rax+rax+00h]
0x1800daef3  mov     ebx, eax
0x1800daef5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daefc  cmp     rcx, rdi
0x1800daeff  jz      short loc_1800DAF27
0x1800daf01  test    [rcx+1Ch], r14b
0x1800daf05  jz      short loc_1800DAF27
0x1800daf07  mov     r9d, [rbp+250h+var_2B0.rasconnstate]
0x1800daf0b  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800daf12  mov     rcx, [rcx+10h]
0x1800daf16  mov     edx, 129h
0x1800daf1b  call    WPP_SF_d
0x1800daf20  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daf27  test    ebx, ebx
0x1800daf29  jz      loc_1800DAFBF
0x1800daf2f  cmp     ebx, 6
0x1800daf32  jnz     short loc_1800DAF89
0x1800daf34  cmp     rcx, rdi
0x1800daf37  jz      short loc_1800DAF54
0x1800daf39  test    [rcx+1Ch], r14b
0x1800daf3d  jz      short loc_1800DAF54
0x1800daf3f  mov     rcx, [rcx+10h]
0x1800daf43  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800daf4a  mov     edx, 12Ah
0x1800daf4f  call    WPP_SF_
0x1800daf54  lea     rcx, [rsi+38h]; Destination
0x1800daf58  mov     [r15], r12
0x1800daf5b  lea     r8, Class; Source
0x1800daf62  mov     [rsi+30h], r12
0x1800daf66  mov     edx, 104h; SizeInWords
0x1800daf6b  mov     [rsi+244h], r12d
0x1800daf72  call    cs:__imp_wcscpy_s
0x1800daf79  nop     dword ptr [rax+rax+00h]
0x1800daf7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daf85  xor     ebx, ebx
0x1800daf87  jmp     short loc_1800DAFFA
0x1800daf89  mov     r12d, 11h
0x1800daf8f  cmp     rcx, rdi
0x1800daf92  jz      loc_1800DB688
0x1800daf98  test    byte ptr [rcx+1Ch], 1
0x1800daf9c  jz      loc_1800DB688
0x1800dafa2  mov     edx, 12Bh
0x1800dafa7  mov     r9d, ebx
0x1800dafaa  mov     rcx, [rcx+10h]
0x1800dafae  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dafb5  call    WPP_SF_d
0x1800dafba  jmp     loc_1800DB688
0x1800dafbf  cmp     [rbp+250h+var_2B0.rasconnstate], 2001h
0x1800dafc6  jnz     short loc_1800DAFF4
0x1800dafc8  cmp     rcx, rdi
0x1800dafcb  jz      short loc_1800DAFEF
0x1800dafcd  test    [rcx+1Ch], r14b
0x1800dafd1  jz      short loc_1800DAFEF
0x1800dafd3  mov     rcx, [rcx+10h]
0x1800dafd7  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800dafde  mov     edx, 12Ch
0x1800dafe3  call    WPP_SF_
0x1800dafe8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dafef  mov     [r15], r12
0x1800daff2  jmp     short loc_1800DAFFA
0x1800daff4  mov     r12d, 13h
0x1800daffa  cmp     qword ptr [r15], 0
0x1800daffe  jnz     loc_1800DB688
0x1800db004  cmp     rcx, rdi
0x1800db007  jz      short loc_1800DB024
0x1800db009  test    [rcx+1Ch], r14b
0x1800db00d  jz      short loc_1800DB024
0x1800db00f  mov     rcx, [rcx+10h]
0x1800db013  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800db01a  mov     edx, 12Dh
0x1800db01f  call    WPP_SF_
0x1800db024  lea     rcx, [rsp+350h+var_308]
0x1800db029  call    NlmHandlerCheckInternetConnectivity
0x1800db02e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db035  mov     ebx, [rsp+350h+var_308]
0x1800db039  cmp     rcx, rdi
0x1800db03c  jz      short loc_1800DB066
0x1800db03e  test    [rcx+1Ch], r14b
0x1800db042  jz      short loc_1800DB066
0x1800db044  mov     rcx, [rcx+10h]
0x1800db048  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800db04f  test    ebx, ebx
0x1800db051  mov     edx, 12Eh
0x1800db056  setnz   r9b
0x1800db05a  call    WPP_SF_c
0x1800db05f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db066  cmp     ebx, 1
0x1800db069  jz      short loc_1800DB0B8
0x1800db06b  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800db072  mov     r15d, 15h
0x1800db078  mov     ebx, r15d
0x1800db07b  lea     r12d, [r15-14h]
0x1800db07f  jz      short loc_1800DB098
0x1800db081  mov     r8, [rsi+8]
0x1800db085  lea     rdx, InternetUnavailableTriggerFailed
0x1800db08c  call    McTemplateU0z_EventWriteTransfer
0x1800db091  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db098  cmp     rcx, rdi
0x1800db09b  jz      loc_1800DB688
0x1800db0a1  test    [rcx+1Ch], r14b
0x1800db0a5  jz      loc_1800DB688
0x1800db0ab  mov     edx, 12Fh
0x1800db0b0  mov     r9d, r15d
0x1800db0b3  jmp     loc_1800DAFAA
0x1800db0b8  lea     r8, [rsp+350h+var_304]
0x1800db0bd  lea     rdx, [rsp+350h+Buf2]
0x1800db0c2  lea     rcx, [rbp+250h+Buf1]
0x1800db0c6  call    NlmGetBestCostNetworkConnectionInternal
0x1800db0cb  mov     r12d, 2
0x1800db0d1  test    eax, eax
0x1800db0d3  jns     short loc_1800DB108
0x1800db0d5  mov     rdi, cs:WPP_GLOBAL_Control
0x1800db0dc  lea     rbx, WPP_GLOBAL_Control
0x1800db0e3  cmp     rdi, rbx
0x1800db0e6  jz      short loc_1800DB14A
0x1800db0e8  test    [rdi+1Ch], r12b
0x1800db0ec  jz      short loc_1800DB116
0x1800db0ee  mov     rcx, [rdi+10h]
0x1800db0f2  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800db0f9  mov     edx, 130h
0x1800db0fe  mov     r9d, eax
0x1800db101  call    WPP_SF_d
0x1800db106  jmp     short loc_1800DB10F
0x1800db108  lea     rbx, WPP_GLOBAL_Control
0x1800db10f  mov     rdi, cs:WPP_GLOBAL_Control
0x1800db116  cmp     rdi, rbx
0x1800db119  jz      short loc_1800DB14A
0x1800db11b  test    [rdi+1Ch], r14b
0x1800db11f  jz      short loc_1800DB14A
0x1800db121  mov     eax, [rsp+350h+var_304]
0x1800db125  lea     r9, [rsp+350h+Buf2]
0x1800db12a  mov     rcx, [rdi+10h]
0x1800db12e  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800db135  mov     edx, 131h
0x1800db13a  mov     dword ptr [rsp+350h+var_330], eax
0x1800db13e  call    WPP_SF__guid_d
0x1800db143  mov     rdi, cs:WPP_GLOBAL_Control
0x1800db14a  mov     r8d, 10h; Size
0x1800db150  lea     rdx, [rsp+350h+Buf2]; Buf2
0x1800db155  lea     rcx, [rbp+250h+Buf1]; Buf1
0x1800db159  call    memcmp_0
0x1800db15e  test    eax, eax
0x1800db160  jnz     short loc_1800DB1C6
0x1800db162  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800db169  lea     r15d, [rax+15h]
0x1800db16d  mov     ebx, r15d
0x1800db170  jz      short loc_1800DB189
0x1800db172  mov     r8, [rsi+8]
0x1800db176  lea     rdx, InternetUnavailableTriggerFailed
0x1800db17d  call    McTemplateU0z_EventWriteTransfer
0x1800db182  mov     rdi, cs:WPP_GLOBAL_Control
0x1800db189  lea     rax, WPP_GLOBAL_Control
0x1800db190  cmp     rdi, rax
0x1800db193  jz      loc_1800DB688
0x1800db199  test    byte ptr [rdi+1Ch], 1
0x1800db19d  jz      loc_1800DB688
0x1800db1a3  mov     r9, [rsi+8]
0x1800db1a7  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800db1ae  mov     rcx, [rdi+10h]
0x1800db1b2  mov     edx, 132h
0x1800db1b7  mov     dword ptr [rsp+350h+var_330], r15d
0x1800db1bc  call    WPP_SF_Sd
0x1800db1c1  jmp     loc_1800DB688
0x1800db1c6  cmp     rdi, rbx
0x1800db1c9  jz      short loc_1800DB203
0x1800db1cb  test    [rdi+1Ch], r14b
0x1800db1cf  jz      short loc_1800DB203
0x1800db1d1  mov     eax, [rsi+244h]
0x1800db1d7  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800db1de  mov     r9d, [rsi+20h]
0x1800db1e2  mov     edx, 133h
0x1800db1e7  mov     rcx, [rdi+10h]
0x1800db1eb  mov     dword ptr [rsp+350h+var_328], eax
0x1800db1ef  mov     dword ptr [rsp+350h+var_330], 1
0x1800db1f7  call    WPP_SF_ddd
0x1800db1fc  mov     rdi, cs:WPP_GLOBAL_Control
0x1800db203  mov     dword ptr [rsi+20h], 1
  ... truncated ...
```
