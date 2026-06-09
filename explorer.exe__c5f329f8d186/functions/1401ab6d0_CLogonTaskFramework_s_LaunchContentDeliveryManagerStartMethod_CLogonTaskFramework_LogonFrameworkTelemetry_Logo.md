# CLogonTaskFramework::s_LaunchContentDeliveryManagerStartMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x1401ab6d0`
- end: `0x1401ac489`
- name: `?s_LaunchContentDeliveryManagerStartMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `3513`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `62`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140006f8c`
- `0x14000714c`
- `0x14000d768`
- `0x14001076c`
- `0x1400107a8`
- `0x1400116b8`
- `0x14001b2c8`
- `0x140023118`
- `0x140027508`
- `0x1400327a4`
- `0x140033f38`
- `0x14004856c`
- `0x140066ba0`
- `0x140066e28`
- `0x1400816c4`
- `0x140084830`
- `0x140084894`
- `0x140087688`
- `0x1400896ec`
- `0x14008ae68`
- `0x14008e760`
- `0x140096f2c`
- `0x14009ac68`
- `0x14009ad38`
- `0x1400aae5c`
- `0x1400ab8b0`
- `0x1400ab8d4`
- `0x1400ab924`
- `0x1400acaec`
- `0x1400acdf8`
- `0x1400ace34`
- `0x1400add54`
- `0x1400b4804`
- `0x1400f93dc`
- `0x14010e160`
- `0x14013d0f0`
- `0x140142034`
- `0x1401420a4`
- `0x140143c2c`
- `0x140144800`
- `0x140155290`
- `0x1401566fc`
- `0x140157394`
- `0x140157c4c`
- `0x140158938`
- `0x14016791c`
- `0x14016878c`
- `0x1401687e8`
- `0x140168844`
- `0x1401688a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1401ac276`
- `ntdll!RtlInitUnicodeString` at `0x1401ac276`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateApplicationEntryPoint` at `0x1401ac352`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateApplicationEntryPoint` at `0x1401ac352`
- `SystemEventsBrokerClient!SebSignalOEMPreInstallEvent` at `0x1401ac3d4`
- `SystemEventsBrokerClient!SebSignalOEMPreInstallEvent` at `0x1401ac3d4`
- `SystemEventsBrokerClient!SebCreateOEMPreInstallEvent` at `0x1401ac2a8`
- `SystemEventsBrokerClient!SebCreateOEMPreInstallEvent` at `0x1401ac2a8`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x1401ac177`
- `api-ms-win-core-biplmapi-l1-1-0!BiChangeSessionState` at `0x1401ac177`

## string_xrefs

- `0x1401ab83a`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ab92f`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ab984`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abc43`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abcbc`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abdd5`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401abf73`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac06d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac19a`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac220`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac2c5`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac36d`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac3f1`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401ac267`: `ContentDeliveryManager.Background.RegistrationTask`
- `0x1401ac18e`: `Failed to change BI session state to SessionOemPreinstallStart`
- `0x1401abc71`: `IsDisabledByCommercialControl`
- `0x1401abc97`: `IsDisabledByCommercialControl`

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
  CallerIdentity *v53; // rcx
  unsigned __int16 **v54; // r8
  int SinglePackageFullNameFromPackageFamilyName; // eax
  unsigned int v56; // ebx
  int v58; // eax
  int v59; // eax
  int v60; // eax
  wil *v61; // rcx
  int v62; // ebx
  wil *v63; // rcx
  int v64; // ebx
  int *v65; // [rsp+20h] [rbp-138h]
  int v66; // [rsp+20h] [rbp-138h]
  int v67; // [rsp+20h] [rbp-138h]
  const char *v68; // [rsp+28h] [rbp-130h]
  bool v69; // [rsp+50h] [rbp-108h] BYREF
  unsigned __int16 v70[3]; // [rsp+51h] [rbp-107h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-100h] BYREF
  char v72; // [rsp+60h] [rbp-F8h] BYREF
  unsigned int v73; // [rsp+68h] [rbp-F0h] BYREF
  unsigned int v74; // [rsp+70h] [rbp-E8h] BYREF
  int v75; // [rsp+78h] [rbp-E0h] BYREF
  int v76; // [rsp+80h] [rbp-D8h] BYREF
  unsigned int v77; // [rsp+88h] [rbp-D0h] BYREF
  unsigned int v78; // [rsp+90h] [rbp-C8h] BYREF
  unsigned int v79; // [rsp+94h] [rbp-C4h] BYREF
  _QWORD v80[2]; // [rsp+98h] [rbp-C0h] BYREF
  char v81; // [rsp+A8h] [rbp-B0h]
  unsigned __int16 v82[4]; // [rsp+B0h] [rbp-A8h] BYREF
  __int64 v83; // [rsp+B8h] [rbp-A0h]
  __int64 v84; // [rsp+C0h] [rbp-98h]
  __int128 v85; // [rsp+D0h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-78h] BYREF
  __int128 v87; // [rsp+F0h] [rbp-68h] BYREF
  __int128 v88; // [rsp+100h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v2 = a1;
  *(_QWORD *)&v85 = a1;
  *(_QWORD *)&v88 = a1;
  v76 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl'::`2'::impl,
                          a2) )
    CheckLogonFlagsForSpotlightOnboarding(*((unsigned int *)v2 + 54));
  v69 = 0;
  try
  {
    v5 = !EnterpriseFeatureControl::IsFeatureEnabled(0x2B5DB70u);
    v69 = v5;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x110F,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      v4);
    v5 = v69;
    v2 = (struct CLogonTaskFramework *)v88;
    *(_QWORD *)&v85 = v88;
  }
  if ( v5 )
  {
    LOBYTE(v3) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
      v3);
  }
  v6 = (unsigned int *)((char *)v2 + 216);
  *(_QWORD *)&DestinationString.Length = (char *)v2 + 216;
  DesktopSpotlightLogonTelemetry::TraceLoggingInfo("_logonTypeFlags=%x", *((_DWORD *)v2 + 54));
  pv = 0;
  v7 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v7 + 8LL, &v87);
  v8 = *((_DWORD *)v2 + 54);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(
                           &pv,
                           &v77)
            + 272LL) = v8;
  tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(&v77);
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl'::`2'::impl,
    v9);
  if ( (*((_BYTE *)v2 + 216) & 2) != 0 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(
                            &pv,
                            &v77)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(&v77);
    refreshed = s_RefreshUndockedDesktopSpotlightIfNeeded(&pv);
    v13 = retaddr;
    if ( refreshed < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x111E,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)refreshed,
        (int)v65);
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
    `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl'::`2'::impl,
    v10,
    v11);
  pv = 0;
  v15 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::ensure_data(&pv);
  tip2::details::shared_data<0,0,0>::start(*v15 + 8LL, &v87);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                          &pv,
                          &v73)
           + 297LL) = !v5;
  tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v73);
  if ( CLogonTaskFramework::s_isCDMSpotlightEnabled() )
  {
    if ( (int)SHRegGetBOOLWithREGSAM(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
                L"SubscribedContent-88000326Enabled",
                (unsigned int)v16,
                (int *)&v73) >= 0 )
    {
      v18 = SHRegSetBOOL(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
              L"SubscribedContent-88000326Enabled",
              0);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1136,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v18,
          v66);
    }
    if ( (int)SHRegGetBOOLWithREGSAM(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
                L"SubscribedContent-88000325Enabled",
                v17,
                (int *)&v73) >= 0 )
    {
      v19 = SHRegSetBOOL(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager",
              L"SubscribedContent-88000325Enabled",
              0);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x113B,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v19,
          (int)v65);
    }
    try
    {
      winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings((winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings *)&v74);
      if ( !(unsigned int)_lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_::_lambda_invoker_cdecl_((const struct winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics *)&v74) )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                                &pv,
                                &v73)
                 + 279LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v73);
        s_EnableUndockedDesktopSpotlightInternal(&pv);
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v74);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x1149,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        v16);
      v62 = wil::ResultFromCaughtException(v61);
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                               &pv,
                               &v85)
                + 320LL) = v62;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v85);
      v5 = v69;
      *(_QWORD *)&v85 = v88;
      v6 = *(unsigned int **)&DestinationString.Length;
    }
  }
  try
  {
    v78 = 0;
    if ( (*v6 & 0x330A) == 2
      && (int)SHRegGetDWORD(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudRestore\\EarlyDownload",
                L"Status",
                &v78) >= 0
      && v78 == 1 )
    {
      v20 = 1;
      LOBYTE(v70[0]) = 1;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v73)
               + 328LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v73);
      v74 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
        L"WallpaperRestored",
        v21,
        (int *)&v74);
      v22 = v74 != 0;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v73)
               + 325LL) = v22;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v73);
      v73 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
        L"ThemeRestored",
        v23,
        (int *)&v73);
      v24 = v73 != 0;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v75)
               + 326LL) = v24;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v75);
      v75 = 0;
      SHRegGetBOOLWithREGSAM(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
        L"RestoreSpotlight",
        v25,
        &v75);
      v26 = v75 != 0;
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                              &pv,
                              &v87)
               + 327LL) = v26;
      tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v87);
      if ( (!v74 && !v73 || v75) && (!v74 && !v73 && !v75 || v75) )
        s_EnableUndockedDesktopSpotlightInternal(&pv);
    }
    else
    {
      v20 = 0;
      LOBYTE(v70[0]) = 0;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1174,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      v16);
    v64 = wil::ResultFromCaughtException(v63);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                             &pv,
                             &v87)
              + 320LL) = v64;
    tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v87);
    v5 = v69;
    v20 = v70[0];
    *(_QWORD *)&v85 = v88;
    v6 = *(unsigned int **)&DestinationString.Length;
  }
  v79 = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
              L"IsRestoreLogon",
              &v79) < 0
    || v79 != v20 )
  {
    v27 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
            L"IsRestoreLogon",
            v20);
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x117F,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v27,
        (int)v65);
    DesktopSpotlightLogonTelemetry::SpotlightRestoreLogon<bool &>(v70);
  }
  v77 = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
              L"IsDisabledByCommercialControl",
              &v77) < 0
    || v77 != v5 )
  {
    v30 = SHRegSetDWORD(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
            L"IsDisabledByCommercialControl",
            v5);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1188,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v30,
        (int)v65);
    DesktopSpotlightLogonTelemetry::SpotlightEnterpriseDisabledControl<bool &>(&v69);
  }
  if ( v5 || v20 || !(unsigned __int8)s_CanDesktopSpotlighBeTurnedOnForLogonType(*v6) )
    goto LABEL_96;
  DesktopSpotlightLogonTelemetry::TraceLoggingInfo("_logonTypeFlags=%x", *v6);
  v31 = *v6;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                           &pv,
                           &v87)
            + 272LL) = v31;
  tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v87);
  v33 = *v6;
  if ( (*v6 & 2) == 0 || (v33 & 4) != 0 )
  {
    if ( (v33 & 0x12) != 0x12 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::GetImpl'::`2'::impl) )
      {
        v73 = 0;
        if ( (unsigned int)SHRegGetDWORD(
                             HKEY_CURRENT_USER,
                             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
                             L"OneTimeUpgrade",
                             &v73) != -2147024894 )
          DesktopSpotlightLogonTelemetry::OneTimeUpgradeRegistryValue<unsigned long &>(&v73);
      }
      v74 = 0;
      if ( (unsigned int)SHRegGetDWORD(
                           HKEY_CURRENT_USER,
                           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DesktopSpotlight\\Settings",
                           L"OneTimeUpgrade",
                           &v74) == -2147024894
        || v74 != 1 )
      {
        DesktopSpotlightLogonTelemetry::OneTimeUpgrade();
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                                &pv,
                                &v87)
                 + 324LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v87);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::GetImpl'::`2'::impl) )
        {
          tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>>(&v88);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::operator->(
                                  &v88,
                                  &v87)
                   + 272LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>(&v87);
          tip2::tip_test<tip2::details::merged_data<_tip_s_RetryEnablementTipTest,_tip_s_RetryEnablementTipTest>>::complete(&v88);
          if ( !(unsigned int)CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 2) )
            SaveOneTimeUpgrade(v44);
          wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>(&v88);
        }
        else
        {
          v45 = CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 2);
          v46 = retaddr;
          if ( v45 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x11F0,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v45,
              (int)v65);
          SaveOneTimeUpgrade(v46);
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::GetImpl'::`2'::impl) )
          goto LABEL_96;
        DesktopSpotlightLogonTelemetry::OneTimeUpgradeWithValue<unsigned long const &>(&v76);
      }
      else
      {
        if ( !(unsigned __int8)ShouldRunPeriodicUpgrade() )
          goto LABEL_96;
        DesktopSpotlightLogonTelemetry::PeriodicUpgrade();
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                                &pv,
                                &v87)
                 + 329LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v87);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightPeriodicUpgradeInstrumentation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightPeriodicUpgradeInstrumentation>::GetImpl'::`2'::impl) )
        {
          tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>>(&v88);
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::operator->(
                                  &v88,
                                  &v87)
                   + 273LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>::~test_data_control<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>>(&v87);
          tip2::tip_test<tip2::details::merged_data<_tip_s_RetryEnablementTipTest,_tip_s_RetryEnablementTipTest>>::complete(&v88);
          if ( !(unsigned int)CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 3) )
            SavePeriodicUpgrade(v41);
          wil::com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip,_tip_DesktopSpotlightOneTimeOrPeriodicUpgradeTip>,wil::err_returncode_policy>(&v88);
        }
        else
        {
          v42 = CLogonTaskFramework::s_EnableUndockedDesktopSpotlight(&pv, 3);
          v43 = retaddr;
          if ( v42 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1213,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v42,
              (int)v65);
          SavePeriodicUpgrade(v43);
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::GetImpl'::`2'::impl) )
          goto LABEL_96;
      }
      v40 = 0;
      goto LABEL_95;
    }
    v34 = 0;
  }
  else
  {
    v34 = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl'::`2'::impl,
                          v32) )
  {
    if ( v34 )
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithFirstLogonNewUserStart();
    else
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithOneTimeUpgradeStart();
  }
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(
                          &pv,
                          &v87)
           + 276LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(&v87);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightOneTimeUpgradeInstrumentation>::GetImpl'::`2'::impl);
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
        (void *)0x11B6,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v39,
        (int)v65);
  }
  SaveOneTimeUpgrade(v38);
