# int_VpnProfileCopyNrptRules(ushort *,tagRASENTRYADVANCED *,_VPNPROFILEACTIVESETTINGS *)

- ea: `0x1800d77e0`
- end: `0x1800d80e4`
- name: `?int_VpnProfileCopyNrptRules@@YAKPEAGPEAUtagRASENTRYADVANCED@@PEAU_VPNPROFILEACTIVESETTINGS@@@Z`
- size: `2308`
- prototype: `__int64 __fastcall(const char *, struct tagRASENTRYADVANCED *, struct _VPNPROFILEACTIVESETTINGS *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1800dc964`

## callees

- `0x180005e34`
- `0x18000e5f0`
- `0x1800b81fc`
- `0x1800d6120`
- `0x1800d77e0`
- `0x1800e1b9c`
- `0x1800e1e64`
- `0x1800e2294`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e71ee`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!tolower` at `0x1800d7ec2`
- `msvcrt!tolower` at `0x1800d7ec2`
- `RPCRT4!UuidCreate` at `0x1800d7c2d`
- `RPCRT4!UuidCreate` at `0x1800d7c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d7882`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d7882`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d7894`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d7894`

## string_xrefs

- `0x1800d78f3`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7959`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d79e1`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7ab8`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7b76`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7d1a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7ddd`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7e7a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d7f4f`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d80ab`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d78e6`: `int_VpnProfileCopyNrptRules`
- `0x1800d7952`: `int_VpnProfileCopyNrptRules`
- `0x1800d79d4`: `int_VpnProfileCopyNrptRules`
- `0x1800d7a1e`: `int_VpnProfileCopyNrptRules`
- `0x1800d7aab`: `int_VpnProfileCopyNrptRules`
- `0x1800d7ae8`: `int_VpnProfileCopyNrptRules`
- `0x1800d7b69`: `int_VpnProfileCopyNrptRules`
- `0x1800d7d11`: `int_VpnProfileCopyNrptRules`
- `0x1800d7dd0`: `int_VpnProfileCopyNrptRules`
- `0x1800d7e6d`: `int_VpnProfileCopyNrptRules`
- `0x1800d7f42`: `int_VpnProfileCopyNrptRules`
- `0x1800d809e`: `int_VpnProfileCopyNrptRules`
- `0x1800d8046`: `VpnStringCopy NRPT rule ProxyName`
- `0x1800d8034`: `VpnStringCopy NRPT rule DnsSuffix`

## pseudocode

```c
__int64 __fastcall int_VpnProfileCopyNrptRules(
        const char *a1,
        struct tagRASENTRYADVANCED *a2,
        struct _VPNPROFILEACTIVESETTINGS *a3)
{
  unsigned __int64 v5; // rdi
  const char *v6; // r9
  unsigned int v7; // r15d
  HANDLE ProcessHeap; // rax
  LPVOID v9; // rax
  __int64 v10; // r8
  int v11; // ebx
  int v12; // eax
  int v13; // ecx
  int v14; // edx
  bool v15; // zf
  const char *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  int v19; // ebx
  int v20; // eax
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // r13
  unsigned int v26; // eax
  unsigned int v27; // r12d
  __int64 i; // rbx
  RPC_STATUS v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  size_t v35; // rbx
  __int64 v36; // rax
  void *v37; // rcx
  _QWORD *v38; // r14
  int v39; // eax
  int v40; // ecx
  _WORD *v41; // rcx
  __int64 v42; // rbx
  __int16 v43; // ax
  int v44; // eax
  int v45; // ecx
  struct tagRASENTRYADVANCED *v46; // r14
  __int64 v47; // rdx
  __int64 v49; // [rsp+30h] [rbp-79h] BYREF
  __int64 v50; // [rsp+38h] [rbp-71h] BYREF
  __int64 v51; // [rsp+40h] [rbp-69h] BYREF
  __int64 v52; // [rsp+48h] [rbp-61h]
  struct tagRASENTRYADVANCED *v53; // [rsp+50h] [rbp-59h]
  struct _VPNPROFILEACTIVESETTINGS *v54; // [rsp+58h] [rbp-51h]
  UUID Uuid; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 v56[40]; // [rsp+70h] [rbp-39h] BYREF

