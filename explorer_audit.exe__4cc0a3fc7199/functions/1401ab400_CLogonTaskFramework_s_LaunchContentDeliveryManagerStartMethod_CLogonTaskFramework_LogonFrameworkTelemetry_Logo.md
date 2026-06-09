# CLogonTaskFramework::s_LaunchContentDeliveryManagerStartMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x1401ab400`
- end: `0x1401ac1ac`
- name: `?s_LaunchContentDeliveryManagerStartMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `3500`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `61`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140006e64`
- `0x140007e10`
- `0x140007e4c`
- `0x140009f84`
- `0x1400119c8`
- `0x1400193bc`
- `0x140019550`
- `0x14001eba8`
- `0x14001f554`
- `0x140029c80`
- `0x140030944`
- `0x140034d20`
- `0x1400632b0`
- `0x140063518`
- `0x14007bc08`
- `0x14007f010`
- `0x14007f074`
- `0x1400817d8`
- `0x14008247c`
- `0x1400851ac`
- `0x140088d98`
- `0x140091afc`
- `0x1400954e0`
- `0x1400957d8`
- `0x1400a4d00`
- `0x1400a57fc`
- `0x1400a584c`
- `0x1400a69d0`
- `0x1400a6e94`
- `0x1400a6ed0`
- `0x1400a7ee4`
- `0x1400ae46c`
- `0x1400f0ba8`
- `0x1401040e0`
- `0x140131210`
- `0x140135fb0`
- `0x140136020`
- `0x140137ac0`
- `0x1401385fc`
- `0x14014aaf0`
- `0x14014c0b4`
- `0x14014d0f0`
- `0x14014d968`
- `0x14014e810`
- `0x14015cfec`
- `0x14015df0c`
- `0x14015df68`
- `0x14015dfc4`
- `0x14015e020`
- `0x140185dcc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1401abfb2`
- `ntdll!RtlInitUnicodeString` at `0x1401abfb2`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateApplicationEntryPoint` at `0x1401ac082`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateApplicationEntryPoint` at `0x1401ac082`
- `SystemEventsBrokerClient!SebSignalOEMPreInstallEvent` at `0x1401ac0fe`
- `SystemEventsBrokerClient!SebSignalOEMPreInstallEvent` at `0x1401ac0fe`
- `SystemEventsBrokerClient!SebCreateOEMPreInstallEvent` at `0x1401abfde`
- `SystemEventsBrokerClient!SebCreateOEMPreInstallEvent` at `0x1401abfde`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x1401abeb9`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x1401abeb9`

## string_xrefs

