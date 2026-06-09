# LoadParameters(ulong)

- ea: `0x18009cbc4`
- end: `0x18009d6fe`
- name: `?LoadParameters@@YAJK@Z`
- size: `2874`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800adbf0`
- `0x1800af4b0`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x180087a7c`
- `0x18008e61c`
- `0x180090278`
- `0x1800934c8`
- `0x18009cbc4`
- `0x1800bc040`
- `0x1800d7880`
- `0x18013ad2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009d638`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009d638`
- `LSAADT!__imp_?LsapCrashOnAuditFailState@@3KA` at `0x18009cbe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d389`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009d389`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d33f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009d33f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d376`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009d376`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18009d10a`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18009d10a`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtInitializeCrashOnAuditFail` at `0x18009d0f2`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtInitializeCrashOnAuditFail` at `0x18009d0f2`

## string_xrefs

- `0x18009cd5c`: `IdCacheEntryLifeSpanNegative`
- `0x18009cd78`: `IdCacheEntryLifeSpanAll`
- `0x18009ce0b`: `IdCacheDisabled`
- `0x18009ce32`: `TokenLeakDetectDelaySecs`
- `0x18009ce86`: `AllowUnprivilegedProxyAuth`
- `0x18009cea2`: `UACInstalled`
- `0x18009cefe`: `LocalAccountTokenFilterPolicy`
- `0x18009cf14`: `FilterNetworkAuthenticationTokens`
- `0x18009cf40`: `FilterAdministratorToken`
- `0x18009cf56`: `EnableLinkedConnections`
- `0x18009cf6c`: `EnableLocalLogonSid`
- `0x18009d041`: `AutomaticRestartSignOnConfig`
- `0x18009d079`: `EnableFullTokenForRemoteAuth`
- `0x18009d36f`: `Security Packages`
- `0x18009d47a`: `Security Packages`

## pseudocode