  v54 = a3;
  v53 = a2;
  v5 = (unsigned __int64)a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    v6 = a1;
    if ( !a1 )
      v6 = L"<NULL>";
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 550, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v6);
  }
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v7 = 0;
  Uuid = 0;
  memset_0(v56, 0, 0x4Au);
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, 0x40u);
  *((_QWORD *)a3 + 2) = v9;
  if ( !v9 )
  {
    v7 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 551, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        5295,
        "int_VpnProfileCopyNrptRules");
  }
  if ( !*((_QWORD *)a3 + 2) )
  {
    v7 = 14;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 552, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
    }
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      return v7;
    v10 = 5297;
    goto LABEL_18;
  }
  v11 = VpnStringBuild(&v49, L"VPN_AUTO_", v5, L"_");
  if ( v11 >= 0 )
    goto LABEL_34;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 553, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v11);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorHRImpl(
      (unsigned int)v11,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      5300,
      "int_VpnProfileCopyNrptRules");
  v12 = (v11 >> 16) & 0x1FFF;
  v13 = v12 == 7 ? (unsigned __int16)v11 : v11;
  v14 = (unsigned __int16)v11;
  if ( !v13 )
  {
LABEL_34:
    v17 = *((_QWORD *)a3 + 2);
    v52 = v49;
    *(_QWORD *)(v17 + 48) = v49;
    v18 = VpnStringBuild(&v50, L"VPN_PERSISTENT_", v5, L"_");
    LODWORD(v5) = 0;
    v19 = v18;
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 554, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v18);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorHRImpl(
          (unsigned int)v19,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          5306,
          "int_VpnProfileCopyNrptRules");
      v20 = (v19 >> 16) & 0x1FFF;
      if ( v20 == 7 ? (unsigned __int16)v19 : v19 )
      {
        if ( v20 == 7 )
          v19 = (unsigned __int16)v19;
        VpnReportError("int_VpnProfileCopyNrptRules", "VpnStringBuild", (unsigned int)v19);
        return v7;
      }
    }
    v22 = *((_DWORD *)a2 + 22);
    if ( !v22 )
      return v7;
    v23 = VpnAlloc((unsigned int)(v22 << 6));
    *((_QWORD *)a3 + 1) = v23;
    if ( !v23 )
    {
      v7 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 555, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          14,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          5316,
          "int_VpnProfileCopyNrptRules");
    }
    v24 = *((_QWORD *)a3 + 1);
    if ( !v24 )
    {
      v7 = 14;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 556, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
      }
      if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        return v7;
      v10 = 5318;
LABEL_18:
      TraceVpnWppErrorW32Impl(
        14,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        v10,
        "int_VpnProfileCopyNrptRules");
      return v7;
    }
    v25 = *((_QWORD *)a2 + 12);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        557,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        *((unsigned int *)a2 + 22));
    }
    v26 = *((_DWORD *)a2 + 22);
    v27 = 0;
    LODWORD(v49) = 0;
    if ( !v26 )
    {
LABEL_135:
      *(_DWORD *)v54 = v26;
      return v7;
    }
    for ( i = v50; ; i = v50 )
    {
      v29 = UuidCreate(&Uuid);
      if ( v29 && v29 != 1824 )
        return 87;
      int_StringFromGUID(&Uuid, v56, v30);
      if ( *(_DWORD *)(v25 + 28) )
        break;
      v11 = VpnStringBuild(&v51, v52, v56, 0);
      if ( v11 >= 0 )
        goto LABEL_85;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 559, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v11);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      {
        v31 = 5346;
LABEL_80:
        TraceVpnWppErrorHRImpl(
          (unsigned int)v11,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          v31,
          "int_VpnProfileCopyNrptRules");
      }
LABEL_81:
      v32 = v11 & 0x1FFF0000;
      if ( (v11 & 0x1FFF0000) == 0x70000 )
      {
        v33 = (unsigned __int16)v11;
        v32 = 458752;
      }
      else
      {
        v33 = v11;
      }
      v14 = (unsigned __int16)v11;
      if ( v33 )
      {
        v15 = v32 == 458752;
        goto LABEL_30;
      }
