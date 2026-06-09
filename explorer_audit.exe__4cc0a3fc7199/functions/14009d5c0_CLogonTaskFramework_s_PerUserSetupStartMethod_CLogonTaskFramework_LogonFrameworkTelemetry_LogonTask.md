# CLogonTaskFramework::s_PerUserSetupStartMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x14009d5c0`
- end: `0x14009ed60`
- name: `?s_PerUserSetupStartMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `6048`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `84`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x14000a150`
- `0x14000a3e0`
- `0x14000edcc`
- `0x1400119c8`
- `0x1400137b8`
- `0x140019308`
- `0x140019b50`
- `0x14001a5dc`
- `0x14001eba8`
- `0x140028388`
- `0x140028b38`
- `0x14002f838`
- `0x140030944`
- `0x140034af0`
- `0x140035360`
- `0x1400353c0`
- `0x140035578`
- `0x1400361a8`
- `0x14004b6f0`
- `0x140062518`
- `0x140062f4c`
- `0x1400632b0`
- `0x140066c4c`
- `0x1400747a0`
- `0x140075164`
- `0x14007754c`
- `0x140077f58`
- `0x140079b9c`
- `0x140079be0`
- `0x14007afcc`
- `0x14007be88`
- `0x1400811ac`
- `0x14008192c`
- `0x14008194c`
- `0x140082398`
- `0x14008431c`
- `0x140084358`
- `0x140084f84`
- `0x140087624`
- `0x14008809c`
- `0x140090e8c`
- `0x1400954e0`
- `0x14009d298`
- `0x14009d5c0`
- `0x14009ed68`
- `0x14009edd0`
- `0x14009ee4c`
- `0x14009ee9c`
- `0x14009ef5c`
- `0x14009ef7c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009daf4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14009daf4`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x14009d95e`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x14009d95e`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14009d903`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14009d932`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14009d903`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14009d932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009e503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009e583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009ead4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009e503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009e583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14009ead4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e4dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e55c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e4dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e537`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e55c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e5b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14009e886`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14009dc8c`
- `dsreg!DsrGetCxhScenarioInfo` at `0x14009dc8c`
- `dsreg!DsrGetJoinInfo` at `0x14009db3d`
- `dsreg!DsrGetJoinInfo` at `0x14009db3d`
- `dsreg!NgcIncrementPinRetryAttempts` at `0x14009ec7c`
- `dsreg!NgcIncrementPinRetryAttempts` at `0x14009ec7c`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14009dc6d`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14009dcdb`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14009dc6d`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x14009dcdb`

## string_xrefs

- `0x14009d686`: `shell\lib\logontasks\logontasks.cpp`
- `0x14009dde1`: `shell\lib\logontasks\logontasks.cpp`
- `0x14009d6af`: `DisablePerUserSetupTask`
- `0x14009dbd4`: `EnableWindowsHelloProvisioningForSecurityKeys`
- `0x14009db08`: `EnableWindowsHelloLogonProvisioningForSecurityKeys`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CLogonTaskFramework::s_PerUserSetupStartMethod(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  struct CLogonTaskFramework *v2; // rsi
  int v3; // eax
  unsigned int v4; // r9d
  int v5; // ebx
  struct CLogonTaskFramework **v6; // rcx
  _BYTE *v7; // r12
  int updated; // eax
  __int64 v9; // rdx
  int ElevatedObject; // eax
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  const unsigned __int16 *v15; // r13
  int v16; // eax
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  __int64 v19; // rdx
  bool v20; // bl
  __int64 v21; // r8
  const unsigned __int16 *v22; // rdx
  char shouldLaunchCloudExperienceHostForAAD; // al
  const wchar_t *v24; // rdx
  __int64 v25; // r8
  struct _CXH_SCENARIO_INFO *v26; // rbx
  char v27; // al
  struct _CXH_SCENARIO_INFO *v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  __int64 v33; // r13
  __int64 v34; // rdx
  int v35; // eax
  int v36; // eax
  bool *v37; // rdx
  int IsRestoreAllowedByPolicy; // eax
  wil::details::in1diag3 *v39; // rcx
  __int64 v40; // rdx
  int v41; // eax
  bool v42; // bl
  int v43; // eax
  __int64 v44; // rdx
  HSTRING v45; // rbx
  const wchar_t *v46; // rdx
  char IsEnabled; // al
  const wchar_t *v48; // rdx
  int v49; // eax
  int v50; // eax
  HSTRING v51; // rbx
  bool ShouldLaunchGuidedSetup; // al
  PCWSTR StringRawBuffer; // rax
  __int64 v54; // r8
  __int64 v55; // rdx
  PCWSTR v56; // rax
  __int64 v57; // r8
  __int64 v58; // rax
  __int64 v59; // rbx
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // r8
  __int128 *v74; // rdx
  int v75; // ebx
  int v77; // ebx
  int v78; // eax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  __int64 v80; // rdx
  unsigned int v81; // ebx
  __int64 v82; // rdx
  __int64 v83; // rdx
  unsigned __int16 *v84; // rax
  char v85; // dl
  int ShellHostComponentIdForLaunchUri; // eax
  __int64 v87; // rdx
  int v88; // eax
  __int64 v89; // rdx
  __int64 v90; // rdx
  __int64 v91; // rax
  int v92; // eax
  int v93; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-338h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-338h]
  bool shouldLaunchWebExperienceHostForBioRecallSetup; // [rsp+40h] [rbp-318h] BYREF
  char v97; // [rsp+41h] [rbp-317h] BYREF
  char shouldLaunchCloudExperienceHostForPrivacySettings; // [rsp+42h] [rbp-316h]
  PCWSTR v99; // [rsp+48h] [rbp-310h] BYREF
  const unsigned __int16 *v100; // [rsp+50h] [rbp-308h] BYREF
  char v101; // [rsp+58h] [rbp-300h]
  unsigned int v102[2]; // [rsp+60h] [rbp-2F8h] BYREF
  struct _CXH_SCENARIO_INFO *v103; // [rsp+68h] [rbp-2F0h] BYREF
  HSTRING string; // [rsp+70h] [rbp-2E8h] BYREF
  HSTRING v105; // [rsp+78h] [rbp-2E0h] BYREF
  unsigned __int16 *v106; // [rsp+80h] [rbp-2D8h] BYREF
  LPOLESTR lpsz; // [rsp+88h] [rbp-2D0h] BYREF
  __int64 v108; // [rsp+90h] [rbp-2C8h] BYREF
  struct CLogonTaskFramework *v109; // [rsp+98h] [rbp-2C0h] BYREF
  char v110; // [rsp+A0h] [rbp-2B8h]
  const unsigned __int16 *v111; // [rsp+A8h] [rbp-2B0h]
  char *v112; // [rsp+B0h] [rbp-2A8h]
  struct CLogonTaskFramework *v113; // [rsp+B8h] [rbp-2A0h] BYREF
  char v114; // [rsp+C0h] [rbp-298h]
  __int128 v115; // [rsp+C8h] [rbp-290h] BYREF
  __int64 v116; // [rsp+D8h] [rbp-280h]
  unsigned __int64 v117; // [rsp+E0h] [rbp-278h]
  unsigned __int16 *Src[5]; // [rsp+E8h] [rbp-270h] BYREF
  WCHAR String1[264]; // [rsp+110h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  v2 = a1;
  v109 = a1;
  v113 = a1;
  v114 = 1;
  GetUserLogonTracingCorrelationId(&v108, L"PerUserSetupTipTestCorrelationId");
  v111 = (const unsigned __int16 *)((char *)v2 + 592);
  if ( v108 )
    TryFailPreviousUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>((char *)v2 + 592);
  v100 = (const unsigned __int16 *)((char *)v2 + 592);
  StartUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>(&lpsz);
  v3 = SHRegSetString(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserLogonTracing",
         L"PerUserSetupTipTestCorrelationId",
         lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x164D,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
  v102[0] = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
              L"DisablePerUserSetupTask",
              v4,
              (int *)v102) >= 0
    && v102[0] )
  {
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                             (char *)v2 + 592,
                             &v109)
              + 272LL) = 3;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v109);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v108);
    v5 = *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                  (char *)v2 + 592,
                                  &v109)
                   + 272LL);
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v109);
    if ( v5 != 3 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                              (char *)v2 + 592,
                              &v109)
               + 276LL) = 1;
      v6 = &v109;