- `0x1401ab56a`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ab65f`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ab6b4`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ab973`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ab9ec`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abb05`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abcac`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abdaf`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abed6`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abf5c`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abff5`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac097`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac115`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abfa3`: `ContentDeliveryManager.Background.RegistrationTask`
- `0x1401ab9a1`: `IsDisabledByCommercialControl`
- `0x1401ab9c7`: `IsDisabledByCommercialControl`
- `0x1401abeca`: `Failed to change BI session state to SessionOemPreinstallStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CLogonTaskFramework::s_LaunchContentDeliveryManagerStartMethod(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  struct CLogonTaskFramework *v2; // r13
  __int64 v3; // rdx
  const char *v4; // r9
  bool v5; // r12
  unsigned int *v6; // r15
  _QWORD *v7; // rax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  int refreshed; // eax
  wil::details::in1diag3 *v13; // rcx
  void *v14; // rcx
  _QWORD *v15; // rax
  const char *v16; // r9
  unsigned int v17; // r9d
  int v18; // eax
  int v19; // eax
  unsigned __int8 v20; // r13
  unsigned int v21; // r9d
  bool v22; // bl
  unsigned int v23; // r9d
  bool v24; // bl
  unsigned int v25; // r9d
  bool v26; // bl
  int v27; // eax
  const unsigned __int16 *v28; // rdx
  bool *v29; // r9
  int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rdx
  unsigned int v33; // eax
  unsigned __int8 v34; // bl
  char IsEnabled; // al
  __int64 v36; // rdx
  __int64 v37; // rdx
  wil::details::in1diag3 *v38; // rcx
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  int v42; // eax
  wil::details::in1diag3 *v43; // rcx
  __int64 v44; // rcx
  int v45; // eax
  wil::details::in1diag3 *v46; // rcx
  void *v47; // rcx
  const unsigned __int16 *v48; // rdx
  CreativeFramework::ContentDeliveryManagerSettings *v49; // rcx
  const unsigned __int16 *v50; // r8
  char v51; // cl
  unsigned int v52; // eax
  __int64 v53; // rdx
  CallerIdentity *v54; // rcx
  unsigned __int16 **v55; // r8
  int SinglePackageFullNameFromPackageFamilyName; // eax
  unsigned int v57; // ebx
  __int64 v58; // rdx
  int v60; // eax
  __int64 v61; // rdx
  int v62; // eax
  __int64 v63; // rdx
  int v64; // eax
  __int64 v65; // rdx
  __int64 v66; // rdx
  wil *v67; // rcx
  int v68; // ebx
  wil *v69; // rcx
  int v70; // ebx
  int *v71; // [rsp+20h] [rbp-138h]
  int v72; // [rsp+20h] [rbp-138h]
  int v73; // [rsp+20h] [rbp-138h]
  const char *v74; // [rsp+28h] [rbp-130h]
  bool v75; // [rsp+50h] [rbp-108h] BYREF
  unsigned __int16 v76[3]; // [rsp+51h] [rbp-107h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-100h] BYREF
  char v78; // [rsp+60h] [rbp-F8h] BYREF
  unsigned int v79; // [rsp+68h] [rbp-F0h] BYREF
  unsigned int v80; // [rsp+70h] [rbp-E8h] BYREF
  int v81; // [rsp+78h] [rbp-E0h] BYREF
  int v82; // [rsp+80h] [rbp-D8h] BYREF
  unsigned int v83; // [rsp+88h] [rbp-D0h] BYREF
  unsigned int v84; // [rsp+90h] [rbp-C8h] BYREF
  unsigned int v85; // [rsp+94h] [rbp-C4h] BYREF
  _QWORD v86[2]; // [rsp+98h] [rbp-C0h] BYREF
  char v87; // [rsp+A8h] [rbp-B0h]
  unsigned __int16 v88[4]; // [rsp+B0h] [rbp-A8h] BYREF
  __int64 v89; // [rsp+B8h] [rbp-A0h]
  __int64 v90; // [rsp+C0h] [rbp-98h]
  __int128 v91; // [rsp+D0h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-78h] BYREF
  __int128 v93; // [rsp+F0h] [rbp-68h] BYREF
  __int128 v94; // [rsp+100h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v2 = a1;
  *(_QWORD *)&v91 = a1;
  *(_QWORD *)&v94 = a1;
  v82 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(
                          &`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl'::`2'::impl,
                          a2) )
    CheckLogonFlagsForSpotlightOnboarding(*((unsigned int *)v2 + 54));
  v75 = 0;
  try
  {
    v5 = !EnterpriseFeatureControl::IsFeatureEnabled(0x2B5DB70u);
    v75 = v5;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x110B,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      v4);
    v5 = v75;
    v2 = (struct CLogonTaskFramework *)v94;
    *(_QWORD *)&v91 = v94;
  }
  if ( v5 )
  {
    LOBYTE(v3) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
      v3);
  }
  v6 = (unsigned int *)((char *)v2 + 216);
  *(_QWORD *)&DestinationString.Length = (char *)v2 + 216;
  DesktopSpotlightLogonTelemetry::TraceLoggingInfo("_logonTypeFlags=%x", *((_DWORD *)v2 + 54));
  pv = 0;
  v7 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v7 + 8LL, &v93);
  v8 = *((_DWORD *)v2 + 54);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(
                           &pv,
                           &v83)
            + 272LL) = v8;
  tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(&v83);
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
    v9);
  if ( (*((_BYTE *)v2 + 216) & 2) != 0 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(
                            &pv,
                            &v83)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(&v83);
    refreshed = s_RefreshUndockedDesktopSpotlightIfNeeded(&pv);
    v13 = retaddr;
    if ( refreshed < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x111A,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)refreshed,
        (int)v71);
    SaveOneTimeUpgrade(v13);
  }
  v14 = pv;
  if ( pv )
  {
    tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8);
    v14 = pv;
  }
  if ( v14 )
    tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>::Release(v14);
  LOBYTE(v11) = 3;
  LOBYTE(v10) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl'::`2'::impl,
    v10,
    v11);
  pv = 0;
  v15 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v15 + 8LL, &v93);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                          &pv,
                          &v79)
           + 297LL) = !v5;
  tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v79);
  if ( CLogonTaskFramework::s_isCDMSpotlightEnabled() )
  {
    if ( (int)SHRegGetBOOLWithREGSAM(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
                L"SubscribedContent-88000326Enabled",
                (unsigned int)v16,
                (int *)&v79) >= 0 )
    {
      v18 = SHRegSetBOOL(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
              L"SubscribedContent-88000326Enabled",
              0);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1132,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v18,
          v72);
    }
    if ( (int)SHRegGetBOOLWithREGSAM(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
                L"SubscribedContent-88000325Enabled",
                v17,
                (int *)&v79) >= 0 )
    {
      v19 = SHRegSetBOOL(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
              L"SubscribedContent-88000325Enabled",
              0);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1137,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v19,
          (int)v71);
    }
    try
    {
      winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings((winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings *)&v80);
      if ( !(unsigned int)_lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_::_lambda_invoker_cdecl_((const struct winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics *)&v80) )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                                &pv,
                                &v79)
                 + 279LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v79);
        s_EnableUndockedDesktopSpotlightInternal(&pv);
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v80);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1145,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        v16);
      v68 = wil::ResultFromCaughtException(v67);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                               &pv,
                               &v91)
                + 320LL) = v68;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v91);
      v5 = v75;
      *(_QWORD *)&v91 = v94;
      v6 = *(unsigned int **)&DestinationString.Length;
    }
  }
  try
  {
    v84 = 0;
    if ( (*v6 & 0x330A) == 2
      && (int)SHRegGetDWORD(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudRestore\\EarlyDownload",
                L"Status",
                &v84) >= 0
      && v84 == 1 )
    {
      v20 = 1;
      LOBYTE(v76[0]) = 1;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v79)
               + 328LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v79);
      v80 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
        L"WallpaperRestored",
        v21,
        (int *)&v80);
      v22 = v80 != 0;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v79)
               + 325LL) = v22;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v79);
      v79 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
        L"ThemeRestored",
        v23,
        (int *)&v79);
      v24 = v79 != 0;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v81)
               + 326LL) = v24;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v81);
      v81 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
        L"RestoreSpotlight",
        v25,
        &v81);
      v26 = v81 != 0;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v93)
               + 327LL) = v26;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v93);
      if ( (!v80 && !v79 || v81) && (!v80 && !v79 && !v81 || v81) )
        s_EnableUndockedDesktopSpotlightInternal(&pv);
    }
    else
    {
      v20 = 0;
      LOBYTE(v76[0]) = 0;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1170,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      v16);
    v70 = wil::ResultFromCaughtException(v69);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                             &pv,
                             &v93)
              + 320LL) = v70;
    tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v93);
    v5 = v75;
    v20 = v76[0];
    *(_QWORD *)&v91 = v94;
    v6 = *(unsigned int **)&DestinationString.Length;
  }
  v85 = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
              L"IsRestoreLogon",
              &v85) < 0
    || v85 != v20 )
  {
    v27 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
            L"IsRestoreLogon",
            v20);
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x117B,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v27,
        (int)v71);
    DesktopSpotlightLogonTelemetry::SpotlightRestoreLogon<bool &>(v76);
  }
  v83 = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
              L"IsDisabledByCommercialControl",
              &v83) < 0
    || v83 != v5 )
  {
    v30 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
            L"IsDisabledByCommercialControl",
            v5);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1184,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v30,
        (int)v71);
    DesktopSpotlightLogonTelemetry::SpotlightEnterpriseDisabledControl<bool &>(&v75);
  }
  if ( v5 || v20 || !(unsigned __int8)s_CanDesktopSpotlighBeTurnedOnForLogonType(*v6) )
    goto LABEL_100;
  DesktopSpotlightLogonTelemetry::TraceLoggingInfo("_logonTypeFlags=%x", *v6);
  v31 = *v6;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                           &pv,
                           &v93)
            + 272LL) = v31;
  tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v93);
  v33 = *v6;
  if ( (*v6 & 2) == 0 || (v33 & 4) != 0 )
  {
    if ( (v33 & 0x12) != 0x12 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::GetImpl'::`2'::impl) )
      {
        v79 = 0;
        if ( (unsigned int)SHRegGetDWORD(
                             HKEY_CURRENT_USER,
                             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
                             L"OneTimeUpgrade",
                             &v79) != -2147024894 )
          DesktopSpotlightLogonTelemetry::OneTimeUpgradeRegistryValue<unsigned long &>(&v79);
      }
      v80 = 0;
      if ( (unsigned int)SHRegGetDWORD(
                           HKEY_CURRENT_USER,
                           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
                           L"OneTimeUpgrade",
                           &v80) == -2147024894
        || v80 != 1 )
      {
        DesktopSpotlightLogonTelemetry::OneTimeUpgrade();
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                                &pv,
                                &v93)
                 + 324LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v93);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::GetImpl'::`2'::impl) )
        {
          tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>>(&v94);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::operator->(
                                  &v94,
                                  &v93)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>(&v93);
          if ( (_QWORD)v94 )
            tip2::details::shared_data<0,0,0>::complete_without_lock(v94 + 8);
          if ( !(unsigned int)CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 2) )
            SaveOneTimeUpgrade(v44);
          wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>(&v94);
        }
        else
        {
          v45 = CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 2);
          v46 = retaddr;
          if ( v45 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x11EC,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v45,
              (int)v71);
          SaveOneTimeUpgrade(v46);
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::GetImpl'::`2'::impl) )
          goto LABEL_100;
        DesktopSpotlightLogonTelemetry::OneTimeUpgradeWithValue<unsigned long const &>(&v82);
      }
      else
      {
        if ( !(unsigned __int8)ShouldRunPeriodicUpgrade() )
          goto LABEL_100;
        DesktopSpotlightLogonTelemetry::PeriodicUpgrade();
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                                &pv,
                                &v93)
                 + 329LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v93);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightPeriodicUpgradeInstrumentation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightPeriodicUpgradeInstrumentation>::GetImpl'::`2'::impl) )
        {
          tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>>(&v94);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::operator->(
                                  &v94,
                                  &v93)
                   + 273LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>(&v93);
          if ( (_QWORD)v94 )
            tip2::details::shared_data<0,0,0>::complete_without_lock(v94 + 8);
          if ( !(unsigned int)CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 3) )
            SavePeriodicUpgrade(v41);
          wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>(&v94);
        }
        else
        {
          v42 = CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 3);
          v43 = retaddr;
          if ( v42 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x120F,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v42,
              (int)v71);
          SavePeriodicUpgrade(v43);
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::GetImpl'::`2'::impl) )
          goto LABEL_100;
      }
      v40 = 0;
      goto LABEL_99;
    }
    v34 = 0;
  }
  else
  {
    v34 = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(
                          &`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl'::`2'::impl,
                          v32) )
  {
    if ( v34 )
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithFirstLogonNewUserStart();
    else
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithOneTimeUpgradeStart();
  }
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                          &pv,
                          &v93)
           + 276LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v93);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::GetImpl'::`2'::impl);
  v36 = 2 * (v34 ^ 1u);
  if ( IsEnabled )
  {
    if ( (unsigned int)CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, v36) )
      goto LABEL_64;
  }
  else
  {
    v39 = CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, v36);
    v38 = retaddr;
    if ( v39 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x11B2,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v39,
        (int)v71);
  }
  SaveOneTimeUpgrade(v38);
