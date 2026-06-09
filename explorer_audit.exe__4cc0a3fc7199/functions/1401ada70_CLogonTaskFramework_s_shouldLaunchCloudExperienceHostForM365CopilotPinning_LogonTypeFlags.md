# CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForM365CopilotPinning(LogonTypeFlags)

- ea: `0x1401ada70`
- end: `0x1401aedc3`
- name: `?s_shouldLaunchCloudExperienceHostForM365CopilotPinning@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z`
- size: `4947`
- prototype: ``
- caller_count: `1`
- callee_count: `68`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14009d5c0`

## callees

- `0x140007ea0`
- `0x14000a150`
- `0x14000fe54`
- `0x140011984`
- `0x140013790`
- `0x140013bb4`
- `0x140013c48`
- `0x140013e6c`
- `0x140016450`
- `0x14001c134`
- `0x14001eba8`
- `0x140030944`
- `0x140033070`
- `0x140033a3c`
- `0x14003401c`
- `0x1400632b0`
- `0x1400645f0`
- `0x1400655ec`
- `0x140074ea0`
- `0x1400770ac`
- `0x14007ce54`
- `0x140080a70`
- `0x140080b6c`
- `0x1400817d8`
- `0x140081aa8`
- `0x14008925c`
- `0x140091afc`
- `0x140097920`
- `0x1400a4580`
- `0x1400aa478`
- `0x1400b7748`
- `0x1401010ec`
- `0x1401040e0`
- `0x140131210`
- `0x140131bfc`
- `0x14013a478`
- `0x14013b460`
- `0x14013c05c`
- `0x14014aac0`
- `0x14014b6e4`
- `0x14014d144`
- `0x14014da10`
- `0x14014db78`
- `0x14015cb0c`
- `0x14015db38`
- `0x14015dbb0`
- `0x14015eba4`
- `0x14015ec30`
- `0x14016684c`
- `0x140166960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401adeb0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401adeef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401aebec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401aec2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401adeb0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401adeef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401aebec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1401aec2b`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1401ade68`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1401aeb9d`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1401ade68`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x1401aeb9d`

## string_xrefs

- `0x1401addea`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aeadb`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aece4`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401aedb1`: `shell\lib\logontasks\logontasks.cpp`
- `0x1401adea6`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1401aebdb`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1401adee5`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1401aec21`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x1401adbf3`: `M365CopilotPinningTest::reason::userAlreadyPinnedToTaskbarBefore`
- `0x1401adbd6`: `UserPinnedM365CopilotToTaskbar`
- `0x1401ae743`: `M365CopilotPinningTest::reason::copilotAppAlreadyPinned`
- `0x1401ae3ed`: `M365CopilotPinningTest::reason::m365CopilotNotInstalled`
- `0x1401ae991`: `M365CopilotPinningTest::reason::windowsUpdateManaged`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
char __fastcall CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForM365CopilotPinning(
        int a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int16 v4; // r12
  char v5; // bl
  __int64 v6; // rdi
  __int64 v7; // rdi
  __int64 v8; // rdi
  __int64 v9; // rdi
  unsigned int v10; // r9d
  const char *v11; // rdx
  const char *v12; // rax
  __int64 v13; // rdx
  wil::filetime *v14; // rcx
  unsigned __int64 system_time; // rax
  unsigned __int64 v16; // rdi
  unsigned int v17; // r9d
  __int64 v18; // rdi
  const char *v19; // rdx
  __int64 v20; // rdi
  const char *v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rdi
  const char *v25; // rdx
  __int64 v26; // rdi
  int v27; // esi
  __int64 v28; // rdi
  const char *v29; // rdx
  bool IsAadUser; // si
  __int64 v31; // rdi
  bool IsMSA; // al
  bool v33; // r14
  char v34; // si
  __int64 v35; // rdi
  __int64 v36; // rdi
  const char *v37; // rdx
  unsigned int v38; // esi
  unsigned int v39; // edi
  const char *v40; // rdx
  const char *v41; // rax
  __int64 v42; // rdx
  const char *v43; // rdx
  bool IsDeviceManaged; // si
  __int64 v45; // rdi
  const char *v46; // rdx
  bool IsM365CopilotPinningCampaignAllowed; // si
  __int64 v48; // rdi
  const char *v49; // rdx
  const char *v50; // rdx
  char v51; // si
  __int64 v52; // rdi
  const char *v53; // rdx
  void *v54; // rax
  char IsPackageFamilyInstalled; // si
  __int64 v56; // rdi
  const char *v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rax
  char v60; // si
  __int64 v61; // rdi
  __int64 v62; // rax
  __int64 AreAppsPinnedAsync; // rax
  char v64; // si
  char v65; // r14
  __int64 v66; // rdi
  __int64 v67; // rdi
  const char *v68; // rdx
  const char *v69; // rax
  char v70; // si
  __int64 v71; // rdi
  const char *v72; // rdx
  const char *v73; // rax
  __int64 v74; // rdx
  char v75; // si
  __int64 v76; // rdi
  const char *v77; // rdx
  char v78; // si
  __int64 v79; // rdi
  const char *v80; // rdx
  const char *v81; // rdx
  wil::filetime *v82; // rcx
  HKEY v83; // rcx
  int v84; // eax
  __int64 v85; // rdi
  const char *v86; // rdx
  const char *v87; // rax
  wil::filetime *v88; // rcx
  HKEY v89; // rcx
  int v90; // eax
  __int64 v91; // rdi
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  DWORD pvData[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v96[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v97; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v98[8]; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData[2]; // [rsp+70h] [rbp-90h] BYREF
  char v100; // [rsp+78h] [rbp-88h]
  __int128 v101; // [rsp+80h] [rbp-80h] BYREF
  __int64 v102; // [rsp+90h] [rbp-70h]
  _QWORD v103[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v104[56]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v105; // [rsp+E8h] [rbp-18h]
  struct _FILETIME v106; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v107[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v108[16]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v4 = a1;
  v5 = 1;
  if ( (a1 & 0x400000) != 0 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x22E4,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      a4);
  v103[0] = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::start_and_watch_errors(
    v103,
    v104);
  wil::com_ptr_t<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>,wil::err_returncode_policy>(v103);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
    goto LABEL_16;
  v6 = v105;
  v96[0] = v105;
  if ( v105 )
    _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
  tip2::details::shared_data<0,0,1>::begin_update(v6 + 8);
  *(_BYTE *)(v6 + 277) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
  v7 = v105;
  v96[0] = v105;
  if ( v105 )
    _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
  tip2::details::shared_data<0,0,1>::begin_update(v7 + 8);
  *(_BYTE *)(v7 + 278) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
  v8 = v105;
  v96[0] = v105;
  if ( v105 )
    _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
  tip2::details::shared_data<0,0,1>::begin_update(v8 + 8);
  *(_BYTE *)(v8 + 281) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
  v9 = v105;
  v96[0] = v105;
  if ( v105 )
    _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
  tip2::details::shared_data<0,0,1>::begin_update(v9 + 8);
  *(_BYTE *)(v9 + 285) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
  fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_1402563C0);
  if ( !byte_1402563E1
    || (pvData[0] = 0,
        (int)SHRegGetBOOLWithREGSAM(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\M365Copilot",
               L"UserPinnedM365CopilotToTaskbar",
               v10,
               (int *)pvData) < 0)
    || !pvData[0] )
  {
LABEL_16:
    v106 = 0;
    if ( (int)SHRegGetFILETIME(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\M365Copilot",
                L"PinningTimestamp",
                &v106) >= 0 )
    {
      system_time = (unsigned __int64)wil::filetime::get_system_time(v14);
      v16 = (((HIDWORD(system_time) - v106.dwHighDateTime) << 32) - v106.dwLowDateTime + (unsigned int)system_time)
          / 0xC92A69C000uLL;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinning>::GetCachedVariantState(
        864000000000LL,
        v96);
      if ( (unsigned int)v16 <= HIDWORD(v96[0]) )
      {
        v18 = v105;
        v96[0] = v105;
        if ( v105 )
          _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
        tip2::details::shared_data<0,0,1>::begin_update(v18 + 8);
        *(_BYTE *)(v18 + 273) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
        {
          v12 = tip2::details::reason_string((tip2::details *)"M365CopilotPinningTest::reason::shownTooSoon", v19);
          v13 = 3;
          goto LABEL_15;
        }
LABEL_57:
        tip2::details::shared_data<0,0,0>::complete_without_lock(v105 + 8);
        goto LABEL_218;
      }
      pcbData[0] = 0;
      if ( (int)SHRegGetBOOLWithREGSAM(
                  HKEY_CURRENT_USER,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\M365Copilot",
                  L"PinningSuccess",
                  v17,
                  (int *)pcbData) >= 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
        {
          if ( !pcbData[0] )
            goto LABEL_38;
          fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_1402562A0);
          if ( !byte_1402562C1
            || (pvData[0] = v16,
                fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_140256270),
                (int)fc::details::key_cmp<unsigned int,0>(&unk_140256294, pvData) > 0) )
          {
            v20 = v105;
            v96[0] = v105;
            if ( v105 )
              _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
            tip2::details::shared_data<0,0,1>::begin_update(v20 + 8);
            *(_BYTE *)(v20 + 279) = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
            v12 = tip2::details::reason_string(
                    (tip2::details *)"M365CopilotPinningTest::reason::hasRunCampaignBefore",
                    v21);
            v13 = 4;
            goto LABEL_15;
          }
        }
        else
        {
          if ( !pcbData[0] )
            goto LABEL_38;
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningFrequency>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningFrequency>::GetImpl'::`2'::impl)
            || (wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningFrequency>::GetCachedVariantState(
                  v22,
                  v96),
                (unsigned int)v16 <= HIDWORD(v96[0])) )
          {
            v26 = v105;
            v96[0] = v105;
            if ( v105 )
              _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
            tip2::details::shared_data<0,0,1>::begin_update(v26 + 8);
            *(_BYTE *)(v26 + 279) = 1;
            tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
            goto LABEL_57;
          }
          v23 = SHRegSetBOOL(
                  HKEY_CURRENT_USER,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\M365Copilot",
                  L"PinningSuccess",
                  0);
          if ( v23 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2340,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v23,
              pdwType);
        }
        v24 = v105;
        v96[0] = v105;
        if ( v105 )
          _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
        tip2::details::shared_data<0,0,1>::begin_update(v24 + 8);
        *(_BYTE *)(v24 + 274) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
      }
    }
LABEL_38:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl)
      && (v4 & 0x3308) != 0
      && !CLogonTaskFramework::s_IsCompanionDeviceAccount()
      && !IsOS(0xDu) )
    {
      pvData[0] = 0;
      pcbData[0] = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Enabled",
             0x10010u,
             0,
             pvData,
             pcbData) )
      {
        pcbData[0] = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
          L"Enabled",
          0x20010010u,
          0,
          pvData,
          pcbData);
      }
      if ( !pvData[0]
        && !IsSharedPCMode()
        && !CLogonTaskFramework::s_IsExplorerRestart()
        && !IsShellLauncherEnabledForCurrentUser()
        && !IsPreserveOobeAutologonCredentialsSet()
        && !IsUnattendedAutoLogonSet()
        && !(unsigned int)IsUserAssignedAccessSingleApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
        && !IsUserAssignedAccessMultiApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
        && !IsUserAssignedAccessSingleAppClassicApp((HANDLE)0xFFFFFFFFFFFFFFFCLL) )
      {
        v12 = tip2::details::reason_string(
                (tip2::details *)"M365CopilotPinningTest::reason::ineligibleLogonTypeForInterruption",
                v25);
        v13 = 21;
        goto LABEL_15;
      }
    }
    v96[0] = L"dbfadcb8-0302-4de0-87be-4dfbb71950f9";
    v96[1] = 36;
    winrt::guid::parse<std::basic_string_view<unsigned short>>(v108, v96);
    v96[0] = v108;
    v27 = winrt::impl::call_factory<winrt::Windows::Internal::System::Profile::RegionPolicyEvaluator,winrt::Windows::Internal::System::Profile::IRegionPolicyEvaluatorStatics,_lambda_619f5862083d42432f26fb2b85cca6a3_>(v96);
    v28 = v105;
    v96[0] = v105;
    if ( v105 )
      _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
    tip2::details::shared_data<0,0,1>::begin_update(v28 + 8);
    *(_BYTE *)(v28 + 278) = v27 == 2;
    tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
    if ( v27 != 2 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
      {
        v12 = tip2::details::reason_string((tip2::details *)"M365CopilotPinningTest::reason::regionNotAllowed", v29);
        v13 = 7;
        goto LABEL_15;
      }
      goto LABEL_57;
    }
    IsAadUser = CLogonTaskFramework::s_IsAadUser();
    v31 = v105;
    v96[0] = v105;
    if ( v105 )
      _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
    tip2::details::shared_data<0,0,1>::begin_update(v31 + 8);
    *(_BYTE *)(v31 + 281) = IsAadUser;
    tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
    {
      IsMSA = CLogonTaskFramework::s_IsMSA();
      v33 = IsMSA;
      if ( IsAadUser || (v34 = 1, IsMSA) )
        v34 = 0;
      v35 = v105;
      v96[0] = v105;
      if ( v105 )
        _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
      tip2::details::shared_data<0,0,1>::begin_update(v35 + 8);
      *(_BYTE *)(v35 + 282) = v33;
      tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
      v36 = v105;
      v96[0] = v105;
      if ( v105 )
        _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
      tip2::details::shared_data<0,0,1>::begin_update(v36 + 8);
      *(_BYTE *)(v36 + 283) = v34;
      tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
      if ( v34
        && (fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_1402562D0), !byte_1402562F1)
        || v33
        && (fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_140256300), !byte_140256321) )
      {
        v12 = tip2::details::reason_string((tip2::details *)"M365CopilotPinningTest::reason::notTargetAudience", v37);
        v13 = 16;
        goto LABEL_15;
      }
      winrt::CloudExperienceHostAPI::UtilStaticsCore::DaysSinceFirstLogon();
      if ( *(_QWORD *)pcbData )
        v38 = _lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_::_lambda_invoker_cdecl_((const struct winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics *)pcbData);
      else
        v38 = 0;
      winrt::CloudExperienceHostAPI::UtilStaticsCore::DaysSinceFirstLogonOnCurrentInstallation();
      if ( *(_QWORD *)pvData )
        v39 = _lambda_5bc3bff0dc49a5a3c9d09c28dc81a521_::_lambda_invoker_cdecl_((const struct winrt::WindowsUdk::System::UserProfile::IPersonalizedOffersSettingsStatics *)pvData);
      else
        v39 = 0;
      if ( (unsigned __int8)fc::operator><unsigned int,fc::details::minmax<unsigned int,0>>(&unk_140256208, v38) )
      {
        v41 = tip2::details::reason_string(
                (tip2::details *)"M365CopilotPinningTest::reason::notEnoughDaysSinceOOBE",
                v40);
        v42 = 19;
LABEL_86:
        tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::complete_and_succeed(
          v104,
          v42,
          v41);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pvData);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pcbData);
        goto LABEL_218;
      }
      if ( (unsigned __int8)fc::operator><unsigned int,fc::details::minmax<unsigned int,0>>(&unk_140256238, v39) )
      {
        v41 = tip2::details::reason_string(
                (tip2::details *)"M365CopilotPinningTest::reason::notEnoughDaysSinceOsSwap",
                v43);
        v42 = 20;
        goto LABEL_86;
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pvData);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pcbData);
    }
    else if ( !IsAadUser )
    {
      goto LABEL_57;
    }
    IsDeviceManaged = CLogonTaskFramework::IsDeviceManaged();
    v45 = v105;
    v96[0] = v105;
    if ( v105 )
      _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
    tip2::details::shared_data<0,0,1>::begin_update(v45 + 8);
    *(_BYTE *)(v45 + 275) = IsDeviceManaged;
    tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
    if ( IsDeviceManaged )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
      {
        v12 = tip2::details::reason_string((tip2::details *)"M365CopilotPinningTest::reason::deviceManaged", v46);
        v13 = 10;
        goto LABEL_15;
      }
      goto LABEL_57;
    }
    IsM365CopilotPinningCampaignAllowed = CLogonTaskFramework::IsM365CopilotPinningCampaignAllowed();
    v48 = v105;
    v96[0] = v105;
    if ( v105 )
      _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
    tip2::details::shared_data<0,0,1>::begin_update(v48 + 8);
    *(_BYTE *)(v48 + 285) = IsM365CopilotPinningCampaignAllowed;
    tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
    if ( !IsM365CopilotPinningCampaignAllowed )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
      {
        v12 = tip2::details::reason_string(
                (tip2::details *)"M365CopilotPinningTest::reason::m365CopilotPinningCampaignDenied",
                v49);
        v13 = 6;
        goto LABEL_15;
      }
      goto LABEL_57;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl)
      && !CLogonTaskFramework::UserSetupAllowedBySLPolicy() )
    {
      v12 = tip2::details::reason_string(
              (tip2::details *)"M365CopilotPinningTest::reason::userSetupExperienceDisabledByEditionPolicy",
              v50);
      v13 = 17;
      goto LABEL_15;
    }
    v51 = winrt::impl::call_factory_cast<bool (*)(winrt::Windows::System::Profile::IEducationSettingsStatics const &),winrt::Windows::System::Profile::EducationSettings,winrt::Windows::System::Profile::IEducationSettingsStatics,_lambda_0379b32abc0657f54a544af3521b1cb2_>();
    v52 = v105;
    v96[0] = v105;
    if ( v105 )
      _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
    tip2::details::shared_data<0,0,1>::begin_update(v52 + 8);
    *(_BYTE *)(v52 + 276) = v51;
    tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
    if ( v51 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
      {
        v12 = tip2::details::reason_string((tip2::details *)"M365CopilotPinningTest::reason::eduSku", v53);
        v13 = 9;
        goto LABEL_15;
      }
      goto LABEL_57;
    }
    v54 = (void *)std::wstring::wstring(&v101, L"Microsoft.MicrosoftOfficeHub_8wekyb3d8bbwe");
    IsPackageFamilyInstalled = CLogonTaskFramework::IsPackageFamilyInstalled(v54);
    v56 = v105;
    v96[0] = v105;
    if ( v105 )
      _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
    tip2::details::shared_data<0,0,1>::begin_update(v56 + 8);
    *(_BYTE *)(v56 + 277) = IsPackageFamilyInstalled;
    tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
    if ( !IsPackageFamilyInstalled )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
      {
        v12 = tip2::details::reason_string(
                (tip2::details *)"M365CopilotPinningTest::reason::m365CopilotNotInstalled",
                v57);
        v13 = 11;
        goto LABEL_15;
      }
      goto LABEL_57;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
    {
      winrt::WindowsUdk::System::UserProfile::OfficeEnrollManager::GetDefault();
      v101 = 0;
      v102 = 0;
      winrt::hstring::hstring(
        (winrt::hstring *)v96,
        L"Microsoft.MicrosoftOfficeHub_8wekyb3d8bbwe!Microsoft.MicrosoftOfficeHub");
      std::vector<winrt::hstring>::push_back(&v101, v96);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v96);
      winrt::hstring::hstring((winrt::hstring *)v96, L"Microsoft.Copilot_8wekyb3d8bbwe!App");
      std::vector<winrt::hstring>::push_back(&v101, v96);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v96);
      v62 = winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(v96, &v101);
      winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
        v62,
        v98);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v96);
      winrt::param::async_vector_view<winrt::hstring>::async_vector_view<winrt::hstring>(pcbData, v98);
      AreAppsPinnedAsync = winrt::WindowsUdk::System::UserProfile::OfficeEnrollManager::GetAreAppsPinnedAsync(
                             v96,
                             pcbData);
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<bool>>,winrt::Windows::Foundation::Collections::IVectorView<bool>>::get(
        AreAppsPinnedAsync,
        pvData);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v96);
      if ( !v100 )
        *(_QWORD *)pcbData = 0;
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pcbData);
      v64 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<bool>,bool>::GetAt(
              pvData,
              0);
      v65 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<bool>,bool>::GetAt(
              pvData,
              1);
      v66 = v105;
      v96[0] = v105;
      if ( v105 )
        _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
      tip2::details::shared_data<0,0,1>::begin_update(v66 + 8);
      *(_BYTE *)(v66 + 280) = v64;
      tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
      v67 = v105;
      v96[0] = v105;
      if ( v105 )
        _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
      tip2::details::shared_data<0,0,1>::begin_update(v67 + 8);
      *(_BYTE *)(v67 + 287) = v65;
      tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v96);
      if ( v64
        || (fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_140256390), !byte_1402563B1)
        && v65 )
      {
        v69 = tip2::details::reason_string(
                (tip2::details *)"M365CopilotPinningTest::reason::copilotAppAlreadyPinned",
                v68);
        tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::complete_and_succeed(
          v104,
          15,
          v69);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pvData);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v98);
        if ( (_QWORD)v101 )
        {
          std::_Destroy_range<std::allocator<winrt::hstring>>(v101, *((_QWORD *)&v101 + 1));
          std::_Deallocate<16>(v101, (v102 - v101) & 0xFFFFFFFFFFFFFFF8uLL);
          v102 = 0;
          v101 = 0;
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v103);
        goto LABEL_218;
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pvData);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v98);
      if ( (_QWORD)v101 )
      {
        std::_Destroy_range<std::allocator<winrt::hstring>>(v101, *((_QWORD *)&v101 + 1));
        std::_Deallocate<16>(v101, (v102 - v101) & 0xFFFFFFFFFFFFFFF8uLL);
        v101 = 0;
        v102 = 0;
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v103);
    }
    else
    {
      winrt::WindowsUdk::System::UserProfile::OfficeEnrollManager::GetDefault();
      v101 = 0;
      v102 = 0;
      winrt::hstring::hstring(
        (winrt::hstring *)v98,
        L"Microsoft.MicrosoftOfficeHub_8wekyb3d8bbwe!Microsoft.MicrosoftOfficeHub");
      std::vector<winrt::hstring>::push_back(&v101, v98);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v98);
      v58 = winrt::single_threaded_vector<winrt::hstring,std::allocator<winrt::hstring>>(pvData, &v101);
      winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::hstring>::GetView(
        v58,
        v98);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pvData);
      winrt::param::async_vector_view<winrt::hstring>::async_vector_view<winrt::hstring>(pcbData, v98);
      v59 = winrt::WindowsUdk::System::UserProfile::OfficeEnrollManager::GetAreAppsPinnedAsync(pvData, pcbData);
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<bool>>,winrt::Windows::Foundation::Collections::IVectorView<bool>>::get(
        v59,
        v103);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pvData);
      if ( !v100 )
        *(_QWORD *)pcbData = 0;
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(pcbData);
      v60 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<bool>,bool>::GetAt(
              v103,
              0);
      v61 = v105;
      *(_QWORD *)pvData = v105;
      if ( v105 )
        _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
      tip2::details::shared_data<0,0,1>::begin_update(v61 + 8);
      *(_BYTE *)(v61 + 280) = v60;
      tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(pvData);
      if ( v60 )
      {
        tip2::details::shared_data<0,0,0>::complete_without_lock(v105 + 8);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v103);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v98);
        if ( (_QWORD)v101 )
        {
          std::_Destroy_range<std::allocator<winrt::hstring>>(v101, *((_QWORD *)&v101 + 1));
          std::_Deallocate<16>(v101, (v102 - v101) & 0xFFFFFFFFFFFFFFF8uLL);
          v101 = 0;
          v102 = 0;
        }
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v96);
LABEL_191:
        v5 = 0;
