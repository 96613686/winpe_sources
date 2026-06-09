# int_SetActiveProfile(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800d4f20`
- end: `0x1800d5e73`
- name: `?int_SetActiveProfile@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `3923`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180065328`
- `0x1800a4874`
- `0x1800a49ec`
- `0x1800a56d8`
- `0x1800a68d8`
- `0x1800a6cbc`
- `0x1800b81fc`
- `0x1800bf670`
- `0x1800c0e48`
- `0x1800c0ef0`
- `0x1800d4f20`
- `0x1800d61bc`
- `0x1800daba4`
- `0x1800db0ac`
- `0x1800dbbb0`
- `0x1800dc76c`
- `0x1800dc964`
- `0x1800dde2c`
- `0x1800e014c`
- `0x1800e0b3c`
- `0x1800e1cd8`
- `0x1800e1d04`
- `0x1800e1e64`
- `0x1800e218c`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800d56be`
- `ntdll!RtlFreeSid` at `0x1800d56be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d58c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d58c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d5e1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d5e1d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d5d31`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d5d31`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d58b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d58b7`

## string_xrefs

- `0x1800d5219`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5279`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5332`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d561a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d57b1`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5869`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5918`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d596f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d59db`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5b49`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5bee`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5cb1`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d5d88`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d589c`: `VpnStringCopy for pProfileName`
- `0x1800d57e4`: `VpnStringCopy for pProfilePhonebookPath `

## pseudocode