LABEL_64:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(
                          &`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl'::`2'::impl,
                          v37) )
  {
    if ( v34 )
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithFirstLogonNewUserComplete();
    else
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithOneTimeUpgradeComplete();
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v40) = 1;
LABEL_99:
    CLogonTaskFramework::LogAndSaveThemeAndWallpaperData(v40, *v6);
  }
LABEL_100:
  v47 = pv;
  if ( pv )
  {
    tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8);
    v47 = pv;
  }
  if ( v47 )
    tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>::Release(v47);
  v78 = 0;
  v86[0] = &v78;
  v86[1] = (char *)v76 + 1;
  v87 = 1;
  v76[0] = 0;
  v75 = 0;
  if ( (*v6 & 0x1200) == 0 )
  {
    if ( (*(_BYTE *)v6 & 2) == 0 )
    {
      if ( (int)CreativeFramework::ContentDeliveryManagerSettings::DoesSettingExist(
                  (CreativeFramework::ContentDeliveryManagerSettings *)v47,
                  v28,
                  v76,
                  v29) >= 0
        && LOBYTE(v76[0])
        && (int)CreativeFramework::ContentDeliveryManagerSettings::GetBoolSetting(
                  v49,
                  v48,
                  v50,
                  (bool)&v75,
                  (bool *)v71) >= 0 )
      {
        v51 = 2 - v75;
        HIBYTE(v76[0]) = v51;
      }
      else
      {
        v51 = HIBYTE(v76[0]);
      }
      if ( v51 && (v51 != 1 || (unsigned __int8)s_IsContentDeliveryManagerMaintenanceTaskRegistered()) )
        goto LABEL_131;
    }
    v78 = 1;
    v52 = BiChangeSessionState(5);
    if ( !wil::details::in1diag3::Log_IfNtStatusFailedMsg(
            retaddr,
            (void *)0x1248,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)v52,
            (int)"Failed to change BI session state to SessionOemPreinstallStart",
            v74) )
      *(_BYTE *)(v91 + 234) = 1;
    *(_QWORD *)v88 = 0;
    v89 = 0;
    v90 = 0;
    DestinationString = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v88, v53);
    v89 = -1;
    v90 = -1;
    SinglePackageFullNameFromPackageFamilyName = CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
                                                   v54,
                                                   v88,
                                                   v55);
    v57 = SinglePackageFullNameFromPackageFamilyName;
    if ( SinglePackageFullNameFromPackageFamilyName >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ContentDeliveryManager.Background.RegistrationTask");
      v93 = 0;
      v94 = 0;
      v60 = SebCreateOEMPreInstallEvent(&v93, *(_QWORD *)v88);
      v57 = v60;
      if ( v60 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1255,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v60,
          v73);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v88, v61);
        if ( !v87 )
          return v57;
        goto LABEL_119;
      }
      v82 = 199;
      v62 = BiPtAssociateApplicationEntryPoint(&v94, &DestinationString, &v93, 0);
      if ( v62 < 0 )
      {
        v57 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x1257,
                (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                (const char *)(unsigned int)v62,
                0);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v88, v63);
        if ( !v87 )
          return v57;
        goto LABEL_119;
      }
      v91 = v93;
      v64 = SebSignalOEMPreInstallEvent(&v91, *(_QWORD *)v88);
      v57 = v64;
      if ( v64 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v88, v65);
        goto LABEL_131;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x125A,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v64,
        0);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v88, v66);
      if ( v87 )
      {
LABEL_119:
        v87 = 0;
        _lambda_e644f3c3b127476a4047d2034a493bb3_::operator()(v86);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1250,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)SinglePackageFullNameFromPackageFamilyName,
        v73);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v88, v58);
      if ( v87 )
        goto LABEL_119;
    }
    return v57;
  }
  HIBYTE(v76[0]) = 2;