LABEL_223:
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v6);
      return 0;
    }
    return 0;
  }
  v112 = (char *)v2 + 592;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                           (char *)v2 + 592,
                           &string)
            + 272LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&string);
  v115 = 0;
  v116 = 0;
  v117 = 7;
  LOWORD(v115) = 0;
  v106 = 0;
  v103 = 0;
  v101 = 0;
  v7 = (char *)v2 + 216;
  v105 = (HSTRING)((char *)v2 + 216);
  if ( (*((_DWORD *)v2 + 54) & 0x1206) == 2 )
  {
    updated = UpdateUserPrivacyConsentVersion();
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1672,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)updated,
        bIgnoreCasea);
  }
  shouldLaunchCloudExperienceHostForPrivacySettings = CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForPrivacySettings(*(unsigned int *)v7);
  if ( IsOobeInEnduserSession() && (unsigned int)LUAIsAdminAndIsOSSilentElevationOn() )
  {
    v102[0] = 0;
    if ( (int)SHRegGetDWORD(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
                L"EndUserOOBEStartCount",
                v102) < 0
      || v102[0] < 5 )
    {
      *((_BYTE *)v2 + 236) = 1;
      SHRegSetDWORD(
        HKEY_CURRENT_USER,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
        L"EndUserOOBEStartCount",
        v102[0] + 1);
    }
    else
    {
      string = 0;
      ElevatedObject = CloudExperienceHostCreateElevatedObject(
                         &GUID_1ee026d0_f551_4c71_aea2_f9897b159eaf,
                         &GUID_93b534b1_db4b_40c7_b912_91401a2ec4f0,
                         (void **)&string);
      if ( ElevatedObject >= 0 )
      {
        CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[35],unsigned short const (&)[24]>(retaddr);
        v11 = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)string + 72LL))(string);
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1681,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v11,
            bIgnoreCasea);
        v12 = SHDeleteValueW(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
                L"WillRunOobeEnduserSession");
        if ( v12 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1682,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)v12,
            bIgnoreCasea);
        v13 = SHDeleteValueW(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
                L"EndUserOOBEStartCount");
        if ( v13 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1683,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)v13,
            bIgnoreCasea);
        v14 = SHDeleteKeyW(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Intent\\OobeStorage");
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        wil::details::in1diag3::Log_IfFailedWithExpected(
          retaddr,
          (void *)0x1686,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v14,
          3,
          2,
          -2147024893,
          -2147023728);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x167E,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)ElevatedObject,
          bIgnoreCasea);
      }
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&string);
    }
  }
  v15 = (const unsigned __int16 *)((char *)v2 + 236);
  v99 = (PCWSTR)((char *)v2 + 236);
  if ( *((_BYTE *)v2 + 236) )
  {
    v16 = SHRegSetBOOL(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
            L"WillRunOobeEnduserSession",
            1);
    if ( v16 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1693,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v16,
        bIgnoreCasea);
    v17 = 13;
    v18 = L"ms-cxh://OOBE";
    goto LABEL_33;
  }
  LOBYTE(v9) = *((_BYTE *)v2 + 237);
  if ( (unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthMSA(*(unsigned int *)v7, v9) )
  {
    if ( (*v7 & 2) != 0 )
    {
      v18 = L"ms-cxh://NTH";
      v17 = 12;
    }
    else
    {
      v18 = L"ms-cxh://NTHNGCUPSELL";
      v17 = 21;
    }
LABEL_33:
    std::wstring::_Assign<unsigned short>(&v115, v18, v17);
    goto LABEL_83;
  }
  memset_0(String1, 0, 0x208u);
  v102[0] = 0;
  if ( (int)SHRegGetStringEx(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI",
              L"LastLoggedOnProvider",
              2,
              String1,
              0x104u) >= 0
    && CompareStringOrdinal(String1, -1, L"{F8A1793B-7873-4046-B2A7-1F318747F427}", -1, 1) == 2 )
  {
    if ( (int)SHRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"Software\\Policies\\Microsoft\\FIDO",
                L"EnableWindowsHelloLogonProvisioningForSecurityKeys",
                v102) < 0 )
    {
      v20 = 1;
      string = 0;
      if ( (int)DsrGetJoinInfo(0, &string) >= 0 && string && *((_QWORD *)string + 4) )
      {
        std::wstring::wstring(Src, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork\\");
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(*((_QWORD *)string + 4) + 2 * v21) );
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Append<unsigned short>(Src);
        v22 = (const unsigned __int16 *)Src;
        if ( Src[3] > (unsigned __int16 *)7 )
          v22 = Src[0];
        if ( (int)SHRegGetDWORD(HKEY_LOCAL_MACHINE, v22, L"EnableWindowsHelloProvisioningForSecurityKeys", v102) >= 0 )
          v20 = v102[0] == 0;
        std::wstring::~wstring(Src);
      }
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&string);
    }
    else
    {
      v20 = v102[0] == 0;
    }
  }
  else
  {
    v20 = 0;
  }
  shouldLaunchCloudExperienceHostForAAD = CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForAAD(*(_DWORD *)v105);
  if ( !v20 )
  {
    if ( shouldLaunchCloudExperienceHostForAAD )
    {
      v26 = v103;
      if ( v103 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v100);
        DsrFreeCxhScenarioInfo(v26);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v100);
      }
      v103 = 0;
      if ( (int)DsrGetCxhScenarioInfo(2, &v103) >= 0 )
      {
        v24 = (const wchar_t *)*((_QWORD *)v103 + 1);
        v25 = -1;
        do
          ++v25;
        while ( v24[v25] );
        v101 = 1;
        goto LABEL_58;
      }