LABEL_85:
      *(_QWORD *)(v24 + 48) = v51;
      *(_DWORD *)(v24 + 28) = *(_DWORD *)(v25 + 28);
      *(_DWORD *)(v24 + 24) = *(_DWORD *)(v25 + 24);
      v34 = *(_DWORD *)(v25 + 12);
      *(_DWORD *)(v24 + 12) = v34;
      if ( v34 )
      {
        v35 = (unsigned int)(20 * v34);
        v36 = VpnAlloc(v35);
        *(_QWORD *)(v24 + 32) = v36;
        if ( !v36 )
        {
          v7 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 560, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
          }
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
            TraceVpnWppErrorW32Impl(
              14,
              L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
              5363,
              "int_VpnProfileCopyNrptRules");
        }
        v37 = *(void **)(v24 + 32);
        if ( !v37 )
        {
          v7 = 14;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 561, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
          }
          if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          {
            v10 = 5365;
            goto LABEL_18;
          }
          return v7;
        }
        memcpy_0(v37, *(const void **)(v25 + 32), v35);
      }
      else
      {
        *(_QWORD *)(v24 + 32) = 0;
      }
      v38 = (_QWORD *)(v24 + 40);
      *(_DWORD *)(v24 + 16) = *(_DWORD *)(v25 + 16);
      v11 = VpnStringCopy(*(void **)(v25 + 40));
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Flink,
            562,
            &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
            (unsigned int)v11);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorHRImpl(
            (unsigned int)v11,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            5376,
            "int_VpnProfileCopyNrptRules");
        v39 = v11 & 0x1FFF0000;
        if ( (v11 & 0x1FFF0000) == 0x70000 )
        {
          v40 = (unsigned __int16)v11;
          v39 = 458752;
        }
        else
        {
          v40 = v11;
        }
        if ( v40 )
        {
          if ( v39 == 458752 )
            v11 = (unsigned __int16)v11;
          v16 = "VpnStringCopy NRPT rule DnsSuffix";
          goto LABEL_33;
        }
      }
      v41 = (_WORD *)*v38;
      if ( *(_WORD *)*v38 )
      {
        do
        {
          v42 = (unsigned int)v5;
          v43 = tolower((unsigned __int16)v41[(unsigned int)v5]);
          v5 = (unsigned int)(v5 + 1);
          *(_WORD *)(*v38 + 2 * v42) = v43;
          v41 = (_WORD *)*v38;
        }
        while ( *(_WORD *)(*v38 + 2 * v5) );
        v27 = v49;
        LODWORD(v5) = 0;
      }
      *(_DWORD *)(v24 + 20) = *(_DWORD *)(v25 + 20);
      v11 = VpnStringCopy(*(void **)(v25 + 56));
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Flink,
            563,
            &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
            (unsigned int)v11);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorHRImpl(
            (unsigned int)v11,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            5388,
            "int_VpnProfileCopyNrptRules");
        v44 = v11 & 0x1FFF0000;
        if ( (v11 & 0x1FFF0000) == 0x70000 )
        {
          v45 = (unsigned __int16)v11;
          v44 = 458752;
        }
        else
        {
          v45 = v11;
        }
        if ( v45 )
        {
          if ( v44 == 458752 )
            v11 = (unsigned __int16)v11;
          v16 = "VpnStringCopy NRPT rule ProxyName";
          goto LABEL_33;
        }
      }
      v46 = v53;
      v47 = 0;
      if ( v27 != *((_DWORD *)v53 + 22) - 1 )
        v47 = v24 + 64;
      ++v27;
      *(_QWORD *)v24 = v47;
      v25 += 64;
      v26 = *((_DWORD *)v46 + 22);
      v24 = v47;
      LODWORD(v49) = v27;
      if ( v27 >= v26 )
        goto LABEL_135;
    }
    v11 = VpnStringBuild(&v51, i, v56, 0);
    if ( v11 >= 0 )
      goto LABEL_85;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 558, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v11);
    }
    if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_81;
    v31 = 5340;
    goto LABEL_80;
  }
  v15 = v12 == 7;