LABEL_131:
  if ( v87 )
  {
    v87 = 0;
    _lambda_e644f3c3b127476a4047d2034a493bb3_::operator()(v86);
  }
  return 0;
}

```

## disassembly

```asm
0x1401ab400  push    rbx
0x1401ab402  push    rdi
0x1401ab403  push    r12
0x1401ab405  push    r13
0x1401ab407  push    r14
0x1401ab409  push    r15
0x1401ab40b  sub     rsp, 128h
0x1401ab412  mov     rax, cs:__security_cookie
0x1401ab419  xor     rax, rsp
0x1401ab41c  mov     [rsp+158h+var_48], rax
0x1401ab424  mov     r13, rcx
0x1401ab427  mov     qword ptr [rsp+158h+var_88], rcx
0x1401ab42f  mov     qword ptr [rsp+158h+var_58], rcx
0x1401ab437  mov     [rsp+158h+var_D8], 1
0x1401ab442  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl(void)'::`2'::impl
0x1401ab449  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(void)
0x1401ab44e  xor     edi, edi
0x1401ab450  test    al, al
0x1401ab452  jz      short loc_1401AB460
0x1401ab454  mov     ecx, [r13+0D8h]
0x1401ab45b  call    CheckLogonFlagsForSpotlightOnboarding
0x1401ab460  mov     [rsp+158h+var_108], dil
0x1401ab465  mov     ecx, 2B5DB70h; unsigned int
0x1401ab46a  call    ?IsFeatureEnabled@EnterpriseFeatureControl@@SA_NK@Z; EnterpriseFeatureControl::IsFeatureEnabled(ulong)
0x1401ab46f  mov     r12b, al
0x1401ab472  xor     r12b, 1
0x1401ab476  mov     [rsp+158h+var_108], r12b
0x1401ab47b  jmp     short loc_1401AB494
0x1401ab47d  xor     edi, edi
0x1401ab47f  mov     r12b, [rsp+158h+var_108]
0x1401ab484  mov     r13, qword ptr [rsp+158h+var_58]
0x1401ab48c  mov     qword ptr [rsp+158h+var_88], r13
0x1401ab494  test    r12b, r12b
0x1401ab497  jz      short loc_1401AB4A7
0x1401ab499  mov     dl, 1
0x1401ab49b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl(void)'::`2'::impl
0x1401ab4a2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401ab4a7  lea     r15, [r13+0D8h]
0x1401ab4ae  mov     qword ptr [rsp+158h+DestinationString.Length], r15
0x1401ab4b6  mov     edx, [r15]
0x1401ab4b9  lea     rcx, aLogontypeflags_0; "_logonTypeFlags=%x"
0x1401ab4c0  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x1401ab4c5  mov     [rsp+158h+pv], rdi
0x1401ab4ca  lea     rcx, [rsp+158h+pv]
0x1401ab4cf  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::ensure_data(void)
0x1401ab4d4  mov     rcx, [rax]
0x1401ab4d7  add     rcx, 8
0x1401ab4db  lea     rdx, [rsp+158h+var_68]
0x1401ab4e3  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1401ab4e8  nop
0x1401ab4e9  mov     ebx, [r15]
0x1401ab4ec  lea     rdx, [rsp+158h+var_D0]
0x1401ab4f4  lea     rcx, [rsp+158h+pv]
0x1401ab4f9  call    ??C?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab4fe  mov     rdx, [rax]
0x1401ab501  mov     [rdx+110h], ebx
0x1401ab507  lea     rcx, [rsp+158h+var_D0]
0x1401ab50f  call    ??1?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(void)
0x1401ab514  mov     dl, 1
0x1401ab516  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl(void)'::`2'::impl
0x1401ab51d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401ab522  test    byte ptr [r15], 2
0x1401ab526  jz      short loc_1401AB580
0x1401ab528  lea     rdx, [rsp+158h+var_D0]
0x1401ab530  lea     rcx, [rsp+158h+pv]
0x1401ab535  call    ??C?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab53a  mov     rcx, [rax]
0x1401ab53d  mov     byte ptr [rcx+114h], 1
0x1401ab544  lea     rcx, [rsp+158h+var_D0]
0x1401ab54c  call    ??1?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(void)
0x1401ab551  lea     rcx, [rsp+158h+pv]
0x1401ab556  call    ?s_RefreshUndockedDesktopSpotlightIfNeeded@@YAJAEAV?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@@Z; s_RefreshUndockedDesktopSpotlightIfNeeded(tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>> &)
0x1401ab55b  mov     rcx, [rsp+158h]; this
0x1401ab563  test    eax, eax
0x1401ab565  jns     short loc_1401AB57B
0x1401ab567  mov     r9d, eax; char *
0x1401ab56a  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401ab571  mov     edx, 111Ah; void *
0x1401ab576  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401ab57b  call    SaveOneTimeUpgrade
0x1401ab580  mov     rcx, [rsp+158h+pv]
0x1401ab585  test    rcx, rcx
0x1401ab588  jz      short loc_1401AB598
0x1401ab58a  add     rcx, 8
0x1401ab58e  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1401ab593  mov     rcx, [rsp+158h+pv]; pv
0x1401ab598  test    rcx, rcx
0x1401ab59b  jz      short loc_1401AB5A2
0x1401ab59d  call    ?Release@?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>::Release(void)
0x1401ab5a2  mov     r8b, 3
0x1401ab5a5  mov     dl, 1
0x1401ab5a7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl(void)'::`2'::impl
0x1401ab5ae  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401ab5b3  mov     [rsp+158h+pv], rdi
0x1401ab5b8  lea     rcx, [rsp+158h+pv]
0x1401ab5bd  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::ensure_data(void)
0x1401ab5c2  mov     rcx, [rax]
0x1401ab5c5  add     rcx, 8
0x1401ab5c9  lea     rdx, [rsp+158h+var_68]
0x1401ab5d1  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1401ab5d6  nop
0x1401ab5d7  test    r12b, r12b
0x1401ab5da  setz    bl
0x1401ab5dd  lea     rdx, [rsp+158h+var_F0]
0x1401ab5e2  lea     rcx, [rsp+158h+pv]
0x1401ab5e7  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab5ec  mov     rcx, [rax]
0x1401ab5ef  mov     [rcx+129h], bl
0x1401ab5f5  lea     rcx, [rsp+158h+var_F0]
0x1401ab5fa  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab5ff  nop
0x1401ab600  call    ?s_isCDMSpotlightEnabled@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_isCDMSpotlightEnabled(void)
0x1401ab605  mov     r14, 0FFFFFFFF80000001h
0x1401ab60c  test    al, al
0x1401ab60e  jz      loc_1401AB717
0x1401ab614  lea     rax, [rsp+158h+var_F0]
0x1401ab619  mov     [rsp+158h+var_138], rax; int
0x1401ab61e  lea     r8, aSubscribedcont_0; "SubscribedContent-88000326Enabled"
0x1401ab625  lea     rbx, aSoftwareMicros_45; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401ab62c  mov     rdx, rbx; unsigned __int16 *
0x1401ab62f  mov     rcx, r14; HKEY
0x1401ab632  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401ab637  test    eax, eax
0x1401ab639  js      short loc_1401AB670
0x1401ab63b  xor     r9d, r9d; int
0x1401ab63e  lea     r8, aSubscribedcont_0; "SubscribedContent-88000326Enabled"
0x1401ab645  mov     rdx, rbx; unsigned __int16 *
0x1401ab648  mov     rcx, r14; HKEY
0x1401ab64b  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1401ab650  mov     rcx, [rsp+158h]; this
0x1401ab658  test    eax, eax
0x1401ab65a  jns     short loc_1401AB670
0x1401ab65c  mov     r9d, eax; char *
0x1401ab65f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401ab666  mov     edx, 1132h; void *
0x1401ab66b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401ab670  lea     rax, [rsp+158h+var_F0]
0x1401ab675  mov     [rsp+158h+var_138], rax; int
0x1401ab67a  lea     r8, aSubscribedcont; "SubscribedContent-88000325Enabled"
0x1401ab681  mov     rdx, rbx; unsigned __int16 *
0x1401ab684  mov     rcx, r14; HKEY
0x1401ab687  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401ab68c  test    eax, eax
0x1401ab68e  js      short loc_1401AB6C5
0x1401ab690  xor     r9d, r9d; int
0x1401ab693  lea     r8, aSubscribedcont; "SubscribedContent-88000325Enabled"
0x1401ab69a  mov     rdx, rbx; unsigned __int16 *
0x1401ab69d  mov     rcx, r14; HKEY
0x1401ab6a0  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1401ab6a5  mov     rcx, [rsp+158h]; this
0x1401ab6ad  test    eax, eax
0x1401ab6af  jns     short loc_1401AB6C5
0x1401ab6b1  mov     r9d, eax; char *
0x1401ab6b4  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401ab6bb  mov     edx, 1137h; void *
0x1401ab6c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401ab6c5  lea     rcx, [rsp+158h+var_E8]; this
0x1401ab6ca  call    ??0UserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings(void)
0x1401ab6cf  nop
0x1401ab6d0  lea     rcx, [rsp+158h+var_E8]; struct winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics *
0x1401ab6d5  call    ?_lambda_invoker_cdecl_@_lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_@@CA@AEBUIPersonalizedOffersSettingsStatics@UserProfile@System@WindowsUdk@winrt@@@Z; _lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_::_lambda_invoker_cdecl_(winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics const &)
0x1401ab6da  test    eax, eax
0x1401ab6dc  jnz     short loc_1401AB70C
0x1401ab6de  lea     rdx, [rsp+158h+var_F0]
0x1401ab6e3  lea     rcx, [rsp+158h+pv]
0x1401ab6e8  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab6ed  mov     rcx, [rax]
0x1401ab6f0  mov     byte ptr [rcx+117h], 1
0x1401ab6f7  lea     rcx, [rsp+158h+var_F0]
0x1401ab6fc  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab701  lea     rcx, [rsp+158h+pv]
0x1401ab706  call    s_EnableUndockedDesktopSpotlightInternal
0x1401ab70b  nop
0x1401ab70c  lea     rcx, [rsp+158h+var_E8]
0x1401ab711  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1401ab716  nop
0x1401ab717  jmp     short loc_1401AB73F
0x1401ab719  xor     edi, edi
0x1401ab71b  mov     r14, 0FFFFFFFF80000001h
0x1401ab722  mov     r12b, [rsp+158h+var_108]
0x1401ab727  mov     rax, qword ptr [rsp+158h+var_58]
0x1401ab72f  mov     qword ptr [rsp+158h+var_88], rax
0x1401ab737  mov     r15, qword ptr [rsp+158h+DestinationString.Length]
0x1401ab73f  mov     [rsp+158h+var_C8], edi
0x1401ab746  mov     eax, [r15]
0x1401ab749  and     eax, 330Ah
0x1401ab74e  cmp     eax, 2
0x1401ab751  jnz     loc_1401AB90D
0x1401ab757  lea     r9, [rsp+158h+var_C8]; unsigned int *
0x1401ab75f  lea     r8, aStatus; "Status"
0x1401ab766  lea     rdx, aSoftwareMicros_118; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401ab76d  mov     rcx, r14; HKEY
0x1401ab770  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1401ab775  test    eax, eax
0x1401ab777  js      loc_1401AB90D
0x1401ab77d  cmp     [rsp+158h+var_C8], 1
0x1401ab785  jnz     loc_1401AB90D
0x1401ab78b  mov     r13b, 1
0x1401ab78e  mov     byte ptr [rsp+158h+var_107], r13b
0x1401ab793  lea     rdx, [rsp+158h+var_F0]
0x1401ab798  lea     rcx, [rsp+158h+pv]
0x1401ab79d  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab7a2  mov     rcx, [rax]
0x1401ab7a5  mov     [rcx+148h], r13b
0x1401ab7ac  lea     rcx, [rsp+158h+var_F0]
0x1401ab7b1  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab7b6  nop
0x1401ab7b7  mov     [rsp+158h+var_E8], edi
0x1401ab7bb  lea     rax, [rsp+158h+var_E8]
0x1401ab7c0  mov     [rsp+158h+var_138], rax; int *
0x1401ab7c5  lea     r8, aWallpaperresto; "WallpaperRestored"
0x1401ab7cc  lea     rdx, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401ab7d3  mov     rcx, r14; HKEY
0x1401ab7d6  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401ab7db  cmp     [rsp+158h+var_E8], edi
0x1401ab7df  setnz   bl
0x1401ab7e2  lea     rdx, [rsp+158h+var_F0]
0x1401ab7e7  lea     rcx, [rsp+158h+pv]
0x1401ab7ec  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab7f1  mov     rcx, [rax]
0x1401ab7f4  mov     [rcx+145h], bl
0x1401ab7fa  lea     rcx, [rsp+158h+var_F0]
0x1401ab7ff  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab804  mov     [rsp+158h+var_F0], edi
0x1401ab808  lea     rax, [rsp+158h+var_F0]
0x1401ab80d  mov     [rsp+158h+var_138], rax; int *
0x1401ab812  lea     r8, aThemerestored; "ThemeRestored"
0x1401ab819  lea     rdx, aSoftwareMicros_60; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401ab820  mov     rcx, r14; HKEY
0x1401ab823  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401ab828  cmp     [rsp+158h+var_F0], edi
0x1401ab82c  setnz   bl
0x1401ab82f  lea     rdx, [rsp+158h+var_E0]
0x1401ab834  lea     rcx, [rsp+158h+pv]
0x1401ab839  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab83e  mov     rcx, [rax]
0x1401ab841  mov     [rcx+146h], bl
0x1401ab847  lea     rcx, [rsp+158h+var_E0]
0x1401ab84c  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab851  mov     [rsp+158h+var_E0], edi
0x1401ab855  lea     rax, [rsp+158h+var_E0]
0x1401ab85a  mov     [rsp+158h+var_138], rax; int *
0x1401ab85f  lea     r8, aRestorespotlig; "RestoreSpotlight"
0x1401ab866  lea     rdx, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401ab86d  mov     rcx, r14; HKEY
0x1401ab870  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401ab875  cmp     [rsp+158h+var_E0], edi
0x1401ab879  setnz   bl
0x1401ab87c  lea     rdx, [rsp+158h+var_68]
0x1401ab884  lea     rcx, [rsp+158h+pv]
0x1401ab889  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab88e  mov     rcx, [rax]
0x1401ab891  mov     [rcx+147h], bl
0x1401ab897  lea     rcx, [rsp+158h+var_68]
0x1401ab89f  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab8a4  cmp     [rsp+158h+var_E8], edi
0x1401ab8a8  jnz     short loc_1401AB8B0
0x1401ab8aa  cmp     [rsp+158h+var_F0], edi
0x1401ab8ae  jz      short loc_1401AB8B6
0x1401ab8b0  cmp     [rsp+158h+var_E0], edi
0x1401ab8b4  jz      short loc_1401AB8DE
0x1401ab8b6  cmp     [rsp+158h+var_E0], edi
0x1401ab8ba  setnz   al
0x1401ab8bd  cmp     [rsp+158h+var_E8], edi
0x1401ab8c1  jnz     short loc_1401AB8CF
0x1401ab8c3  cmp     [rsp+158h+var_F0], edi
0x1401ab8c7  jnz     short loc_1401AB8CF
0x1401ab8c9  cmp     [rsp+158h+var_E0], edi
0x1401ab8cd  jz      short loc_1401AB8D3
0x1401ab8cf  test    al, al
0x1401ab8d1  jz      short loc_1401AB8DE
0x1401ab8d3  lea     rcx, [rsp+158h+pv]
0x1401ab8d8  call    s_EnableUndockedDesktopSpotlightInternal
0x1401ab8dd  nop
0x1401ab8de  jmp     short loc_1401AB915
0x1401ab8e0  xor     edi, edi
0x1401ab8e2  mov     r14, 0FFFFFFFF80000001h
0x1401ab8e9  mov     r12b, [rsp+158h+var_108]
0x1401ab8ee  mov     r13b, byte ptr [rsp+158h+var_107]
0x1401ab8f3  mov     rax, qword ptr [rsp+158h+var_58]
0x1401ab8fb  mov     qword ptr [rsp+158h+var_88], rax
0x1401ab903  mov     r15, qword ptr [rsp+158h+DestinationString.Length]
0x1401ab90b  jmp     short loc_1401AB915
0x1401ab90d  mov     r13b, dil
0x1401ab910  mov     byte ptr [rsp+158h+var_107], dil
0x1401ab915  movzx   ebx, r13b
0x1401ab919  mov     [rsp+158h+var_C4], edi
0x1401ab920  lea     r9, [rsp+158h+var_C4]; unsigned int *
0x1401ab928  lea     r8, aIsrestorelogon; "IsRestoreLogon"
0x1401ab92f  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401ab936  mov     rcx, r14; HKEY
0x1401ab939  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1401ab93e  test    eax, eax
0x1401ab940  js      short loc_1401AB94B
0x1401ab942  cmp     [rsp+158h+var_C4], ebx
0x1401ab949  jz      short loc_1401AB98E
0x1401ab94b  mov     r9d, ebx; unsigned int
0x1401ab94e  lea     r8, aIsrestorelogon; "IsRestoreLogon"
0x1401ab955  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401ab95c  mov     rcx, r14; HKEY
  ... truncated ...
```
