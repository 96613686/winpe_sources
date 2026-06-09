# int_ReadActiveDeviceTunnelRegistryContent(ushort * *,ushort * *,void * *)

- ea: `0x1800d35a4`
- end: `0x1800d3f43`
- name: `?int_ReadActiveDeviceTunnelRegistryContent@@YAKPEAPEAG0PEAPEAX@Z`
- size: `2463`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **, void **)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c945c`
- `0x1800de2d8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e5f0`
- `0x1800a5770`
- `0x1800b81fc`
- `0x1800c0bf0`
- `0x1800d35a4`
- `0x1800dab4c`
- `0x1800e1b9c`
- `0x1800e1e64`
- `0x1800e218c`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e7260`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d3622`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800d3622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d37c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d3916`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d3a35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d3b1e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d37c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d3916`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d3a35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800d3b1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d3655`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d3655`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d3e4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d3e4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3d3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3e81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3d3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d3e81`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d3c4f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d3c4f`

## string_xrefs

- `0x1800d3637`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800d3628`: `SYSTEM\CurrentControlSet\Services\RasMan\DeviceTunnel`
- `0x1800d369d`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d3725`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d380b`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d3e0d`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d37b7`: `AutoTriggerProfilePhoneBookPath`
- `0x1800d3696`: `int_ReadActiveDeviceTunnelRegistryContent`
- `0x1800d371e`: `int_ReadActiveDeviceTunnelRegistryContent`
- `0x1800d3804`: `int_ReadActiveDeviceTunnelRegistryContent`
- `0x1800d3e06`: `int_ReadActiveDeviceTunnelRegistryContent`
- `0x1800d3cbc`: `ConvertStringSidToSid`
- `0x1800d3d2e`: `VpnSidCopy`
- `0x1800d36be`: `RegOpenKeyEx`
- `0x1800d38e3`: `FixAutoTriggerProfilePath`
- `0x1800d39cd`: `VpnStringCopy for profile name`
- `0x1800d3a27`: `UserSID`
- `0x1800d3b17`: `UserSID`
- `0x1800d388f`: `VpnStringCopy for profile path`

## pseudocode

