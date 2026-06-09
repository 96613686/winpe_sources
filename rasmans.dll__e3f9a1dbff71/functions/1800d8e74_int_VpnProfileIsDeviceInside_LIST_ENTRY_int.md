# int_VpnProfileIsDeviceInside(_LIST_ENTRY *,int)

- ea: `0x1800d8e74`
- end: `0x1800d9ce9`
- name: `?int_VpnProfileIsDeviceInside@@YAHPEAU_LIST_ENTRY@@H@Z`
- size: `3701`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, unsigned int, __int64, __int64)`
- caller_count: `6`
- callee_count: `31`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c9f1c`
- `0x1800cd9ac`
- `0x1800d26c0`
- `0x1800d29ec`
- `0x1800d3430`
- `0x1800d34e0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bf38`
- `0x18000bf70`
- `0x18000e5f0`
- `0x1800593d0`
- `0x180065328`
- `0x1800b81fc`
- `0x1800bda40`
- `0x1800bf530`
- `0x1800c03fc`
- `0x1800cacf8`
- `0x1800cae38`
- `0x1800caed8`
- `0x1800cb8dc`
- `0x1800cbf38`
- `0x1800d2344`
- `0x1800d8b6c`
- `0x1800d8e74`
- `0x1800dab4c`
- `0x1800daba4`
- `0x1800db0ac`
- `0x1800dde2c`
- `0x1800e0ab4`
- `0x1800e0e9c`
- `0x1800e1cd8`
- `0x1800e1d04`
- `0x1800e2900`
- `0x1800e2dbc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800d95d1`
- `msvcrt!_wcsicmp` at `0x1800d95fc`
- `msvcrt!_wcsicmp` at `0x1800d95d1`
- `msvcrt!_wcsicmp` at `0x1800d95fc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d938c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800d938c`

## string_xrefs

- `0x1800d9401`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d9a09`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d9a86`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d9c38`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d93f4`: `int_VpnProfileIsDeviceInside`
- `0x1800d99fc`: `int_VpnProfileIsDeviceInside`
- `0x1800d9a79`: `int_VpnProfileIsDeviceInside`
- `0x1800d9c2b`: `int_VpnProfileIsDeviceInside`

## pseudocode