LABEL_64:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl'::`2'::impl,
                          v37) )
  {
    if ( v34 )
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithFirstLogonNewUserComplete();
    else
      DesktopSpotlightLogonTelemetry::DesktopSpotlightOnboardingWithOneTimeUpgradeComplete();
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightDeviceInfoTelemetry>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v40) = 1;
LABEL_95:
    CLogonTaskFramework::LogAndSaveThemeAndWallpaperData(v40, *v6);
  }
LABEL_96:
  v47 = pv;
  if ( pv )
  {
    tip2::details::shared_data<0,0,0>::complete_without_lock((char *)pv + 8);
    v47 = pv;
  }
  if ( v47 )
    tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>::Release(v47);
  v72 = 0;
  v80[0] = &v72;
  v80[1] = (char *)v70 + 1;
  v81 = 1;
  v70[0] = 0;
  v69 = 0;
  if ( (*v6 & 0x1200) == 0 )
  {
    if ( (*(_BYTE *)v6 & 2) == 0 )
    {
      if ( (int)CreativeFramework::ContentDeliveryManagerSettings::DoesSettingExist(
                  (CreativeFramework::ContentDeliveryManagerSettings *)v47,
                  v28,
                  v70,
                  v29) >= 0
        && LOBYTE(v70[0])
        && (int)CreativeFramework::ContentDeliveryManagerSettings::GetBoolSetting(
                  v49,
                  v48,
                  v50,
                  (bool)&v69,
                  (bool *)v65) >= 0 )
      {
        v51 = 2 - v69;
        HIBYTE(v70[0]) = v51;
      }
      else
      {
        v51 = HIBYTE(v70[0]);
      }
      if ( v51 && (v51 != 1 || (unsigned __int8)s_IsContentDeliveryManagerMaintenanceTaskRegistered()) )
        goto LABEL_127;
    }
    v72 = 1;
    v52 = BiChangeSessionState(5);
    if ( !wil::details::in1diag3::Log_IfNtStatusFailedMsg(
            retaddr,
            (void *)0x124C,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)v52,
            (int)"Failed to change BI session state to SessionOemPreinstallStart",
            v68) )
      *(_BYTE *)(v85 + 234) = 1;
    *(_QWORD *)v82 = 0;
    v83 = 0;
    v84 = 0;
    DestinationString = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v82);
    v83 = -1;
    v84 = -1;
    SinglePackageFullNameFromPackageFamilyName = CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
                                                   v53,
                                                   v82,
                                                   v54);
    v56 = SinglePackageFullNameFromPackageFamilyName;
    if ( SinglePackageFullNameFromPackageFamilyName >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"ContentDeliveryManager.Background.RegistrationTask");
      v87 = 0;
      v88 = 0;
      v58 = SebCreateOEMPreInstallEvent(&v87, *(_QWORD *)v82);
      v56 = v58;
      if ( v58 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1259,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v58,
          v67);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v82);
        if ( !v81 )
          return v56;
        goto LABEL_115;
      }
      v76 = 199;
      v59 = BiPtAssociateApplicationEntryPoint(&v88, &DestinationString, &v87, 0);
      if ( v59 < 0 )
      {
        v56 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x125B,
                (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                (const char *)(unsigned int)v59,
                0);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v82);
        if ( !v81 )
          return v56;
        goto LABEL_115;
      }
      v85 = v87;
      v60 = SebSignalOEMPreInstallEvent(&v85, *(_QWORD *)v82);
      v56 = v60;
      if ( v60 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v82);
        goto LABEL_127;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x125E,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v60,
        0);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v82);
      if ( v81 )
      {
LABEL_115:
        v81 = 0;
        _lambda_e644f3c3b127476a4047d2034a493bb3_::operator()(v80);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1254,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)SinglePackageFullNameFromPackageFamilyName,
        v67);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v82);
      if ( v81 )
        goto LABEL_115;
    }
    return v56;
  }
  HIBYTE(v70[0]) = 2;