LABEL_57:
      v24 = L"ms-cxh://NTHENTORMDM";
      v25 = 20;
LABEL_58:
      std::wstring::_Assign<unsigned short>(&v115, v24, v25);
      goto LABEL_83;
    }
    if ( (unsigned __int8)CLogonTaskFramework::s_ShouldLaunchCloudExperienceHostForMDM(*(_DWORD *)v105) )
      goto LABEL_57;
  }
  v27 = shouldLaunchCloudExperienceHostForPrivacySettings;
  if ( shouldLaunchCloudExperienceHostForPrivacySettings )
    goto LABEL_84;
  try
  {
    shouldLaunchWebExperienceHostForBioRecallSetup = 0;
    v28 = v103;
    if ( v103 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&string);
      DsrFreeCxhScenarioInfo(v28);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&string);
    }
    v103 = 0;
    if ( (int)GetGenericCloudExperienceHostInfo(&v103, &shouldLaunchWebExperienceHostForBioRecallSetup) < 0 )
    {
      v106 = 0;
      if ( (int)GetMSACloudExperienceHostInfo(&v106, &shouldLaunchWebExperienceHostForBioRecallSetup) >= 0 )
      {
        if ( !shouldLaunchWebExperienceHostForBioRecallSetup )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16FC,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)0x8000FFFFLL,
            bIgnoreCasea);
        *((_BYTE *)v2 + 238) = 1;
        v32 = -1;
        do
          ++v32;
        while ( v106[v32] );
        std::wstring::_Assign<unsigned short>(&v115, v106, v32);
      }
    }
    else
    {
      if ( !shouldLaunchWebExperienceHostForBioRecallSetup )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16EC,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)0x8000FFFFLL,
          bIgnoreCasea);
      v29 = *((_QWORD *)v103 + 1);
      v30 = -1;
      do
        ++v30;
      while ( *(_WORD *)(v29 + 2 * v30) );
      std::wstring::_Assign<unsigned short>(&v115, v29, v30);
      if ( *(_DWORD *)v103 == 3 || (unsigned int)(*(_DWORD *)v103 - 6) <= 1 )
        *((_BYTE *)v2 + 238) = 1;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1701,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      v31);
    v101 = 0;
    v111 = v100;
    v2 = v109;
    v15 = v99;
  }
LABEL_83:
  v27 = shouldLaunchCloudExperienceHostForPrivacySettings;