```c
__int64 __fastcall int_VpnProfileIsDeviceInside(struct _LIST_ENTRY *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  int v4; // ebx
  unsigned int v6; // r12d
  int v7; // ebx
  LPCWSTR *v8; // r14
  LPCWSTR v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  int v13; // ecx
  unsigned int v14; // ebx
  int v15; // esi
  __int64 v16; // rcx
  wchar_t *v17; // rdx
  int IsSuffix; // eax
  int v19; // ecx
  LPCWSTR v20; // rdx
  __int64 v21; // r8
  __int64 Flink_low; // r9
  struct _LIST_ENTRY *v23; // r10
  struct _LIST_ENTRY *Flink; // rbx
  int v25; // r15d
  const wchar_t *v26; // rax
  __int64 Blink; // rsi
  int i; // r14d
  struct _LIST_ENTRY *v29; // rbx
  struct _LIST_ENTRY *v30; // r15
  struct _LIST_ENTRY *v31; // rsi
  unsigned int v32; // r14d
  unsigned int v33; // esi
  struct _LIST_ENTRY *v34; // rsi
  int v35; // r13d
  const wchar_t *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  int v39; // r8d
  LPCWSTR v40; // rcx
  const wchar_t *v41; // rdx
  const wchar_t *v42; // r9
  const wchar_t *v43; // rcx
  struct _LIST_ENTRY *v44; // r10
  unsigned int v45; // r15d
  int v46; // r9d
  const wchar_t *v47; // rdx
  const wchar_t *v48; // r8
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  unsigned int v52; // edi
  unsigned int v53; // ebx
  __int64 v54; // r8
  __int64 v55; // r9
  struct _LIST_ENTRY *v56; // rcx
  bool v57; // zf
  unsigned int v58; // eax
  unsigned int v59; // ebx
  __int64 v60; // r9
  int v62; // [rsp+20h] [rbp-E0h]
  int v64; // [rsp+44h] [rbp-BCh]
  unsigned int v65; // [rsp+48h] [rbp-B8h]
  int v66; // [rsp+4Ch] [rbp-B4h] BYREF
  int v67; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR *v68; // [rsp+58h] [rbp-A8h]
  GUID pInterfaceGuid; // [rsp+60h] [rbp-A0h] BYREF
  GUID pclsid; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v71; // [rsp+90h] [rbp-70h]
  int v72; // [rsp+98h] [rbp-68h]
  int v73; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v74; // [rsp+A0h] [rbp-60h]
  int v75; // [rsp+A8h] [rbp-58h]
  int v76; // [rsp+ACh] [rbp-54h]
  wchar_t String2[264]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(a4) = a2 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 465, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, a4);
  }
  v66 = 0;
  v67 = 0;
  v6 = 0;
  memset_0(String2, 0, 0x202u);
  pclsid = 0;
  VpnCriticalSectionEnter(&g_LpCriticalSection);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup>::GetImpl'::`2'::impl)
    && dword_18010E210 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 466, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    v7 = 11;
    goto LABEL_237;
  }
  v65 = 0;
  v64 = 0;
  v8 = &g_ActiveUserProfile;
  if ( !v4 )
    v8 = &g_ActiveDeviceProfile;
  v68 = v8;
  v9 = v8[74];
  if ( v9 )
  {
    v10 = qword_18010E480;
    v11 = qword_18010E220;
    v12 = qword_18010E480;
    if ( !v4 )
      v12 = qword_18010E220;
    if ( v12 )
    {
      v13 = *((_DWORD *)v9 + 16);
      if ( v13 == *(_DWORD *)(v12 + 64) )
      {
        v14 = 0;
        v15 = 1;
        v64 = 1;
        v65 = 0;
        if ( v13 )
        {
          while ( 1 )
          {
            v16 = 520LL * v14;
            v17 = (wchar_t *)(v16 + *((_QWORD *)v9 + 9));
            if ( !a2 )
              v10 = v11;
            IsSuffix = int_IsSuffix((wchar_t *)(*(_QWORD *)(v10 + 72) + v16), v17);
            v9 = v8[74];
            ++v14;
            v19 = IsSuffix != 0 ? v15 : 0;
            v15 = v19;
            if ( v14 >= *((_DWORD *)v9 + 16) )
              break;
            v11 = qword_18010E220;
            v10 = qword_18010E480;
          }
          v65 = v14;
          v4 = a2;
          v64 = v19;
        }
        else
        {
          v4 = a2;
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 467, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  DumpActiveProfileInfo(v4 != 0);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        468,
        &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        g_deviceLastPowerState);
      v23 = WPP_GLOBAL_Control;
    }
    if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
    {
      WPP_SF_(v23[1].Flink, 469, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      v23 = WPP_GLOBAL_Control;
    }
  }
  if ( v8[74] )
  {
    if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
    {
      LOBYTE(Flink_low) = g_fIsInside != 0;
      WPP_SF_c(v23[1].Flink, 470, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, Flink_low);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix>::GetImpl'::`2'::impl) )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 471, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
        v23 = WPP_GLOBAL_Control;
      }
      Flink = a1->Flink;
      if ( a1->Flink == a1 )
      {
        if ( v23 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_77;
        if ( (BYTE4(v23[1].Blink) & 4) != 0 )
        {
          WPP_SF_(v23[1].Flink, 479, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
          v23 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        v25 = 0;
        do
        {
          if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( (BYTE4(v23[1].Blink) & 4) != 0 )
            {
              v26 = L"(null)";
              if ( Flink[1].Flink )
                v26 = (const wchar_t *)Flink[1].Flink;
              WPP_SF_LS(v23[1].Flink, 472, v21, v25, (__int64)v26);
              v23 = WPP_GLOBAL_Control;
            }
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
              if ( (BYTE4(v23[1].Blink) & 4) != 0 )
              {
                WPP_SF_d(v23[1].Flink, 473, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, HIDWORD(Flink[1].Blink));
                v23 = WPP_GLOBAL_Control;
              }
              if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
                if ( (BYTE4(v23[1].Blink) & 4) != 0 )
                {
                  WPP_SF_d(v23[1].Flink, 474, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LODWORD(Flink[1].Blink));
                  v23 = WPP_GLOBAL_Control;
                }
                if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                {
                  if ( (BYTE4(v23[1].Blink) & 4) != 0 )
                  {
                    WPP_SF_d(
                      v23[1].Flink,
                      475,
                      &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                      LODWORD(Flink[3].Flink));
                    v23 = WPP_GLOBAL_Control;
                  }
                  if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
                  {
                    WPP_SF__guid_(v23[1].Flink, 476, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, &Flink[2]);
                    v23 = WPP_GLOBAL_Control;
                  }
                }
              }
            }
          }
          Blink = (__int64)Flink[3].Blink;
          for ( i = 0; Blink; ++i )
          {
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
              if ( (BYTE4(v23[1].Blink) & 4) != 0 )
              {
                WPP_SF_LS(v23[1].Flink, 477, v21, i, Blink);
                v23 = WPP_GLOBAL_Control;
              }
              if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
              {
                WPP_SF__guid_(v23[1].Flink, 478, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, Blink + 520);
                v23 = WPP_GLOBAL_Control;
              }
            }
            Blink = *(_QWORD *)(Blink + 536);
          }
          Flink = Flink->Flink;
          ++v25;
        }
        while ( Flink != a1 );
        v6 = v66;
      }
      if ( v23 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v23[1].Blink) & 4) == 0 )
      {
LABEL_77:
        v29 = a1->Flink;
        if ( a1->Flink == a1 )
        {
          v7 = 3;
          if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
            WPP_SF_(v23[1].Flink, 481, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
          v6 = g_fIsInside;
          goto LABEL_237;
        }
        while ( 1 )
        {
          v66 = 0;
          v30 = v29;
          v31 = v29[3].Blink;
          if ( v31 )
          {
            while ( 1 )
            {
              CLSIDFromString((LPCOLESTR)v31, &pclsid);
              pInterfaceGuid = pclsid;
              v32 = int_ConnectedToMdmProvisionedWifi(&pInterfaceGuid, &v66);
              if ( v32 )
              {
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 482, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v32);
                }
                if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
                  TraceVpnWppErrorW32Impl(
                    v32,
                    L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
                    4562,
                    "int_VpnProfileIsDeviceInside");
              }
              if ( v66 )
                break;
              v31 = v31[33].Blink;
              if ( !v31 )
              {
                v23 = WPP_GLOBAL_Control;
                goto LABEL_92;
              }
            }
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 483, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
              v23 = WPP_GLOBAL_Control;
            }
            v33 = 0;
          }
          else
          {
LABEL_92:
            v33 = 0;
            if ( !HIDWORD(v29[1].Blink) )
            {
              if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
              {
                WPP_SF_S(v23[1].Flink, 484, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v29[1].Flink);
                v23 = WPP_GLOBAL_Control;
              }
              v8 = v68;
              goto LABEL_110;
            }
          }
          if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
          {
            WPP_SF_(v23[1].Flink, 485, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
            v23 = WPP_GLOBAL_Control;
          }
          v8 = v68;
          v65 = 0;
          v20 = v68[74];
          if ( *((_DWORD *)v20 + 16) )
          {
            while ( 1 )
            {
              if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
                WPP_SF_SS(
                  v23[1].Flink,
                  486,
                  (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
                  v29[1].Flink,
                  *((_QWORD *)v20 + 9) + 520LL * v33);
              if ( (unsigned int)int_IsSuffix(
                                   (wchar_t *)v29[1].Flink,
                                   (wchar_t *)(*((_QWORD *)v8[74] + 9) + 520LL * v33)) )
                break;
              v20 = v8[74];
              ++v33;
              v23 = WPP_GLOBAL_Control;
              v65 = v33;
              if ( v33 >= *((_DWORD *)v20 + 16) )
                goto LABEL_110;
            }
            v34 = v29[3].Blink;
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
            {
              WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 487, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v29[1].Flink);
              v23 = WPP_GLOBAL_Control;
            }
            v35 = v64;
            if ( v34 )
            {
              while ( 1 )
              {
                int_VpnProfileGetInterfaceName((unsigned __int16 *)v34, String2);
                if ( !_wcsicmp(v8[1], String2) )
                  break;
                if ( v64 )
                {
                  v36 = qword_18010E238;
                  if ( !a2 )
                    v36 = qword_18010DFD8;
                  if ( !_wcsicmp(v36, String2) )
                    break;
                }
                v34 = v34[33].Blink;
                if ( !v34 )
                {
                  v23 = WPP_GLOBAL_Control;
                  goto LABEL_123;
                }
              }
              Flink_low = LODWORD(v29[3].Flink);
              if ( v64 )
              {
                if ( (unsigned int)Flink_low > 2 )
                  goto LABEL_135;
LABEL_137:
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
                {
                  v37 = 489;
LABEL_126:
                  WPP_SF_d(v23[1].Flink, v37, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, Flink_low);
                  v23 = WPP_GLOBAL_Control;
                }
                goto LABEL_127;
              }
              if ( (_DWORD)Flink_low == 1 )
                goto LABEL_137;
LABEL_135:
              v23 = WPP_GLOBAL_Control;
            }
LABEL_123:
            v6 = 1;
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
            {
              Flink_low = LODWORD(v29[3].Flink);
              v37 = 488;
              goto LABEL_126;
            }
LABEL_127:
            if ( g_fBypassTrustedNetworkCheck )
            {
              if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
              {
                WPP_SF_(v23[1].Flink, 490, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
                v23 = WPP_GLOBAL_Control;
              }
              v6 = 0;
            }
            v4 = a2;
LABEL_145:
            if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v23[1].Blink) & 4) != 0 )
            {
              LOBYTE(Flink_low) = v6;
              WPP_SF_cd(v23[1].Flink, v20, v21, Flink_low, g_deviceLastPowerState);
            }
            goto LABEL_149;
          }
