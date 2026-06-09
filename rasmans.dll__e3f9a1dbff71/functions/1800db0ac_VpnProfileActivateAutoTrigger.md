# VpnProfileActivateAutoTrigger

- ea: `0x1800db0ac`
- end: `0x1800dbba8`
- name: `VpnProfileActivateAutoTrigger`
- size: `2812`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d4f20`
- `0x1800d8e74`
- `0x1800d9cf0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bf70`
- `0x18000e5f0`
- `0x1800a67e8`
- `0x1800a68d8`
- `0x1800a6cbc`
- `0x1800aa6e0`
- `0x1800b81fc`
- `0x1800da78c`
- `0x1800daba4`
- `0x1800db0ac`
- `0x1800e1e64`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db56a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800db671`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800db114`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x1800db114`
- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800dba0c`
- `fwpuclnt!FwpiVpnTriggerResetNrptTriggering` at `0x1800dba0c`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800db353`
- `fwpuclnt!FwpiVpnTriggerRemoveAppSids` at `0x1800db353`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800db6db`
- `fwpuclnt!FwpiVpnTriggerRemoveSecurityDescriptor` at `0x1800db6db`
- `fwpuclnt!FwpiVpnTriggerConfigureParameters` at `0x1800db168`
- `fwpuclnt!FwpiVpnTriggerConfigureParameters` at `0x1800db168`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800db4a7`
- `fwpuclnt!FwpiVpnTriggerRemoveFilePaths` at `0x1800db4a7`
- `fwpuclnt!FwpiVpnTriggerAddAppSids` at `0x1800db2b2`
- `fwpuclnt!FwpiVpnTriggerAddAppSids` at `0x1800db2b2`
- `fwpuclnt!FwpiVpnTriggerAddFilePaths` at `0x1800db406`
- `fwpuclnt!FwpiVpnTriggerAddFilePaths` at `0x1800db406`
- `fwpuclnt!FwpiVpnTriggerAddSecurityDescriptor` at `0x1800db5c2`
- `fwpuclnt!FwpiVpnTriggerAddSecurityDescriptor` at `0x1800db5c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800db564`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800db564`

## string_xrefs

- `0x1800db1bc`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800db259`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800db302`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800db320`: `FwpiVpnTriggerAddAppSids`
- `0x1800db466`: `FwpiVpnTriggerAddFilePaths`
- `0x1800db1da`: `FwpiVpnTriggerConfigureParameters`
- `0x1800db68b`: `FwpiVpnTriggerAddSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall VpnProfileActivateAutoTrigger(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  struct _LIST_ENTRY *v6; // rcx
  int v7; // ebx
  DWORD LastError; // ebx
  DWORD v9; // eax
  const char *v10; // rdx
  __int64 v11; // r9
  DWORD v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r9
  DWORD v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned int v19; // ebx
  __int64 v20; // rcx
  unsigned int v21; // eax
  __int64 v22; // r8
  unsigned int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  unsigned int v26; // eax
  unsigned int v27; // ebx
  DWORD v28; // eax
  __int64 v29; // r8
  __int64 v30; // rcx
  unsigned int v31; // ebx
  unsigned int v32; // eax
  unsigned int v33; // ebx
  DWORD appended; // eax
  ULONG SecurityDescriptorSize; // [rsp+68h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+18h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a2 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 691, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, a4);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v7 = *(_DWORD *)(a1 + 24);
    if ( v7 != WTSGetActiveConsoleSessionId() )
    {
      LastError = 0;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 693, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      return LastError;
    }
    v9 = FwpiVpnTriggerConfigureParameters(g_FwpEngineHandle, *(unsigned int *)(*(_QWORD *)(a1 + 592) + 124LL));
    LastError = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 694, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v9);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          LastError,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6805,
          "VpnProfileActivateAutoTrigger");
      v10 = "FwpiVpnTriggerConfigureParameters";
LABEL_16:
      VpnReportError("VpnProfileActivateAutoTrigger", v10, LastError);
      goto LABEL_162;
    }
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
  {
    WPP_SF_S(v6[1].Flink, 695, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, *(_QWORD *)(a1 + 8));
    v6 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v6, VpnAutoTriggerProfileActivated, *(_QWORD *)(a1 + 8));
    v6 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v11 = *(unsigned int *)(*(_QWORD *)(a1 + 592) + 24LL);
    if ( (_DWORD)v11 )
    {
      if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
        WPP_SF_d(v6[1].Flink, 696, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v11);
      v12 = FwpiVpnTriggerAddAppSids(
              g_FwpEngineHandle,
              *(unsigned int *)(*(_QWORD *)(a1 + 592) + 24LL),
              *(_QWORD *)(*(_QWORD *)(a1 + 592) + 32LL));
      LastError = v12;
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 697, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v12);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            LastError,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6825,
            "VpnProfileActivateAutoTrigger");
        v10 = "FwpiVpnTriggerAddAppSids";
        goto LABEL_16;
      }
    }
    else
    {
      if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
        WPP_SF_(v6[1].Flink, 698, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      v13 = FwpiVpnTriggerRemoveAppSids(g_FwpEngineHandle);
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 699, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v13);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v13,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6833,
            "VpnProfileActivateAutoTrigger");
      }
    }
    v14 = *(unsigned int *)(*(_QWORD *)(a1 + 592) + 40LL);
    if ( (_DWORD)v14 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 700, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v14);
      }
      v15 = FwpiVpnTriggerAddFilePaths(
              g_FwpEngineHandle,
              *(unsigned int *)(*(_QWORD *)(a1 + 592) + 40LL),
              *(_QWORD *)(*(_QWORD *)(a1 + 592) + 48LL));
      LastError = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 701, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v15);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            LastError,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6843,
            "VpnProfileActivateAutoTrigger");
        v10 = "FwpiVpnTriggerAddFilePaths";
        goto LABEL_16;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 702, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      v16 = FwpiVpnTriggerRemoveFilePaths(g_FwpEngineHandle);
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 703, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v16);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v16,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6850,
            "VpnProfileActivateAutoTrigger");
      }
    }
    if ( !*(_QWORD *)(*(_QWORD *)(a1 + 592) + 56LL) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 708, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      v19 = FwpiVpnTriggerRemoveSecurityDescriptor(g_FwpEngineHandle);
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 709, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v19);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v19,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6896,
            "VpnProfileActivateAutoTrigger");
      }
LABEL_99:
      v6 = WPP_GLOBAL_Control;
      goto LABEL_100;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 704, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    v17 = *(_QWORD *)(a1 + 592);
    SecurityDescriptor = 0;
    SecurityDescriptorSize = 0;
    ConvertStringSecurityDescriptorToSecurityDescriptorW(
      *(LPCWSTR *)(v17 + 56),
      1u,
      &SecurityDescriptor,
      &SecurityDescriptorSize);
    LastError = GetLastError();
    if ( LastError == 1332 )
    {
      LastError = 0;
      goto LABEL_86;
    }
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 707, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v18 = 6882;
        goto LABEL_85;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 705, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      }
      LastError = FwpiVpnTriggerAddSecurityDescriptor(g_FwpEngineHandle, SecurityDescriptor);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 706, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        {
          v18 = 6878;
LABEL_85:
          TraceVpnWppErrorW32Impl(
            LastError,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            v18,
            "VpnProfileActivateAutoTrigger");
        }
      }
    }
LABEL_86:
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    if ( LastError )
    {
      VpnReportError("VpnProfileActivateAutoTrigger", "FwpiVpnTriggerAddSecurityDescriptor", LastError);
      goto LABEL_162;
    }
    goto LABEL_99;
  }
LABEL_100:
  if ( **(_DWORD **)(a1 + 592) )
  {
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
      WPP_SF_(v6[1].Flink, 710, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    v20 = qword_18010E220;
    if ( !a2 )
      v20 = qword_18010E480;
    v21 = RasRemoveNrptRules(*(_QWORD *)(v20 + 16), 1);
    v23 = v21;
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 711, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v21);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v23,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6908,
          "VpnProfileActivateAutoTrigger");
    }
    v24 = RasAddNrptRulesEx(*(__int64 **)(*(_QWORD *)(a1 + 592) + 8LL), **(unsigned int **)(a1 + 592), v22, 0, 0, 1);
    v25 = v24;
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 712, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v24);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v25,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6917,
          "VpnProfileActivateAutoTrigger");
    }
    v26 = RasAddNrptRules(*(_QWORD *)(*(_QWORD *)(a1 + 592) + 112LL), *(unsigned int *)(*(_QWORD *)(a1 + 592) + 120LL));
    v27 = v26;
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 713, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v26);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v27,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6922,
          "VpnProfileActivateAutoTrigger");
    }
  }
  else
  {
    if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v6[1].Blink) & 4) != 0 )
      WPP_SF_(v6[1].Flink, 714, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    v30 = qword_18010E220;
    if ( !a2 )
      v30 = qword_18010E480;
    v31 = RasRemoveNrptRules(*(_QWORD *)(v30 + 16), 1);
    if ( v31 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 715, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v31);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v31,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6929,
          "VpnProfileActivateAutoTrigger");
    }
    if ( a2 )
    {
      int_VpnProfileUnPlumbWfpFilter();
      v32 = FwpiVpnTriggerResetNrptTriggering(g_FwpEngineHandle);
      v33 = v32;
      if ( v32 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 716, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v32);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v33,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6936,
            "VpnProfileActivateAutoTrigger");
      }
    }
  }
  if ( !*(_DWORD *)(*(_QWORD *)(a1 + 592) + 80LL) )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 719, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    appended = AppendDnsSuffixSearchListToGlobalList(0, 0);
    LastError = appended;
    if ( !appended )
      goto LABEL_167;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 720, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, appended);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_162;
    v29 = 6953;
    goto LABEL_161;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 717, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  v28 = AppendDnsSuffixSearchListToGlobalList(
          *(_QWORD *)(*(_QWORD *)(a1 + 592) + 88LL),
          *(unsigned int *)(*(_QWORD *)(a1 + 592) + 80LL));
  LastError = v28;
  if ( !v28 )
    goto LABEL_167;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 718, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v28);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
  {
    v29 = 6946;
LABEL_161:
    TraceVpnWppErrorW32Impl(
      LastError,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v29,
      "VpnProfileActivateAutoTrigger");
  }
LABEL_162:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 721, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      LastError,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      6959,
      "VpnProfileActivateAutoTrigger");
LABEL_167:
  if ( (LastError & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 722, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        LastError,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        6962,
        "VpnProfileActivateAutoTrigger");
  }
  return LastError;
}

```