LABEL_214:
        tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v104);
        return v5;
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v103);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v98);
      if ( (_QWORD)v101 )
      {
        std::_Destroy_range<std::allocator<winrt::hstring>>(v101, *((_QWORD *)&v101 + 1));
        std::_Deallocate<16>(v101, (v102 - v101) & 0xFFFFFFFFFFFFFFF8uLL);
        v101 = 0;
        v102 = 0;
      }
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v96);
    }
    pvData[0] = 1;
    winrt::WindowsUdk::System::UserProfile::UserSetupEligibilityDataHelper::GetData((const enum winrt::WindowsUdk::System::UserProfile::UserSetupEligibilityDataOptions *)v98);
    winrt::param::hstring::hstring((winrt::param::hstring *)v107, L"IsUserSetupBlockedDueToUserChoice");
    winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
      v98,
      &v97,
      v107);
    if ( v97 )
      v70 = winrt::impl::unbox_value_type<bool,winrt::Windows::Foundation::IInspectable const &>(&v97);
    else
      v70 = 0;
    v71 = v105;
    *(_QWORD *)pvData = v105;
    if ( v105 )
      _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
    tip2::details::shared_data<0,0,1>::begin_update(v71 + 8);
    *(_BYTE *)(v71 + 284) = v70;
    tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(pvData);
    if ( v70 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
      {
        v73 = tip2::details::reason_string(
                (tip2::details *)"M365CopilotPinningTest::reason::userSetupBlockedDueToUserChoice",
                v72);
        v74 = 8;
        goto LABEL_187;
      }
LABEL_149:
      tip2::details::shared_data<0,0,0>::complete_without_lock(v105 + 8);
LABEL_188:
      if ( v97 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v97);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v98);
      goto LABEL_191;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
    {
      fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_140256330);
      if ( !byte_140256351 )
      {
        if ( (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(63)
          || (unsigned __int8)CLogonTaskFramework::IsUpdatePolicyConfigured(3)
          || (unsigned __int8)CLogonTaskFramework::IsUpdatePolicyConfigured(7)
          || (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(20)
          || (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(46)
          || (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(47)
          || (v75 = 0, (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(45)) )
        {
          v75 = 1;
        }
        v76 = v105;
        *(_QWORD *)pvData = v105;
        if ( v105 )
          _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
        tip2::details::shared_data<0,0,1>::begin_update(v76 + 8);
        *(_BYTE *)(v76 + 286) = v75;
        tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(pvData);
        if ( v75 )
        {
          v73 = tip2::details::reason_string(
                  (tip2::details *)"M365CopilotPinningTest::reason::windowsUpdateManaged",
                  v77);
          v74 = 14;
          goto LABEL_187;
        }
      }
    }
    else
    {
      if ( (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(63)
        || (unsigned __int8)CLogonTaskFramework::IsUpdatePolicyConfigured(3)
        || (unsigned __int8)CLogonTaskFramework::IsUpdatePolicyConfigured(7)
        || (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(20)
        || (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(46)
        || (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(47)
        || (v78 = 0, (unsigned __int8)CLogonTaskFramework::IsEnterprisePolicyConfigured(45)) )
      {
        v78 = 1;
      }
      v79 = v105;
      *(_QWORD *)pvData = v105;
      if ( v105 )
        _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
      tip2::details::shared_data<0,0,1>::begin_update(v79 + 8);
      *(_BYTE *)(v79 + 286) = v78;
      tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(pvData);
      if ( v78 )
        goto LABEL_149;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl)
      || (fc::config_property_base::ensure_initialized((fc::config_property_base *)&unk_140256360), byte_140256381)
      || !ArePrivacySettingsManagedByPolicy() )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl'::`2'::impl) )
      {
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningEnablement>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningEnablement>::GetImpl'::`2'::impl) )
        {
          v73 = tip2::details::reason_string(
                  (tip2::details *)"M365CopilotPinningTest::reason::disabledByVelocityTrigger",
                  v81);
          v74 = 22;
          goto LABEL_187;
        }
        *(struct _FILETIME *)pvData = wil::filetime::get_system_time(v82);
        v84 = SHRegSetFILETIME(
                v83,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\M365Copilot",
                L"PinningTimestamp",
                (const struct _FILETIME *)pvData);
        if ( v84 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2480,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v84,
            pdwType);
        v85 = v105;
        *(_QWORD *)pcbData = v105;
        if ( v105 )
          _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
        tip2::details::shared_data<0,0,1>::begin_update(v85 + 8);
        *(_BYTE *)(v85 + 272) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(pcbData);
        v87 = tip2::details::reason_string((tip2::details *)"M365CopilotPinningTest::reason::showPinningPage", v86);
        tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::complete_and_succeed(
          v104,
          2,
          v87);
      }
      else
      {
        if ( (v4 & 0x3308) != 0 || CLogonTaskFramework::s_IsCompanionDeviceAccount() || IsOS(0xDu) )
          goto LABEL_215;
        pcbData[0] = 0;
        pvData[0] = 4;
        if ( RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
               L"Enabled",
               0x10010u,
               0,
               pcbData,
               pvData) )
        {
          pvData[0] = 4;
          RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
            L"Enabled",
            0x20010010u,
            0,
            pcbData,
            pvData);
        }
        if ( pcbData[0]
          || IsSharedPCMode()
          || CLogonTaskFramework::s_IsExplorerRestart()
          || IsShellLauncherEnabledForCurrentUser()
          || IsPreserveOobeAutologonCredentialsSet()
          || IsUnattendedAutoLogonSet()
          || (unsigned int)IsUserAssignedAccessSingleApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
          || IsUserAssignedAccessMultiApp((HANDLE)0xFFFFFFFFFFFFFFFCLL)
          || IsUserAssignedAccessSingleAppClassicApp((HANDLE)0xFFFFFFFFFFFFFFFCLL) )
        {
LABEL_215:
          tip2::details::shared_data<0,0,0>::complete_without_lock(v105 + 8);
          if ( v97 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v97);
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v98);
          goto LABEL_218;
        }
        *(struct _FILETIME *)pcbData = wil::filetime::get_system_time(v88);
        v90 = SHRegSetFILETIME(
                v89,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\M365Copilot",
                L"PinningTimestamp",
                (const struct _FILETIME *)pcbData);
        if ( v90 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x249B,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v90,
            pdwTypea);
        v91 = v105;
        *(_QWORD *)pvData = v105;
        if ( v105 )
          _InterlockedAdd((volatile signed __int32 *)(v105 + 288), 1u);
        tip2::details::shared_data<0,0,1>::begin_update(v91 + 8);
        *(_BYTE *)(v91 + 272) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(pvData);
        tip2::details::shared_data<0,0,0>::complete_without_lock(v105 + 8);
      }
      if ( v97 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v97);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v98);
      goto LABEL_214;
    }
    v73 = tip2::details::reason_string(
            (tip2::details *)"M365CopilotPinningTest::reason::privacySettingsManagedByPolicy",
            v80);
    v74 = 18;