LABEL_110:
          v29 = v29->Flink;
          if ( v29 == a1 )
          {
            v4 = a2;
            goto LABEL_144;
          }
        }
      }
      WPP_SF_(v23[1].Flink, 480, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    }
    v23 = WPP_GLOBAL_Control;
    goto LABEL_77;
  }
  v30 = 0;
  if ( v23 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(v23[1].Blink) & 4) != 0 )
    {
      WPP_SF_(v23[1].Flink, 491, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      v23 = WPP_GLOBAL_Control;
    }
LABEL_144:
    v35 = v64;
    goto LABEL_145;
  }
  v35 = v64;
LABEL_149:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
  {
    if ( v6 && (v40 = v8[74]) != 0 && v65 < *((_DWORD *)v40 + 16) )
    {
      v41 = (const wchar_t *)(*((_QWORD *)v40 + 9) + 520LL * v65);
    }
    else
    {
      v41 = L"<None>";
      if ( !v6 )
      {
LABEL_157:
        v42 = L"<None>";
LABEL_158:
        v43 = L"<Unknown>";
        if ( v8[1] )
          v43 = v8[1];
        TraceNlmInsideOutsideDetectionImpl((_DWORD)v43, v6, v39, (_DWORD)v42, (__int64)v41);
        goto LABEL_161;
      }
    }
    if ( v30 )
    {
      v42 = (const wchar_t *)v30[1].Flink;
      if ( v42 )
        goto LABEL_158;
    }
    goto LABEL_157;
  }