LABEL_127:
  if ( v81 )
  {
    v81 = 0;
    _lambda_e644f3c3b127476a4047d2034a493bb3_::operator()(v80);
  }
  return 0;
}

```

## disassembly

```asm
0x1401ab6d0  push    rbx
0x1401ab6d2  push    rdi
0x1401ab6d3  push    r12
0x1401ab6d5  push    r13
0x1401ab6d7  push    r14
0x1401ab6d9  push    r15
0x1401ab6db  sub     rsp, 128h
0x1401ab6e2  mov     rax, cs:__security_cookie
0x1401ab6e9  xor     rax, rsp
0x1401ab6ec  mov     [rsp+158h+var_48], rax
0x1401ab6f4  mov     r13, rcx
0x1401ab6f7  mov     qword ptr [rsp+158h+var_88], rcx
0x1401ab6ff  mov     qword ptr [rsp+158h+var_58], rcx
0x1401ab707  mov     [rsp+158h+var_D8], 1
0x1401ab712  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::GetImpl(void)'::`2'::impl
0x1401ab719  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightTelemetryForLogonFlagsWithSpotlightParameters>::__private_IsEnabled(void)
0x1401ab71e  xor     edi, edi
0x1401ab720  test    al, al
0x1401ab722  jz      short loc_1401AB730
0x1401ab724  mov     ecx, [r13+0D8h]
0x1401ab72b  call    CheckLogonFlagsForSpotlightOnboarding
0x1401ab730  mov     [rsp+158h+var_108], dil
0x1401ab735  mov     ecx, 2B5DB70h; unsigned int
0x1401ab73a  call    ?IsFeatureEnabled@EnterpriseFeatureControl@@SA_NK@Z; EnterpriseFeatureControl::IsFeatureEnabled(ulong)
0x1401ab73f  mov     r12b, al
0x1401ab742  xor     r12b, 1
0x1401ab746  mov     [rsp+158h+var_108], r12b
0x1401ab74b  jmp     short loc_1401AB764
0x1401ab74d  xor     edi, edi
0x1401ab74f  mov     r12b, [rsp+158h+var_108]
0x1401ab754  mov     r13, qword ptr [rsp+158h+var_58]
0x1401ab75c  mov     qword ptr [rsp+158h+var_88], r13
0x1401ab764  test    r12b, r12b
0x1401ab767  jz      short loc_1401AB777
0x1401ab769  mov     dl, 1
0x1401ab76b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl(void)'::`2'::impl
0x1401ab772  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401ab777  lea     r15, [r13+0D8h]
0x1401ab77e  mov     qword ptr [rsp+158h+DestinationString.Length], r15
0x1401ab786  mov     edx, [r15]
0x1401ab789  lea     rcx, aLogontypeflags_0; "_logonTypeFlags=%x"
0x1401ab790  call    ?TraceLoggingInfo@DesktopSpotlightLogonTelemetry@@SAXPEBDZZ; DesktopSpotlightLogonTelemetry::TraceLoggingInfo(char const *,...)
0x1401ab795  mov     [rsp+158h+pv], rdi
0x1401ab79a  lea     rcx, [rsp+158h+pv]
0x1401ab79f  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::ensure_data(void)
0x1401ab7a4  mov     rcx, [rax]
0x1401ab7a7  add     rcx, 8
0x1401ab7ab  lea     rdx, [rsp+158h+var_68]
0x1401ab7b3  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1401ab7b8  nop
0x1401ab7b9  mov     ebx, [r15]
0x1401ab7bc  lea     rdx, [rsp+158h+var_D0]
0x1401ab7c4  lea     rcx, [rsp+158h+pv]
0x1401ab7c9  call    ??C?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab7ce  mov     rdx, [rax]
0x1401ab7d1  mov     [rdx+110h], ebx
0x1401ab7d7  lea     rcx, [rsp+158h+var_D0]
0x1401ab7df  call    ??1?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(void)
0x1401ab7e4  mov     dl, 1
0x1401ab7e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::GetImpl(void)'::`2'::impl
0x1401ab7ed  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightThemeEnabledOnFirstLogon>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401ab7f2  test    byte ptr [r15], 2
0x1401ab7f6  jz      short loc_1401AB850
0x1401ab7f8  lea     rdx, [rsp+158h+var_D0]
0x1401ab800  lea     rcx, [rsp+158h+pv]
0x1401ab805  call    ??C?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab80a  mov     rcx, [rax]
0x1401ab80d  mov     byte ptr [rcx+114h], 1
0x1401ab814  lea     rcx, [rsp+158h+var_D0]
0x1401ab81c  call    ??1?$test_data_control@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>>(void)
0x1401ab821  lea     rcx, [rsp+158h+pv]
0x1401ab826  call    ?s_RefreshUndockedDesktopSpotlightIfNeeded@@YAJAEAV?$tip_test@V?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@@Z; s_RefreshUndockedDesktopSpotlightIfNeeded(tip2::tip_test<tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>> &)
0x1401ab82b  mov     rcx, [rsp+158h]; this
0x1401ab833  test    eax, eax
0x1401ab835  jns     short loc_1401AB84B
0x1401ab837  mov     r9d, eax; char *
0x1401ab83a  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401ab841  mov     edx, 111Eh; void *
0x1401ab846  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401ab84b  call    SaveOneTimeUpgrade
0x1401ab850  mov     rcx, [rsp+158h+pv]
0x1401ab855  test    rcx, rcx
0x1401ab858  jz      short loc_1401AB868
0x1401ab85a  add     rcx, 8
0x1401ab85e  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1401ab863  mov     rcx, [rsp+158h+pv]; pv
0x1401ab868  test    rcx, rcx
0x1401ab86b  jz      short loc_1401AB872
0x1401ab86d  call    ?Release@?$merged_data@U_tip_RefreshUndockedDesktopSpotlightTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_RefreshUndockedDesktopSpotlightTest,_tip_RefreshUndockedDesktopSpotlightTest>::Release(void)
0x1401ab872  mov     r8b, 3
0x1401ab875  mov     dl, 1
0x1401ab877  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::GetImpl(void)'::`2'::impl
0x1401ab87e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightUdk@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightUdk>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1401ab883  mov     [rsp+158h+pv], rdi
0x1401ab888  lea     rcx, [rsp+158h+pv]
0x1401ab88d  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::ensure_data(void)
0x1401ab892  mov     rcx, [rax]
0x1401ab895  add     rcx, 8
0x1401ab899  lea     rdx, [rsp+158h+var_68]
0x1401ab8a1  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1401ab8a6  nop
0x1401ab8a7  test    r12b, r12b
0x1401ab8aa  setz    bl
0x1401ab8ad  lea     rdx, [rsp+158h+var_F0]
0x1401ab8b2  lea     rcx, [rsp+158h+pv]
0x1401ab8b7  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab8bc  mov     rcx, [rax]
0x1401ab8bf  mov     [rcx+129h], bl
0x1401ab8c5  lea     rcx, [rsp+158h+var_F0]
0x1401ab8ca  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab8cf  nop
0x1401ab8d0  call    ?s_isCDMSpotlightEnabled@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_isCDMSpotlightEnabled(void)
0x1401ab8d5  mov     r14, 0FFFFFFFF80000001h
0x1401ab8dc  test    al, al
0x1401ab8de  jz      loc_1401AB9E7
0x1401ab8e4  lea     rax, [rsp+158h+var_F0]
0x1401ab8e9  mov     [rsp+158h+var_138], rax; int
0x1401ab8ee  lea     r8, aSubscribedcont_0; "SubscribedContent-88000326Enabled"
0x1401ab8f5  lea     rbx, aSoftwareMicros_45; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401ab8fc  mov     rdx, rbx; unsigned __int16 *
0x1401ab8ff  mov     rcx, r14; HKEY
0x1401ab902  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401ab907  test    eax, eax
0x1401ab909  js      short loc_1401AB940
0x1401ab90b  xor     r9d, r9d; int
0x1401ab90e  lea     r8, aSubscribedcont_0; "SubscribedContent-88000326Enabled"
0x1401ab915  mov     rdx, rbx; unsigned __int16 *
0x1401ab918  mov     rcx, r14; HKEY
0x1401ab91b  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1401ab920  mov     rcx, [rsp+158h]; this
0x1401ab928  test    eax, eax
0x1401ab92a  jns     short loc_1401AB940
0x1401ab92c  mov     r9d, eax; char *
0x1401ab92f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401ab936  mov     edx, 1136h; void *
0x1401ab93b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401ab940  lea     rax, [rsp+158h+var_F0]
0x1401ab945  mov     [rsp+158h+var_138], rax; int
0x1401ab94a  lea     r8, aSubscribedcont; "SubscribedContent-88000325Enabled"
0x1401ab951  mov     rdx, rbx; unsigned __int16 *
0x1401ab954  mov     rcx, r14; HKEY
0x1401ab957  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401ab95c  test    eax, eax
0x1401ab95e  js      short loc_1401AB995
0x1401ab960  xor     r9d, r9d; int
0x1401ab963  lea     r8, aSubscribedcont; "SubscribedContent-88000325Enabled"
0x1401ab96a  mov     rdx, rbx; unsigned __int16 *
0x1401ab96d  mov     rcx, r14; HKEY
0x1401ab970  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1401ab975  mov     rcx, [rsp+158h]; this
0x1401ab97d  test    eax, eax
0x1401ab97f  jns     short loc_1401AB995
0x1401ab981  mov     r9d, eax; char *
0x1401ab984  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401ab98b  mov     edx, 113Bh; void *
0x1401ab990  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401ab995  lea     rcx, [rsp+158h+var_E8]; this
0x1401ab99a  call    ??0UserProfilePersonalizationSettings@UserProfile@System@WindowsUdk@winrt@@QEAA@XZ; winrt::WindowsUdk::System::UserProfile::UserProfilePersonalizationSettings::UserProfilePersonalizationSettings(void)
0x1401ab99f  nop
0x1401ab9a0  lea     rcx, [rsp+158h+var_E8]; struct winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics *
0x1401ab9a5  call    ?_lambda_invoker_cdecl_@_lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_@@CA@AEBUIPersonalizedOffersSettingsStatics@UserProfile@System@WindowsUdk@winrt@@@Z; _lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_::_lambda_invoker_cdecl_(winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics const &)
0x1401ab9aa  test    eax, eax
0x1401ab9ac  jnz     short loc_1401AB9DC
0x1401ab9ae  lea     rdx, [rsp+158h+var_F0]
0x1401ab9b3  lea     rcx, [rsp+158h+pv]
0x1401ab9b8  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401ab9bd  mov     rcx, [rax]
0x1401ab9c0  mov     byte ptr [rcx+117h], 1
0x1401ab9c7  lea     rcx, [rsp+158h+var_F0]
0x1401ab9cc  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401ab9d1  lea     rcx, [rsp+158h+pv]
0x1401ab9d6  call    s_EnableUndockedDesktopSpotlightInternal
0x1401ab9db  nop
0x1401ab9dc  lea     rcx, [rsp+158h+var_E8]
0x1401ab9e1  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1401ab9e6  nop
0x1401ab9e7  jmp     short loc_1401ABA0F
0x1401ab9e9  xor     edi, edi
0x1401ab9eb  mov     r14, 0FFFFFFFF80000001h
0x1401ab9f2  mov     r12b, [rsp+158h+var_108]
0x1401ab9f7  mov     rax, qword ptr [rsp+158h+var_58]
0x1401ab9ff  mov     qword ptr [rsp+158h+var_88], rax
0x1401aba07  mov     r15, qword ptr [rsp+158h+DestinationString.Length]
0x1401aba0f  mov     [rsp+158h+var_C8], edi
0x1401aba16  mov     eax, [r15]
0x1401aba19  and     eax, 330Ah
0x1401aba1e  cmp     eax, 2
0x1401aba21  jnz     loc_1401ABBDD
0x1401aba27  lea     r9, [rsp+158h+var_C8]; unsigned int *
0x1401aba2f  lea     r8, aStatus; "Status"
0x1401aba36  lea     rdx, aSoftwareMicros_119; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401aba3d  mov     rcx, r14; HKEY
0x1401aba40  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1401aba45  test    eax, eax
0x1401aba47  js      loc_1401ABBDD
0x1401aba4d  cmp     [rsp+158h+var_C8], 1
0x1401aba55  jnz     loc_1401ABBDD
0x1401aba5b  mov     r13b, 1
0x1401aba5e  mov     byte ptr [rsp+158h+var_107], r13b
0x1401aba63  lea     rdx, [rsp+158h+var_F0]
0x1401aba68  lea     rcx, [rsp+158h+pv]
0x1401aba6d  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401aba72  mov     rcx, [rax]
0x1401aba75  mov     [rcx+148h], r13b
0x1401aba7c  lea     rcx, [rsp+158h+var_F0]
0x1401aba81  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401aba86  nop
0x1401aba87  mov     [rsp+158h+var_E8], edi
0x1401aba8b  lea     rax, [rsp+158h+var_E8]
0x1401aba90  mov     [rsp+158h+var_138], rax; int *
0x1401aba95  lea     r8, aWallpaperresto; "WallpaperRestored"
0x1401aba9c  lea     rdx, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401abaa3  mov     rcx, r14; HKEY
0x1401abaa6  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401abaab  cmp     [rsp+158h+var_E8], edi
0x1401abaaf  setnz   bl
0x1401abab2  lea     rdx, [rsp+158h+var_F0]
0x1401abab7  lea     rcx, [rsp+158h+pv]
0x1401ababc  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401abac1  mov     rcx, [rax]
0x1401abac4  mov     [rcx+145h], bl
0x1401abaca  lea     rcx, [rsp+158h+var_F0]
0x1401abacf  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401abad4  mov     [rsp+158h+var_F0], edi
0x1401abad8  lea     rax, [rsp+158h+var_F0]
0x1401abadd  mov     [rsp+158h+var_138], rax; int *
0x1401abae2  lea     r8, aThemerestored; "ThemeRestored"
0x1401abae9  lea     rdx, aSoftwareMicros_60; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401abaf0  mov     rcx, r14; HKEY
0x1401abaf3  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401abaf8  cmp     [rsp+158h+var_F0], edi
0x1401abafc  setnz   bl
0x1401abaff  lea     rdx, [rsp+158h+var_E0]
0x1401abb04  lea     rcx, [rsp+158h+pv]
0x1401abb09  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401abb0e  mov     rcx, [rax]
0x1401abb11  mov     [rcx+146h], bl
0x1401abb17  lea     rcx, [rsp+158h+var_E0]
0x1401abb1c  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401abb21  mov     [rsp+158h+var_E0], edi
0x1401abb25  lea     rax, [rsp+158h+var_E0]
0x1401abb2a  mov     [rsp+158h+var_138], rax; int *
0x1401abb2f  lea     r8, aRestorespotlig; "RestoreSpotlight"
0x1401abb36  lea     rdx, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401abb3d  mov     rcx, r14; HKEY
0x1401abb40  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401abb45  cmp     [rsp+158h+var_E0], edi
0x1401abb49  setnz   bl
0x1401abb4c  lea     rdx, [rsp+158h+var_68]
0x1401abb54  lea     rcx, [rsp+158h+pv]
0x1401abb59  call    ??C?$tip_test@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::operator->(void)
0x1401abb5e  mov     rcx, [rax]
0x1401abb61  mov     [rcx+147h], bl
0x1401abb67  lea     rcx, [rsp+158h+var_68]
0x1401abb6f  call    ??1?$test_data_control@V?$merged_data@U_tip_UndockedDesktopSpotlightTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>::~test_data_control<tip2::details::merged_data<_tip_UndockedDesktopSpotlightTest,_tip_UndockedDesktopSpotlightTest>>(void)
0x1401abb74  cmp     [rsp+158h+var_E8], edi
0x1401abb78  jnz     short loc_1401ABB80
0x1401abb7a  cmp     [rsp+158h+var_F0], edi
0x1401abb7e  jz      short loc_1401ABB86
0x1401abb80  cmp     [rsp+158h+var_E0], edi
0x1401abb84  jz      short loc_1401ABBAE
0x1401abb86  cmp     [rsp+158h+var_E0], edi
0x1401abb8a  setnz   al
0x1401abb8d  cmp     [rsp+158h+var_E8], edi
0x1401abb91  jnz     short loc_1401ABB9F
0x1401abb93  cmp     [rsp+158h+var_F0], edi
0x1401abb97  jnz     short loc_1401ABB9F
0x1401abb99  cmp     [rsp+158h+var_E0], edi
0x1401abb9d  jz      short loc_1401ABBA3
0x1401abb9f  test    al, al
0x1401abba1  jz      short loc_1401ABBAE
0x1401abba3  lea     rcx, [rsp+158h+pv]
0x1401abba8  call    s_EnableUndockedDesktopSpotlightInternal
0x1401abbad  nop
0x1401abbae  jmp     short loc_1401ABBE5
0x1401abbb0  xor     edi, edi
0x1401abbb2  mov     r14, 0FFFFFFFF80000001h
0x1401abbb9  mov     r12b, [rsp+158h+var_108]
0x1401abbbe  mov     r13b, byte ptr [rsp+158h+var_107]
0x1401abbc3  mov     rax, qword ptr [rsp+158h+var_58]
0x1401abbcb  mov     qword ptr [rsp+158h+var_88], rax
0x1401abbd3  mov     r15, qword ptr [rsp+158h+DestinationString.Length]
0x1401abbdb  jmp     short loc_1401ABBE5
0x1401abbdd  mov     r13b, dil
0x1401abbe0  mov     byte ptr [rsp+158h+var_107], dil
0x1401abbe5  movzx   ebx, r13b
0x1401abbe9  mov     [rsp+158h+var_C4], edi
0x1401abbf0  lea     r9, [rsp+158h+var_C4]; unsigned int *
0x1401abbf8  lea     r8, aIsrestorelogon; "IsRestoreLogon"
0x1401abbff  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401abc06  mov     rcx, r14; HKEY
0x1401abc09  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1401abc0e  test    eax, eax
0x1401abc10  js      short loc_1401ABC1B
0x1401abc12  cmp     [rsp+158h+var_C4], ebx
0x1401abc19  jz      short loc_1401ABC5E
0x1401abc1b  mov     r9d, ebx; unsigned int
0x1401abc1e  lea     r8, aIsrestorelogon; "IsRestoreLogon"
0x1401abc25  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401abc2c  mov     rcx, r14; HKEY
  ... truncated ...
```