LABEL_84:
  if ( *(_BYTE *)v15 )
  {
LABEL_170:
    if ( !v116 )
    {
      v51 = 0;
      if ( !IsOnUserDesktop() )
      {
        WindowsDeleteString(0);
        string = 0;
        ShouldLaunchGuidedSetup = CLogonTaskFramework::s_ShouldLaunchGuidedSetup(v2, &string);
        v51 = string;
        if ( ShouldLaunchGuidedSetup )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v54 = -1;
          do
            ++v54;
          while ( StringRawBuffer[v54] );
          std::wstring::_Assign<unsigned short>(&v115, StringRawBuffer, v54);
          *((_DWORD *)v2 + 84) = 1;
          *((_DWORD *)v2 + 85) = 1;
        }
      }
      WindowsDeleteString(v51);
      if ( !v116 )
      {
        LOBYTE(v55) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_TailoredScoobeEligibility>::ReportUsage(
          &`wil::Feature<__WilFeatureTraits_Feature_TailoredScoobeEligibility>::GetImpl'::`2'::impl,
          v55);
        WindowsDeleteString(0);
        string = 0;
        if ( !CLogonTaskFramework::s_ShouldLaunchTailoredScoobe(v2, &string) )
        {
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                   v112,
                                   &v99)
                    + 272LL) = 3;
          tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v99);
          WindowsDeleteString(string);
          goto LABEL_221;
        }
        v56 = WindowsGetStringRawBuffer(string, 0);
        v57 = -1;
        do
          ++v57;
        while ( v56[v57] );
        std::wstring::_Assign<unsigned short>(&v115, v56, v57);
        *((_DWORD *)v2 + 84) = 0;
        WindowsDeleteString(string);
      }
    }
    v58 = tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::ensure_data(v111);
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(
      v102,
      v58);
    v59 = *(_QWORD *)v102;
    *(_DWORD *)(*(_QWORD *)v102 + 272LL) = 2;
    *(_DWORD *)(v59 + 280) = *((_DWORD *)v2 + 84);
    *(_DWORD *)(v59 + 284) = *((_DWORD *)v2 + 85);
    std::wstring::operator=(v59 + 288, &v115);
    v60 = *((_QWORD *)v2 + 44);
    if ( v60 )
    {
      v61 = -1;
      do
        ++v61;
      while ( *(_WORD *)(v60 + 2 * v61) );
      std::wstring::_Assign<unsigned short>(v59 + 320, v60, v61);
    }
    v62 = *((_QWORD *)v2 + 45);
    if ( v62 )
    {
      v63 = -1;
      do
        ++v63;
      while ( *(_WORD *)(v62 + 2 * v63) );
      std::wstring::_Assign<unsigned short>(v59 + 352, v62, v63);
    }
    v64 = *((_QWORD *)v2 + 46);
    if ( v64 )
    {
      v65 = -1;
      do
        ++v65;
      while ( *(_WORD *)(v64 + 2 * v65) );
      std::wstring::_Assign<unsigned short>(v59 + 384, v64, v65);
    }
    v66 = *((_QWORD *)v2 + 47);
    if ( v66 )
    {
      v67 = -1;
      do
        ++v67;
      while ( *(_WORD *)(v66 + 2 * v67) );
      std::wstring::_Assign<unsigned short>(v59 + 416, v66, v67);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinning>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinning>::GetImpl'::`2'::impl) )
    {
      v68 = *((_QWORD *)v2 + 48);
      if ( v68 )
      {
        v69 = -1;
        do
          ++v69;
        while ( *(_WORD *)(v68 + 2 * v69) );
        std::wstring::_Assign<unsigned short>(v59 + 448, v68, v69);
      }
      v70 = *((_QWORD *)v2 + 49);
      if ( v70 )
      {
        v71 = -1;
        do
          ++v71;
        while ( *(_WORD *)(v70 + 2 * v71) );
        std::wstring::_Assign<unsigned short>(v59 + 480, v70, v71);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58374879>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_58374879>::GetImpl'::`2'::impl) )
    {
      v72 = *((_QWORD *)v2 + 50);
      if ( v72 )
      {
        v73 = -1;
        do
          ++v73;
        while ( *(_WORD *)(v72 + 2 * v73) );
        std::wstring::_Assign<unsigned short>(v59 + 512, v72, v73);
      }
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::close(v102);
    if ( *((_DWORD *)v2 + 84) == 1 )
    {
      v74 = &v115;
      if ( v117 > 7 )
        v74 = (__int128 *)v115;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v100,
        v74,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 344,
        &v100);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
      if ( !*((_QWORD *)v2 + 43) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18C3,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCasea);
        tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v102);
        goto LABEL_216;
      }
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                               v112,
                               &v99)
                + 272LL) = 3;
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v99);
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v102);
LABEL_221:
      wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v103);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v106);
      std::wstring::~wstring(&v115);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v108);
      v77 = *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                     (char *)v2 + 592,
                                     &v109)
                      + 272LL);
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v109);
      if ( v77 != 3 )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                (char *)v2 + 592,
                                &v99)
                 + 276LL) = 1;
        v6 = (struct CLogonTaskFramework **)&v99;
        goto LABEL_223;
      }
      return 0;
    }
    if ( *((_BYTE *)v2 + 239) )
    {
      v78 = SHRegSetBOOL(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
              L"IsExistingUser",
              (*(_DWORD *)v105 >> 2) & 1);
      if ( v78 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18CA,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v78,
          bIgnoreCasea);
    }
    *((_BYTE *)v2 + 235) = 1;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)v2 + 424, 1, L"CloudExperienceHostFirstWebAppVisible");
    v81 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v82 = 6352;
      goto LABEL_232;
    }
    if ( *((_BYTE *)v2 + 238) )
    {
      v99 = (PCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v115, v80);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v2 + 416);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = Microsoft::WRL::Details::MakeAndInitialize<CredentialResetHostAppManager,IHostAppManager,unsigned short const *>((char *)v2 + 416, &v99);
      v81 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v82 = 6356;
        goto LABEL_232;
      }
      goto LABEL_241;
    }
    LOBYTE(v83) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHost>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Scoobe_ShellHost>::GetImpl'::`2'::impl);
    v84 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v115, v83);
    if ( v85 )
    {
      v105 = 0;
      ShellHostComponentIdForLaunchUri = CLogonTaskFramework::s_GetShellHostComponentIdForLaunchUri(v84, &v105);
      if ( ShellHostComponentIdForLaunchUri >= 0 )
      {
        v97 = 1;
        v99 = WindowsGetStringRawBuffer(v105, 0);
        v100 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v115, v90);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v2 + 416);
        v88 = Microsoft::WRL::Details::MakeAndInitialize<ShellHostManager,IHostAppManager,unsigned short const *,unsigned short const *,bool>(
                (_QWORD *)v2 + 52,
                &v100,
                &v99,
                &v97);
        v81 = v88;
        if ( v88 < 0 )
        {
          v89 = 6367;
          goto LABEL_239;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18DD,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)ShellHostComponentIdForLaunchUri,
          bIgnoreCasea);
        v97 = 1;
        v99 = (PCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v115, v87);
        v88 = Microsoft::WRL::Details::MakeAndInitialize<UserOobeHostAppManager,IHostAppManager,unsigned short const *,bool>(
                (char *)v2 + 416,
                &v99,
                &v97);
        v81 = v88;
        if ( v88 < 0 )
        {
          v89 = 6371;
LABEL_239:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v89,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v88,
            bIgnoreCasea);
          Windows::Internal::String::~String((Windows::Internal::String *)&v105);
          goto LABEL_247;
        }
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&v105);
    }
    else
    {
      v97 = 1;
      v99 = v84;
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = Microsoft::WRL::Details::MakeAndInitialize<UserOobeHostAppManager,IHostAppManager,unsigned short const *,bool>((char *)v2 + 416, &v99, &v97);
      v81 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v82 = 6376;
        goto LABEL_232;
      }
    }
LABEL_241:
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 52) + 24LL))(*((_QWORD *)v2 + 52));
    v81 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      v91 = wistd::__compressed_pair<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase *,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase>>::__compressed_pair<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase *,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase>>(
              &v99,
              &v109);
      wil::ScopeExit<_lambda_e8b785d941a318e7096881f697316bf1_>(&v109, v91);
      v92 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v2 + 52) + 40LL))(*((_QWORD *)v2 + 52), 0);
      v81 = v92;
      if ( v92 >= 0 )
      {
        v110 = 0;
        if ( v101 )
        {
          v93 = NgcIncrementPinRetryAttempts();
          if ( v93 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x18F9,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v93,
              bIgnoreCasea);
        }
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                 v112,
                                 &v99)
                  + 272LL) = 3;
        tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v99);
        wil::details::ScopeExitFn<_lambda_21fc2e4b73a81fdb4734890a3f7de92a_>::~ScopeExitFn<_lambda_21fc2e4b73a81fdb4734890a3f7de92a_>(&v109);
        tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v102);
        wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v103);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v106);
        std::wstring::~wstring(&v115);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v108);
        wil::details::ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>::~ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>(&v113);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18F4,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v92,
        bIgnoreCasea);
      wil::details::ScopeExitFn<_lambda_21fc2e4b73a81fdb4734890a3f7de92a_>::~ScopeExitFn<_lambda_21fc2e4b73a81fdb4734890a3f7de92a_>(&v109);
LABEL_247:
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v102);
      wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v103);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v106);
      std::wstring::~wstring(&v115);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v108);
      wil::details::ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>::~ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>(&v113);
      return v81;
    }
    v82 = 6381;