```c
__int64 __fastcall int_ReadActiveDeviceTunnelRegistryContent(unsigned __int16 **a1, unsigned __int16 **a2, void **a3)
{
  struct _LIST_ENTRY *v3; // rcx
  char IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  unsigned int LastError; // ebx
  BYTE *v8; // r13
  const char *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r8
  int v12; // edi
  int v13; // eax
  unsigned int fixed; // eax
  int v16; // eax
  unsigned __int16 *v18; // rdi
  LSTATUS v19; // eax
  void *v20; // rdi
  PSID v21; // rcx
  __int64 v22; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-69h]
  DWORD cbData; // [rsp+30h] [rbp-59h] BYREF
  LPVOID v26; // [rsp+38h] [rbp-51h] BYREF
  DWORD Type; // [rsp+40h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-41h] BYREF
  PSID Sid; // [rsp+50h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-31h] BYREF
  LPVOID v31; // [rsp+60h] [rbp-29h]
  unsigned __int16 **v32; // [rsp+68h] [rbp-21h]
  unsigned __int16 **v33; // [rsp+70h] [rbp-19h]
  void **v34; // [rsp+78h] [rbp-11h]
  char v35; // [rsp+80h] [rbp-9h] BYREF
  LPVOID *v36; // [rsp+90h] [rbp+7h]
  __int64 v37; // [rsp+98h] [rbp+Fh]

  v34 = a3;
  v33 = a2;
  v32 = a1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 144, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  hKey = 0;
  cbData = 0;
  Type = 0;
  Sid = 0;
  lpMem = 0;
  v31 = 0;
  v26 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v3);
  v5 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
  if ( !IsStateSeparationEnabled )
    v5 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\DeviceTunnel";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x2001Fu, &hKey);
  LastError = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 145, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v6);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        LastError,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1555,
        "int_ReadActiveDeviceTunnelRegistryContent");
    v8 = 0;
    v9 = "RegOpenKeyEx";
    v10 = LastError;
    goto LABEL_126;
  }
  cbData = 522;
  v8 = (BYTE *)VpnAlloc(522);
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 146, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1564,
        "int_ReadActiveDeviceTunnelRegistryContent");
    LastError = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 147, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_127;
    v11 = 1566;
    goto LABEL_24;
  }
  cbData = 520;
  LastError = RegQueryValueExW(hKey, L"AutoTriggerProfilePhoneBookPath", 0, &Type, v8, &cbData);
  if ( LastError || Type - 1 > 1 )
  {
    v12 = 1168;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 148, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1168);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        1168,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1574,
        "int_ReadActiveDeviceTunnelRegistryContent");
    v9 = "RegQueryValueEx";
    goto LABEL_124;
  }
  *(_WORD *)&v8[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v12 = VpnStringCopy(v8);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 149, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v12);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        (unsigned int)v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1581,
        "int_ReadActiveDeviceTunnelRegistryContent",
        phkResult);
    v13 = (v12 >> 16) & 0x1FFF;
    if ( v13 == 7 ? (unsigned __int16)v12 : v12 )
    {
      if ( v13 == 7 )
        v12 = (unsigned __int16)v12;
      v9 = "VpnStringCopy for profile path";
      goto LABEL_125;
    }
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 150, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, lpMem);
  fixed = FixAutoTriggerProfilePath(hKey, (wchar_t **)&lpMem);
  LastError = fixed;
  if ( fixed )
  {
    v10 = fixed;
    v9 = "FixAutoTriggerProfilePath";
LABEL_126:
    VpnReportError("int_ReadActiveDeviceTunnelRegistryContent", v9, v10);
    goto LABEL_127;
  }
  cbData = 520;
  LastError = RegQueryValueExW(hKey, L"AutoTriggerProfileEntryName", 0, &Type, v8, &cbData);
  if ( LastError || Type - 1 > 1 )
  {
    v12 = 1168;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 151, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1168);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        1168,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1596,
        "int_ReadActiveDeviceTunnelRegistryContent");
    v9 = "RegQueryValueEx for REG_VAL_PROFILE_NAME";
LABEL_124:
    LastError = 1168;
LABEL_125:
    v10 = (unsigned int)v12;
    goto LABEL_126;
  }
  *(_WORD *)&v8[2 * ((unsigned __int64)cbData >> 1)] = 0;
  v12 = VpnStringCopy(v8);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 152, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v12);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        (unsigned int)v12,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1604,
        "int_ReadActiveDeviceTunnelRegistryContent",
        phkResult);
    v16 = (v12 >> 16) & 0x1FFF;
    if ( v16 == 7 ? (unsigned __int16)v12 : v12 )
    {
      if ( v16 == 7 )
        v12 = (unsigned __int16)v12;
      v9 = "VpnStringCopy for profile name";
      goto LABEL_125;
    }
  }
  v18 = (unsigned __int16 *)v31;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 153, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v31);
  cbData = 520;
  v19 = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v8, &cbData);
  if ( v19 != 234 )
  {
    if ( v19 || Type - 1 > 1 )
    {
      LastError = 1168;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 157, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 1168);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          1168,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          1633,
          "int_ReadActiveDeviceTunnelRegistryContent");
LABEL_92:
      v10 = 1168;
LABEL_82:
      v9 = "RegQueryValueEx";
      goto LABEL_126;
    }
LABEL_90:
    if ( cbData > 1 )
    {
      *(_WORD *)&v8[2 * ((unsigned __int64)cbData >> 1)] = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 158, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8);
      }
      if ( ConvertStringSidToSidW((LPCWSTR)v8, &Sid) )
      {
        LastError = VpnSidCopy(Sid);
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 160, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              LastError,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              1659,
              "int_ReadActiveDeviceTunnelRegistryContent");
          v10 = LastError;
          v9 = "VpnSidCopy";
          goto LABEL_126;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 159, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              LastError,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              1653,
              "int_ReadActiveDeviceTunnelRegistryContent");
          v10 = LastError;
          v9 = "ConvertStringSidToSid";
          goto LABEL_126;
        }
      }
      LocalFree(Sid);
      Sid = 0;
      *v32 = (unsigned __int16 *)lpMem;
      *v33 = v18;
      v20 = v26;
      *v34 = v26;
      goto LABEL_128;
    }
    LastError = 1168;
    goto LABEL_92;
  }
  MprCommonFree(v8);
  v8 = (BYTE *)VpnAlloc(cbData + 1);
  if ( v8 )
  {
    LastError = RegQueryValueExW(hKey, L"UserSID", 0, &Type, v8, &cbData);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 156, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          LastError,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          1627,
          "int_ReadActiveDeviceTunnelRegistryContent");
      v10 = LastError;
      goto LABEL_82;
    }
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 154, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      14,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      1622,
      "int_ReadActiveDeviceTunnelRegistryContent");
  LastError = 14;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 155, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    goto LABEL_127;
  v11 = 1624;
LABEL_24:
  TraceVpnWppErrorW32Impl(
    14,
    L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
    v11,
    "int_ReadActiveDeviceTunnelRegistryContent");
LABEL_127:
  v20 = v26;
LABEL_128:
  if ( hKey )
    RegCloseKey(hKey);
  MprCommonFree(v8);
  if ( LastError )
  {
    MprCommonFree(lpMem);
    MprCommonFree(v31);
    MprCommonFree(v20);
    v21 = Sid;
    if ( Sid )
    {
      LocalFree(Sid);
      Sid = 0;
    }
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    LODWORD(v26) = LastError;
    v36 = &v26;
    v37 = 4;
    phkResult = (PHKEY)&v35;
    McGenEventWrite_EventWriteTransfer(v21, VpnAutoTriggerReadConfigRegistryContent, v22, 2);
  }
  g_fConfigDeviceRegContentFailed = LastError != 0;
  if ( (LastError & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 161, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        LastError,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        1705,
        "int_ReadActiveDeviceTunnelRegistryContent",
        phkResult);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800d35a4  push    rbp
0x1800d35a6  push    rbx
0x1800d35a7  push    rsi
0x1800d35a8  push    rdi
0x1800d35a9  push    r12
0x1800d35ab  push    r13
0x1800d35ad  push    r15
0x1800d35af  lea     rbp, [rsp-27h]
0x1800d35b4  sub     rsp, 0B0h
0x1800d35bb  mov     rax, cs:__security_cookie
0x1800d35c2  xor     rax, rsp
0x1800d35c5  mov     [rbp+57h+var_40], rax
0x1800d35c9  mov     [rbp+57h+var_68], r8
0x1800d35cd  mov     [rbp+57h+var_70], rdx
0x1800d35d1  mov     [rbp+57h+var_78], rcx
0x1800d35d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d35dc  lea     r15, WPP_GLOBAL_Control
0x1800d35e3  lea     r12, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d35ea  cmp     rcx, r15
0x1800d35ed  jz      short loc_1800D3606
0x1800d35ef  test    byte ptr [rcx+1Ch], 8
0x1800d35f3  jz      short loc_1800D3606
0x1800d35f5  mov     rcx, [rcx+10h]
0x1800d35f9  mov     edx, 90h
0x1800d35fe  mov     r8, r12
0x1800d3601  call    WPP_SF_
0x1800d3606  xor     esi, esi
0x1800d3608  mov     [rbp+57h+hKey], rsi
0x1800d360c  mov     [rbp+57h+cbData], esi
0x1800d360f  mov     [rbp+57h+Type], esi
0x1800d3612  mov     [rbp+57h+Sid], rsi
0x1800d3616  mov     [rbp+57h+lpMem], rsi
0x1800d361a  mov     [rbp+57h+var_80], rsi
0x1800d361e  mov     [rbp+57h+var_A8], rsi
0x1800d3622  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800d3628  lea     rcx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800d362f  mov     r9d, 2001Fh; samDesired
0x1800d3635  test    al, al
0x1800d3637  lea     rdx, aOsdataSystemCu_1; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x1800d363e  lea     rax, [rbp+57h+hKey]
0x1800d3642  cmovz   rdx, rcx; lpSubKey
0x1800d3646  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800d364b  xor     r8d, r8d; ulOptions
0x1800d364e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d3655  call    cs:__imp_RegOpenKeyExW
0x1800d365b  mov     ebx, eax
0x1800d365d  test    eax, eax
0x1800d365f  jz      short loc_1800D36CD
0x1800d3661  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3668  cmp     rcx, r15
0x1800d366b  jz      short loc_1800D3687
0x1800d366d  test    byte ptr [rcx+1Ch], 1
0x1800d3671  jz      short loc_1800D3687
0x1800d3673  mov     rcx, [rcx+10h]
0x1800d3677  mov     edx, 91h
0x1800d367c  mov     r9d, eax
0x1800d367f  mov     r8, r12
0x1800d3682  call    WPP_SF_d
0x1800d3687  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d368e  mov     rcx, r15
0x1800d3691  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d3696  lea     rsi, aIntReadactived; "int_ReadActiveDeviceTunnelRegistryConte"...
0x1800d369d  lea     r12, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d36a4  test    al, al
0x1800d36a6  jz      short loc_1800D36BB
0x1800d36a8  mov     r9, rsi
0x1800d36ab  mov     r8d, 613h
0x1800d36b1  mov     rdx, r12
0x1800d36b4  mov     ecx, ebx
0x1800d36b6  call    TraceVpnWppErrorW32Impl
0x1800d36bb  xor     r13d, r13d
0x1800d36be  lea     rdx, aRegopenkeyex; "RegOpenKeyEx"
0x1800d36c5  mov     r8d, ebx
0x1800d36c8  jmp     loc_1800D3E37
0x1800d36cd  mov     ecx, 20Ah
0x1800d36d2  mov     [rbp+57h+cbData], ecx
0x1800d36d5  call    VpnAlloc
0x1800d36da  mov     r13, rax
0x1800d36dd  test    rax, rax
0x1800d36e0  jnz     loc_1800D379E
0x1800d36e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d36ed  lea     edi, [rax+0Eh]
0x1800d36f0  cmp     rcx, r15
0x1800d36f3  jz      short loc_1800D370F
0x1800d36f5  test    byte ptr [rcx+1Ch], 1
0x1800d36f9  jz      short loc_1800D370F
0x1800d36fb  mov     rcx, [rcx+10h]
0x1800d36ff  mov     edx, 92h
0x1800d3704  mov     r9d, edi
0x1800d3707  mov     r8, r12
0x1800d370a  call    WPP_SF_d
0x1800d370f  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d3716  mov     rcx, r15
0x1800d3719  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d371e  lea     rsi, aIntReadactived; "int_ReadActiveDeviceTunnelRegistryConte"...
0x1800d3725  lea     r12, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d372c  test    al, al
0x1800d372e  jz      short loc_1800D3743
0x1800d3730  mov     r9, rsi
0x1800d3733  mov     r8d, 61Ch
0x1800d3739  mov     rdx, r12
0x1800d373c  mov     ecx, edi
0x1800d373e  call    TraceVpnWppErrorW32Impl
0x1800d3743  mov     ebx, edi
0x1800d3745  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d374c  lea     rax, WPP_GLOBAL_Control
0x1800d3753  cmp     rcx, rax
0x1800d3756  jz      short loc_1800D3776
0x1800d3758  test    byte ptr [rcx+1Ch], 1
0x1800d375c  jz      short loc_1800D3776
0x1800d375e  mov     rcx, [rcx+10h]
0x1800d3762  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d3769  mov     edx, 93h
0x1800d376e  mov     r9d, edi
0x1800d3771  call    WPP_SF_d
0x1800d3776  mov     rcx, r15
0x1800d3779  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d377e  test    al, al
0x1800d3780  jz      loc_1800D3E3F
0x1800d3786  mov     r8d, 61Eh
0x1800d378c  mov     r9, rsi
0x1800d378f  mov     rdx, r12
0x1800d3792  mov     ecx, edi
0x1800d3794  call    TraceVpnWppErrorW32Impl
0x1800d3799  jmp     loc_1800D3E3F
0x1800d379e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d37a2  lea     rax, [rbp+57h+cbData]
0x1800d37a6  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800d37ab  lea     r9, [rbp+57h+Type]; lpType
0x1800d37af  xor     r8d, r8d; lpReserved
0x1800d37b2  mov     [rsp+0E0h+phkResult], r13; lpData
0x1800d37b7  lea     rdx, aAutotriggerpro_0; "AutoTriggerProfilePhoneBookPath"
0x1800d37be  mov     [rbp+57h+cbData], 208h
0x1800d37c5  call    cs:__imp_RegQueryValueExW
0x1800d37cb  mov     ebx, eax
0x1800d37cd  test    eax, eax
0x1800d37cf  jnz     loc_1800D3DCC
0x1800d37d5  mov     eax, [rbp+57h+Type]
0x1800d37d8  dec     eax
0x1800d37da  cmp     eax, 1
0x1800d37dd  ja      loc_1800D3DCC
0x1800d37e3  mov     ecx, [rbp+57h+cbData]
0x1800d37e6  lea     rdx, [rbp+57h+lpMem]
0x1800d37ea  shr     rcx, 1
0x1800d37ed  mov     [r13+rcx*2+0], si
0x1800d37f3  mov     rcx, r13; Src
0x1800d37f6  call    VpnStringCopy
0x1800d37fb  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d3802  mov     edi, eax
0x1800d3804  lea     rsi, aIntReadactived; "int_ReadActiveDeviceTunnelRegistryConte"...
0x1800d380b  lea     r12, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d3812  test    eax, eax
0x1800d3814  jns     loc_1800D389B
0x1800d381a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d3821  lea     rax, WPP_GLOBAL_Control
0x1800d3828  cmp     rcx, rax
0x1800d382b  jz      short loc_1800D384B
0x1800d382d  test    byte ptr [rcx+1Ch], 1
0x1800d3831  jz      short loc_1800D384B
0x1800d3833  mov     rcx, [rcx+10h]
0x1800d3837  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d383e  mov     edx, 95h
0x1800d3843  mov     r9d, edi
0x1800d3846  call    WPP_SF_d
0x1800d384b  mov     rcx, r15
0x1800d384e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d3853  test    al, al
0x1800d3855  jz      short loc_1800D386A
0x1800d3857  mov     r9, rsi
0x1800d385a  mov     r8d, 62Dh
0x1800d3860  mov     rdx, r12
0x1800d3863  mov     ecx, edi
0x1800d3865  call    TraceVpnWppErrorHRImpl
0x1800d386a  mov     eax, edi
0x1800d386c  sar     eax, 10h
0x1800d386f  and     eax, 1FFFh
0x1800d3874  cmp     eax, 7
0x1800d3877  jnz     short loc_1800D3880
0x1800d3879  movzx   ecx, di
0x1800d387c  mov     edx, ecx
0x1800d387e  jmp     short loc_1800D3885
0x1800d3880  mov     ecx, edi
0x1800d3882  movzx   edx, di
0x1800d3885  test    ecx, ecx
0x1800d3887  jz      short loc_1800D389B
0x1800d3889  cmp     eax, 7
0x1800d388c  cmovz   edi, edx
0x1800d388f  lea     rdx, aVpnstringcopyF_2; "VpnStringCopy for profile path"
0x1800d3896  jmp     loc_1800D3E34
0x1800d389b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d38a2  lea     rax, WPP_GLOBAL_Control
0x1800d38a9  cmp     rcx, rax
0x1800d38ac  jz      short loc_1800D38CD
0x1800d38ae  test    byte ptr [rcx+1Ch], 4
0x1800d38b2  jz      short loc_1800D38CD
0x1800d38b4  mov     r9, [rbp+57h+lpMem]
0x1800d38b8  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d38bf  mov     rcx, [rcx+10h]
0x1800d38c3  mov     edx, 96h
0x1800d38c8  call    WPP_SF_S
0x1800d38cd  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d38d1  lea     rdx, [rbp+57h+lpMem]
0x1800d38d5  call    FixAutoTriggerProfilePath
0x1800d38da  mov     ebx, eax
0x1800d38dc  test    eax, eax
0x1800d38de  jz      short loc_1800D38EF
0x1800d38e0  mov     r8d, eax
0x1800d38e3  lea     rdx, aFixautotrigger; "FixAutoTriggerProfilePath"
0x1800d38ea  jmp     loc_1800D3E37
0x1800d38ef  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d38f3  lea     rax, [rbp+57h+cbData]
0x1800d38f7  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800d38fc  lea     r9, [rbp+57h+Type]; lpType
0x1800d3900  xor     r8d, r8d; lpReserved
0x1800d3903  mov     [rsp+0E0h+phkResult], r13; lpData
0x1800d3908  lea     rdx, aAutotriggerpro; "AutoTriggerProfileEntryName"
0x1800d390f  mov     [rbp+57h+cbData], 208h
0x1800d3916  call    cs:__imp_RegQueryValueExW
0x1800d391c  mov     ebx, eax
0x1800d391e  test    eax, eax
0x1800d3920  jnz     loc_1800D3D6E
0x1800d3926  mov     eax, [rbp+57h+Type]
0x1800d3929  dec     eax
0x1800d392b  cmp     eax, 1
0x1800d392e  ja      loc_1800D3D6E
0x1800d3934  mov     ecx, [rbp+57h+cbData]
0x1800d3937  lea     rdx, [rbp+57h+var_80]
0x1800d393b  shr     rcx, 1
0x1800d393e  xor     eax, eax
0x1800d3940  mov     [r13+rcx*2+0], ax
0x1800d3946  mov     rcx, r13; Src
0x1800d3949  call    VpnStringCopy
0x1800d394e  mov     edi, eax
0x1800d3950  test    eax, eax
0x1800d3952  jns     loc_1800D39D9
0x1800d3958  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d395f  lea     rax, WPP_GLOBAL_Control
0x1800d3966  cmp     rcx, rax
0x1800d3969  jz      short loc_1800D3989
0x1800d396b  test    byte ptr [rcx+1Ch], 1
0x1800d396f  jz      short loc_1800D3989
0x1800d3971  mov     rcx, [rcx+10h]
0x1800d3975  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d397c  mov     edx, 98h
0x1800d3981  mov     r9d, edi
0x1800d3984  call    WPP_SF_d
0x1800d3989  mov     rcx, r15
0x1800d398c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d3991  test    al, al
0x1800d3993  jz      short loc_1800D39A8
0x1800d3995  mov     r9, rsi
0x1800d3998  mov     r8d, 644h
0x1800d399e  mov     rdx, r12
0x1800d39a1  mov     ecx, edi
0x1800d39a3  call    TraceVpnWppErrorHRImpl
0x1800d39a8  mov     eax, edi
0x1800d39aa  sar     eax, 10h
0x1800d39ad  and     eax, 1FFFh
0x1800d39b2  cmp     eax, 7
0x1800d39b5  jnz     short loc_1800D39BE
0x1800d39b7  movzx   ecx, di
0x1800d39ba  mov     edx, ecx
0x1800d39bc  jmp     short loc_1800D39C3
0x1800d39be  mov     ecx, edi
0x1800d39c0  movzx   edx, di
0x1800d39c3  test    ecx, ecx
0x1800d39c5  jz      short loc_1800D39D9
0x1800d39c7  cmp     eax, 7
0x1800d39ca  cmovz   edi, edx
0x1800d39cd  lea     rdx, aVpnstringcopyF_0; "VpnStringCopy for profile name"
0x1800d39d4  jmp     loc_1800D3E34
0x1800d39d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d39e0  lea     rbx, WPP_GLOBAL_Control
0x1800d39e7  mov     rdi, [rbp+57h+var_80]
0x1800d39eb  cmp     rcx, rbx
0x1800d39ee  jz      short loc_1800D3A0E
0x1800d39f0  test    byte ptr [rcx+1Ch], 4
0x1800d39f4  jz      short loc_1800D3A0E
0x1800d39f6  mov     rcx, [rcx+10h]
0x1800d39fa  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d3a01  mov     edx, 99h
0x1800d3a06  mov     r9, rdi
0x1800d3a09  call    WPP_SF_S
0x1800d3a0e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800d3a12  lea     rax, [rbp+57h+cbData]
0x1800d3a16  mov     [rsp+0E0h+lpcbData], rax; lpcbData
0x1800d3a1b  lea     r9, [rbp+57h+Type]; lpType
0x1800d3a1f  xor     r8d, r8d; lpReserved
0x1800d3a22  mov     [rsp+0E0h+phkResult], r13; lpData
0x1800d3a27  lea     rdx, aUsersid; "UserSID"
0x1800d3a2e  mov     [rbp+57h+cbData], 208h
0x1800d3a35  call    cs:__imp_RegQueryValueExW
0x1800d3a3b  cmp     eax, 0EAh
0x1800d3a40  jnz     loc_1800D3B8D
0x1800d3a46  mov     rcx, r13; lpMem
0x1800d3a49  call    MprCommonFree
0x1800d3a4e  mov     ecx, [rbp+57h+cbData]
0x1800d3a51  inc     ecx
0x1800d3a53  call    VpnAlloc
0x1800d3a58  mov     r13, rax
  ... truncated ...
```