```c
void __fastcall int_SetActiveProfile(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v4; // rsi
  struct _LIST_ENTRY *v5; // rdx
  struct _LIST_ENTRY *v6; // rbp
  struct _LIST_ENTRY *Blink; // r14
  const WCHAR *v8; // r12
  int v9; // ebx
  unsigned int Blink_high; // r15d
  struct _LIST_ENTRY *v11; // rcx
  const char *v12; // r8
  const char *v13; // rax
  LPCWSTR *v14; // rsi
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // r8
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // ebx
  int v21; // edi
  unsigned int v22; // ebx
  struct _LIST_ENTRY *v23; // rcx
  LPCWSTR v24; // rax
  int v25; // edx
  int v26; // r8d
  LPCWSTR v27; // rax
  int v28; // edx
  int v29; // r8d
  unsigned int v30; // ebx
  __int64 v31; // r8
  struct _LIST_ENTRY *v32; // rcx
  __int64 v33; // rdx
  LPCWSTR v34; // rax
  int v35; // edx
  int v36; // r8d
  LPCWSTR v37; // rax
  int v38; // edx
  int v39; // r8d
  _QWORD *v40; // rbx
  WCHAR *v41; // rcx
  struct tagRASENTRYADVANCED **v42; // rdi
  int v43; // eax
  int v44; // ebx
  int v45; // eax
  const char *v47; // rdx
  __int64 *v48; // rdi
  int v49; // eax
  int v50; // eax
  DWORD LastError; // eax
  DWORD ActiveTokenAndSessionId; // ebx
  __int64 v54; // r8
  DWORD v55; // eax
  struct _LIST_ENTRY *v56; // rcx
  DWORD v57; // eax
  int v58; // r8d
  unsigned int LockdownNciNrptRule; // eax
  unsigned int v60; // eax
  unsigned int v61; // ebx
  struct _LIST_ENTRY *v62; // rcx
  __int64 v63; // rdx
  DWORD v64; // eax
  bool v65; // di
  struct _TP_WORK *v66; // rcx
  struct _LIST_ENTRY *v67; // [rsp+40h] [rbp-58h]
  PSID Sid; // [rsp+48h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 618, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  Sid = 0;
  VpnCriticalSectionEnter(&g_CsSetActiveProfileOperation);
  Flink = g_RasSetActiveList.Flink;
  if ( g_RasSetActiveList.Flink == &g_RasSetActiveList )
  {
    v4 = 0;
    v67 = 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 619, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
  }
  else
  {
    if ( g_RasSetActiveList.Flink->Blink != &g_RasSetActiveList
      || (v5 = g_RasSetActiveList.Flink->Flink, g_RasSetActiveList.Flink->Flink->Blink != g_RasSetActiveList.Flink) )
    {
      __fastfail(3u);
    }
    v4 = g_RasSetActiveList.Flink - 2;
    g_RasSetActiveList.Flink = g_RasSetActiveList.Flink->Flink;
    v67 = Flink - 2;
    v5->Blink = &g_RasSetActiveList;
  }
  VpnCriticalSectionLeave(&g_CsSetActiveProfileOperation);
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  if ( v4 )
  {
    v6 = v4->Flink;
    Blink = v4->Blink;
    v8 = (const WCHAR *)v4[1].Flink;
    v9 = (int)v4[1].Blink;
    Blink_high = HIDWORD(v4[1].Blink);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      v12 = L"<NULL>";
      v13 = L"<NULL>";
      if ( v8 )
        v12 = (const char *)v4[1].Flink;
      if ( Blink )
        v13 = (const char *)v4->Blink;
      WPP_SF_SSScc((TRACEHANDLE)WPP_GLOBAL_Control[1].Flink, (__int64)v13, (__int64)v12, v9 != 0, Blink_high != 0);
      v11 = WPP_GLOBAL_Control;
    }
    v14 = &g_ActiveUserProfile;
    if ( !Blink_high )
      v14 = &g_ActiveDeviceProfile;
    if ( !v9 )
    {
LABEL_56:
      if ( !v6 || !Blink || !v8 )
      {
        if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 1) != 0 )
          WPP_SF_(v11[1].Flink, 655, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        goto LABEL_262;
      }
      v21 = 1;
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
        WPP_SF_(v11[1].Flink, 626, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      v22 = VpnProfileSetRasManServiceState(1);
      if ( v22 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 627, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v22);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v22,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            6212,
            "int_SetActiveProfile");
      }
      if ( Blink_high )
      {
        if ( g_IsActiveUserProfile )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 628, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            v23 = WPP_GLOBAL_Control;
          }
          v24 = g_ActiveUserProfile;
          do
          {
            v25 = *(LPCWSTR)((char *)v24 + (char *)v6 - (char *)g_ActiveUserProfile);
            v26 = *v24 - v25;
            if ( v26 )
              break;
            ++v24;
          }
          while ( v25 );
          if ( v26 )
            goto LABEL_83;
          v27 = qword_18010DFD8;
          do
          {
            v28 = *(LPCWSTR)((char *)v27 + (char *)Blink - (char *)qword_18010DFD8);
            v29 = *v27 - v28;
            if ( v29 )
              break;
            ++v27;
          }
          while ( v28 );
          if ( v29 )
          {
LABEL_83:
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
              WPP_SF_(v23[1].Flink, 629, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            VpnProfileDeActivateAutoTrigger(1, Blink_high);
            VpnProfileActiveFree(&g_ActiveUserProfile);
            v23 = WPP_GLOBAL_Control;
            g_IsActiveUserProfile = 0;
          }
          else
          {
            v21 = 0;
          }
          if ( g_pNrptRuleListPersistentPrefixForUserTunnel )
          {
            v30 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForUserTunnel, 1);
            if ( !v30 )
              goto LABEL_121;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 630, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v30);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_121;
            v31 = 6238;
LABEL_120:
            TraceVpnWppErrorW32Impl(
              v30,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              v31,
              "int_SetActiveProfile");
LABEL_121:
            v23 = WPP_GLOBAL_Control;
            goto LABEL_122;
          }
          goto LABEL_122;
        }
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          v33 = 631;
LABEL_137:
          WPP_SF_(v32[1].Flink, v33, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        }
      }
      else
      {
        if ( g_IsActiveDeviceProfile )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 632, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            v23 = WPP_GLOBAL_Control;
          }
          v34 = g_ActiveDeviceProfile;
          do
          {
            v35 = *(LPCWSTR)((char *)v34 + (char *)v6 - (char *)g_ActiveDeviceProfile);
            v36 = *v34 - v35;
            if ( v36 )
              break;
            ++v34;
          }
          while ( v35 );
          if ( v36 )
            goto LABEL_110;
          v37 = qword_18010E238;
          do
          {
            v38 = *(LPCWSTR)((char *)v37 + (char *)Blink - (char *)qword_18010E238);
            v39 = *v37 - v38;
            if ( v39 )
              break;
            ++v37;
          }
          while ( v38 );
          if ( v39 )
          {
LABEL_110:
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
              WPP_SF_(v23[1].Flink, 633, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            VpnProfileDeActivateAutoTrigger(1, 0);
            VpnProfileActiveFree(&g_ActiveDeviceProfile);
            v23 = WPP_GLOBAL_Control;
            g_IsActiveDeviceProfile = 0;
          }
          else
          {
            v21 = 0;
          }
          if ( g_pNrptRuleListPersistentPrefixForDeviceTunnel )
          {
            v30 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForDeviceTunnel, 1);
            if ( !v30 )
              goto LABEL_121;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 634, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v30);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_121;
            v31 = 6271;
            goto LABEL_120;
          }
LABEL_122:
          if ( !v21 )
          {
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
            {
              WPP_SF_(v23[1].Flink, 644, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
              v23 = WPP_GLOBAL_Control;
            }
            if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
            {
              McTemplateU0z_EventWriteTransfer(v23, VpnAutoTriggerProfileModified, v14[1]);
              v23 = WPP_GLOBAL_Control;
            }
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
              WPP_SF_SS(
                v23[1].Flink,
                645,
                (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                (unsigned int)*v14,
                (__int64)v14[1]);
            v40 = v14 + 73;
            v41 = (WCHAR *)v14[73];
            if ( v41 )
            {
              RtlFreeSid(v41);
              *v40 = 0;
            }
            v42 = (struct tagRASENTRYADVANCED **)(v14 + 74);
            VpnProfileActiveSettingsFree((LPVOID)v14[74]);
            v14[74] = 0;
            *((_DWORD *)v14 + 6) = 0;
            goto LABEL_201;
          }
LABEL_141:
          if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
            WPP_SF_(v23[1].Flink, 636, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
          v43 = VpnStringCopy(v6);
          v44 = v43;
          if ( v43 < 0 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                637,
                &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                (unsigned int)v43);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorHRImpl(
                (unsigned int)v44,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6285,
                "int_SetActiveProfile");
            v45 = (v44 >> 16) & 0x1FFF;
            if ( v45 == 7 ? (unsigned __int16)v44 : v44 )
            {
              if ( v45 == 7 )
                v44 = (unsigned __int16)v44;
              v47 = "VpnStringCopy for pProfilePhonebookPath ";
LABEL_157:
              VpnReportError("int_SetActiveProfile", v47, (unsigned int)v44);
LABEL_262:
              v4 = v67;
              goto LABEL_263;
            }
          }
          v48 = (__int64 *)(v14 + 1);
          v49 = VpnStringCopy(Blink);
          v44 = v49;
          if ( v49 < 0 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                638,
                &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                (unsigned int)v49);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorHRImpl(
                (unsigned int)v44,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6289,
                "int_SetActiveProfile");
            v50 = (v44 >> 16) & 0x1FFF;
            if ( v50 == 7 ? (unsigned __int16)v44 : v44 )
            {
              if ( v50 == 7 )
                v44 = (unsigned __int16)v44;
              v47 = "VpnStringCopy for pProfileName";
              goto LABEL_157;
            }
          }
          if ( ConvertStringSidToSidW(v8, &Sid) )
          {
            v55 = VpnSidCopy(Sid);
            ActiveTokenAndSessionId = v55;
            if ( v55 )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 641, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v55);
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                TraceVpnWppErrorW32Impl(
                  ActiveTokenAndSessionId,
                  L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                  6301,
                  "int_SetActiveProfile");
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  642,
                  &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                  ActiveTokenAndSessionId);
              }
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                goto LABEL_262;
              v54 = 6302;
LABEL_183:
              TraceVpnWppErrorW32Impl(
                ActiveTokenAndSessionId,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                v54,
                "int_SetActiveProfile");
              goto LABEL_262;
            }
          }
          else
          {
            LastError = GetLastError();
            ActiveTokenAndSessionId = LastError;
            if ( LastError )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 639, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                TraceVpnWppErrorW32Impl(
                  ActiveTokenAndSessionId,
                  L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                  6295,
                  "int_SetActiveProfile");
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  640,
                  &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                  ActiveTokenAndSessionId);
              }
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                goto LABEL_262;
              v54 = 6296;
              goto LABEL_183;
            }
          }
          v56 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_SS(
              WPP_GLOBAL_Control[1].Flink,
              643,
              (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
              (unsigned int)*v14,
              *v48);
          }
          if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
            McTemplateU0z_EventWriteTransfer(v56, VpnAutoTriggerProfileAdded, *v48);
          v42 = (struct tagRASENTRYADVANCED **)(v14 + 74);
          v40 = v14 + 73;
LABEL_201:
          v57 = VpnProfileActiveSettingsGet(*v14, (WCHAR *)v14[1], (__int64)v40, v42);
          ActiveTokenAndSessionId = v57;
          if ( v57 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 646, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v57);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_262;
            v54 = 6335;
            goto LABEL_183;
          }
          if ( *((_DWORD *)*v42 + 33) )
          {
            LockdownNciNrptRule = int_VpnCreateLockdownNciNrptRule((unsigned __int16 *)v14[1]);
            ActiveTokenAndSessionId = LockdownNciNrptRule;
            if ( LockdownNciNrptRule )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  647,
                  &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                  LockdownNciNrptRule);
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                TraceVpnWppErrorW32Impl(
                  ActiveTokenAndSessionId,
                  L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                  6344,
                  "int_SetActiveProfile");
              ActiveTokenAndSessionId = 0;
            }
          }
          if ( Blink_high )
            ActiveTokenAndSessionId = GetActiveTokenAndSessionId((void *)v14[2]);
          if ( ActiveTokenAndSessionId )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                653,
                &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                ActiveTokenAndSessionId);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                ActiveTokenAndSessionId,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6419,
                "int_SetActiveProfile");
LABEL_254:
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                654,
                &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                ActiveTokenAndSessionId);
            }
            if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              goto LABEL_262;
            v54 = 6424;
            goto LABEL_183;
          }
          v60 = RasAddNrptRulesEx(*((_QWORD *)*v42 + 1), *(_DWORD *)*v42, v58, 0, 1, 0);
          v61 = v60;
          if ( v60 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 648, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v60);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                v61,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6365,
                "int_SetActiveProfile");
          }
          *((_DWORD *)v14 + 6) = 0;
          if ( Blink_high )
          {
            g_IsActiveUserProfile = 1;
            v62 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
            {
              v63 = 649;
LABEL_231:
              WPP_SF_(v62[1].Flink, v63, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            }
          }
          else
          {
            g_IsActiveDeviceProfile = 1;
            v62 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
            {
              v63 = 650;
              goto LABEL_231;
            }
          }
          v64 = VpnProfileActivateAutoTrigger(v14, Blink_high);
          ActiveTokenAndSessionId = v64;
          if ( v64 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 651, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v64);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
              TraceVpnWppErrorW32Impl(
                ActiveTokenAndSessionId,
                L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                6386,
                "int_SetActiveProfile");
            ActiveTokenAndSessionId = 0;
          }
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 652, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
          }
          VpnCriticalSectionEnter(&g_CsLogicalConnection);
          v65 = g_fIsDeviceTunnelAllowed;
          VpnCriticalSectionLeave(&g_CsLogicalConnection);
          if ( Blink_high || v65 )
          {
            AddVPNTriggerEvent(7, Blink_high);
            v66 = g_pReConnectUserTunnelWorkItem;
            if ( !Blink_high )
              v66 = g_pReConnectDeviceTunnelWorkItem;
            SubmitThreadpoolWork(v66);
          }
          if ( !ActiveTokenAndSessionId )
            goto LABEL_262;
          goto LABEL_254;
        }
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          v33 = 635;
          goto LABEL_137;
        }
      }
      if ( (unsigned int)IsDefaultTracingEnabled() )
        EnableAutoWPPTracingForSubComponent(0);
      v23 = WPP_GLOBAL_Control;
      goto LABEL_141;
    }
    if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v11[1].Blink) & 4) != 0 )
      WPP_SF_(v11[1].Flink, 622, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(v11, VpnAutoTriggerProfileDeleted, v14[1]);
    VpnProfileDeActivateAutoTrigger(1, Blink_high);
    VpnProfileActiveFree(v14);
    if ( Blink_high )
      g_IsActiveUserProfile = 0;
    else
      g_IsActiveDeviceProfile = 0;
    DisableAutoWPPTracingForSubComponent(0);
    if ( Blink_high )
    {
      if ( !g_pNrptRuleListPersistentPrefixForUserTunnel )
        goto LABEL_49;
      v15 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForUserTunnel, 1);
      v16 = v15;
      if ( !v15 )
        goto LABEL_49;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 623, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v15);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_49;
      v17 = 6188;
    }
    else
    {
      if ( !g_pNrptRuleListPersistentPrefixForDeviceTunnel )
        goto LABEL_49;
      v18 = RasRemoveNrptRules(g_pNrptRuleListPersistentPrefixForDeviceTunnel, 1);
      v16 = v18;
      if ( !v18 )
        goto LABEL_49;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 624, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v18);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_49;
      v17 = 6196;
    }
    TraceVpnWppErrorW32Impl(
      v16,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v17,
      "int_SetActiveProfile");
LABEL_49:
    v19 = VpnProfileSetRasManServiceState(0);
    v20 = v19;
    if ( v19 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 625, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v19);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v20,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          6204,
          "int_SetActiveProfile");
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 620, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
LABEL_263:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
  FreeSetProfileContext((struct _SET_ACTIVE_PROFILE_WORK_CONTEXT *)v4);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 656, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
}

```