LABEL_232:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v82,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      bIgnoreCasea);
    goto LABEL_247;
  }
  if ( !v27 || *((_BYTE *)v2 + 239) )
  {
    v33 = 27;
  }
  else
  {
    LOBYTE(v19) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::GetImpl'::`2'::impl,
      v19);
    if ( (*(_BYTE *)v105 & 8) != 0 )
    {
      v33 = 27;
      std::wstring::_Assign<unsigned short>(&v115, L"ms-cxh://NTHPRIVACYONSERVER", 27);
    }
    else
    {
      if ( v116 )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v100,
          L"ms-cxh://NTHPRIVACY",
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          (char *)v2 + 352,
          &v100);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
        if ( !*((_QWORD *)v2 + 44) )
        {
          v34 = 5917;
          goto LABEL_93;
        }
        v35 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                (char *)v2 + 144,
                1,
                L"DestroyCloudExperienceHostAppBackgroundEvent");
        if ( v35 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x171F,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v35,
            bIgnoreCasea);
      }
      else
      {
        std::wstring::_Assign<unsigned short>(&v115, L"ms-cxh://NTHPRIVACY", 19);
      }
      v33 = 27;
    }
    *((_BYTE *)v2 + 239) = shouldLaunchCloudExperienceHostForPrivacySettings;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_44077960>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_44077960>::GetImpl'::`2'::impl)
    && (unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthWASC(*(_DWORD *)v105) )
  {
    if ( v116 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v100,
        L"ms-cxh://NTHWASC",
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 376,
        &v100);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
      if ( !*((_QWORD *)v2 + 47) )
      {
        v34 = 5940;
        goto LABEL_93;
      }
      v36 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)v2 + 144,
              1,
              L"DestroyCloudExperienceHostAppBackgroundEvent");
      if ( v36 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1737,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v36,
          bIgnoreCasea);
    }
    else
    {
      std::wstring::_Assign<unsigned short>(&v115, L"ms-cxh://NTHWASC", 16);
    }
    *((_BYTE *)v2 + 243) = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56882719>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56882719>::GetImpl'::`2'::impl)
    && (unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthAadCloudBackupRestore(*(_DWORD *)v105) )
  {
    if ( v116 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v100,
        L"ms-cxh://NTH/AADCLOUDBACKUPRESTORE",
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 408,
        &v100);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
      if ( !*((_QWORD *)v2 + 51) )
      {
        v34 = 6001;
        goto LABEL_93;
      }
      IsRestoreAllowedByPolicy = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                                   (char *)v2 + 144,
                                   1,
                                   L"DestroyCloudExperienceHostAppBackgroundEvent");
      v39 = retaddr;
      if ( IsRestoreAllowedByPolicy >= 0 )
        goto LABEL_120;
      v40 = 6004;
    }
    else
    {
      shouldLaunchWebExperienceHostForBioRecallSetup = 0;
      IsRestoreAllowedByPolicy = CloudBackupRestoreLogonTask::IsRestoreAllowedByPolicy(
                                   (CloudBackupRestoreLogonTask *)&shouldLaunchWebExperienceHostForBioRecallSetup,
                                   v37);
      v39 = retaddr;
      if ( IsRestoreAllowedByPolicy >= 0 )
      {
        CloudBackupRestoreTelemetry::CloudBackupRestoreNthAadIsRestoreEnabled<bool &>(&shouldLaunchWebExperienceHostForBioRecallSetup);
        if ( shouldLaunchWebExperienceHostForBioRecallSetup )
          std::wstring::_Assign<unsigned short>(&v115, L"ms-cxh://NTH/AADCLOUDBACKUPRESTORE", 34);
        goto LABEL_120;
      }
      v40 = 5984;
    }
    wil::details::in1diag3::_Log_Hr(
      v39,
      (void *)v40,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)IsRestoreAllowedByPolicy,
      bIgnoreCasea);
LABEL_120:
    *((_BYTE *)v2 + 247) = 1;
  }
  LOBYTE(v37) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnusedBioConsent>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_UnusedBioConsent>::GetImpl'::`2'::impl,
    v37);
  if ( (unsigned __int8)CLogonTaskFramework::s_ShouldLaunchCloudExperienceHostForBiometricUseConsent(*(_DWORD *)v105) )
  {
    if ( v116 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v100,
        L"ms-cxh://NTHBIOCONSENT",
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 360,
        &v100);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
      if ( !*((_QWORD *)v2 + 45) )
      {
        v34 = 6029;
        goto LABEL_93;
      }
      v41 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)v2 + 144,
              1,
              L"DestroyCloudExperienceHostAppBackgroundEvent");
      if ( v41 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x178F,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v41,
          bIgnoreCasea);
    }
    else
    {
      std::wstring::_Assign<unsigned short>(&v115, L"ms-cxh://NTHBIOCONSENT", 22);
    }
    *((_BYTE *)v2 + 240) = 1;
  }
  v42 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58374879>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_58374879>::GetImpl'::`2'::impl) )
  {
    shouldLaunchWebExperienceHostForBioRecallSetup = CLogonTaskFramework::s_shouldLaunchWebExperienceHostForBioRecallSetup(*(_DWORD *)v105);
    if ( shouldLaunchWebExperienceHostForBioRecallSetup )
    {
      if ( v116 )
      {
        if ( *((_BYTE *)v2 + 240) )
        {
          v102[0] = 4;
          v97 = 1;
          NthBioRecallSetupTelemetry::ShouldShowNthBioRecallSetupForUser<bool,enum SnapshotCaptureNthLogonSkipReason>(
            &v97,
            v102);
          goto LABEL_139;
        }
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v100,
          L"ms-cxh://NTH/BIORECALLSETUP",
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          (char *)v2 + 400,
          &v100);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
        if ( !*((_QWORD *)v2 + 50) )
        {
          v34 = 6060;
          goto LABEL_93;
        }
        v43 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                (char *)v2 + 144,
                1,
                L"DestroyCloudExperienceHostAppBackgroundEvent");
        if ( v43 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17AE,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v43,
            bIgnoreCasea);
      }
      else
      {
        std::wstring::_Assign<unsigned short>(&v115, L"ms-cxh://NTH/BIORECALLSETUP", 27);
      }
      *((_BYTE *)v2 + 246) = 1;
LABEL_139:
      v42 = shouldLaunchWebExperienceHostForBioRecallSetup;
      goto LABEL_142;
    }
    v42 = 0;
  }
LABEL_142:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52601481>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_52601481>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v44) = v42;
    v45 = v105;
    if ( !(unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForSnapshotCapture(
                             *(_DWORD *)v105,
                             v44) )
      goto LABEL_159;
    if ( !v116 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54825031>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_54825031>::GetImpl'::`2'::impl) )
      {
        v46 = L"ms-cxh://NTH/RECALLSETUP";
        v33 = 24;
      }
      else
      {
        v46 = L"ms-cxh://NTHSNAPSHOTCAPTURE";
      }
      std::wstring::_Assign<unsigned short>(&v115, v46, v33);