LABEL_187:
    tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::complete_and_succeed(
      v104,
      v74,
      v73);
    goto LABEL_188;
  }
  v12 = tip2::details::reason_string(
          (tip2::details *)"M365CopilotPinningTest::reason::userAlreadyPinnedToTaskbarBefore",
          v11);
  v13 = 23;
LABEL_15:
  tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::complete_and_succeed(
    v104,
    v13,
    v12);
LABEL_218:
  tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(v104);
  return 0;
}

```

## disassembly

```asm
0x1401ada70  push    rbp
0x1401ada72  push    rbx
0x1401ada73  push    rsi
0x1401ada74  push    rdi
0x1401ada75  push    r12
0x1401ada77  push    r13
0x1401ada79  push    r14
0x1401ada7b  push    r15
0x1401ada7d  lea     rbp, [rsp-48h]
0x1401ada82  sub     rsp, 148h
0x1401ada89  mov     rax, cs:__security_cookie
0x1401ada90  xor     rax, rsp
0x1401ada93  mov     [rbp+80h+var_50], rax
0x1401ada97  mov     r12d, ecx
0x1401ada9a  mov     eax, ecx
0x1401ada9c  shr     eax, 16h
0x1401ada9f  mov     ebx, 1
0x1401adaa4  test    bl, al
0x1401adaa6  mov     rcx, [rbp+88h]; this
0x1401adaad  jnz     loc_1401AEDB1
0x1401adab3  xor     r13d, r13d
0x1401adab6  mov     [rbp+80h+var_E0], r13
0x1401adaba  lea     rdx, [rbp+80h+var_D0]
0x1401adabe  lea     rcx, [rbp+80h+var_E0]
0x1401adac2  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::start_and_watch_errors(void)
0x1401adac7  lea     rcx, [rbp+80h+var_E0]
0x1401adacb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>,wil::err_returncode_policy>(void)
0x1401adad0  nop
0x1401adad1  lea     rsi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion> `wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::GetImpl(void)'::`2'::impl
0x1401adad8  mov     rcx, rsi
0x1401adadb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(void)
0x1401adae0  lea     r15, aSoftwareMicros_70; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1401adae7  mov     r14, 0FFFFFFFF80000001h
0x1401adaee  test    al, al
0x1401adaf0  jz      loc_1401ADC15
0x1401adaf6  mov     rdi, [rbp+80h+var_98]
0x1401adafa  mov     [rsp+180h+var_130], rdi
0x1401adaff  test    rdi, rdi
0x1401adb02  jz      short loc_1401ADB0B
0x1401adb04  lock add [rdi+120h], ebx
0x1401adb0b  lea     rcx, [rdi+8]
0x1401adb0f  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401adb14  mov     [rdi+115h], r13b
0x1401adb1b  lea     rcx, [rsp+180h+var_130]
0x1401adb20  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401adb25  mov     rdi, [rbp+80h+var_98]
0x1401adb29  mov     [rsp+180h+var_130], rdi
0x1401adb2e  test    rdi, rdi
0x1401adb31  jz      short loc_1401ADB3A
0x1401adb33  lock add [rdi+120h], ebx
0x1401adb3a  lea     rcx, [rdi+8]
0x1401adb3e  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401adb43  mov     [rdi+116h], r13b
0x1401adb4a  lea     rcx, [rsp+180h+var_130]
0x1401adb4f  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401adb54  mov     rdi, [rbp+80h+var_98]
0x1401adb58  mov     [rsp+180h+var_130], rdi
0x1401adb5d  test    rdi, rdi
0x1401adb60  jz      short loc_1401ADB69
0x1401adb62  lock add [rdi+120h], ebx
0x1401adb69  lea     rcx, [rdi+8]
0x1401adb6d  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401adb72  mov     [rdi+119h], r13b
0x1401adb79  lea     rcx, [rsp+180h+var_130]
0x1401adb7e  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401adb83  mov     rdi, [rbp+80h+var_98]
0x1401adb87  mov     [rsp+180h+var_130], rdi
0x1401adb8c  test    rdi, rdi
0x1401adb8f  jz      short loc_1401ADB98
0x1401adb91  lock add [rdi+120h], ebx
0x1401adb98  lea     rcx, [rdi+8]
0x1401adb9c  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401adba1  mov     [rdi+11Dh], r13b
0x1401adba8  lea     rcx, [rsp+180h+var_130]
0x1401adbad  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401adbb2  lea     rcx, unk_1402563C0; this
0x1401adbb9  call    ?ensure_initialized@config_property_base@fc@@IEAAXXZ; fc::config_property_base::ensure_initialized(void)
0x1401adbbe  cmp     cs:byte_1402563E1, r13b
0x1401adbc5  jz      short loc_1401ADC15
0x1401adbc7  mov     [rsp+180h+var_140], r13d
0x1401adbcc  lea     rax, [rsp+180h+var_140]
0x1401adbd1  mov     [rsp+180h+pdwType], rax; int *
0x1401adbd6  lea     r8, aUserpinnedm365; "UserPinnedM365CopilotToTaskbar"
0x1401adbdd  mov     rdx, r15; unsigned __int16 *
0x1401adbe0  mov     rcx, r14; HKEY
0x1401adbe3  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401adbe8  test    eax, eax
0x1401adbea  js      short loc_1401ADC15
0x1401adbec  cmp     [rsp+180h+var_140], r13d
0x1401adbf1  jz      short loc_1401ADC15
0x1401adbf3  lea     rcx, aM365copilotpin_11; "M365CopilotPinningTest::reason::userAlr"...
0x1401adbfa  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1401adbff  mov     edx, 17h
0x1401adc04  mov     r8, rax
0x1401adc07  lea     rcx, [rbp+80h+var_D0]
0x1401adc0b  call    ?complete_and_succeed@?$test_watcher@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::test_watcher<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::complete_and_succeed(ushort,char const *)
0x1401adc10  jmp     loc_1401AED86
0x1401adc15  mov     qword ptr [rbp+80h+var_88.dwLowDateTime], r13
0x1401adc19  lea     r9, [rbp+80h+var_88]; struct _FILETIME *
0x1401adc1d  lea     r8, aPinningtimesta; "PinningTimestamp"
0x1401adc24  mov     rdx, r15; unsigned __int16 *
0x1401adc27  mov     rcx, r14; HKEY
0x1401adc2a  call    ?SHRegGetFILETIME@@YAJPEAUHKEY__@@PEBG1PEAU_FILETIME@@@Z; SHRegGetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME *)
0x1401adc2f  test    eax, eax
0x1401adc31  js      loc_1401ADE29
0x1401adc37  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x1401adc3c  mov     r8, rax
0x1401adc3f  shr     r8, 20h
0x1401adc43  mov     ecx, [rbp+80h+var_88.dwHighDateTime]
0x1401adc46  sub     r8, rcx
0x1401adc49  shl     r8, 20h
0x1401adc4d  mov     ecx, [rbp+80h+var_88.dwLowDateTime]
0x1401adc50  sub     r8, rcx
0x1401adc53  mov     eax, eax
0x1401adc55  add     rax, r8
0x1401adc58  xor     edx, edx
0x1401adc5a  mov     rcx, 0C92A69C000h
0x1401adc64  div     rcx
0x1401adc67  mov     rdi, rax
0x1401adc6a  lea     rdx, [rsp+180h+var_130]
0x1401adc6f  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinning@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinning>::GetCachedVariantState(void)
0x1401adc74  cmp     edi, dword ptr [rsp+180h+var_130+4]
0x1401adc78  ja      short loc_1401ADCCE
0x1401adc7a  mov     rdi, [rbp+80h+var_98]
0x1401adc7e  mov     [rsp+180h+var_130], rdi
0x1401adc83  test    rdi, rdi
0x1401adc86  jz      short loc_1401ADC8F
0x1401adc88  lock add [rdi+120h], ebx
0x1401adc8f  lea     rcx, [rdi+8]
0x1401adc93  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401adc98  mov     [rdi+111h], bl
0x1401adc9e  lea     rcx, [rsp+180h+var_130]
0x1401adca3  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401adca8  mov     rcx, rsi
0x1401adcab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(void)
0x1401adcb0  test    al, al
0x1401adcb2  jz      loc_1401ADFA5
0x1401adcb8  lea     rcx, aM365copilotpin_12; "M365CopilotPinningTest::reason::shownTo"...
0x1401adcbf  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1401adcc4  mov     edx, 3
0x1401adcc9  jmp     loc_1401ADC04
0x1401adcce  mov     [rsp+180h+var_110], r13d
0x1401adcd3  lea     rax, [rsp+180h+var_110]
0x1401adcd8  mov     [rsp+180h+pdwType], rax; int
0x1401adcdd  lea     r8, aPinningsuccess; "PinningSuccess"
0x1401adce4  mov     rdx, r15; unsigned __int16 *
0x1401adce7  mov     rcx, r14; HKEY
0x1401adcea  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1401adcef  test    eax, eax
0x1401adcf1  js      loc_1401ADE29
0x1401adcf7  mov     rcx, rsi
0x1401adcfa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(void)
0x1401adcff  test    al, al
0x1401add01  jz      loc_1401ADD94
0x1401add07  cmp     [rsp+180h+var_110], r13d
0x1401add0c  jz      loc_1401ADE29
0x1401add12  lea     rcx, unk_1402562A0; this
0x1401add19  call    ?ensure_initialized@config_property_base@fc@@IEAAXXZ; fc::config_property_base::ensure_initialized(void)
0x1401add1e  cmp     cs:byte_1402562C1, r13b
0x1401add25  jz      short loc_1401ADD50
0x1401add27  mov     [rsp+180h+var_140], edi
0x1401add2b  lea     rcx, unk_140256270; this
0x1401add32  call    ?ensure_initialized@config_property_base@fc@@IEAAXXZ; fc::config_property_base::ensure_initialized(void)
0x1401add37  lea     rdx, [rsp+180h+var_140]
0x1401add3c  lea     rcx, unk_140256294
0x1401add43  call    ??$key_cmp@I$0A@@details@fc@@YAHAEBI0@Z; fc::details::key_cmp<uint,0>(uint const &,uint const &)
0x1401add48  test    eax, eax
0x1401add4a  jle     loc_1401ADDFB
0x1401add50  mov     rdi, [rbp+80h+var_98]
0x1401add54  mov     [rsp+180h+var_130], rdi
0x1401add59  test    rdi, rdi
0x1401add5c  jz      short loc_1401ADD65
0x1401add5e  lock add [rdi+120h], ebx
0x1401add65  lea     rcx, [rdi+8]
0x1401add69  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401add6e  mov     [rdi+117h], bl
0x1401add74  lea     rcx, [rsp+180h+var_130]
0x1401add79  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401add7e  lea     rcx, aM365copilotpin_2; "M365CopilotPinningTest::reason::hasRunC"...
0x1401add85  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1401add8a  mov     edx, 4
0x1401add8f  jmp     loc_1401ADC04
0x1401add94  cmp     [rsp+180h+var_110], r13d
0x1401add99  jz      loc_1401ADE29
0x1401add9f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_M365CopilotPinningFrequency@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningFrequency@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningFrequency> `wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinningFrequency>::GetImpl(void)'::`2'::impl
0x1401adda6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningFrequency@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningFrequency>::__private_IsEnabled(void)
0x1401addab  test    al, al
0x1401addad  jz      loc_1401ADF77
0x1401addb3  lea     rdx, [rsp+180h+var_130]
0x1401addb8  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningFrequency@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningFrequency>::GetCachedVariantState(void)
0x1401addbd  cmp     edi, dword ptr [rsp+180h+var_130+4]
0x1401addc1  jbe     loc_1401ADF77
0x1401addc7  xor     r9d, r9d; int
0x1401addca  lea     r8, aPinningsuccess; "PinningSuccess"
0x1401addd1  mov     rdx, r15; unsigned __int16 *
0x1401addd4  mov     rcx, r14; HKEY
0x1401addd7  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1401adddc  mov     rcx, [rbp+88h]; this
0x1401adde3  test    eax, eax
0x1401adde5  jns     short loc_1401ADDFB
0x1401adde7  mov     r9d, eax; char *
0x1401addea  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1401addf1  mov     edx, 2340h; void *
0x1401addf6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1401addfb  mov     rdi, [rbp+80h+var_98]
0x1401addff  test    rdi, rdi
0x1401ade02  mov     [rsp+180h+var_130], rdi
0x1401ade07  jz      short loc_1401ADE10
0x1401ade09  lock add [rdi+120h], ebx
0x1401ade10  lea     rcx, [rdi+8]
0x1401ade14  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401ade19  mov     [rdi+112h], bl
0x1401ade1f  lea     rcx, [rsp+180h+var_130]
0x1401ade24  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401ade29  mov     rcx, rsi
0x1401ade2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinningAudienceExpansion>::__private_IsEnabled(void)
0x1401ade31  mov     rsi, 0FFFFFFFF80000002h
0x1401ade38  mov     rdi, 0FFFFFFFFFFFFFFFCh
0x1401ade3f  lea     r15d, [rdi+8]
0x1401ade43  test    al, al
0x1401ade45  jz      loc_1401ADFB7
0x1401ade4b  test    r12d, 3308h
0x1401ade52  jz      loc_1401ADFB7
0x1401ade58  call    ?s_IsCompanionDeviceAccount@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsCompanionDeviceAccount(void)
0x1401ade5d  test    al, al
0x1401ade5f  jnz     loc_1401ADFB7
0x1401ade65  lea     ecx, [rdi+11h]; dwOS
0x1401ade68  call    cs:__imp_IsOS
0x1401ade6e  test    eax, eax
0x1401ade70  jnz     loc_1401ADFB7
0x1401ade76  mov     [rsp+180h+var_140], r13d
0x1401ade7b  mov     [rsp+180h+var_110], r15d
0x1401ade80  lea     rax, [rsp+180h+var_110]
0x1401ade85  mov     [rsp+180h+pcbData], rax; pcbData
0x1401ade8a  lea     rax, [rsp+180h+var_140]
0x1401ade8f  mov     [rsp+180h+pvData], rax; pvData
0x1401ade94  mov     [rsp+180h+pdwType], r13; pdwType
0x1401ade99  mov     r9d, 10010h; dwFlags
0x1401ade9f  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1401adea6  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x1401adead  mov     rcx, rsi; hkey
0x1401adeb0  call    cs:__imp_RegGetValueW
0x1401adeb6  test    eax, eax
0x1401adeb8  jz      short loc_1401ADEF5
0x1401adeba  mov     [rsp+180h+var_110], r15d
0x1401adebf  lea     rax, [rsp+180h+var_110]
0x1401adec4  mov     [rsp+180h+pcbData], rax; pcbData
0x1401adec9  lea     rax, [rsp+180h+var_140]
0x1401adece  mov     [rsp+180h+pvData], rax; pvData
0x1401aded3  mov     [rsp+180h+pdwType], r13; pdwType
0x1401aded8  mov     r9d, 20010010h; dwFlags
0x1401adede  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x1401adee5  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1401adeec  mov     rcx, rsi; hkey
0x1401adeef  call    cs:__imp_RegGetValueW
0x1401adef5  cmp     [rsp+180h+var_140], r13d
0x1401adefa  jnz     loc_1401ADFB7
0x1401adf00  call    ?IsSharedPCMode@@YA_NXZ; IsSharedPCMode(void)
0x1401adf05  test    al, al
0x1401adf07  jnz     loc_1401ADFB7
0x1401adf0d  call    ?s_IsExplorerRestart@CLogonTaskFramework@@CA_NXZ; CLogonTaskFramework::s_IsExplorerRestart(void)
0x1401adf12  test    al, al
0x1401adf14  jnz     loc_1401ADFB7
0x1401adf1a  call    ?IsShellLauncherEnabledForCurrentUser@@YA_NXZ; IsShellLauncherEnabledForCurrentUser(void)
0x1401adf1f  test    al, al
0x1401adf21  jnz     loc_1401ADFB7
0x1401adf27  call    ?IsPreserveOobeAutologonCredentialsSet@@YA_NXZ; IsPreserveOobeAutologonCredentialsSet(void)
0x1401adf2c  test    al, al
0x1401adf2e  jnz     loc_1401ADFB7
0x1401adf34  call    ?IsUnattendedAutoLogonSet@@YA_NXZ; IsUnattendedAutoLogonSet(void)
0x1401adf39  test    al, al
0x1401adf3b  jnz     short loc_1401ADFB7
0x1401adf3d  mov     rcx, rdi; TokenHandle
0x1401adf40  call    IsUserAssignedAccessSingleApp
0x1401adf45  test    eax, eax
0x1401adf47  jnz     short loc_1401ADFB7
0x1401adf49  mov     rcx, rdi; TokenHandle
0x1401adf4c  call    IsUserAssignedAccessMultiApp
0x1401adf51  test    eax, eax
0x1401adf53  jnz     short loc_1401ADFB7
0x1401adf55  mov     rcx, rdi; TokenHandle
0x1401adf58  call    IsUserAssignedAccessSingleAppClassicApp
0x1401adf5d  test    eax, eax
0x1401adf5f  jnz     short loc_1401ADFB7
0x1401adf61  lea     rcx, aM365copilotpin_5; "M365CopilotPinningTest::reason::ineligi"...
0x1401adf68  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1401adf6d  mov     edx, 15h
0x1401adf72  jmp     loc_1401ADC04
0x1401adf77  mov     rdi, [rbp+80h+var_98]
0x1401adf7b  test    rdi, rdi
0x1401adf7e  mov     [rsp+180h+var_130], rdi
0x1401adf83  jz      short loc_1401ADF8C
0x1401adf85  lock add [rdi+120h], ebx
0x1401adf8c  lea     rcx, [rdi+8]
0x1401adf90  call    ?begin_update@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,1>::begin_update(void)
0x1401adf95  mov     [rdi+117h], bl
0x1401adf9b  lea     rcx, [rsp+180h+var_130]
0x1401adfa0  call    ??1?$test_data_control@V?$merged_data@U_tip_M365CopilotPinningTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>::~test_data_control<tip2::details::merged_data<_tip_M365CopilotPinningTest,_tip_M365CopilotPinningTest>>(void)
0x1401adfa5  mov     rcx, [rbp+80h+var_98]
0x1401adfa9  add     rcx, 8
  ... truncated ...
```