LABEL_161:
  if ( !v8[74] )
  {
    if ( g_deviceLastPowerState != 1 )
    {
      v7 = 7;
      goto LABEL_237;
    }
    goto LABEL_235;
  }
  if ( g_deviceLastPowerState == 1 )
  {
LABEL_235:
    v7 = 9;
    goto LABEL_237;
  }
  v44 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 493, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    v44 = WPP_GLOBAL_Control;
  }
  if ( g_fIsInside )
  {
    if ( v6 )
    {
LABEL_202:
      v7 = 8 * v6;
LABEL_237:
      AddVPNCanceledEvent(v7, a2);
      goto LABEL_238;
    }
  }
  else if ( v6 )
  {
    if ( v44 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v44[1].Blink) & 4) != 0 )
    {
      LOBYTE(v62) = v6;
      WPP_SF_cc(v44[1].Flink, 494, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 0, v62);
      v44 = WPP_GLOBAL_Control;
    }
    g_fIsInside = v6;
    if ( v44 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v44[1].Blink) & 4) != 0 )
    {
      WPP_SF_(v44[1].Flink, 495, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
      v44 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    {
      v45 = v65;
      v46 = 10;
      v47 = v8[1];
      v48 = (const wchar_t *)(*((_QWORD *)v8[74] + 9) + 520LL * v65);
      v49 = -1;
      if ( v47 )
      {
        v50 = -1;
        do
          ++v50;
        while ( v47[v50] );
        v51 = (unsigned int)(2 * v50 + 2);
      }
      else
      {
        v47 = L"NULL";
        v51 = 10;
      }
      v71 = v47;
      v72 = v51;
      v73 = 0;
      if ( v48 )
      {
        do
          ++v49;
        while ( v48[v49] );
        v46 = 2 * v49 + 2;
      }
      else
      {
        v48 = L"NULL";
      }
      v75 = v46;
      v74 = v48;
      v76 = 0;
      McGenEventWrite_EventWriteTransfer(v51, VpnAutoTriggerInside, v48, 3);
      v44 = WPP_GLOBAL_Control;
    }
    else
    {
      v45 = v65;
    }
    if ( v44 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v44[1].Blink) & 4) != 0 )
      WPP_SF_SS(
        v44[1].Flink,
        496,
        (unsigned int)&WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
        (unsigned int)v8[1],
        *((_QWORD *)v8[74] + 9) + 520LL * v45);
    v52 = VpnProfileDeActivateAutoTrigger(1, a2);
    if ( v52 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 497, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v52);
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        TraceVpnWppErrorW32Impl(
          v52,
          L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
          4677,
          "int_VpnProfileIsDeviceInside");
    }
    if ( v35 )
    {
      v53 = VpnProfileDeActivateAutoTrigger(1, a2 == 0);
      if ( v53 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 498, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v53);
        }
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorW32Impl(
            v53,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            4683,
            "int_VpnProfileIsDeviceInside");
      }
    }
    goto LABEL_202;
  }
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v38, VpnAutoTriggerOutside, v8[1]);
    v44 = WPP_GLOBAL_Control;
  }
  if ( v44 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v44[1].Blink) & 4) != 0 )
    WPP_SF_S(v44[1].Flink, 499, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v8[1]);
  NlmHandlerCheckInternetConnectivity(&v67);
  if ( v4 )
  {
    v56 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      LOBYTE(v62) = g_IsActiveUserProfile != 0;
      LOBYTE(v55) = v67 != 0;
      WPP_SF_cc(WPP_GLOBAL_Control[1].Flink, 500, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v55, v62);
      v56 = WPP_GLOBAL_Control;
    }
    v57 = g_IsActiveUserProfile == 0;
  }
  else
  {
    v56 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      LOBYTE(v62) = g_IsActiveDeviceProfile != 0;
      LOBYTE(v55) = v67 != 0;
      WPP_SF_cc(WPP_GLOBAL_Control[1].Flink, 501, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v55, v62);
      v56 = WPP_GLOBAL_Control;
    }
    v57 = g_IsActiveDeviceProfile == 0;
  }
  if ( v57 )
  {
    g_fIsInside = v6;
    v7 = 6;
    goto LABEL_237;
  }
  g_fIsInside = v6;
  if ( *((_DWORD *)v8 + 144) )
  {
    if ( v56 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v56[1].Blink) & 4) != 0 )
      WPP_SF_(v56[1].Flink, 502, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
    v7 = 11;
    goto LABEL_237;
  }
  v58 = VpnProfileActivateAutoTrigger((__int64)v8, v4, v54, v55);
  v59 = v58;
  if ( v58 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 503, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v58);
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(
        v59,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        4728,
        "int_VpnProfileIsDeviceInside");
  }
  if ( a2 )
    int_AlwaysOnUserTunnelCallback();
  else
    int_AlwaysOnDeviceTunnelCallback();