LABEL_156:
      *((_BYTE *)v2 + 244) = 1;
      goto LABEL_159;
    }
    if ( !*((_BYTE *)v2 + 240) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54825031>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_54825031>::GetImpl'::`2'::impl);
      v48 = L"ms-cxh://NTH/RECALLSETUP";
      if ( !IsEnabled )
        v48 = L"ms-cxh://NTHSNAPSHOTCAPTURE";
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v100,
        v48,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 384,
        &v100);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
      if ( !*((_QWORD *)v2 + 48) )
      {
        v34 = 6110;
        goto LABEL_93;
      }
      v49 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)v2 + 144,
              1,
              L"DestroyCloudExperienceHostAppBackgroundEvent");
      if ( v49 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x17E0,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v49,
          bIgnoreCasea);
      goto LABEL_156;
    }
    v102[0] = 4;
    v97 = 1;
    NthSnapshotCaptureTelemetry::ShouldShowNthSnapshotCaptureConsentForUser<bool,enum SnapshotCaptureNthLogonSkipReason>(
      &v97,
      v102);
  }
  else
  {
    v45 = v105;
  }
LABEL_159:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinning>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinning>::GetImpl'::`2'::impl)
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl'::`2'::impl)
    || (*(_DWORD *)v45 & 0x400000) != 0
    || !(unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForM365CopilotPinning(*(_DWORD *)v45) )
  {
    goto LABEL_170;
  }
  if ( !v116 )
  {
    std::wstring::_Assign<unsigned short>(&v115, L"ms-cxh://NTH/M365PINNING", 24);
LABEL_169:
    *((_BYTE *)v2 + 245) = 1;
    goto LABEL_170;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v100,
    L"ms-cxh://NTH/M365PINNING",
    -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)v2 + 392,
    &v100);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v100);
  if ( *((_QWORD *)v2 + 49) )
  {
    v50 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (char *)v2 + 144,
            1,
            L"DestroyCloudExperienceHostAppBackgroundEvent");
    if ( v50 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1803,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v50,
        bIgnoreCasea);
    goto LABEL_169;
  }
  v34 = 6144;
LABEL_93:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v34,
    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
    (const char *)0x8007000ELL,
    bIgnoreCasea);
LABEL_216:
  wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v103);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v106);
  std::wstring::~wstring(&v115);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v108);
  v75 = *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                 (char *)v2 + 592,
                                 &v99)
                  + 272LL);
  tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v99);
  if ( v75 != 3 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                            (char *)v2 + 592,
                            &v99)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v99);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x14009d5c0  mov     r11, rsp