```c
__int64 __fastcall LoadParameters(int a1)
{
  unsigned int v2; // eax
  __int64 result; // rax
  struct _RTL_BALANCED_NODE *v4; // rax
  HKEY v5; // rcx
  int RegistryString; // eax
  void *v7; // rdx
  struct _RTL_BALANCED_NODE *v8; // rax
  struct _RTL_BALANCED_NODE *v9; // rcx
  struct _RTL_BALANCED_NODE *v10; // rax
  HKEY v11; // rcx
  int v12; // eax
  void *v13; // rdx
  struct _RTL_BALANCED_NODE *v14; // rax
  struct _RTL_BALANCED_NODE *v15; // rcx
  LSTATUS v16; // ebx
  DWORD v17; // eax
  __int64 v18; // rax
  struct _RTL_BALANCED_NODE *v19; // rdi
  unsigned __int64 i; // rcx
  unsigned __int16 *v21; // rbx
  void *v22; // rdx
  int v23; // esi
  struct _RTL_BALANCED_NODE *v24; // rcx
  signed int v25; // edx
  __int64 v26; // rcx
  int v27; // r14d
  struct _RTL_BALANCED_NODE *j; // rax
  unsigned __int16 *v29; // rax
  HKEY v30; // rcx
  struct _RTL_BALANCED_NODE *v31; // rbx
  unsigned __int16 *v32; // rax
  HKEY v33; // rcx
  int v34; // r15d
  struct _RTL_BALANCED_NODE *k; // rax
  unsigned __int16 **v36; // r8
  int v37; // esi
  __int16 v38; // ax
  int v39; // r14d
  int v40; // eax
  struct _RTL_BALANCED_NODE *v41; // r9
  int v42; // edx
  __int64 v43; // rax
  __int16 v44; // ax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v46[3]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v47[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v48[46]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v49[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v50; // [rsp+1F0h] [rbp+F0h]
  int v51; // [rsp+1F4h] [rbp+F4h]
  const wchar_t *v52; // [rsp+1F8h] [rbp+F8h]
  unsigned int *v53; // [rsp+200h] [rbp+100h]
  int v54; // [rsp+208h] [rbp+108h]
  int v55; // [rsp+20Ch] [rbp+10Ch]
  const wchar_t *v56; // [rsp+210h] [rbp+110h]
  unsigned int *v57; // [rsp+218h] [rbp+118h]
  __int64 v58; // [rsp+220h] [rbp+120h]
  const wchar_t *v59; // [rsp+228h] [rbp+128h]
  unsigned int *v60; // [rsp+230h] [rbp+130h]
  __int64 v61; // [rsp+238h] [rbp+138h]
  const wchar_t *v62; // [rsp+240h] [rbp+140h]
  unsigned int *v63; // [rsp+248h] [rbp+148h]
  __int64 v64; // [rsp+250h] [rbp+150h]
  const wchar_t *v65; // [rsp+258h] [rbp+158h]
  unsigned int *v66; // [rsp+260h] [rbp+160h]
  __int64 v67; // [rsp+268h] [rbp+168h]
  const wchar_t *v68; // [rsp+270h] [rbp+170h]
  unsigned int *v69; // [rsp+278h] [rbp+178h]
  __int64 v70; // [rsp+280h] [rbp+180h]
  const wchar_t *v71; // [rsp+288h] [rbp+188h]
  unsigned int *v72; // [rsp+290h] [rbp+190h]
  __int64 v73; // [rsp+298h] [rbp+198h]
  const wchar_t *v74; // [rsp+2A0h] [rbp+1A0h]
  unsigned int *v75; // [rsp+2A8h] [rbp+1A8h]
  __int64 v76; // [rsp+2B0h] [rbp+1B0h]
  const wchar_t *v77; // [rsp+2B8h] [rbp+1B8h]
  unsigned int *v78; // [rsp+2C0h] [rbp+1C0h]
  __int64 v79; // [rsp+2C8h] [rbp+1C8h]
  const wchar_t *v80; // [rsp+2D0h] [rbp+1D0h]
  unsigned int *v81; // [rsp+2D8h] [rbp+1D8h]
  __int64 v82; // [rsp+2E0h] [rbp+1E0h]
  const wchar_t *v83; // [rsp+2E8h] [rbp+1E8h]
  unsigned int *v84; // [rsp+2F0h] [rbp+1F0h]
  __int64 v85; // [rsp+2F8h] [rbp+1F8h]
  const wchar_t *v86; // [rsp+300h] [rbp+200h]
  unsigned int *v87; // [rsp+308h] [rbp+208h]
  __int64 v88; // [rsp+310h] [rbp+210h]
  const wchar_t *v89; // [rsp+318h] [rbp+218h]
  unsigned int *v90; // [rsp+320h] [rbp+220h]
  __int64 v91; // [rsp+328h] [rbp+228h]
  const wchar_t *v92; // [rsp+330h] [rbp+230h]
  unsigned int *v93; // [rsp+338h] [rbp+238h]
  __int64 v94; // [rsp+340h] [rbp+240h]
  const wchar_t *v95; // [rsp+348h] [rbp+248h]
  unsigned int *v96; // [rsp+350h] [rbp+250h]
  __int64 v97; // [rsp+358h] [rbp+258h]
  const wchar_t *v98; // [rsp+360h] [rbp+260h]
  unsigned int *v99; // [rsp+368h] [rbp+268h]
  int v100; // [rsp+370h] [rbp+270h]
  int v101; // [rsp+374h] [rbp+274h]
  const wchar_t *v102; // [rsp+378h] [rbp+278h]
  unsigned int *v103; // [rsp+380h] [rbp+280h]
  __int64 v104; // [rsp+388h] [rbp+288h]
  const wchar_t *v105; // [rsp+390h] [rbp+290h]
  unsigned int *v106; // [rsp+398h] [rbp+298h]
  __int64 v107; // [rsp+3A0h] [rbp+2A0h]
  unsigned int v108; // [rsp+400h] [rbp+300h] BYREF
  DWORD cbData; // [rsp+408h] [rbp+308h] BYREF
  unsigned int v110; // [rsp+410h] [rbp+310h] BYREF
  DWORD Type; // [rsp+418h] [rbp+318h] BYREF

  hKey = 0;
  Type = 0;
  v108 = 0;
  cbData = 0;
  v49[0] = L"EveryoneIncludesAnonymous";
  v49[1] = &LsapGlobalRestrictNullSessions;
  v52 = L"TurnOffAnonymousBlock";
  v53 = &LsapGlobalRestrictAnonymous;
  v56 = L"AuthenticateAnonymousOnlineIDs";
  v57 = &LsapGlobalAuthenticateAnonymousOnlineIDs;
  v59 = L"HourlyLogLevel";
  v60 = &LsapGlobalHourlyLogLevel;
  v62 = L"DisableDomainCreds";
  v63 = &CredDisableDomainCreds;
  v65 = L"DisableCredMan";
  v66 = &CredDisableCredMan;
  v68 = L"NegEventMask";
  v69 = &NegEventMask;
  v71 = L"CrashOnAuditFail";
  v72 = &v110;
  v74 = L"AcceptUnsafeUnprotectedNegotiation";
  v75 = &NegAcceptUnsafeUnprotectedNegotiation;
  v77 = L"SendOptionalMechlistMIC";
  v78 = &NegSendOptionalMechlistMIC;
  v80 = L"SuppressExtendedProtection";
  v81 = &LsaSuppressChannelBindingInfo;
  v83 = L"SamWaitNoTimeout";
  v84 = &LsapSamWaitNoTimeout;
  v86 = L"IdCacheEntryLifeSpanNegative";
  v87 = &LsapIdCacheEntryLifeSpanNegative;
  v89 = L"IdCacheEntryLifeSpanAll";
  v90 = &LsapIdCacheEntryLifeSpanAll;
  v110 = LsapCrashOnAuditFailState;
  v50 = 1;
  v51 = 1;
  v54 = 1;
  v55 = 1;
  v58 = 0;
  v61 = 3;
  v64 = 0;
  v67 = 0;
  v70 = 0;
  v73 = 0;
  v76 = 1;
  v79 = 0;
  v82 = 0;
  v85 = 0;
  v88 = 1800;
  v91 = 10080;
  v92 = L"IdCacheDisabled";
  v93 = &LsapIdCacheDisabled;
  v95 = L"TokenLeakDetectDelaySecs";
  v96 = &LsapTokenLeakTimerInSecs;
  v98 = L"DisableRestrictedAdmin";
  v99 = &LsapDisableRestrictedAdmin;
  v102 = L"DisableRestrictedAdminOutboundCreds";
  v103 = &LsapDisableRestrictedAdminOutboundCreds;
  v105 = L"AllowUnprivilegedProxyAuth";
  v106 = &AllowUnprivilegedProxyAuth;
  v47[0] = L"UACInstalled";
  v47[1] = &LsapGlobalLUAInstalled;
  v48[0] = L"EnableVirtualization";
  v48[1] = &LsapGlobalVirtEnabled;
  v48[3] = L"ScForceOption";
  v48[4] = &LsapGlobalForceSCLogon;
  v48[6] = L"DisableRestrictionTraversal";
  v48[7] = &LsapGlobalDisableRestrictionTraversal;
  v48[9] = L"LocalAccountTokenFilterPolicy";
  v48[10] = &LsapGlobalLocalAccountTokenFilterPolicy;
  v48[12] = L"FilterNetworkAuthenticationTokens";
  v48[13] = &LsapGlobalFilterNetworkAuthenticationTokens;
  v48[15] = L"DisplayLastLogonInfo";
  v48[16] = &NegEnableLastInteractiveLogonInfo;
  v48[18] = L"FilterAdministratorToken";
  v48[19] = &LsapGlobalFilterAdministratorToken;
  v48[21] = L"EnableLinkedConnections";
  v48[22] = &LsapEnableLinkedConnections;
  v48[24] = L"EnableLocalLogonSid";
  v48[25] = &LsapEnableLocalLogonSid;
  v48[27] = L"ApplyPolicyToAnonymousLogon";
  v48[28] = &LsapApplyPolicyToAnonymousLogon;
  v94 = 0;
  v97 = 30;
  v100 = -2123407173;
  v101 = 0;
  v104 = 0;
  v107 = 1;
  v47[2] = 0;
  v48[2] = 1;
  v48[5] = 0;
  v48[8] = 0;
  v48[11] = 0;
  v48[14] = 0;
  v48[17] = 0;
  v48[20] = 0;
  v48[23] = 0;
  v48[26] = 1;
  v48[29] = 0;
  v48[30] = L"NoConnectedUser";
  v48[31] = &LsapNoConnectedUser;
  v48[33] = L"DisableConnectedNTLMPassword";
  v48[34] = &LsapDisableConnectedNTLMPassword;
  v48[36] = L"DisableAutomaticRestartSignOn";
  v48[37] = &g_lsapDisableAutomaticRestartSignOn;
  v48[39] = L"AutomaticRestartSignOnConfig";
  v48[40] = &g_lsapAutomaticRestartSignOnMode;
  v48[42] = L"TrackLoopbackForSession";
  v48[43] = &LsapLoopbackTrackingEnabled;
  v46[0] = L"EnableFullTokenForRemoteAuth";
  v46[1] = &LsapFullTokenRemoteAuthInShadowAdminEnabled;
  v48[32] = 0;
  v48[35] = 0;
  v48[38] = 0;
  v48[41] = 0;
  v48[44] = 0x7FFFFFFF;
  v46[2] = 0;
  if ( (a1 & 1) != 0 )
  {
    GetRegistryDwords(
      HKEY_LOCAL_MACHINE,
      L"System\\CurrentControlSet\\Control\\Lsa",
      0x13u,
      (struct _LSAP_REG_PARAMETER *)v49);
    if ( (unsigned __int8)IsLsapAdtInitializeCrashOnAuditFailPresent() )
      LsapAdtInitializeCrashOnAuditFail(v110);
  }
  if ( (a1 & 2) != 0 )
  {
    CheckElevationEnabled(&LsapGlobalLUAEnabled);
    GetRegistryDwords(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
      0xFu,
      (struct _LSAP_REG_PARAMETER *)v48);
    LsapShadowAdminEnabled = LUAIsShadowAdminEnabled();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
    {
      if ( LsapShadowAdminEnabled )
      {
        GetRegistryDwords(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          1u,
          (struct _LSAP_REG_PARAMETER *)v46);
        LsapLoadRemoteAdminAllowList();
      }
    }
  }
  if ( !LsapGlobalForceSCLogon || (v2 = 1, LsapGlobalBootState) )
    v2 = 0;
  LsapGlobalForceSCLogon = v2;
  if ( a1 < 0 )
    return 0;
  result = LsapGetComputerName(&LsapGlobalMachineName);
  if ( (int)result >= 0 )
  {
    v108 = 128;
    v4 = (struct _RTL_BALANCED_NODE *)LsapAllocate(128);
    pszPreferred = v4;
    if ( v4 )
      LOWORD(v4->Children[0]) = 0;
    else
      v108 = 0;
    RegistryString = GetRegistryString(
                       v5,
                       L"System\\CurrentControlSet\\Control\\Lsa",
                       szPreferredPackage,
                       (unsigned __int16 *)v4,
                       &v108);
    if ( RegistryString == -1073741789 )
    {
      LsapSubProv_FreeRoutine(pszPreferred, v7);
      v8 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v108);
      pszPreferred = v8;
      v9 = v8;
      if ( !v8 )
        goto LABEL_22;
      LOWORD(v8->Children[0]) = 0;
      RegistryString = GetRegistryString(
                         (HKEY)v8,
                         L"System\\CurrentControlSet\\Control\\Lsa",
                         szPreferredPackage,
                         (unsigned __int16 *)v8,
                         &v108);
    }
    if ( RegistryString >= 0 )
      goto LABEL_24;
    v9 = pszPreferred;
LABEL_22:
    if ( v9 )
    {
      LsapSubProv_FreeRoutine(v9, v7);
      pszPreferred = 0;
    }
LABEL_24:
    v108 = 128;
    v10 = (struct _RTL_BALANCED_NODE *)LsapAllocate(128);
    pszDefaultTLS = v10;
    if ( v10 )
      LOWORD(v10->Children[0]) = 0;
    else
      v108 = 0;
    v12 = GetRegistryString(
            v11,
            L"System\\CurrentControlSet\\Control\\Lsa",
            L"Default TLS SSP",
            (unsigned __int16 *)v10,
            &v108);
    if ( v12 == -1073741789 )
    {
      LsapSubProv_FreeRoutine(pszDefaultTLS, v13);
      v14 = (struct _RTL_BALANCED_NODE *)LsapAllocate(v108);
      pszDefaultTLS = v14;
      v15 = v14;
      if ( !v14 )
        goto LABEL_32;
      LOWORD(v14->Children[0]) = 0;
      v12 = GetRegistryString(
              (HKEY)v14,
              L"System\\CurrentControlSet\\Control\\Lsa",
              L"Default TLS SSP",
              (unsigned __int16 *)v14,
              &v108);
    }
    if ( v12 >= 0 )
    {
LABEL_34:
      ppszPackages = (unsigned __int16 **)&ppszDefault;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x2000000u, &hKey)
        || (v16 = RegQueryValueExW(hKey, szOthersValue, 0, &Type, 0, &cbData), RegCloseKey(hKey), !v16) && Type == 7 )
      {
        v17 = cbData;
      }
      else
      {
        v17 = 0;
        cbData = 0;
      }
      v108 = 0;
      v18 = LsapAllocate(v17 + 126);
      v19 = (struct _RTL_BALANCED_NODE *)v18;
      if ( !v18 )
        return 3221225626LL;
      v108 = 120;
      *(_OWORD *)v18 = *(_OWORD *)L"kerberos";
      *(_OWORD *)(v18 + 16) = *(_OWORD *)L"";
      *(_OWORD *)(v18 + 32) = xmmword_1801696B0;
      *(_OWORD *)(v18 + 48) = xmmword_1801696C0;
      *(_OWORD *)(v18 + 64) = xmmword_1801696D0;
      *(_OWORD *)(v18 + 80) = xmmword_1801696E0;
      *(_OWORD *)(v18 + 96) = xmmword_1801696F0;
      *(_QWORD *)(v18 + 112) = 7143536;
      for ( i = v108; (unsigned int)i >= 2 && !*(_WORD *)(v18 + 2 * ((unsigned __int64)(unsigned int)i >> 1)); v108 = i )
        i = (unsigned int)(i - 2);
      if ( *(_WORD *)(v18 + 2 * ((unsigned __int64)(unsigned int)i >> 1)) )
      {
        i = (unsigned int)(i + 4);
        v108 = i;
      }
      if ( cbData )
      {
        v108 = cbData;
        v21 = (unsigned __int16 *)(v18 + 2 * ((unsigned __int64)(unsigned int)i >> 1));
        v23 = GetRegistryString((HKEY)i, L"System\\CurrentControlSet\\Control\\Lsa", szOthersValue, v21, &v108);
        if ( v23 < 0 )
        {
          v24 = v19;
LABEL_49:
          LsapSubProv_FreeRoutine(v24, v22);
          return (unsigned int)v23;
        }
        if ( !*v21 )
        {
          if ( v21[1] )
          {
            v25 = 0;
            if ( (v108 & 0xFFFFFFFE) != 0 )
            {
              do
              {
                v26 = v25++;
                v21[v26] = v21[v26 + 1];
              }
              while ( v25 < (int)(v108 >> 1) );
            }
          }
        }
      }
      v27 = 0;
      for ( j = v19; LOWORD(j->Children[0]); ++v27 )
      {
        do
          j = (struct _RTL_BALANCED_NODE *)((char *)j + 2);
        while ( LOWORD(j->Children[0]) );
        j = (struct _RTL_BALANCED_NODE *)((char *)j + 2);
      }
      v108 = 128;
      v29 = (unsigned __int16 *)LsapAllocate(128);
      v31 = (struct _RTL_BALANCED_NODE *)v29;
      if ( !v29 )
        return 3221225626LL;
      *v29 = 0;
      v23 = GetRegistryString(v30, L"System\\CurrentControlSet\\Control\\Lsa", szOldValue, v29, &v108);
      if ( v23 == -1073741789 )
      {
        LsapSubProv_FreeRoutine(v31, v22);
        v32 = (unsigned __int16 *)LsapAllocate(v108);
        v31 = (struct _RTL_BALANCED_NODE *)v32;
        if ( !v32 )
          return 3221225626LL;
        *v32 = 0;
        v23 = GetRegistryString(v33, L"System\\CurrentControlSet\\Control\\Lsa", szOldValue, v32, &v108);
        if ( v23 < 0 )
        {
          v24 = v31;
          goto LABEL_49;
        }
      }
      v34 = 0;
      if ( v23 < 0 )
      {
        LsapSubProv_FreeRoutine(v31, v22);
        if ( v23 != -1073741772 )
          return (unsigned int)v23;
        v31 = 0;
      }
      else
      {
        for ( k = v31; LOWORD(k->Children[0]); ++v34 )
        {
          do
            k = (struct _RTL_BALANCED_NODE *)((char *)k + 2);
          while ( LOWORD(k->Children[0]) );
          k = (struct _RTL_BALANCED_NODE *)((char *)k + 2);
        }
      }
      ppszPackages = (unsigned __int16 **)LsapAllocate(8LL * (v27 + 1));
      v36 = ppszPackages;
      if ( ppszPackages )
      {
        v37 = 0;
        while ( LOWORD(v19->Children[0]) )
        {
          v36[v37] = (unsigned __int16 *)v19;
          do
          {
            v38 = (__int16)v19->Children[0];
            v19 = (struct _RTL_BALANCED_NODE *)((char *)v19 + 2);
          }
          while ( v38 );
          v39 = 0;
          if ( v37 > 0 )
          {
            while ( 1 )
            {
              v40 = _o__wcsicmp(v36[v39], v36[v37]);
              v36 = ppszPackages;
              if ( !v40 )
                break;
              if ( ++v39 >= v37 )
                goto LABEL_77;
            }
            --v37;
          }
LABEL_77:
          ++v37;
        }
        v36[v37] = 0;
        ppszOldPkgs = (struct _RTL_BALANCED_NODE *)LsapAllocate(8LL * (v34 + 1));
        v41 = ppszOldPkgs;
        if ( ppszOldPkgs )
        {
          v42 = 0;
          if ( v31 )
          {
            while ( LOWORD(v31->Children[0]) )
            {
              v43 = v42++;
              v41->Children[v43] = v31;
              do
              {
                v44 = (__int16)v31->Children[0];
                v31 = (struct _RTL_BALANCED_NODE *)((char *)v31 + 2);
              }
              while ( v44 );
            }
          }
          v41->Children[v42] = 0;
          GetRegistryDwords(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\LsaInformation",
            1u,
            (struct _LSAP_REG_PARAMETER *)v47);
          return 0;
        }
      }
      return 3221225626LL;
    }
    v15 = pszDefaultTLS;
LABEL_32:
    if ( v15 )
    {
      LsapSubProv_FreeRoutine(v15, v13);
      pszDefaultTLS = 0;
    }
    goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x18009cbc4  push    rbp
0x18009cbc6  push    rbx
0x18009cbc7  push    rsi
0x18009cbc8  push    rdi
0x18009cbc9  push    r12
0x18009cbcb  push    r13
0x18009cbcd  push    r14
0x18009cbcf  push    r15
0x18009cbd1  lea     rbp, [rsp-2B8h]
0x18009cbd9  sub     rsp, 3B8h
0x18009cbe0  mov     rax, cs:__imp_?LsapCrashOnAuditFailState@@3KA; ulong LsapCrashOnAuditFailState
0x18009cbe7  xor     r13d, r13d
0x18009cbea  mov     [rsp+3F0h+hKey], r13
0x18009cbef  mov     ebx, ecx
0x18009cbf1  mov     [rbp+2F0h+Type], r13d
0x18009cbf8  mov     [rbp+2F0h+arg_0], r13d
0x18009cbff  lea     r12d, [r13+1]
0x18009cc03  mov     [rbp+2F0h+cbData], r13d
0x18009cc0a  mov     edx, [rax]
0x18009cc0c  lea     rax, aEveryoneinclud; "EveryoneIncludesAnonymous"
0x18009cc13  mov     [rbp+2F0h+var_210], rax
0x18009cc1a  lea     rax, ?LsapGlobalRestrictNullSessions@@3KA; ulong LsapGlobalRestrictNullSessions
0x18009cc21  mov     [rbp+2F0h+var_208], rax
0x18009cc28  lea     rax, aTurnoffanonymo; "TurnOffAnonymousBlock"
0x18009cc2f  mov     [rbp+2F0h+var_1F8], rax
0x18009cc36  lea     rax, ?LsapGlobalRestrictAnonymous@@3KA; ulong LsapGlobalRestrictAnonymous
0x18009cc3d  mov     [rbp+2F0h+var_1F0], rax
0x18009cc44  lea     rax, aAuthenticatean; "AuthenticateAnonymousOnlineIDs"
0x18009cc4b  mov     [rbp+2F0h+var_1E0], rax
0x18009cc52  lea     rax, ?LsapGlobalAuthenticateAnonymousOnlineIDs@@3KA; ulong LsapGlobalAuthenticateAnonymousOnlineIDs
0x18009cc59  mov     [rbp+2F0h+var_1D8], rax
0x18009cc60  lea     rax, aHourlyloglevel; "HourlyLogLevel"
0x18009cc67  mov     [rbp+2F0h+var_1C8], rax
0x18009cc6e  lea     rax, ?LsapGlobalHourlyLogLevel@@3KA; ulong LsapGlobalHourlyLogLevel
0x18009cc75  mov     [rbp+2F0h+var_1C0], rax
0x18009cc7c  lea     rax, aDisabledomainc; "DisableDomainCreds"
0x18009cc83  mov     [rbp+2F0h+var_1B0], rax
0x18009cc8a  lea     rax, ?CredDisableDomainCreds@@3KA; ulong CredDisableDomainCreds
0x18009cc91  mov     [rbp+2F0h+var_1A8], rax
0x18009cc98  lea     rax, aDisablecredman; "DisableCredMan"
0x18009cc9f  mov     [rbp+2F0h+var_198], rax
0x18009cca6  lea     rax, ?CredDisableCredMan@@3KA; ulong CredDisableCredMan
0x18009ccad  mov     [rbp+2F0h+var_190], rax
0x18009ccb4  lea     rax, aNegeventmask; "NegEventMask"
0x18009ccbb  mov     [rbp+2F0h+var_180], rax
0x18009ccc2  lea     rax, ?NegEventMask@@3KA; ulong NegEventMask
0x18009ccc9  mov     [rbp+2F0h+var_178], rax
0x18009ccd0  lea     rax, aCrashonauditfa; "CrashOnAuditFail"
0x18009ccd7  mov     [rbp+2F0h+var_168], rax
0x18009ccde  lea     rax, [rbp+2F0h+arg_10]
0x18009cce5  mov     [rbp+2F0h+var_160], rax
0x18009ccec  lea     rax, aAcceptunsafeun; "AcceptUnsafeUnprotectedNegotiation"
0x18009ccf3  mov     [rbp+2F0h+var_150], rax
0x18009ccfa  lea     rax, ?NegAcceptUnsafeUnprotectedNegotiation@@3KA; ulong NegAcceptUnsafeUnprotectedNegotiation
0x18009cd01  mov     [rbp+2F0h+var_148], rax
0x18009cd08  lea     rax, aSendoptionalme; "SendOptionalMechlistMIC"
0x18009cd0f  mov     [rbp+2F0h+var_138], rax
0x18009cd16  lea     rax, ?NegSendOptionalMechlistMIC@@3KA; ulong NegSendOptionalMechlistMIC
0x18009cd1d  mov     [rbp+2F0h+var_130], rax
0x18009cd24  lea     rax, aSuppressextend; "SuppressExtendedProtection"
0x18009cd2b  mov     [rbp+2F0h+var_120], rax
0x18009cd32  lea     rax, ?LsaSuppressChannelBindingInfo@@3KA; ulong LsaSuppressChannelBindingInfo
0x18009cd39  mov     [rbp+2F0h+var_118], rax
0x18009cd40  lea     rax, aSamwaitnotimeo; "SamWaitNoTimeout"
0x18009cd47  mov     [rbp+2F0h+var_108], rax
0x18009cd4e  lea     rax, ?LsapSamWaitNoTimeout@@3KA; ulong LsapSamWaitNoTimeout
0x18009cd55  mov     [rbp+2F0h+var_100], rax
0x18009cd5c  lea     rax, aIdcacheentryli; "IdCacheEntryLifeSpanNegative"
0x18009cd63  mov     [rbp+2F0h+var_F0], rax
0x18009cd6a  lea     rax, ?LsapIdCacheEntryLifeSpanNegative@@3KA; ulong LsapIdCacheEntryLifeSpanNegative
0x18009cd71  mov     [rbp+2F0h+var_E8], rax
0x18009cd78  lea     rax, aIdcacheentryli_0; "IdCacheEntryLifeSpanAll"
0x18009cd7f  mov     [rbp+2F0h+var_D8], rax
0x18009cd86  lea     rax, ?LsapIdCacheEntryLifeSpanAll@@3KA; ulong LsapIdCacheEntryLifeSpanAll
0x18009cd8d  mov     [rbp+2F0h+var_D0], rax
0x18009cd94  mov     [rbp+2F0h+arg_10], edx
0x18009cd9a  mov     [rbp+2F0h+var_200], r12d
0x18009cda1  mov     [rbp+2F0h+var_1FC], r12d
0x18009cda8  mov     [rbp+2F0h+var_1E8], r12d
0x18009cdaf  mov     [rbp+2F0h+var_1E4], r12d
0x18009cdb6  mov     [rbp+2F0h+var_1D0], r13
0x18009cdbd  mov     [rbp+2F0h+var_1B8], 3
0x18009cdc8  mov     [rbp+2F0h+var_1A0], r13
0x18009cdcf  mov     [rbp+2F0h+var_188], r13
0x18009cdd6  mov     [rbp+2F0h+var_170], r13
0x18009cddd  mov     [rbp+2F0h+var_158], r13
0x18009cde4  mov     [rbp+2F0h+var_140], r12
0x18009cdeb  mov     [rbp+2F0h+var_128], r13
0x18009cdf2  mov     [rbp+2F0h+var_110], r13
0x18009cdf9  mov     [rbp+2F0h+var_F8], r13
0x18009ce00  mov     [rbp+2F0h+var_E0], 708h
0x18009ce0b  lea     rax, aIdcachedisable; "IdCacheDisabled"
0x18009ce12  mov     [rbp+2F0h+var_C8], 2760h
0x18009ce1d  mov     [rbp+2F0h+var_C0], rax
0x18009ce24  lea     rax, ?LsapIdCacheDisabled@@3KA; ulong LsapIdCacheDisabled
0x18009ce2b  mov     [rbp+2F0h+var_B8], rax
0x18009ce32  lea     rax, aTokenleakdetec; "TokenLeakDetectDelaySecs"
0x18009ce39  mov     [rbp+2F0h+var_A8], rax
0x18009ce40  lea     rax, ?LsapTokenLeakTimerInSecs@@3KA; ulong LsapTokenLeakTimerInSecs
0x18009ce47  mov     [rbp+2F0h+var_A0], rax
0x18009ce4e  lea     rax, aDisablerestric_0; "DisableRestrictedAdmin"
0x18009ce55  mov     [rbp+2F0h+var_90], rax
0x18009ce5c  lea     rax, ?LsapDisableRestrictedAdmin@@3KA; ulong LsapDisableRestrictedAdmin
0x18009ce63  mov     [rbp+2F0h+var_88], rax
0x18009ce6a  lea     rax, aDisablerestric; "DisableRestrictedAdminOutboundCreds"
0x18009ce71  mov     [rbp+2F0h+var_78], rax
0x18009ce78  lea     rax, ?LsapDisableRestrictedAdminOutboundCreds@@3KA; ulong LsapDisableRestrictedAdminOutboundCreds
0x18009ce7f  mov     [rbp+2F0h+var_70], rax
0x18009ce86  lea     rax, aAllowunprivile; "AllowUnprivilegedProxyAuth"
0x18009ce8d  mov     [rbp+2F0h+var_60], rax
0x18009ce94  lea     rax, ?AllowUnprivilegedProxyAuth@@3KA; ulong AllowUnprivilegedProxyAuth
0x18009ce9b  mov     [rbp+2F0h+var_58], rax
0x18009cea2  lea     rax, aUacinstalled; "UACInstalled"
0x18009cea9  mov     [rsp+3F0h+var_3A0], rax
0x18009ceae  lea     rax, ?LsapGlobalLUAInstalled@@3KA; ulong LsapGlobalLUAInstalled
0x18009ceb5  mov     [rsp+3F0h+var_398], rax
0x18009ceba  lea     rax, aEnablevirtuali; "EnableVirtualization"
0x18009cec1  mov     [rsp+3F0h+var_380], rax
0x18009cec6  lea     rax, ?LsapGlobalVirtEnabled@@3KA; ulong LsapGlobalVirtEnabled
0x18009cecd  mov     [rsp+3F0h+var_378], rax
0x18009ced2  lea     rax, aScforceoption; "ScForceOption"
0x18009ced9  mov     [rbp+2F0h+var_368], rax
0x18009cedd  lea     rax, ?LsapGlobalForceSCLogon@@3KA; ulong LsapGlobalForceSCLogon
0x18009cee4  mov     [rbp+2F0h+var_360], rax
0x18009cee8  lea     rax, aDisablerestric_1; "DisableRestrictionTraversal"
0x18009ceef  mov     [rbp+2F0h+var_350], rax
0x18009cef3  lea     rax, ?LsapGlobalDisableRestrictionTraversal@@3KA; ulong LsapGlobalDisableRestrictionTraversal
0x18009cefa  mov     [rbp+2F0h+var_348], rax
0x18009cefe  lea     rax, aLocalaccountto; "LocalAccountTokenFilterPolicy"
0x18009cf05  mov     [rbp+2F0h+var_338], rax
0x18009cf09  lea     rax, ?LsapGlobalLocalAccountTokenFilterPolicy@@3KA; ulong LsapGlobalLocalAccountTokenFilterPolicy
0x18009cf10  mov     [rbp+2F0h+var_330], rax
0x18009cf14  lea     rax, aFilternetworka; "FilterNetworkAuthenticationTokens"
0x18009cf1b  mov     [rbp+2F0h+var_320], rax
0x18009cf1f  lea     rax, ?LsapGlobalFilterNetworkAuthenticationTokens@@3KA; ulong LsapGlobalFilterNetworkAuthenticationTokens
0x18009cf26  mov     [rbp+2F0h+var_318], rax
0x18009cf2a  lea     rax, aDisplaylastlog; "DisplayLastLogonInfo"
0x18009cf31  mov     [rbp+2F0h+var_308], rax
0x18009cf35  lea     rax, ?NegEnableLastInteractiveLogonInfo@@3KA; ulong NegEnableLastInteractiveLogonInfo
0x18009cf3c  mov     [rbp+2F0h+var_300], rax
0x18009cf40  lea     rax, aFilteradminist; "FilterAdministratorToken"
0x18009cf47  mov     [rbp+2F0h+var_2F0], rax
0x18009cf4b  lea     rax, ?LsapGlobalFilterAdministratorToken@@3KA; ulong LsapGlobalFilterAdministratorToken
0x18009cf52  mov     [rbp+2F0h+var_2E8], rax
0x18009cf56  lea     rax, aEnablelinkedco; "EnableLinkedConnections"
0x18009cf5d  mov     [rbp+2F0h+var_2D8], rax
0x18009cf61  lea     rax, ?LsapEnableLinkedConnections@@3KA; ulong LsapEnableLinkedConnections
0x18009cf68  mov     [rbp+2F0h+var_2D0], rax
0x18009cf6c  lea     rax, aEnablelocallog; "EnableLocalLogonSid"
0x18009cf73  mov     [rbp+2F0h+var_2C0], rax
0x18009cf77  lea     rax, ?LsapEnableLocalLogonSid@@3KA; ulong LsapEnableLocalLogonSid
0x18009cf7e  mov     [rbp+2F0h+var_2B8], rax
0x18009cf82  lea     rax, aApplypolicytoa; "ApplyPolicyToAnonymousLogon"
0x18009cf89  mov     [rbp+2F0h+var_2A8], rax
0x18009cf8d  lea     rax, ?LsapApplyPolicyToAnonymousLogon@@3KA; ulong LsapApplyPolicyToAnonymousLogon
0x18009cf94  mov     [rbp+2F0h+var_2A0], rax
0x18009cf98  mov     [rbp+2F0h+var_B0], r13
0x18009cf9f  mov     [rbp+2F0h+var_98], 1Eh
0x18009cfaa  mov     [rbp+2F0h+var_80], 816F60BBh
0x18009cfb4  mov     [rbp+2F0h+var_7C], r13d
0x18009cfbb  mov     [rbp+2F0h+var_68], r13
0x18009cfc2  mov     [rbp+2F0h+var_50], r12
0x18009cfc9  mov     [rsp+3F0h+var_390], r13
0x18009cfce  mov     [rbp+2F0h+var_370], r12
0x18009cfd2  mov     [rbp+2F0h+var_358], r13
0x18009cfd6  mov     [rbp+2F0h+var_340], r13
0x18009cfda  mov     [rbp+2F0h+var_328], r13
0x18009cfde  mov     [rbp+2F0h+var_310], r13
0x18009cfe2  mov     [rbp+2F0h+var_2F8], r13
0x18009cfe6  mov     [rbp+2F0h+var_2E0], r13
0x18009cfea  mov     [rbp+2F0h+var_2C8], r13
0x18009cfee  mov     [rbp+2F0h+var_2B0], r12
0x18009cff2  mov     [rbp+2F0h+var_298], r13
0x18009cff6  lea     rax, aNoconnecteduse; "NoConnectedUser"
0x18009cffd  mov     [rbp+2F0h+var_290], rax
0x18009d001  lea     rax, ?LsapNoConnectedUser@@3KA; ulong LsapNoConnectedUser
0x18009d008  mov     [rbp+2F0h+var_288], rax
0x18009d00c  lea     rax, aDisableconnect; "DisableConnectedNTLMPassword"
0x18009d013  mov     [rbp+2F0h+var_278], rax
0x18009d017  lea     rax, ?LsapDisableConnectedNTLMPassword@@3KA; ulong LsapDisableConnectedNTLMPassword
0x18009d01e  mov     [rbp+2F0h+var_270], rax
0x18009d025  lea     rax, aDisableautomat; "DisableAutomaticRestartSignOn"
0x18009d02c  mov     [rbp+2F0h+var_260], rax
0x18009d033  lea     rax, ?g_lsapDisableAutomaticRestartSignOn@@3HA; int g_lsapDisableAutomaticRestartSignOn
0x18009d03a  mov     [rbp+2F0h+var_258], rax
0x18009d041  lea     rax, aAutomaticresta; "AutomaticRestartSignOnConfig"
0x18009d048  mov     [rbp+2F0h+var_248], rax
0x18009d04f  lea     rax, ?g_lsapAutomaticRestartSignOnMode@@3KA; ulong g_lsapAutomaticRestartSignOnMode
0x18009d056  mov     [rbp+2F0h+var_240], rax
0x18009d05d  lea     rax, aTrackloopbackf; "TrackLoopbackForSession"
0x18009d064  mov     [rbp+2F0h+var_230], rax
0x18009d06b  lea     rax, ?LsapLoopbackTrackingEnabled@@3W4_LSAP_LOOPBACK_TRACKING_STATE@@A; _LSAP_LOOPBACK_TRACKING_STATE LsapLoopbackTrackingEnabled
0x18009d072  mov     [rbp+2F0h+var_228], rax
0x18009d079  lea     rax, aEnablefulltoke; "EnableFullTokenForRemoteAuth"
0x18009d080  mov     [rsp+3F0h+var_3B8], rax
0x18009d085  lea     rax, ?LsapFullTokenRemoteAuthInShadowAdminEnabled@@3HA; int LsapFullTokenRemoteAuthInShadowAdminEnabled
0x18009d08c  mov     [rsp+3F0h+var_3B0], rax
0x18009d091  lea     r15, aSystemCurrentc_14; "System\\CurrentControlSet\\Control\\Lsa"
0x18009d098  mov     [rbp+2F0h+var_280], r13
0x18009d09c  mov     rdi, 0FFFFFFFF80000002h
0x18009d0a3  mov     [rbp+2F0h+var_268], r13
0x18009d0aa  mov     [rbp+2F0h+var_250], r13
0x18009d0b1  mov     [rbp+2F0h+var_238], r13
0x18009d0b8  mov     [rbp+2F0h+var_220], 7FFFFFFFh
0x18009d0c3  mov     [rsp+3F0h+var_3A8], r13
0x18009d0c8  test    r12b, cl
0x18009d0cb  jz      short loc_18009D0FE
0x18009d0cd  lea     r9, [rbp+2F0h+var_210]; struct _LSAP_REG_PARAMETER *
0x18009d0d4  mov     rdx, r15; unsigned __int16 *
0x18009d0d7  lea     r8d, [r13+13h]; unsigned int
0x18009d0db  mov     rcx, rdi; HKEY
0x18009d0de  call    ?GetRegistryDwords@@YAJPEAUHKEY__@@PEAGKPEAU_LSAP_REG_PARAMETER@@@Z; GetRegistryDwords(HKEY__ *,ushort *,ulong,_LSAP_REG_PARAMETER *)
0x18009d0e3  call    IsLsapAdtInitializeCrashOnAuditFailPresent
0x18009d0e8  test    al, al
0x18009d0ea  jz      short loc_18009D0FE
0x18009d0ec  mov     ecx, [rbp+2F0h+arg_10]
0x18009d0f2  call    cs:__imp_LsapAdtInitializeCrashOnAuditFail
0x18009d0f9  nop     dword ptr [rax+rax+00h]
0x18009d0fe  test    bl, 2
0x18009d101  jz      short loc_18009D170
0x18009d103  lea     rcx, ?LsapGlobalLUAEnabled@@3KA; ulong LsapGlobalLUAEnabled
0x18009d10a  call    cs:__imp_CheckElevationEnabled
0x18009d111  nop     dword ptr [rax+rax+00h]
0x18009d116  lea     r9, [rsp+3F0h+var_380]; struct _LSAP_REG_PARAMETER *
0x18009d11b  mov     r8d, 0Fh; unsigned int
0x18009d121  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009d128  mov     rcx, rdi; HKEY
0x18009d12b  call    ?GetRegistryDwords@@YAJPEAUHKEY__@@PEAGKPEAU_LSAP_REG_PARAMETER@@@Z; GetRegistryDwords(HKEY__ *,ushort *,ulong,_LSAP_REG_PARAMETER *)
0x18009d130  call    LUAIsShadowAdminEnabled
0x18009d135  mov     cs:?LsapShadowAdminEnabled@@3HA, eax; int LsapShadowAdminEnabled
0x18009d13b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18009d142  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18009d147  test    al, al
0x18009d149  jz      short loc_18009D170
0x18009d14b  cmp     cs:?LsapShadowAdminEnabled@@3HA, r13d; int LsapShadowAdminEnabled
0x18009d152  jz      short loc_18009D170
0x18009d154  lea     r9, [rsp+3F0h+var_3B8]; struct _LSAP_REG_PARAMETER *
0x18009d159  mov     r8d, r12d; unsigned int
0x18009d15c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009d163  mov     rcx, rdi; HKEY
0x18009d166  call    ?GetRegistryDwords@@YAJPEAUHKEY__@@PEAGKPEAU_LSAP_REG_PARAMETER@@@Z; GetRegistryDwords(HKEY__ *,ushort *,ulong,_LSAP_REG_PARAMETER *)
0x18009d16b  call    ?LsapLoadRemoteAdminAllowList@@YAXXZ; LsapLoadRemoteAdminAllowList(void)
0x18009d170  cmp     cs:?LsapGlobalForceSCLogon@@3KA, r13d; ulong LsapGlobalForceSCLogon
0x18009d177  jz      short loc_18009D185
0x18009d179  cmp     cs:?LsapGlobalBootState@@3KA, r13d; ulong LsapGlobalBootState
0x18009d180  mov     eax, r12d
0x18009d183  jz      short loc_18009D188
0x18009d185  mov     eax, r13d
0x18009d188  mov     cs:?LsapGlobalForceSCLogon@@3KA, eax; ulong LsapGlobalForceSCLogon
0x18009d18e  test    ebx, ebx
0x18009d190  jns     short loc_18009D199
0x18009d192  xor     eax, eax
0x18009d194  jmp     loc_18009D6E9
0x18009d199  lea     rcx, ?LsapGlobalMachineName@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x18009d1a0  call    ?LsapGetComputerName@@YAJPEAU_UNICODE_STRING@@@Z; LsapGetComputerName(_UNICODE_STRING *)
0x18009d1a5  test    eax, eax
0x18009d1a7  js      loc_18009D6E9
0x18009d1ad  mov     ecx, 80h
0x18009d1b2  mov     [rbp+2F0h+arg_0], 80h
0x18009d1bc  call    LsapAllocate
0x18009d1c1  mov     cs:?pszPreferred@@3PEAGEA, rax; ushort * pszPreferred
0x18009d1c8  mov     r9, rax; unsigned __int16 *
0x18009d1cb  test    rax, rax
0x18009d1ce  jnz     short loc_18009D1D9
0x18009d1d0  mov     [rbp+2F0h+arg_0], r13d
0x18009d1d7  jmp     short loc_18009D1DD
0x18009d1d9  mov     [rax], r13w
0x18009d1dd  lea     rax, [rbp+2F0h+arg_0]
0x18009d1e4  mov     rdx, r15; unsigned __int16 *
0x18009d1e7  lea     r8, ?szPreferredPackage@@3PAGA; "Preferred"
0x18009d1ee  mov     [rsp+3F0h+phkResult], rax; unsigned int *
0x18009d1f3  call    ?GetRegistryString@@YAJPEAUHKEY__@@PEAG11PEAK@Z; GetRegistryString(HKEY__ *,ushort *,ushort *,ushort *,ulong *)
0x18009d1f8  mov     ebx, 0C0000023h
0x18009d1fd  cmp     eax, ebx
0x18009d1ff  jnz     short loc_18009D249
0x18009d201  mov     rcx, cs:?pszPreferred@@3PEAGEA; struct _RTL_BALANCED_NODE *
0x18009d208  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18009d20d  mov     ecx, [rbp+2F0h+arg_0]
0x18009d213  call    LsapAllocate
0x18009d218  mov     cs:?pszPreferred@@3PEAGEA, rax; ushort * pszPreferred
0x18009d21f  mov     rcx, rax; HKEY
0x18009d222  test    rax, rax
0x18009d225  jz      short loc_18009D254
0x18009d227  mov     [rax], r13w
0x18009d22b  lea     r8, ?szPreferredPackage@@3PAGA; "Preferred"
0x18009d232  lea     rax, [rbp+2F0h+arg_0]
0x18009d239  mov     r9, rcx; unsigned __int16 *
0x18009d23c  mov     rdx, r15; unsigned __int16 *
0x18009d23f  mov     [rsp+3F0h+phkResult], rax; unsigned int *
0x18009d244  call    ?GetRegistryString@@YAJPEAUHKEY__@@PEAG11PEAK@Z; GetRegistryString(HKEY__ *,ushort *,ushort *,ushort *,ulong *)
0x18009d249  test    eax, eax
0x18009d24b  jns     short loc_18009D265
0x18009d24d  mov     rcx, cs:?pszPreferred@@3PEAGEA; struct _RTL_BALANCED_NODE *
0x18009d254  test    rcx, rcx
0x18009d257  jz      short loc_18009D265
0x18009d259  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18009d25e  mov     cs:?pszPreferred@@3PEAGEA, r13; ushort * pszPreferred
0x18009d265  mov     ecx, 80h
0x18009d26a  mov     [rbp+2F0h+arg_0], 80h
0x18009d274  call    LsapAllocate
  ... truncated ...
```