## disassembly

```asm
0x1800d4f20  push    rbx
0x1800d4f22  push    rbp
0x1800d4f23  push    rsi
0x1800d4f24  push    rdi
0x1800d4f25  push    r12
0x1800d4f27  push    r13
0x1800d4f29  push    r14
0x1800d4f2b  push    r15
0x1800d4f2d  sub     rsp, 58h
0x1800d4f31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4f38  lea     rbp, WPP_GLOBAL_Control
0x1800d4f3f  cmp     rcx, rbp
0x1800d4f42  jz      short loc_1800D4F5F
0x1800d4f44  test    byte ptr [rcx+1Ch], 8
0x1800d4f48  jz      short loc_1800D4F5F
0x1800d4f4a  mov     rcx, [rcx+10h]
0x1800d4f4e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d4f55  mov     edx, 26Ah
0x1800d4f5a  call    WPP_SF_
0x1800d4f5f  xor     r13d, r13d
0x1800d4f62  mov     [rsp+98h+Sid], 0
0x1800d4f6b  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800d4f72  mov     [rsp+98h+arg_18], r13d
0x1800d4f7a  call    VpnCriticalSectionEnter
0x1800d4f7f  mov     rax, cs:?g_RasSetActiveList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RasSetActiveList
0x1800d4f86  lea     rcx, ?g_RasSetActiveList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RasSetActiveList
0x1800d4f8d  cmp     rax, rcx
0x1800d4f90  jnz     short loc_1800D4FC2
0x1800d4f92  xor     esi, esi
0x1800d4f94  mov     [rsp+98h+var_58], rsi
0x1800d4f99  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4fa0  cmp     rcx, rbp
0x1800d4fa3  jz      short loc_1800D4FED
0x1800d4fa5  test    byte ptr [rcx+1Ch], 1
0x1800d4fa9  jz      short loc_1800D4FED
0x1800d4fab  mov     rcx, [rcx+10h]
0x1800d4faf  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d4fb6  mov     edx, 26Bh
0x1800d4fbb  call    WPP_SF_
0x1800d4fc0  jmp     short loc_1800D4FED
0x1800d4fc2  cmp     [rax+8], rcx
0x1800d4fc6  jnz     loc_1800D5E6C
0x1800d4fcc  mov     rdx, [rax]
0x1800d4fcf  cmp     [rdx+8], rax
0x1800d4fd3  jnz     loc_1800D5E6C
0x1800d4fd9  lea     rsi, [rax-20h]
0x1800d4fdd  mov     cs:?g_RasSetActiveList@@3U_LIST_ENTRY@@A, rdx; _LIST_ENTRY g_RasSetActiveList
0x1800d4fe4  mov     [rsp+98h+var_58], rsi
0x1800d4fe9  mov     [rdx+8], rcx
0x1800d4fed  lea     rcx, ?g_CsSetActiveProfileOperation@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_CsSetActiveProfileOperation
0x1800d4ff4  call    VpnCriticalSectionLeave
0x1800d4ff9  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800d5000  call    VpnCriticalSectionEnter
0x1800d5005  test    rsi, rsi
0x1800d5008  jnz     short loc_1800D503E
0x1800d500a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5011  cmp     rcx, rbp
0x1800d5014  jz      loc_1800D5E07
0x1800d501a  test    byte ptr [rcx+1Ch], 1
0x1800d501e  jz      loc_1800D5E07
0x1800d5024  mov     rcx, [rcx+10h]
0x1800d5028  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d502f  mov     edx, 26Ch
0x1800d5034  call    WPP_SF_
0x1800d5039  jmp     loc_1800D5E07
0x1800d503e  mov     rbp, [rsi]
0x1800d5041  mov     r14, [rsi+8]
0x1800d5045  mov     r12, [rsi+10h]
0x1800d5049  mov     ebx, [rsi+18h]
0x1800d504c  mov     r15d, [rsi+1Ch]
0x1800d5050  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5057  lea     rdi, WPP_GLOBAL_Control
0x1800d505e  cmp     rcx, rdi
0x1800d5061  jz      short loc_1800D50C1
0x1800d5063  test    byte ptr [rcx+1Ch], 4
0x1800d5067  jz      short loc_1800D50C1
0x1800d5069  mov     rcx, [rcx+10h]; LoggerHandle
0x1800d506d  lea     r9, aNull_5; "<NULL>"
0x1800d5074  test    r15d, r15d
0x1800d5077  mov     r8, r9
0x1800d507a  mov     rax, r9
0x1800d507d  mov     edx, 26Dh
0x1800d5082  setnz   r11b
0x1800d5086  test    ebx, ebx
0x1800d5088  mov     [rsp+98h+var_60], r11b; char
0x1800d508d  setnz   r10b
0x1800d5091  test    r12, r12
0x1800d5094  mov     [rsp+98h+var_68], r10b; char
0x1800d5099  cmovnz  r8, r12
0x1800d509d  test    r14, r14
0x1800d50a0  mov     [rsp+98h+var_70], r8; __int64
0x1800d50a5  cmovnz  rax, r14
0x1800d50a9  test    rbp, rbp
0x1800d50ac  mov     [rsp+98h+var_78], rax; __int64
0x1800d50b1  cmovnz  r9, rbp
0x1800d50b5  call    WPP_SF_SSScc
0x1800d50ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d50c1  test    r15d, r15d
0x1800d50c4  lea     rax, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800d50cb  lea     rsi, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d50d2  cmovz   rsi, rax
0x1800d50d6  test    ebx, ebx
0x1800d50d8  jz      loc_1800D528E
0x1800d50de  cmp     rcx, rdi
0x1800d50e1  jz      short loc_1800D50FE
0x1800d50e3  test    byte ptr [rcx+1Ch], 4
0x1800d50e7  jz      short loc_1800D50FE
0x1800d50e9  mov     rcx, [rcx+10h]
0x1800d50ed  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d50f4  mov     edx, 26Eh
0x1800d50f9  call    WPP_SF_
0x1800d50fe  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x1800d5105  jz      short loc_1800D5117
0x1800d5107  mov     r8, [rsi+8]
0x1800d510b  lea     rdx, VpnAutoTriggerProfileDeleted
0x1800d5112  call    McTemplateU0z_EventWriteTransfer
0x1800d5117  mov     r8d, 7
0x1800d511d  mov     edx, r15d
0x1800d5120  lea     ebx, [r8-6]
0x1800d5124  mov     ecx, ebx
0x1800d5126  call    VpnProfileDeActivateAutoTrigger
0x1800d512b  mov     rcx, rsi
0x1800d512e  call    VpnProfileActiveFree
0x1800d5133  test    r15d, r15d
0x1800d5136  jz      short loc_1800D5141
0x1800d5138  mov     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800d513f  jmp     short loc_1800D5148
0x1800d5141  mov     cs:?g_IsActiveDeviceProfile@@3HA, r13d; int g_IsActiveDeviceProfile
0x1800d5148  xor     ecx, ecx
0x1800d514a  call    DisableAutoWPPTracingForSubComponent
0x1800d514f  test    r15d, r15d
0x1800d5152  jz      short loc_1800D51B7
0x1800d5154  mov     rcx, cs:?g_pNrptRuleListPersistentPrefixForUserTunnel@@3PEAUtagRASNRPTRULELIST@@EA; tagRASNRPTRULELIST * g_pNrptRuleListPersistentPrefixForUserTunnel
0x1800d515b  test    rcx, rcx
0x1800d515e  jz      loc_1800D5225
0x1800d5164  mov     edx, ebx
0x1800d5166  call    RasRemoveNrptRules
0x1800d516b  mov     ebx, eax
0x1800d516d  test    eax, eax
0x1800d516f  jz      loc_1800D5225
0x1800d5175  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d517c  cmp     rcx, rdi
0x1800d517f  jz      short loc_1800D519F
0x1800d5181  test    byte ptr [rcx+1Ch], 1
0x1800d5185  jz      short loc_1800D519F
0x1800d5187  mov     rcx, [rcx+10h]
0x1800d518b  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d5192  mov     edx, 26Fh
0x1800d5197  mov     r9d, eax
0x1800d519a  call    WPP_SF_d
0x1800d519f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d51a6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d51ab  test    al, al
0x1800d51ad  jz      short loc_1800D5225
0x1800d51af  mov     r8d, 182Ch
0x1800d51b5  jmp     short loc_1800D5210
0x1800d51b7  mov     rcx, cs:?g_pNrptRuleListPersistentPrefixForDeviceTunnel@@3PEAUtagRASNRPTRULELIST@@EA; tagRASNRPTRULELIST * g_pNrptRuleListPersistentPrefixForDeviceTunnel
0x1800d51be  test    rcx, rcx
0x1800d51c1  jz      short loc_1800D5225
0x1800d51c3  mov     edx, ebx
0x1800d51c5  call    RasRemoveNrptRules
0x1800d51ca  mov     ebx, eax
0x1800d51cc  test    eax, eax
0x1800d51ce  jz      short loc_1800D5225
0x1800d51d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d51d7  cmp     rcx, rdi
0x1800d51da  jz      short loc_1800D51FA
0x1800d51dc  test    byte ptr [rcx+1Ch], 1
0x1800d51e0  jz      short loc_1800D51FA
0x1800d51e2  mov     rcx, [rcx+10h]
0x1800d51e6  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d51ed  mov     edx, 270h
0x1800d51f2  mov     r9d, eax
0x1800d51f5  call    WPP_SF_d
0x1800d51fa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d5201  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d5206  test    al, al
0x1800d5208  jz      short loc_1800D5225
0x1800d520a  mov     r8d, 1834h
0x1800d5210  lea     r9, aIntSetactivepr; "int_SetActiveProfile"
0x1800d5217  mov     ecx, ebx
0x1800d5219  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d5220  call    TraceVpnWppErrorW32Impl
0x1800d5225  xor     ecx, ecx
0x1800d5227  call    VpnProfileSetRasManServiceState
0x1800d522c  mov     ebx, eax
0x1800d522e  test    eax, eax
0x1800d5230  jz      short loc_1800D5287
0x1800d5232  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5239  cmp     rcx, rdi
0x1800d523c  jz      short loc_1800D525C
0x1800d523e  test    byte ptr [rcx+1Ch], 1
0x1800d5242  jz      short loc_1800D525C
0x1800d5244  mov     rcx, [rcx+10h]
0x1800d5248  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d524f  mov     edx, 271h
0x1800d5254  mov     r9d, eax
0x1800d5257  call    WPP_SF_d
0x1800d525c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d5263  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d5268  test    al, al
0x1800d526a  jz      short loc_1800D5287
0x1800d526c  lea     r9, aIntSetactivepr; "int_SetActiveProfile"
0x1800d5273  mov     r8d, 183Ch
0x1800d5279  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d5280  mov     ecx, ebx
0x1800d5282  call    TraceVpnWppErrorW32Impl
0x1800d5287  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d528e  test    rbp, rbp
0x1800d5291  jz      loc_1800D5DDB
0x1800d5297  test    r14, r14
0x1800d529a  jz      loc_1800D5DDB
0x1800d52a0  test    r12, r12
0x1800d52a3  jz      loc_1800D5DDB
0x1800d52a9  mov     ebx, 1
0x1800d52ae  mov     edi, ebx
0x1800d52b0  lea     rax, WPP_GLOBAL_Control
0x1800d52b7  cmp     rcx, rax
0x1800d52ba  jz      short loc_1800D52D7
0x1800d52bc  test    byte ptr [rcx+1Ch], 4
0x1800d52c0  jz      short loc_1800D52D7
0x1800d52c2  mov     rcx, [rcx+10h]
0x1800d52c6  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d52cd  mov     edx, 272h
0x1800d52d2  call    WPP_SF_
0x1800d52d7  mov     ecx, ebx
0x1800d52d9  call    VpnProfileSetRasManServiceState
0x1800d52de  mov     ebx, eax
0x1800d52e0  test    eax, eax
0x1800d52e2  jz      short loc_1800D5340
0x1800d52e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d52eb  lea     rax, WPP_GLOBAL_Control
0x1800d52f2  cmp     rcx, rax
0x1800d52f5  jz      short loc_1800D5315
0x1800d52f7  test    [rcx+1Ch], dil
0x1800d52fb  jz      short loc_1800D5315
0x1800d52fd  mov     rcx, [rcx+10h]
0x1800d5301  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d5308  mov     edx, 273h
0x1800d530d  mov     r9d, ebx
0x1800d5310  call    WPP_SF_d
0x1800d5315  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d531c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d5321  test    al, al
0x1800d5323  jz      short loc_1800D5340
0x1800d5325  lea     r9, aIntSetactivepr; "int_SetActiveProfile"
0x1800d532c  mov     r8d, 1844h
0x1800d5332  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d5339  mov     ecx, ebx
0x1800d533b  call    TraceVpnWppErrorW32Impl
0x1800d5340  test    r15d, r15d
0x1800d5343  jz      loc_1800D54CB
0x1800d5349  cmp     cs:?g_IsActiveUserProfile@@3HA, r13d; int g_IsActiveUserProfile
0x1800d5350  jz      loc_1800D54A0
0x1800d5356  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d535d  lea     rbx, WPP_GLOBAL_Control
0x1800d5364  cmp     rcx, rbx
0x1800d5367  jz      short loc_1800D538B
0x1800d5369  test    byte ptr [rcx+1Ch], 4
0x1800d536d  jz      short loc_1800D538B
0x1800d536f  mov     rcx, [rcx+10h]
0x1800d5373  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d537a  mov     edx, 274h
0x1800d537f  call    WPP_SF_
0x1800d5384  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d538b  mov     rax, cs:?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d5392  mov     r9, rbp
0x1800d5395  sub     r9, rax
0x1800d5398  movzx   r8d, word ptr [rax]
0x1800d539c  movzx   edx, word ptr [rax+r9]
0x1800d53a1  sub     r8d, edx
0x1800d53a4  jnz     short loc_1800D53AE
0x1800d53a6  add     rax, 2
0x1800d53aa  test    edx, edx
0x1800d53ac  jnz     short loc_1800D5398
0x1800d53ae  test    r8d, r8d
0x1800d53b1  jnz     short loc_1800D53DF
0x1800d53b3  mov     rax, cs:qword_18010DFD8
0x1800d53ba  mov     r9, r14
0x1800d53bd  sub     r9, rax
0x1800d53c0  movzx   r8d, word ptr [rax]
0x1800d53c4  movzx   edx, word ptr [rax+r9]
0x1800d53c9  sub     r8d, edx
0x1800d53cc  jnz     short loc_1800D53D6
0x1800d53ce  add     rax, 2
0x1800d53d2  test    edx, edx
0x1800d53d4  jnz     short loc_1800D53C0
0x1800d53d6  test    r8d, r8d
0x1800d53d9  jnz     short loc_1800D53DF
0x1800d53db  xor     edi, edi
0x1800d53dd  jmp     short loc_1800D5429
0x1800d53df  cmp     rcx, rbx
0x1800d53e2  jz      short loc_1800D53FF
0x1800d53e4  test    byte ptr [rcx+1Ch], 4
0x1800d53e8  jz      short loc_1800D53FF
0x1800d53ea  mov     rcx, [rcx+10h]
0x1800d53ee  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d53f5  mov     edx, 275h
0x1800d53fa  call    WPP_SF_
0x1800d53ff  mov     r8d, 7
  ... truncated ...
```