0x14009d5c3  mov     [r11+10h], rbx
0x14009d5c7  mov     [r11+18h], rsi
0x14009d5cb  push    rdi
0x14009d5cc  push    r12
0x14009d5ce  push    r13
0x14009d5d0  push    r14
0x14009d5d2  push    r15
0x14009d5d4  sub     rsp, 330h
0x14009d5db  mov     rax, cs:__security_cookie
0x14009d5e2  xor     rax, rsp
0x14009d5e5  mov     [rsp+358h+var_38], rax
0x14009d5ed  mov     rsi, rcx
0x14009d5f0  mov     [r11-2C0h], rcx
0x14009d5f7  xor     edi, edi
0x14009d5f9  mov     [r11-2A0h], rcx
0x14009d600  lea     r14d, [rdi+1]
0x14009d604  mov     [r11-298h], r14b
0x14009d60b  lea     rdx, aPerusersetupti; "PerUserSetupTipTestCorrelationId"
0x14009d612  lea     rcx, [r11-2C8h]
0x14009d619  call    ?GetUserLogonTracingCorrelationId@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGPEAUHKEY__@@@Z; GetUserLogonTracingCorrelationId(ushort const *,HKEY__ *)
0x14009d61e  nop
0x14009d61f  mov     rdx, [rsp+358h+var_2C8]
0x14009d627  lea     rbx, [rsi+250h]
0x14009d62e  mov     [rsp+358h+var_2B0], rbx
0x14009d636  test    rdx, rdx
0x14009d639  jz      short loc_14009D643
0x14009d63b  mov     rcx, rbx
0x14009d63e  call    ??$TryFailPreviousUserLogonTestInstance@V?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@@@YAXPEAV?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@PEBG1PEAUHKEY__@@@Z; TryFailPreviousUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>(tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>> *,ushort const *,ushort const *,HKEY__ *)
0x14009d643  mov     [rsp+358h+var_308], rbx
0x14009d648  mov     rdx, rbx
0x14009d64b  lea     rcx, [rsp+358h+lpsz]; lplpsz
0x14009d653  call    ??$StartUserLogonTestInstance@V?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAV?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@@Z; StartUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>(tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>> *)
0x14009d658  nop
0x14009d659  mov     r9, [rsp+358h+lpsz]; unsigned __int16 *
0x14009d661  lea     r8, aPerusersetupti; "PerUserSetupTipTestCorrelationId"
0x14009d668  lea     rdx, aSoftwareMicros_122; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14009d66f  mov     r13, 0FFFFFFFF80000001h
0x14009d676  mov     rcx, r13; HKEY
0x14009d679  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14009d67e  mov     rcx, [rsp+358h]; this
0x14009d686  lea     r15, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14009d68d  test    eax, eax
0x14009d68f  jns     short loc_14009D6A1
0x14009d691  mov     r9d, eax; char *
0x14009d694  mov     r8, r15; unsigned int
0x14009d697  mov     edx, 164Dh; void *
0x14009d69c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14009d6a1  mov     [rsp+358h+var_2F8], edi
0x14009d6a5  lea     rax, [rsp+358h+var_2F8]
0x14009d6aa  mov     qword ptr [rsp+358h+bIgnoreCase], rax; int
0x14009d6af  lea     r8, aDisableperuser; "DisablePerUserSetupTask"
0x14009d6b6  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14009d6bd  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x14009d6c4  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x14009d6c9  test    eax, eax
0x14009d6cb  js      loc_14009D784
0x14009d6d1  cmp     [rsp+358h+var_2F8], edi
0x14009d6d5  jz      loc_14009D784
0x14009d6db  lea     rcx, [rsi+250h]
0x14009d6e2  lea     rdx, [rsp+358h+var_2C0]
0x14009d6ea  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x14009d6ef  mov     rcx, [rax]
0x14009d6f2  mov     dword ptr [rcx+110h], 3
0x14009d6fc  lea     rcx, [rsp+358h+var_2C0]
0x14009d704  call    ??1?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(void)
0x14009d709  nop
0x14009d70a  lea     rcx, [rsp+358h+lpsz]
0x14009d712  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14009d717  nop
0x14009d718  lea     rcx, [rsp+358h+var_2C8]
0x14009d720  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14009d725  nop
0x14009d726  lea     rdx, [rsp+358h+var_2C0]
0x14009d72e  lea     rcx, [rsi+250h]
0x14009d735  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x14009d73a  mov     rdx, [rax]
0x14009d73d  mov     ebx, [rdx+110h]
0x14009d743  lea     rcx, [rsp+358h+var_2C0]
0x14009d74b  call    ??1?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(void)
0x14009d750  cmp     ebx, 3
0x14009d753  jz      loc_14009ED31
0x14009d759  lea     rdx, [rsp+358h+var_2C0]
0x14009d761  lea     rcx, [rsi+250h]
0x14009d768  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x14009d76d  mov     rcx, [rax]
0x14009d770  mov     [rcx+114h], r14b
0x14009d777  lea     rcx, [rsp+358h+var_2C0]
0x14009d77f  jmp     loc_14009E959
0x14009d784  lea     rax, [rsi+250h]
0x14009d78b  mov     [rsp+358h+var_2A8], rax
0x14009d793  lea     rdx, [rsp+358h+string]
0x14009d798  mov     rcx, rax
0x14009d79b  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x14009d7a0  mov     rcx, [rax]
0x14009d7a3  mov     [rcx+110h], r14d
0x14009d7aa  lea     rcx, [rsp+358h+string]
0x14009d7af  call    ??1?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(void)
0x14009d7b4  xorps   xmm0, xmm0
0x14009d7b7  movups  [rsp+358h+var_290], xmm0
0x14009d7bf  mov     [rsp+358h+var_280], rdi
0x14009d7c7  mov     [rsp+358h+var_278], 7
0x14009d7d3  mov     word ptr [rsp+358h+var_290], di
0x14009d7db  mov     [rsp+358h+var_2D8], rdi
0x14009d7e3  mov     [rsp+358h+var_2F0], rdi
0x14009d7e8  mov     al, dil
0x14009d7eb  mov     [rsp+358h+var_300], al
0x14009d7ef  lea     r12, [rsi+0D8h]
0x14009d7f6  mov     [rsp+358h+var_2E0], r12
0x14009d7fb  mov     eax, [r12]
0x14009d7ff  and     eax, 1206h
0x14009d804  cmp     eax, 2
0x14009d807  jnz     short loc_14009D82A
0x14009d809  call    ?UpdateUserPrivacyConsentVersion@@YAJW4PrivacyConsentPresentationVersion@@W4PrivacyConsentSettingsVersion@@@Z; UpdateUserPrivacyConsentVersion(PrivacyConsentPresentationVersion,PrivacyConsentSettingsVersion)
0x14009d80e  mov     rcx, [rsp+358h]; this
0x14009d816  test    eax, eax
0x14009d818  jns     short loc_14009D82A
0x14009d81a  mov     r9d, eax; char *
0x14009d81d  mov     r8, r15; unsigned int
0x14009d820  mov     edx, 1672h; void *
0x14009d825  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14009d82a  mov     ecx, [r12]
0x14009d82e  call    ?s_shouldLaunchCloudExperienceHostForPrivacySettings@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z; CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForPrivacySettings(LogonTypeFlags)
0x14009d833  mov     [rsp+358h+var_316], al
0x14009d837  call    ?IsOobeInEnduserSession@@YA_NXZ; IsOobeInEnduserSession(void)
0x14009d83c  test    al, al
0x14009d83e  jz      loc_14009D9D8
0x14009d844  call    LUAIsAdminAndIsOSSilentElevationOn
0x14009d849  test    eax, eax
0x14009d84b  jz      loc_14009D9D8
0x14009d851  mov     [rsp+358h+var_2F8], edi
0x14009d855  lea     r9, [rsp+358h+var_2F8]; unsigned int *
0x14009d85a  lea     r8, aEnduseroobesta; "EndUserOOBEStartCount"
0x14009d861  lea     rbx, aSoftwareMicros_107; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14009d868  mov     rdx, rbx; unsigned __int16 *
0x14009d86b  mov     rcx, r13; HKEY
0x14009d86e  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14009d873  test    eax, eax
0x14009d875  js      loc_14009D9B5
0x14009d87b  cmp     [rsp+358h+var_2F8], 5
0x14009d880  jb      loc_14009D9B5
0x14009d886  mov     [rsp+358h+string], rdi
0x14009d88b  lea     r8, [rsp+358h+string]; void **
0x14009d890  lea     rdx, _GUID_93b534b1_db4b_40c7_b912_91401a2ec4f0; struct _GUID *
0x14009d897  lea     rcx, _GUID_1ee026d0_f551_4c71_aea2_f9897b159eaf; struct _GUID *
0x14009d89e  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x14009d8a3  mov     rcx, [rsp+358h]; this
0x14009d8ab  test    eax, eax
0x14009d8ad  jns     short loc_14009D8C4
0x14009d8af  mov     r9d, eax; char *
0x14009d8b2  mov     r8, r15; unsigned int
0x14009d8b5  mov     edx, 167Eh; void *
0x14009d8ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14009d8bf  jmp     loc_14009D9A9
0x14009d8c4  call    ??$CoreEvent1@AEAY0CD@$$CBDAEAY0BI@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0CD@$$CBDAEAY0BI@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[35],ushort const (&)[24]>(char const (&)[35],ushort const (&)[24])
0x14009d8c9  mov     rcx, [rsp+358h+string]
0x14009d8ce  mov     rax, [rcx]
0x14009d8d1  mov     rax, [rax+48h]
0x14009d8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009d8da  mov     rcx, [rsp+358h]; this
0x14009d8e2  test    eax, eax
0x14009d8e4  jns     short loc_14009D8F6
0x14009d8e6  mov     r9d, eax; char *
0x14009d8e9  mov     r8, r15; unsigned int
0x14009d8ec  mov     edx, 1681h; void *
0x14009d8f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14009d8f6  lea     r8, aWillrunoobeend; "WillRunOobeEnduserSession"
0x14009d8fd  mov     rdx, rbx; pszSubKey
0x14009d900  mov     rcx, r13; hkey
0x14009d903  call    cs:__imp_SHDeleteValueW
0x14009d909  mov     rcx, [rsp+358h]; this
0x14009d911  test    eax, eax
0x14009d913  jz      short loc_14009D925
0x14009d915  mov     r9d, eax; char *
0x14009d918  mov     r8, r15; unsigned int
0x14009d91b  mov     edx, 1682h; void *
0x14009d920  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14009d925  lea     r8, aEnduseroobesta; "EndUserOOBEStartCount"
0x14009d92c  mov     rdx, rbx; pszSubKey
0x14009d92f  mov     rcx, r13; hkey
0x14009d932  call    cs:__imp_SHDeleteValueW
0x14009d938  mov     rcx, [rsp+358h]; this
0x14009d940  test    eax, eax
0x14009d942  jz      short loc_14009D954
0x14009d944  mov     r9d, eax; char *
0x14009d947  mov     r8, r15; unsigned int
0x14009d94a  mov     edx, 1683h; void *
0x14009d94f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14009d954  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14009d95b  mov     rcx, r13; hkey
0x14009d95e  call    cs:__imp_SHDeleteKeyW
0x14009d964  test    eax, eax
0x14009d966  jle     short loc_14009D970
0x14009d968  movzx   eax, ax
0x14009d96b  or      eax, 80070000h
0x14009d970  mov     rcx, [rsp+358h]; this
0x14009d978  mov     [rsp+358h+var_320], 80070490h
0x14009d980  mov     [rsp+358h+var_328], 80070003h
0x14009d988  mov     dword ptr [rsp+358h+var_330], 80070002h; char
0x14009d990  mov     [rsp+358h+bIgnoreCase], 3; int
0x14009d998  mov     r9d, eax; char *
0x14009d99b  mov     r8, r15; unsigned int
0x14009d99e  mov     edx, 1686h; void *
0x14009d9a3  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x14009d9a8  nop
0x14009d9a9  lea     rcx, [rsp+358h+string]
0x14009d9ae  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x14009d9b3  jmp     short loc_14009D9DF
0x14009d9b5  mov     [rsi+0ECh], r14b
0x14009d9bc  mov     r9d, [rsp+358h+var_2F8]
0x14009d9c1  inc     r9d; unsigned int
0x14009d9c4  lea     r8, aEnduseroobesta; "EndUserOOBEStartCount"
0x14009d9cb  mov     rdx, rbx; unsigned __int16 *
0x14009d9ce  mov     rcx, r13; HKEY
0x14009d9d1  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x14009d9d6  jmp     short loc_14009D9DF
0x14009d9d8  lea     rbx, aSoftwareMicros_107; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14009d9df  lea     r13, [rsi+0ECh]
0x14009d9e6  mov     [rsp+358h+var_310], r13
0x14009d9eb  cmp     [r13+0], dil
0x14009d9ef  jz      short loc_14009DA45
0x14009d9f1  mov     r9d, r14d; int
0x14009d9f4  lea     r8, aWillrunoobeend; "WillRunOobeEnduserSession"
0x14009d9fb  mov     rdx, rbx; unsigned __int16 *
0x14009d9fe  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x14009da05  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x14009da0a  mov     rcx, [rsp+358h]; this
0x14009da12  test    eax, eax
0x14009da14  jns     short loc_14009DA26
0x14009da16  mov     r9d, eax; char *
0x14009da19  mov     r8, r15; unsigned int
0x14009da1c  mov     edx, 1693h; void *
0x14009da21  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14009da26  mov     r8d, 0Dh
0x14009da2c  lea     rdx, aMsCxhOobe_0; "ms-cxh://OOBE"
0x14009da33  lea     rcx, [rsp+358h+var_290]
0x14009da3b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x14009da40  jmp     loc_14009DE09
0x14009da45  mov     dl, [rsi+0EDh]
0x14009da4b  mov     ecx, [r12]
0x14009da4f  call    ?s_shouldLaunchCloudExperienceHostForNthMSA@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@_N@Z; CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthMSA(LogonTypeFlags,bool)
0x14009da54  test    al, al
0x14009da56  jz      short loc_14009DA7D
0x14009da58  test    byte ptr [r12], 2
0x14009da5d  jz      short loc_14009DA6E
0x14009da5f  lea     rdx, aMsCxhNth; "ms-cxh://NTH"
0x14009da66  mov     r8d, 0Ch
0x14009da6c  jmp     short loc_14009DA33
0x14009da6e  lea     rdx, aMsCxhNthngcups; "ms-cxh://NTHNGCUPSELL"
0x14009da75  mov     r8d, 15h
0x14009da7b  jmp     short loc_14009DA33
0x14009da7d  xor     edx, edx; Val
0x14009da7f  mov     r8d, 208h; Size
0x14009da85  lea     rcx, [rsp+358h+String1]; void *
0x14009da8d  call    memset_0
0x14009da92  mov     [rsp+358h+var_2F8], edi
0x14009da96  mov     dword ptr [rsp+358h+var_330], 104h; unsigned int
0x14009da9e  lea     rax, [rsp+358h+String1]
0x14009daa6  mov     qword ptr [rsp+358h+bIgnoreCase], rax; int
0x14009daab  mov     r9d, 2; int
0x14009dab1  lea     r8, aLastloggedonpr; "LastLoggedOnProvider"
0x14009dab8  lea     rdx, aSoftwareMicros_125; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14009dabf  mov     rbx, 0FFFFFFFF80000002h
0x14009dac6  mov     rcx, rbx; HKEY
0x14009dac9  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x14009dace  or      r12, 0FFFFFFFFFFFFFFFFh
0x14009dad2  test    eax, eax
0x14009dad4  js      loc_14009DC0C
0x14009dada  mov     [rsp+358h+bIgnoreCase], r14d; bIgnoreCase
0x14009dadf  mov     r9d, r12d; cchCount2
0x14009dae2  lea     r8, String2; "{F8A1793B-7873-4046-B2A7-1F318747F427}"
0x14009dae9  mov     edx, r12d; cchCount1
0x14009daec  lea     rcx, [rsp+358h+String1]; lpString1
0x14009daf4  call    cs:__imp_CompareStringOrdinal
0x14009dafa  cmp     eax, 2
0x14009dafd  jnz     loc_14009DC0C
0x14009db03  lea     r9, [rsp+358h+var_2F8]; unsigned int *
0x14009db08  lea     r8, aEnablewindowsh; "EnableWindowsHelloLogonProvisioningForS"...
0x14009db0f  lea     rdx, aSoftwarePolici_5; "Software\\Policies\\Microsoft\\FIDO"
0x14009db16  mov     rcx, rbx; HKEY
0x14009db19  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14009db1e  test    eax, eax
0x14009db20  js      short loc_14009DB2E
0x14009db22  cmp     [rsp+358h+var_2F8], edi
0x14009db26  setz    bl
0x14009db29  jmp     loc_14009DC0F
0x14009db2e  mov     bl, r14b
0x14009db31  mov     [rsp+358h+string], rdi
0x14009db36  lea     rdx, [rsp+358h+string]
0x14009db3b  xor     ecx, ecx
0x14009db3d  call    cs:__imp_DsrGetJoinInfo
0x14009db43  test    eax, eax
0x14009db45  js      loc_14009DC00
0x14009db4b  mov     rax, [rsp+358h+string]
0x14009db50  test    rax, rax
0x14009db53  jz      loc_14009DC00
0x14009db59  cmp     [rax+20h], rdi
0x14009db5d  jz      loc_14009DC00
0x14009db63  lea     rdx, aSoftwareMicros_74; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x14009db6a  lea     rcx, [rsp+358h+Src]
  ... truncated ...
```