## disassembly

```asm
0x1800db0ac  mov     [rsp+arg_0], rbx
0x1800db0b1  mov     [rsp+arg_18], rsi
0x1800db0b6  push    rdi
0x1800db0b7  push    r12
0x1800db0b9  push    r13
0x1800db0bb  push    r14
0x1800db0bd  push    r15
0x1800db0bf  sub     rsp, 30h
0x1800db0c3  mov     r13d, edx
0x1800db0c6  mov     r15, rcx
0x1800db0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db0d0  lea     rbx, WPP_GLOBAL_Control
0x1800db0d7  lea     rsi, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db0de  cmp     rcx, rbx
0x1800db0e1  jz      short loc_1800DB107
0x1800db0e3  test    byte ptr [rcx+1Ch], 8
0x1800db0e7  jz      short loc_1800DB107
0x1800db0e9  mov     rcx, [rcx+10h]
0x1800db0ed  test    edx, edx
0x1800db0ef  mov     edx, 2B3h
0x1800db0f4  mov     r8, rsi
0x1800db0f7  setnz   r9b
0x1800db0fb  call    WPP_SF_c
0x1800db100  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db107  test    r13d, r13d
0x1800db10a  jz      loc_1800DB1FF
0x1800db110  mov     ebx, [r15+18h]
0x1800db114  call    cs:__imp_WTSGetActiveConsoleSessionId
0x1800db11a  cmp     ebx, eax
0x1800db11c  jz      short loc_1800DB157
0x1800db11e  xor     ebx, ebx
0x1800db120  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db127  lea     rax, WPP_GLOBAL_Control
0x1800db12e  cmp     rcx, rax
0x1800db131  jz      loc_1800DBB8E
0x1800db137  test    byte ptr [rcx+1Ch], 4
0x1800db13b  jz      loc_1800DBB8E
0x1800db141  mov     rcx, [rcx+10h]
0x1800db145  mov     edx, 2B5h
0x1800db14a  mov     r8, rsi
0x1800db14d  call    WPP_SF_
0x1800db152  jmp     loc_1800DBB8E
0x1800db157  mov     rdx, [r15+250h]
0x1800db15e  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800db165  mov     edx, [rdx+7Ch]
0x1800db168  call    cs:__imp_FwpiVpnTriggerConfigureParameters
0x1800db16e  mov     ebx, eax
0x1800db170  test    eax, eax
0x1800db172  jz      short loc_1800DB1F1
0x1800db174  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db17b  lea     r13, WPP_GLOBAL_Control
0x1800db182  mov     edi, 1
0x1800db187  cmp     rcx, r13
0x1800db18a  jz      short loc_1800DB1A6
0x1800db18c  test    [rcx+1Ch], dil
0x1800db190  jz      short loc_1800DB1A6
0x1800db192  mov     rcx, [rcx+10h]
0x1800db196  mov     edx, 2B6h
0x1800db19b  mov     r9d, eax
0x1800db19e  mov     r8, rsi
0x1800db1a1  call    WPP_SF_d
0x1800db1a6  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800db1ad  mov     rcx, r12
0x1800db1b0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800db1b5  lea     rsi, aVpnprofileacti_0; "VpnProfileActivateAutoTrigger"
0x1800db1bc  lea     r14, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800db1c3  test    al, al
0x1800db1c5  jz      short loc_1800DB1DA
0x1800db1c7  mov     r9, rsi
0x1800db1ca  mov     r8d, 1A95h
0x1800db1d0  mov     rdx, r14
0x1800db1d3  mov     ecx, ebx
0x1800db1d5  call    TraceVpnWppErrorW32Impl
0x1800db1da  lea     rdx, aFwpivpntrigger_2; "FwpiVpnTriggerConfigureParameters"
0x1800db1e1  mov     r8d, ebx
0x1800db1e4  mov     rcx, rsi
0x1800db1e7  call    VpnReportError
0x1800db1ec  jmp     loc_1800DBAF8
0x1800db1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db1f8  lea     rbx, WPP_GLOBAL_Control
0x1800db1ff  cmp     rcx, rbx
0x1800db202  jz      short loc_1800DB226
0x1800db204  test    byte ptr [rcx+1Ch], 4
0x1800db208  jz      short loc_1800DB226
0x1800db20a  mov     r9, [r15+8]
0x1800db20e  mov     edx, 2B7h
0x1800db213  mov     rcx, [rcx+10h]
0x1800db217  mov     r8, rsi
0x1800db21a  call    WPP_SF_S
0x1800db21f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db226  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800db22d  jz      short loc_1800DB246
0x1800db22f  mov     r8, [r15+8]
0x1800db233  lea     rdx, VpnAutoTriggerProfileActivated
0x1800db23a  call    McTemplateU0z_EventWriteTransfer
0x1800db23f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db246  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800db24d  mov     edi, 1
0x1800db252  lea     rsi, aVpnprofileacti_0; "VpnProfileActivateAutoTrigger"
0x1800db259  lea     r14, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800db260  test    r13d, r13d
0x1800db263  jz      loc_1800DB745
0x1800db269  mov     rax, [r15+250h]
0x1800db270  mov     r9d, [rax+18h]
0x1800db274  test    r9d, r9d
0x1800db277  jz      loc_1800DB32C
0x1800db27d  cmp     rcx, rbx
0x1800db280  jz      short loc_1800DB29D
0x1800db282  test    byte ptr [rcx+1Ch], 4
0x1800db286  jz      short loc_1800DB29D
0x1800db288  mov     rcx, [rcx+10h]
0x1800db28c  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db293  mov     edx, 2B8h
0x1800db298  call    WPP_SF_d
0x1800db29d  mov     rdx, [r15+250h]
0x1800db2a4  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800db2ab  mov     r8, [rdx+20h]
0x1800db2af  mov     edx, [rdx+18h]
0x1800db2b2  call    cs:__imp_FwpiVpnTriggerAddAppSids
0x1800db2b8  mov     ebx, eax
0x1800db2ba  test    eax, eax
0x1800db2bc  jz      loc_1800DB3AF
0x1800db2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db2c9  lea     r13, WPP_GLOBAL_Control
0x1800db2d0  cmp     rcx, r13
0x1800db2d3  jz      short loc_1800DB2F3
0x1800db2d5  test    [rcx+1Ch], dil
0x1800db2d9  jz      short loc_1800DB2F3
0x1800db2db  mov     rcx, [rcx+10h]
0x1800db2df  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db2e6  mov     edx, 2B9h
0x1800db2eb  mov     r9d, eax
0x1800db2ee  call    WPP_SF_d
0x1800db2f3  mov     rcx, r12
0x1800db2f6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800db2fb  lea     rsi, aVpnprofileacti_0; "VpnProfileActivateAutoTrigger"
0x1800db302  lea     r14, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800db309  test    al, al
0x1800db30b  jz      short loc_1800DB320
0x1800db30d  mov     r9, rsi
0x1800db310  mov     r8d, 1AA9h
0x1800db316  mov     rdx, r14
0x1800db319  mov     ecx, ebx
0x1800db31b  call    TraceVpnWppErrorW32Impl
0x1800db320  lea     rdx, aFwpivpntrigger; "FwpiVpnTriggerAddAppSids"
0x1800db327  jmp     loc_1800DB1E1
0x1800db32c  cmp     rcx, rbx
0x1800db32f  jz      short loc_1800DB34C
0x1800db331  test    byte ptr [rcx+1Ch], 4
0x1800db335  jz      short loc_1800DB34C
0x1800db337  mov     rcx, [rcx+10h]
0x1800db33b  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db342  mov     edx, 2BAh
0x1800db347  call    WPP_SF_
0x1800db34c  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800db353  call    cs:__imp_FwpiVpnTriggerRemoveAppSids
0x1800db359  mov     ebx, eax
0x1800db35b  test    eax, eax
0x1800db35d  jz      short loc_1800DB3AF
0x1800db35f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db366  lea     rax, WPP_GLOBAL_Control
0x1800db36d  cmp     rcx, rax
0x1800db370  jz      short loc_1800DB390
0x1800db372  test    [rcx+1Ch], dil
0x1800db376  jz      short loc_1800DB390
0x1800db378  mov     rcx, [rcx+10h]
0x1800db37c  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db383  mov     edx, 2BBh
0x1800db388  mov     r9d, ebx
0x1800db38b  call    WPP_SF_d
0x1800db390  mov     rcx, r12
0x1800db393  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800db398  test    al, al
0x1800db39a  jz      short loc_1800DB3AF
0x1800db39c  mov     r9, rsi
0x1800db39f  mov     r8d, 1AB1h
0x1800db3a5  mov     rdx, r14
0x1800db3a8  mov     ecx, ebx
0x1800db3aa  call    TraceVpnWppErrorW32Impl
0x1800db3af  mov     rax, [r15+250h]
0x1800db3b6  mov     r9d, [rax+28h]
0x1800db3ba  test    r9d, r9d
0x1800db3bd  jz      loc_1800DB472
0x1800db3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db3ca  lea     rax, WPP_GLOBAL_Control
0x1800db3d1  cmp     rcx, rax
0x1800db3d4  jz      short loc_1800DB3F1
0x1800db3d6  test    byte ptr [rcx+1Ch], 4
0x1800db3da  jz      short loc_1800DB3F1
0x1800db3dc  mov     rcx, [rcx+10h]
0x1800db3e0  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db3e7  mov     edx, 2BCh
0x1800db3ec  call    WPP_SF_d
0x1800db3f1  mov     rdx, [r15+250h]
0x1800db3f8  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800db3ff  mov     r8, [rdx+30h]
0x1800db403  mov     edx, [rdx+28h]
0x1800db406  call    cs:__imp_FwpiVpnTriggerAddFilePaths
0x1800db40c  mov     ebx, eax
0x1800db40e  test    eax, eax
0x1800db410  jz      loc_1800DB503
0x1800db416  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db41d  lea     r13, WPP_GLOBAL_Control
0x1800db424  cmp     rcx, r13
0x1800db427  jz      short loc_1800DB447
0x1800db429  test    [rcx+1Ch], dil
0x1800db42d  jz      short loc_1800DB447
0x1800db42f  mov     rcx, [rcx+10h]
0x1800db433  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db43a  mov     edx, 2BDh
0x1800db43f  mov     r9d, eax
0x1800db442  call    WPP_SF_d
0x1800db447  mov     rcx, r12
0x1800db44a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800db44f  test    al, al
0x1800db451  jz      short loc_1800DB466
0x1800db453  mov     r9, rsi
0x1800db456  mov     r8d, 1ABBh
0x1800db45c  mov     rdx, r14
0x1800db45f  mov     ecx, ebx
0x1800db461  call    TraceVpnWppErrorW32Impl
0x1800db466  lea     rdx, aFwpivpntrigger_3; "FwpiVpnTriggerAddFilePaths"
0x1800db46d  jmp     loc_1800DB1E1
0x1800db472  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db479  lea     rax, WPP_GLOBAL_Control
0x1800db480  cmp     rcx, rax
0x1800db483  jz      short loc_1800DB4A0
0x1800db485  test    byte ptr [rcx+1Ch], 4
0x1800db489  jz      short loc_1800DB4A0
0x1800db48b  mov     rcx, [rcx+10h]
0x1800db48f  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db496  mov     edx, 2BEh
0x1800db49b  call    WPP_SF_
0x1800db4a0  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
0x1800db4a7  call    cs:__imp_FwpiVpnTriggerRemoveFilePaths
0x1800db4ad  mov     ebx, eax
0x1800db4af  test    eax, eax
0x1800db4b1  jz      short loc_1800DB503
0x1800db4b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db4ba  lea     rax, WPP_GLOBAL_Control
0x1800db4c1  cmp     rcx, rax
0x1800db4c4  jz      short loc_1800DB4E4
0x1800db4c6  test    [rcx+1Ch], dil
0x1800db4ca  jz      short loc_1800DB4E4
0x1800db4cc  mov     rcx, [rcx+10h]
0x1800db4d0  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db4d7  mov     edx, 2BFh
0x1800db4dc  mov     r9d, ebx
0x1800db4df  call    WPP_SF_d
0x1800db4e4  mov     rcx, r12
0x1800db4e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800db4ec  test    al, al
0x1800db4ee  jz      short loc_1800DB503
0x1800db4f0  mov     r9, rsi
0x1800db4f3  mov     r8d, 1AC2h
0x1800db4f9  mov     rdx, r14
0x1800db4fc  mov     ecx, ebx
0x1800db4fe  call    TraceVpnWppErrorW32Impl
0x1800db503  mov     rax, [r15+250h]
0x1800db50a  xor     ebx, ebx
0x1800db50c  cmp     [rax+38h], rbx
0x1800db510  jz      loc_1800DB6A6
0x1800db516  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db51d  lea     rax, WPP_GLOBAL_Control
0x1800db524  cmp     rcx, rax
0x1800db527  jz      short loc_1800DB544
0x1800db529  test    byte ptr [rcx+1Ch], 4
0x1800db52d  jz      short loc_1800DB544
0x1800db52f  mov     rcx, [rcx+10h]
0x1800db533  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db53a  mov     edx, 2C0h
0x1800db53f  call    WPP_SF_
0x1800db544  mov     rcx, [r15+250h]
0x1800db54b  lea     r9, [rsp+58h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800db550  mov     [rsp+58h+SecurityDescriptor], rbx
0x1800db555  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x1800db55a  mov     [rsp+58h+SecurityDescriptorSize], ebx
0x1800db55e  mov     edx, edi; StringSDRevision
0x1800db560  mov     rcx, [rcx+38h]; StringSecurityDescriptor
0x1800db564  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800db56a  call    cs:__imp_GetLastError
0x1800db570  mov     ebx, eax
0x1800db572  cmp     eax, 534h
0x1800db577  jnz     short loc_1800DB580
0x1800db579  xor     ebx, ebx
0x1800db57b  jmp     loc_1800DB667
0x1800db580  test    ebx, ebx
0x1800db582  jnz     loc_1800DB617
0x1800db588  mov     rcx, cs:WPP_GLOBAL_Control
0x1800db58f  lea     rax, WPP_GLOBAL_Control
0x1800db596  cmp     rcx, rax
0x1800db599  jz      short loc_1800DB5B6
0x1800db59b  test    byte ptr [rcx+1Ch], 4
0x1800db59f  jz      short loc_1800DB5B6
0x1800db5a1  mov     rcx, [rcx+10h]
0x1800db5a5  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800db5ac  mov     edx, 2C1h
0x1800db5b1  call    WPP_SF_
0x1800db5b6  mov     rdx, [rsp+58h+SecurityDescriptor]
0x1800db5bb  mov     rcx, cs:?g_FwpEngineHandle@@3PEAXEA; void * g_FwpEngineHandle
  ... truncated ...
```