LABEL_238:
  VpnCriticalSectionLeave(&g_LpCriticalSection);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    LOBYTE(v60) = v6 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 504, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v60);
  }
  return v6;
}

```

## disassembly

```asm
0x1800d8e74  mov     [rsp-8+arg_10], rbx
0x1800d8e79  push    rbp
0x1800d8e7a  push    rsi
0x1800d8e7b  push    rdi
0x1800d8e7c  push    r12
0x1800d8e7e  push    r13
0x1800d8e80  push    r14
0x1800d8e82  push    r15
0x1800d8e84  lea     rbp, [rsp-1D0h]
0x1800d8e8c  sub     rsp, 2D0h
0x1800d8e93  mov     rax, cs:__security_cookie
0x1800d8e9a  xor     rax, rsp
0x1800d8e9d  mov     [rbp+200h+var_40], rax
0x1800d8ea4  mov     ebx, edx
0x1800d8ea6  mov     [rsp+300h+var_2C0], edx
0x1800d8eaa  mov     r13, rcx
0x1800d8ead  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8eb4  lea     r14, WPP_GLOBAL_Control
0x1800d8ebb  xor     esi, esi
0x1800d8ebd  cmp     rcx, r14
0x1800d8ec0  jz      short loc_1800D8EE3
0x1800d8ec2  test    byte ptr [rcx+1Ch], 8
0x1800d8ec6  jz      short loc_1800D8EE3
0x1800d8ec8  mov     rcx, [rcx+10h]
0x1800d8ecc  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d8ed3  test    edx, edx
0x1800d8ed5  mov     edx, 1D1h
0x1800d8eda  setnz   r9b
0x1800d8ede  call    WPP_SF_c
0x1800d8ee3  xor     edx, edx; Val
0x1800d8ee5  mov     [rsp+300h+var_2B4], esi
0x1800d8ee9  mov     r8d, 202h; Size
0x1800d8eef  mov     [rsp+300h+var_2B0], esi
0x1800d8ef3  lea     rcx, [rbp+200h+String2]; void *
0x1800d8ef7  mov     r12d, esi
0x1800d8efa  call    memset_0
0x1800d8eff  xorps   xmm0, xmm0
0x1800d8f02  lea     rcx, ?g_LpCriticalSection@@3UVPN_CRITICAL_SECTION_@@A; VPN_CRITICAL_SECTION_ g_LpCriticalSection
0x1800d8f09  movups  xmmword ptr [rsp+300h+pclsid.Data1], xmm0
0x1800d8f0e  call    VpnCriticalSectionEnter
0x1800d8f13  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup>::GetImpl(void)'::`2'::impl
0x1800d8f1a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_VPN_LowPowerCleanup>::__private_IsEnabled(void)
0x1800d8f1f  test    al, al
0x1800d8f21  jz      short loc_1800D8F5F
0x1800d8f23  cmp     cs:dword_18010E210, esi
0x1800d8f29  jz      short loc_1800D8F5F
0x1800d8f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8f32  cmp     rcx, r14
0x1800d8f35  jz      short loc_1800D8F55
0x1800d8f37  mov     dil, 4
0x1800d8f3a  test    [rcx+1Ch], dil
0x1800d8f3e  jz      short loc_1800D8F55
0x1800d8f40  mov     rcx, [rcx+10h]
0x1800d8f44  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d8f4b  mov     edx, 1D2h
0x1800d8f50  call    WPP_SF_
0x1800d8f55  mov     ebx, 0Bh
0x1800d8f5a  jmp     loc_1800D9C70
0x1800d8f5f  test    ebx, ebx
0x1800d8f61  mov     [rsp+300h+var_2B8], esi
0x1800d8f65  lea     rax, ?g_ActiveDeviceProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveDeviceProfile
0x1800d8f6c  mov     [rsp+300h+var_2BC], esi
0x1800d8f70  lea     r14, ?g_ActiveUserProfile@@3U_VPNPROFILEACTIVE@@A; _VPNPROFILEACTIVE g_ActiveUserProfile
0x1800d8f77  cmovz   r14, rax
0x1800d8f7b  mov     [rsp+300h+var_2A8], r14
0x1800d8f80  mov     rdx, [r14+250h]
0x1800d8f87  test    rdx, rdx
0x1800d8f8a  jz      loc_1800D9022
0x1800d8f90  mov     r8, cs:qword_18010E480
0x1800d8f97  test    ebx, ebx
0x1800d8f99  mov     r9, cs:qword_18010E220
0x1800d8fa0  mov     rax, r8
0x1800d8fa3  cmovz   rax, r9
0x1800d8fa7  test    rax, rax
0x1800d8faa  jz      short loc_1800D9022
0x1800d8fac  mov     ecx, [rdx+40h]
0x1800d8faf  cmp     ecx, [rax+40h]
0x1800d8fb2  jnz     short loc_1800D9022
0x1800d8fb4  xor     ebx, ebx
0x1800d8fb6  mov     esi, 1
0x1800d8fbb  mov     [rsp+300h+var_2BC], esi
0x1800d8fbf  mov     [rsp+300h+var_2B8], ebx
0x1800d8fc3  test    ecx, ecx
0x1800d8fc5  jz      short loc_1800D901C
0x1800d8fc7  mov     edi, [rsp+300h+var_2C0]
0x1800d8fcb  mov     rdx, [rdx+48h]
0x1800d8fcf  mov     eax, ebx
0x1800d8fd1  imul    rcx, rax, 208h
0x1800d8fd8  add     rdx, rcx; SubStr
0x1800d8fdb  test    edi, edi
0x1800d8fdd  cmovz   r8, r9
0x1800d8fe1  add     rcx, [r8+48h]; Str
0x1800d8fe5  call    ?int_IsSuffix@@YAHPEBG0@Z; int_IsSuffix(ushort const *,ushort const *)
0x1800d8fea  mov     rdx, [r14+250h]
0x1800d8ff1  neg     eax
0x1800d8ff3  sbb     ecx, ecx
0x1800d8ff5  inc     ebx
0x1800d8ff7  and     ecx, esi
0x1800d8ff9  mov     esi, ecx
0x1800d8ffb  cmp     ebx, [rdx+40h]
0x1800d8ffe  jnb     short loc_1800D9010
0x1800d9000  mov     r9, cs:qword_18010E220
0x1800d9007  mov     r8, cs:qword_18010E480
0x1800d900e  jmp     short loc_1800D8FCB
0x1800d9010  mov     [rsp+300h+var_2B8], ebx
0x1800d9014  mov     ebx, edi
0x1800d9016  mov     [rsp+300h+var_2BC], ecx
0x1800d901a  jmp     short loc_1800D9020
0x1800d901c  mov     ebx, [rsp+300h+var_2C0]
0x1800d9020  xor     esi, esi
0x1800d9022  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9029  lea     r15, WPP_GLOBAL_Control
0x1800d9030  mov     dil, 4
0x1800d9033  cmp     rcx, r15
0x1800d9036  jz      short loc_1800D9053
0x1800d9038  test    [rcx+1Ch], dil
0x1800d903c  jz      short loc_1800D9053
0x1800d903e  mov     rcx, [rcx+10h]
0x1800d9042  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d9049  mov     edx, 1D3h
0x1800d904e  call    WPP_SF_
0x1800d9053  test    ebx, ebx
0x1800d9055  setnz   cl; bool
0x1800d9058  call    ?DumpActiveProfileInfo@@YAX_N@Z; DumpActiveProfileInfo(bool)
0x1800d905d  mov     r10, cs:WPP_GLOBAL_Control
0x1800d9064  cmp     r10, r15
0x1800d9067  jz      short loc_1800D90B9
0x1800d9069  test    [r10+1Ch], dil
0x1800d906d  jz      short loc_1800D9092
0x1800d906f  mov     r9d, cs:?g_deviceLastPowerState@@3W4_VPNPROFILEDEVICESTATE@@A; _VPNPROFILEDEVICESTATE g_deviceLastPowerState
0x1800d9076  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d907d  mov     rcx, [r10+10h]
0x1800d9081  mov     edx, 1D4h
0x1800d9086  call    WPP_SF_d
0x1800d908b  mov     r10, cs:WPP_GLOBAL_Control
0x1800d9092  cmp     r10, r15
0x1800d9095  jz      short loc_1800D90B9
0x1800d9097  test    [r10+1Ch], dil
0x1800d909b  jz      short loc_1800D90B9
0x1800d909d  mov     rcx, [r10+10h]
0x1800d90a1  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d90a8  mov     edx, 1D5h
0x1800d90ad  call    WPP_SF_
0x1800d90b2  mov     r10, cs:WPP_GLOBAL_Control
0x1800d90b9  cmp     [r14+250h], rsi
0x1800d90c0  jz      loc_1800D96E0
0x1800d90c6  lea     r14, WPP_GLOBAL_Control
0x1800d90cd  cmp     r10, r14
0x1800d90d0  jz      short loc_1800D90F7
0x1800d90d2  test    [r10+1Ch], dil
0x1800d90d6  jz      short loc_1800D90F7
0x1800d90d8  cmp     cs:?g_fIsInside@@3HA, esi; int g_fIsInside
0x1800d90de  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d90e5  mov     rcx, [r10+10h]
0x1800d90e9  mov     edx, 1D6h
0x1800d90ee  setnz   r9b
0x1800d90f2  call    WPP_SF_c
0x1800d90f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix> `wil::Feature<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix>::GetImpl(void)'::`2'::impl
0x1800d90fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_BugFixes_25C_AutoConnectFix>::__private_IsEnabled(void)
0x1800d9103  test    al, al
0x1800d9105  jz      loc_1800D932F
0x1800d910b  mov     r10, cs:WPP_GLOBAL_Control
0x1800d9112  cmp     r10, r14
0x1800d9115  jz      short loc_1800D9139
0x1800d9117  test    [r10+1Ch], dil
0x1800d911b  jz      short loc_1800D9139
0x1800d911d  mov     rcx, [r10+10h]
0x1800d9121  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d9128  mov     edx, 1D7h
0x1800d912d  call    WPP_SF_
0x1800d9132  mov     r10, cs:WPP_GLOBAL_Control
0x1800d9139  mov     rbx, [r13+0]
0x1800d913d  cmp     rbx, r13
0x1800d9140  jnz     short loc_1800D9176
0x1800d9142  cmp     r10, r14
0x1800d9145  jz      loc_1800D9336
0x1800d914b  test    [r10+1Ch], dil
0x1800d914f  jz      loc_1800D930F
0x1800d9155  mov     rcx, [r10+10h]
0x1800d9159  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d9160  mov     edx, 1DFh
0x1800d9165  call    WPP_SF_
0x1800d916a  mov     r10, cs:WPP_GLOBAL_Control
0x1800d9171  jmp     loc_1800D930F
0x1800d9176  mov     r15d, r12d
0x1800d9179  cmp     r10, r14
0x1800d917c  jz      loc_1800D9265
0x1800d9182  test    [r10+1Ch], dil
0x1800d9186  jz      short loc_1800D91B5
0x1800d9188  cmp     [rbx+10h], r12
0x1800d918c  lea     rax, aNull_3; "(null)"
0x1800d9193  mov     rcx, [r10+10h]
0x1800d9197  mov     edx, 1D8h
0x1800d919c  cmovnz  rax, [rbx+10h]
0x1800d91a1  mov     r9d, r15d
0x1800d91a4  mov     qword ptr [rsp+300h+var_2E0], rax
0x1800d91a9  call    WPP_SF_LS
0x1800d91ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800d91b5  cmp     r10, r14
0x1800d91b8  jz      loc_1800D9265
0x1800d91be  test    [r10+1Ch], dil
0x1800d91c2  jz      short loc_1800D91E4
0x1800d91c4  mov     r9d, [rbx+1Ch]
0x1800d91c8  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d91cf  mov     rcx, [r10+10h]
0x1800d91d3  mov     edx, 1D9h
0x1800d91d8  call    WPP_SF_d
0x1800d91dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800d91e4  cmp     r10, r14
0x1800d91e7  jz      short loc_1800D9265
0x1800d91e9  test    [r10+1Ch], dil
0x1800d91ed  jz      short loc_1800D920F
0x1800d91ef  mov     r9d, [rbx+18h]
0x1800d91f3  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d91fa  mov     rcx, [r10+10h]
0x1800d91fe  mov     edx, 1DAh
0x1800d9203  call    WPP_SF_d
0x1800d9208  mov     r10, cs:WPP_GLOBAL_Control
0x1800d920f  cmp     r10, r14
0x1800d9212  jz      short loc_1800D9265
0x1800d9214  test    [r10+1Ch], dil
0x1800d9218  jz      short loc_1800D923A
0x1800d921a  mov     r9d, [rbx+30h]
0x1800d921e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d9225  mov     rcx, [r10+10h]
0x1800d9229  mov     edx, 1DBh
0x1800d922e  call    WPP_SF_d
0x1800d9233  mov     r10, cs:WPP_GLOBAL_Control
0x1800d923a  cmp     r10, r14
0x1800d923d  jz      short loc_1800D9265
0x1800d923f  test    [r10+1Ch], dil
0x1800d9243  jz      short loc_1800D9265
0x1800d9245  mov     rcx, [r10+10h]
0x1800d9249  lea     r9, [rbx+20h]
0x1800d924d  mov     edx, 1DCh
0x1800d9252  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d9259  call    WPP_SF__guid_
0x1800d925e  mov     r10, cs:WPP_GLOBAL_Control
0x1800d9265  mov     rsi, [rbx+38h]
0x1800d9269  mov     r14d, r12d
0x1800d926c  test    rsi, rsi
0x1800d926f  jz      short loc_1800D92EB
0x1800d9271  lea     rax, WPP_GLOBAL_Control
0x1800d9278  cmp     r10, rax
0x1800d927b  jz      short loc_1800D92DC
0x1800d927d  test    [r10+1Ch], dil
0x1800d9281  jz      short loc_1800D92A7
0x1800d9283  mov     rcx, [r10+10h]
0x1800d9287  mov     edx, 1DDh
0x1800d928c  mov     r9d, r14d
0x1800d928f  mov     qword ptr [rsp+300h+var_2E0], rsi
0x1800d9294  call    WPP_SF_LS
0x1800d9299  mov     r10, cs:WPP_GLOBAL_Control
0x1800d92a0  lea     rax, WPP_GLOBAL_Control
0x1800d92a7  cmp     r10, rax
0x1800d92aa  jz      short loc_1800D92DC
0x1800d92ac  test    [r10+1Ch], dil
0x1800d92b0  jz      short loc_1800D92DC
0x1800d92b2  mov     rcx, [r10+10h]
0x1800d92b6  lea     r9, [rsi+208h]
0x1800d92bd  mov     edx, 1DEh
0x1800d92c2  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d92c9  call    WPP_SF__guid_
0x1800d92ce  mov     r10, cs:WPP_GLOBAL_Control
0x1800d92d5  lea     rax, WPP_GLOBAL_Control
0x1800d92dc  mov     rsi, [rsi+218h]
0x1800d92e3  inc     r14d
0x1800d92e6  test    rsi, rsi
0x1800d92e9  jnz     short loc_1800D9278
0x1800d92eb  mov     rbx, [rbx]
0x1800d92ee  lea     r14, WPP_GLOBAL_Control
0x1800d92f5  inc     r15d
0x1800d92f8  cmp     rbx, r13
0x1800d92fb  jnz     loc_1800D9179
0x1800d9301  mov     r12d, [rsp+300h+var_2B4]
0x1800d9306  lea     r14, WPP_GLOBAL_Control
0x1800d930d  xor     esi, esi
0x1800d930f  cmp     r10, r14
0x1800d9312  jz      short loc_1800D9336
0x1800d9314  test    [r10+1Ch], dil
0x1800d9318  jz      short loc_1800D9336
0x1800d931a  mov     rcx, [r10+10h]
0x1800d931e  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d9325  mov     edx, 1E0h
0x1800d932a  call    WPP_SF_
0x1800d932f  mov     r10, cs:WPP_GLOBAL_Control
0x1800d9336  mov     rbx, [r13+0]
0x1800d933a  cmp     rbx, r13
0x1800d933d  jnz     short loc_1800D9370
0x1800d933f  mov     ebx, 3
0x1800d9344  cmp     r10, r14
0x1800d9347  jz      short loc_1800D9364
0x1800d9349  test    [r10+1Ch], dil
0x1800d934d  jz      short loc_1800D9364
0x1800d934f  mov     rcx, [r10+10h]
0x1800d9353  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d935a  mov     edx, 1E1h
0x1800d935f  call    WPP_SF_
0x1800d9364  mov     r12d, cs:?g_fIsInside@@3HA; int g_fIsInside
0x1800d936b  jmp     loc_1800D9C70
  ... truncated ...
```