LABEL_30:
  if ( v15 )
    v11 = v14;
  v16 = "VpnStringBuild";
LABEL_33:
  VpnReportError("int_VpnProfileCopyNrptRules", v16, (unsigned int)v11);
  return v7;
}

```

## disassembly

```asm
0x1800d77e0  mov     [rsp-8+arg_18], rbx
0x1800d77e5  push    rbp
0x1800d77e6  push    rsi
0x1800d77e7  push    rdi
0x1800d77e8  push    r12
0x1800d77ea  push    r13
0x1800d77ec  push    r14
0x1800d77ee  push    r15
0x1800d77f0  lea     rbp, [rsp-27h]
0x1800d77f5  sub     rsp, 0D0h
0x1800d77fc  mov     rax, cs:__security_cookie
0x1800d7803  xor     rax, rsp
0x1800d7806  mov     [rbp+57h+var_40], rax
0x1800d780a  mov     rsi, r8
0x1800d780d  mov     [rbp+57h+var_A8], r8
0x1800d7811  mov     r14, rdx
0x1800d7814  mov     [rbp+57h+var_B0], rdx
0x1800d7818  mov     rdi, rcx
0x1800d781b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7822  lea     rbx, WPP_GLOBAL_Control
0x1800d7829  xor     r12d, r12d
0x1800d782c  cmp     rcx, rbx
0x1800d782f  jz      short loc_1800D785D
0x1800d7831  test    byte ptr [rcx+1Ch], 8
0x1800d7835  jz      short loc_1800D785D
0x1800d7837  mov     rcx, [rcx+10h]
0x1800d783b  lea     rax, aNull_5; "<NULL>"
0x1800d7842  test    rdi, rdi
0x1800d7845  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d784c  mov     r9, rdi
0x1800d784f  mov     edx, 226h
0x1800d7854  cmovz   r9, rax
0x1800d7858  call    WPP_SF_S
0x1800d785d  xor     edx, edx; Val
0x1800d785f  mov     [rbp+57h+var_D0], r12
0x1800d7863  xorps   xmm0, xmm0
0x1800d7866  mov     [rbp+57h+var_C8], r12
0x1800d786a  lea     rcx, [rbp+57h+var_90]; void *
0x1800d786e  mov     [rbp+57h+var_C0], r12
0x1800d7872  mov     r15d, r12d
0x1800d7875  lea     r8d, [rdx+4Ah]; Size
0x1800d7879  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x1800d787d  call    memset_0
0x1800d7882  call    cs:__imp_GetProcessHeap
0x1800d7888  mov     edx, 8; dwFlags
0x1800d788d  mov     rcx, rax; hHeap
0x1800d7890  lea     r8d, [rdx+38h]; dwBytes
0x1800d7894  call    cs:__imp_HeapAlloc
0x1800d789a  mov     [rsi+10h], rax
0x1800d789e  mov     r13d, 0Eh
0x1800d78a4  test    rax, rax
0x1800d78a7  jnz     short loc_1800D7902
0x1800d78a9  mov     r15d, r13d
0x1800d78ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d78b3  cmp     rcx, rbx
0x1800d78b6  jz      short loc_1800D78D6
0x1800d78b8  test    byte ptr [rcx+1Ch], 1
0x1800d78bc  jz      short loc_1800D78D6
0x1800d78be  mov     rcx, [rcx+10h]
0x1800d78c2  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d78c9  mov     edx, 227h
0x1800d78ce  mov     r9d, r13d
0x1800d78d1  call    WPP_SF_d
0x1800d78d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d78dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d78e2  test    al, al
0x1800d78e4  jz      short loc_1800D7902
0x1800d78e6  lea     r9, aIntVpnprofilec_1; "int_VpnProfileCopyNrptRules"
0x1800d78ed  mov     r8d, 14AFh
0x1800d78f3  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d78fa  mov     ecx, r13d
0x1800d78fd  call    TraceVpnWppErrorW32Impl
0x1800d7902  cmp     [rsi+10h], r12
0x1800d7906  jnz     short loc_1800D796A
0x1800d7908  mov     r15d, r13d
0x1800d790b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7912  cmp     rcx, rbx
0x1800d7915  jz      short loc_1800D7935
0x1800d7917  test    byte ptr [rcx+1Ch], 1
0x1800d791b  jz      short loc_1800D7935
0x1800d791d  mov     rcx, [rcx+10h]
0x1800d7921  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d7928  mov     edx, 228h
0x1800d792d  mov     r9d, r13d
0x1800d7930  call    WPP_SF_d
0x1800d7935  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d793c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d7941  test    al, al
0x1800d7943  jz      loc_1800D80BA
0x1800d7949  mov     r8d, 14B1h
0x1800d794f  mov     ecx, r13d
0x1800d7952  lea     r9, aIntVpnprofilec_1; "int_VpnProfileCopyNrptRules"
0x1800d7959  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d7960  call    TraceVpnWppErrorW32Impl
0x1800d7965  jmp     loc_1800D80BA
0x1800d796a  lea     r9, asc_1800FB984; "_"
0x1800d7971  mov     [rsp+100h+var_E0], r12
0x1800d7976  mov     r8, rdi
0x1800d7979  lea     rdx, aVpnAuto; "VPN_AUTO_"
0x1800d7980  lea     rcx, [rbp+57h+var_D0]
0x1800d7984  call    VpnStringBuild
0x1800d7989  mov     ebx, eax
0x1800d798b  test    eax, eax
0x1800d798d  jns     loc_1800D7A2F
0x1800d7993  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d799a  lea     rax, WPP_GLOBAL_Control
0x1800d79a1  cmp     rcx, rax
0x1800d79a4  jz      short loc_1800D79C4
0x1800d79a6  test    byte ptr [rcx+1Ch], 1
0x1800d79aa  jz      short loc_1800D79C4
0x1800d79ac  mov     rcx, [rcx+10h]
0x1800d79b0  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d79b7  mov     edx, 229h
0x1800d79bc  mov     r9d, ebx
0x1800d79bf  call    WPP_SF_d
0x1800d79c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d79cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d79d0  test    al, al
0x1800d79d2  jz      short loc_1800D79EF
0x1800d79d4  lea     r9, aIntVpnprofilec_1; "int_VpnProfileCopyNrptRules"
0x1800d79db  mov     r8d, 14B4h
0x1800d79e1  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d79e8  mov     ecx, ebx
0x1800d79ea  call    TraceVpnWppErrorHRImpl
0x1800d79ef  mov     eax, ebx
0x1800d79f1  sar     eax, 10h
0x1800d79f4  and     eax, 1FFFh
0x1800d79f9  cmp     eax, 7
0x1800d79fc  jnz     short loc_1800D7A05
0x1800d79fe  movzx   ecx, bx
0x1800d7a01  mov     edx, ecx
0x1800d7a03  jmp     short loc_1800D7A0A
0x1800d7a05  mov     ecx, ebx
0x1800d7a07  movzx   edx, bx
0x1800d7a0a  test    ecx, ecx
0x1800d7a0c  jz      short loc_1800D7A2F
0x1800d7a0e  cmp     eax, 7
0x1800d7a11  cmovz   ebx, edx
0x1800d7a14  lea     rdx, aVpnstringbuild_3; "VpnStringBuild"
0x1800d7a1b  mov     r8d, ebx
0x1800d7a1e  lea     rcx, aIntVpnprofilec_1; "int_VpnProfileCopyNrptRules"
0x1800d7a25  call    VpnReportError
0x1800d7a2a  jmp     loc_1800D8058
0x1800d7a2f  mov     rcx, [rbp+57h+var_D0]
0x1800d7a33  lea     r9, asc_1800FB984; "_"
0x1800d7a3a  mov     rax, [rsi+10h]
0x1800d7a3e  lea     rdx, aVpnPersistent; "VPN_PERSISTENT_"
0x1800d7a45  mov     [rbp+57h+var_B8], rcx
0x1800d7a49  mov     r8, rdi
0x1800d7a4c  mov     [rsp+100h+var_E0], r12
0x1800d7a51  mov     [rax+30h], rcx
0x1800d7a55  lea     rcx, [rbp+57h+var_C8]
0x1800d7a59  call    VpnStringBuild
0x1800d7a5e  xor     edi, edi
0x1800d7a60  mov     ebx, eax
0x1800d7a62  test    eax, eax
0x1800d7a64  jns     loc_1800D7B06
0x1800d7a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7a71  lea     r12, WPP_GLOBAL_Control
0x1800d7a78  cmp     rcx, r12
0x1800d7a7b  jz      short loc_1800D7A9B
0x1800d7a7d  test    byte ptr [rcx+1Ch], 1
0x1800d7a81  jz      short loc_1800D7A9B
0x1800d7a83  mov     rcx, [rcx+10h]
0x1800d7a87  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d7a8e  mov     edx, 22Ah
0x1800d7a93  mov     r9d, eax
0x1800d7a96  call    WPP_SF_d
0x1800d7a9b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d7aa2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d7aa7  test    al, al
0x1800d7aa9  jz      short loc_1800D7AC6
0x1800d7aab  lea     r9, aIntVpnprofilec_1; "int_VpnProfileCopyNrptRules"
0x1800d7ab2  mov     r8d, 14BAh
0x1800d7ab8  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d7abf  mov     ecx, ebx
0x1800d7ac1  call    TraceVpnWppErrorHRImpl
0x1800d7ac6  mov     eax, ebx
0x1800d7ac8  sar     eax, 10h
0x1800d7acb  and     eax, 1FFFh
0x1800d7ad0  cmp     eax, 7
0x1800d7ad3  jnz     short loc_1800D7ADC
0x1800d7ad5  movzx   ecx, bx
0x1800d7ad8  mov     edx, ecx
0x1800d7ada  jmp     short loc_1800D7AE1
0x1800d7adc  mov     ecx, ebx
0x1800d7ade  movzx   edx, bx
0x1800d7ae1  test    ecx, ecx
0x1800d7ae3  jz      short loc_1800D7B0D
0x1800d7ae5  cmp     eax, 7
0x1800d7ae8  lea     rcx, aIntVpnprofilec_1; "int_VpnProfileCopyNrptRules"
0x1800d7aef  cmovz   ebx, edx
0x1800d7af2  lea     rdx, aVpnstringbuild_3; "VpnStringBuild"
0x1800d7af9  mov     r8d, ebx
0x1800d7afc  call    VpnReportError
0x1800d7b01  jmp     loc_1800D805F
0x1800d7b06  lea     r12, WPP_GLOBAL_Control
0x1800d7b0d  mov     eax, [r14+58h]
0x1800d7b11  test    eax, eax
0x1800d7b13  jz      loc_1800D8058
0x1800d7b19  shl     eax, 6
0x1800d7b1c  mov     ecx, eax
0x1800d7b1e  call    VpnAlloc
0x1800d7b23  mov     [rsi+8], rax
0x1800d7b27  test    rax, rax
0x1800d7b2a  jnz     short loc_1800D7B85
0x1800d7b2c  mov     r15d, r13d
0x1800d7b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7b36  cmp     rcx, r12
0x1800d7b39  jz      short loc_1800D7B59
0x1800d7b3b  test    byte ptr [rcx+1Ch], 1
0x1800d7b3f  jz      short loc_1800D7B59
0x1800d7b41  mov     rcx, [rcx+10h]
0x1800d7b45  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d7b4c  mov     edx, 22Bh
0x1800d7b51  mov     r9d, r13d
0x1800d7b54  call    WPP_SF_d
0x1800d7b59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d7b60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d7b65  test    al, al
0x1800d7b67  jz      short loc_1800D7B85
0x1800d7b69  lea     r9, aIntVpnprofilec_1; "int_VpnProfileCopyNrptRules"
0x1800d7b70  mov     r8d, 14C4h
0x1800d7b76  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d7b7d  mov     ecx, r13d
0x1800d7b80  call    TraceVpnWppErrorW32Impl
0x1800d7b85  mov     rsi, [rsi+8]
0x1800d7b89  test    rsi, rsi
0x1800d7b8c  jnz     short loc_1800D7BDA
0x1800d7b8e  mov     r15d, r13d
0x1800d7b91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7b98  cmp     rcx, r12
0x1800d7b9b  jz      short loc_1800D7BBB
0x1800d7b9d  test    byte ptr [rcx+1Ch], 1
0x1800d7ba1  jz      short loc_1800D7BBB
0x1800d7ba3  mov     rcx, [rcx+10h]
0x1800d7ba7  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d7bae  mov     edx, 22Ch
0x1800d7bb3  mov     r9d, r13d
0x1800d7bb6  call    WPP_SF_d
0x1800d7bbb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d7bc2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d7bc7  test    al, al
0x1800d7bc9  jz      loc_1800D80BA
0x1800d7bcf  mov     r8d, 14C6h
0x1800d7bd5  jmp     loc_1800D794F
0x1800d7bda  mov     r13, [r14+60h]
0x1800d7bde  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7be5  cmp     rcx, r12
0x1800d7be8  jz      short loc_1800D7C09
0x1800d7bea  test    byte ptr [rcx+1Ch], 4
0x1800d7bee  jz      short loc_1800D7C09
0x1800d7bf0  mov     r9d, [r14+58h]
0x1800d7bf4  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d7bfb  mov     rcx, [rcx+10h]
0x1800d7bff  mov     edx, 22Dh
0x1800d7c04  call    WPP_SF_d
0x1800d7c09  mov     eax, [r14+58h]
0x1800d7c0d  mov     r12d, edi
0x1800d7c10  mov     dword ptr [rbp+57h+var_D0], edi
0x1800d7c13  test    eax, eax
0x1800d7c15  jz      loc_1800D8052
0x1800d7c1b  mov     rbx, [rbp+57h+var_C8]
0x1800d7c1f  mov     [rbp+57h+var_C8], rbx
0x1800d7c23  lea     rcx, [rbp+57h+Uuid]; Uuid
0x1800d7c27  mov     r14d, 70000h
0x1800d7c2d  call    cs:__imp_UuidCreate
0x1800d7c33  test    eax, eax
0x1800d7c35  jz      short loc_1800D7C42
0x1800d7c37  cmp     eax, 720h
0x1800d7c3c  jnz     loc_1800D7FC5
0x1800d7c42  lea     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x1800d7c46  lea     rcx, [rbp+57h+Uuid]; struct _GUID *
0x1800d7c4a  call    ?int_StringFromGUID@@YAXAEAU_GUID@@PEAGK@Z; int_StringFromGUID(_GUID &,ushort *,ulong)
0x1800d7c4f  xor     r9d, r9d
0x1800d7c52  lea     r8, [rbp+57h+var_90]
0x1800d7c56  lea     rcx, [rbp+57h+var_C0]
0x1800d7c5a  cmp     [r13+1Ch], edi
0x1800d7c5e  jz      short loc_1800D7CBB
0x1800d7c60  mov     rdx, rbx
0x1800d7c63  call    VpnStringBuild
0x1800d7c68  mov     ebx, eax
0x1800d7c6a  test    eax, eax
0x1800d7c6c  jns     loc_1800D7D49
0x1800d7c72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d7c79  lea     rax, WPP_GLOBAL_Control
0x1800d7c80  cmp     rcx, rax
0x1800d7c83  jz      short loc_1800D7CA3
0x1800d7c85  test    byte ptr [rcx+1Ch], 1
0x1800d7c89  jz      short loc_1800D7CA3
0x1800d7c8b  mov     rcx, [rcx+10h]
0x1800d7c8f  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d7c96  mov     edx, 22Eh
0x1800d7c9b  mov     r9d, ebx
0x1800d7c9e  call    WPP_SF_d
0x1800d7ca3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d7caa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d7caf  test    al, al
0x1800d7cb1  jz      short loc_1800D7D26
0x1800d7cb3  mov     r8d, 14DCh
  ... truncated ...
```
