# CLogonTaskFramework::s_PerUserSetupStartMethod(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x1400a08d0`
- end: `0x1400a20db`
- name: `?s_PerUserSetupStartMethod@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `6155`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `0`
- callee_count: `84`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x140005aa8`
- `0x140005e14`
- `0x140006244`
- `0x140006edc`
- `0x1400077a4`
- `0x14000d980`
- `0x14000dc10`
- `0x14000fbdc`
- `0x140012594`
- `0x140012800`
- `0x140015c60`
- `0x140019918`
- `0x14001b2c8`
- `0x14001e264`
- `0x140023118`
- `0x140027b3c`
- `0x140027ba0`
- `0x140027d74`
- `0x140028d14`
- `0x140044f10`
- `0x14004856c`
- `0x140065d58`
- `0x1400667f0`
- `0x140066ba0`
- `0x14006aae0`
- `0x140079298`
- `0x140079cc8`
- `0x14007c5d0`
- `0x14007df04`
- `0x14007df48`
- `0x140080568`
- `0x140081448`
- `0x140086444`
- `0x140086b94`
- `0x140087550`
- `0x140087664`
- `0x14008a018`
- `0x14008a054`
- `0x14008aea0`
- `0x14008d55c`
- `0x14008dc84`
- `0x140097784`
- `0x14009ac68`
- `0x1400a0594`
- `0x1400a08d0`
- `0x1400a20e4`
- `0x1400a214c`
- `0x1400a21cc`
- `0x1400a2294`
- `0x1400a22b8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400a0e16`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400a0e16`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400a0c13`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400a0c48`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400a0c13`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x1400a0c48`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1400a0c7a`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1400a0c7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400a184d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400a18df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400a1e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400a184d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400a18df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400a1e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a18b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1913`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1bee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1821`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a18b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1913`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400a1bee`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400a0fc4`
- `dsreg!DsrGetCxhScenarioInfo` at `0x1400a0fc4`
- `dsreg!DsrGetJoinInfo` at `0x1400a0e65`
- `dsreg!DsrGetJoinInfo` at `0x1400a0e65`
- `dsreg!NgcIncrementPinRetryAttempts` at `0x1400a1ff0`
- `dsreg!NgcIncrementPinRetryAttempts` at `0x1400a1ff0`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x1400a0f9f`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x1400a1019`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x1400a0f9f`
- `dsreg!DsrFreeCxhScenarioInfo` at `0x1400a1019`

## string_xrefs

- `0x1400a0996`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a1125`: `shell\lib\logontasks\logontasks.cpp`
- `0x1400a09bf`: `DisablePerUserSetupTask`
- `0x1400a0e30`: `EnableWindowsHelloLogonProvisioningForSecurityKeys`
- `0x1400a0f02`: `EnableWindowsHelloProvisioningForSecurityKeys`

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
  _BYTE *v15; // r13
  int v16; // eax
  const wchar_t *v17; // rdx
  __int64 v18; // rdx
  bool v19; // bl
  __int64 v20; // r8
  const unsigned __int16 *v21; // rdx
  char shouldLaunchCloudExperienceHostForAAD; // al
  const wchar_t *v23; // rdx
  struct _CXH_SCENARIO_INFO *v24; // rbx
  __int64 v25; // r8
  char v26; // al
  struct _CXH_SCENARIO_INFO *v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  bool *v35; // rdx
  int IsRestoreAllowedByPolicy; // eax
  wil::details::in1diag3 *v37; // rcx
  __int64 v38; // rdx
  int v39; // eax
  bool v40; // bl
  int v41; // eax
  __int64 v42; // rdx
  HSTRING v43; // rbx
  const wchar_t *v44; // rdx
  char IsEnabled; // al
  const wchar_t *v46; // rdx
  int v47; // eax
  int v48; // eax
  HSTRING v49; // rbx
  bool ShouldLaunchGuidedSetup; // al
  PCWSTR StringRawBuffer; // rax
  __int64 v52; // r8
  __int64 v53; // rdx
  PCWSTR v54; // rax
  __int64 v55; // r8
  __int64 v56; // rax
  __int64 v57; // rbx
  __int64 v58; // rdx
  __int64 v59; // r8
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
  __int128 *v72; // rdx
  int v73; // ebx
  int v75; // ebx
  int v76; // eax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  __int64 v78; // rdx
  unsigned int v79; // ebx
  __int64 v80; // rdx
  __int64 v81; // rdx
  unsigned __int16 *v82; // rax
  char v83; // dl
  int ShellHostComponentIdForLaunchUri; // eax
  __int64 v85; // rdx
  int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // rdx
  __int64 v89; // rax
  int v90; // eax
  int v91; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-338h]
  unsigned int bIgnoreCasea; // [rsp+20h] [rbp-338h]
  bool shouldLaunchWebExperienceHostForBioRecallSetup; // [rsp+40h] [rbp-318h] BYREF
  char v95; // [rsp+41h] [rbp-317h] BYREF
  char shouldLaunchCloudExperienceHostForPrivacySettings; // [rsp+42h] [rbp-316h]
  PCWSTR v97; // [rsp+48h] [rbp-310h] BYREF
  __int64 v98; // [rsp+50h] [rbp-308h] BYREF
  char v99; // [rsp+58h] [rbp-300h]
  unsigned int v100[2]; // [rsp+60h] [rbp-2F8h] BYREF
  struct _CXH_SCENARIO_INFO *v101; // [rsp+68h] [rbp-2F0h] BYREF
  HSTRING string; // [rsp+70h] [rbp-2E8h] BYREF
  HSTRING v103; // [rsp+78h] [rbp-2E0h] BYREF
  unsigned __int16 *v104; // [rsp+80h] [rbp-2D8h] BYREF
  LPOLESTR lpsz; // [rsp+88h] [rbp-2D0h] BYREF
  __int64 v106; // [rsp+90h] [rbp-2C8h] BYREF
  struct CLogonTaskFramework *v107; // [rsp+98h] [rbp-2C0h] BYREF
  char v108; // [rsp+A0h] [rbp-2B8h]
  char *v109; // [rsp+A8h] [rbp-2B0h]
  char *v110; // [rsp+B0h] [rbp-2A8h]
  struct CLogonTaskFramework *v111; // [rsp+B8h] [rbp-2A0h] BYREF
  char v112; // [rsp+C0h] [rbp-298h]
  __int128 v113; // [rsp+C8h] [rbp-290h] BYREF
  __int64 v114; // [rsp+D8h] [rbp-280h]
  unsigned __int64 v115; // [rsp+E0h] [rbp-278h]
  unsigned __int16 *Src[5]; // [rsp+E8h] [rbp-270h] BYREF
  WCHAR String1[264]; // [rsp+110h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+0h]

  v2 = a1;
  v107 = a1;
  v111 = a1;
  v112 = 1;
  GetUserLogonTracingCorrelationId(&v106, L"PerUserSetupTipTestCorrelationId");
  v109 = (char *)v2 + 608;
  if ( v106 )
    TryFailPreviousUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>((char *)v2 + 608);
  v98 = (__int64)v2 + 608;
  StartUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>(&lpsz);
  v3 = SHRegSetString(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserLogonTracing",
         L"PerUserSetupTipTestCorrelationId",
         lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1646,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
  v100[0] = 0;
  if ( (int)SHRegGetBOOLWithREGSAM(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
              L"DisablePerUserSetupTask",
              v4,
              (int *)v100) >= 0
    && v100[0] )
  {
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                             (char *)v2 + 608,
                             &v107)
              + 272LL) = 3;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v107);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v106);
    v5 = *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                  (char *)v2 + 608,
                                  &v107)
                   + 272LL);
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v107);
    if ( v5 != 3 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                              (char *)v2 + 608,
                              &v107)
               + 276LL) = 1;
      v6 = &v107;
LABEL_221:
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v6);
      return 0;
    }
    return 0;
  }
  v110 = (char *)v2 + 608;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                           (char *)v2 + 608,
                           &string)
            + 272LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&string);
  v113 = 0;
  v114 = 0;
  v115 = 7;
  LOWORD(v113) = 0;
  v104 = 0;
  v101 = 0;
  v99 = 0;
  v7 = (char *)v2 + 216;
  v103 = (HSTRING)((char *)v2 + 216);
  if ( (*((_DWORD *)v2 + 54) & 0x1206) == 2 )
  {
    updated = UpdateUserPrivacyConsentVersion();
    if ( updated < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x166B,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)updated,
        bIgnoreCasea);
  }
  shouldLaunchCloudExperienceHostForPrivacySettings = CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForPrivacySettings(*(unsigned int *)v7);
  if ( IsOobeInEnduserSession() && (unsigned int)LUAIsAdminAndIsOSSilentElevationOn() )
  {
    v100[0] = 0;
    if ( (int)SHRegGetDWORD(
                HKEY_CURRENT_USER,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
                L"EndUserOOBEStartCount",
                v100) < 0
      || v100[0] < 5 )
    {
      *((_BYTE *)v2 + 236) = 1;
      SHRegSetDWORD(
        HKEY_CURRENT_USER,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost",
        L"EndUserOOBEStartCount",
        v100[0] + 1);
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
            (void *)0x167A,
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
            (void *)0x167B,
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
            (void *)0x167C,
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
          (void *)0x167F,
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
          (void *)0x1677,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)ElevatedObject,
          bIgnoreCasea);
      }
      wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(&string);
    }
  }
  v15 = (char *)v2 + 236;
  v97 = (PCWSTR)((char *)v2 + 236);
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
        (void *)0x168C,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v16,
        bIgnoreCasea);
    v17 = L"ms-cxh://OOBE";
    goto LABEL_33;
  }
  LOBYTE(v9) = *((_BYTE *)v2 + 237);
  if ( (unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthMSA(*(unsigned int *)v7, v9) )
  {
    if ( (*v7 & 2) != 0 )
      v17 = L"ms-cxh://NTH";
    else
      v17 = L"ms-cxh://NTHNGCUPSELL";
LABEL_33:
    std::wstring::_Assign<unsigned short>(&v113, v17);
    goto LABEL_83;
  }
  memset_0(String1, 0, 0x208u);
  v100[0] = 0;
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
                v100) < 0 )
    {
      v19 = 1;
      string = 0;
      if ( (int)DsrGetJoinInfo(0, &string) >= 0 && string && *((_QWORD *)string + 4) )
      {
        std::wstring::wstring(Src, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork\\");
        v20 = -1;
        do
          ++v20;
        while ( *(_WORD *)(*((_QWORD *)string + 4) + 2 * v20) );
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Append<unsigned short>(Src);
        v21 = (const unsigned __int16 *)Src;
        if ( Src[3] > (unsigned __int16 *)7 )
          v21 = Src[0];
        if ( (int)SHRegGetDWORD(HKEY_LOCAL_MACHINE, v21, L"EnableWindowsHelloProvisioningForSecurityKeys", v100) >= 0 )
          v19 = v100[0] == 0;
        std::wstring::~wstring(Src);
      }
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&string);
    }
    else
    {
      v19 = v100[0] == 0;
    }
  }
  else
  {
    v19 = 0;
  }
  shouldLaunchCloudExperienceHostForAAD = CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForAAD(*(_DWORD *)v103);
  if ( !v19 )
  {
    if ( shouldLaunchCloudExperienceHostForAAD )
    {
      v24 = v101;
      if ( v101 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v98);
        DsrFreeCxhScenarioInfo(v24);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v98);
      }
      v101 = 0;
      if ( (int)DsrGetCxhScenarioInfo(2, &v101) >= 0 )
      {
        v23 = (const wchar_t *)*((_QWORD *)v101 + 1);
        v25 = -1;
        do
          ++v25;
        while ( v23[v25] );
        v99 = 1;
        goto LABEL_58;
      }
LABEL_57:
      v23 = L"ms-cxh://NTHENTORMDM";
LABEL_58:
      std::wstring::_Assign<unsigned short>(&v113, v23);
      goto LABEL_83;
    }
    if ( (unsigned __int8)CLogonTaskFramework::s_ShouldLaunchCloudExperienceHostForMDM(*(_DWORD *)v103) )
      goto LABEL_57;
  }
  v26 = shouldLaunchCloudExperienceHostForPrivacySettings;
  if ( shouldLaunchCloudExperienceHostForPrivacySettings )
    goto LABEL_84;
  try
  {
    shouldLaunchWebExperienceHostForBioRecallSetup = 0;
    v27 = v101;
    if ( v101 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&string);
      DsrFreeCxhScenarioInfo(v27);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&string);
    }
    v101 = 0;
    if ( (int)GetGenericCloudExperienceHostInfo(&v101, &shouldLaunchWebExperienceHostForBioRecallSetup) < 0 )
    {
      v104 = 0;
      if ( (int)GetMSACloudExperienceHostInfo(&v104, &shouldLaunchWebExperienceHostForBioRecallSetup) >= 0 )
      {
        if ( !shouldLaunchWebExperienceHostForBioRecallSetup )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x16F5,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)0x8000FFFFLL,
            bIgnoreCasea);
        *((_BYTE *)v2 + 238) = 1;
        v31 = -1;
        do
          ++v31;
        while ( v104[v31] );
        std::wstring::_Assign<unsigned short>(&v113, v104);
      }
    }
    else
    {
      if ( !shouldLaunchWebExperienceHostForBioRecallSetup )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16E5,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)0x8000FFFFLL,
          bIgnoreCasea);
      v28 = *((_QWORD *)v101 + 1);
      v29 = -1;
      do
        ++v29;
      while ( *(_WORD *)(v28 + 2 * v29) );
      std::wstring::_Assign<unsigned short>(&v113, v28);
      if ( *(_DWORD *)v101 == 3 || (unsigned int)(*(_DWORD *)v101 - 6) <= 1 )
        *((_BYTE *)v2 + 238) = 1;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x16FA,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      v30);
    v99 = 0;
    v109 = (char *)v98;
    v2 = v107;
    v15 = v97;
  }
LABEL_83:
  v26 = shouldLaunchCloudExperienceHostForPrivacySettings;
LABEL_84:
  if ( *v15 )
  {
LABEL_168:
    if ( !v114 )
    {
      v49 = 0;
      if ( !IsOnUserDesktop() )
      {
        WindowsDeleteString(0);
        string = 0;
        ShouldLaunchGuidedSetup = CLogonTaskFramework::s_ShouldLaunchGuidedSetup(v2, &string);
        v49 = string;
        if ( ShouldLaunchGuidedSetup )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v52 = -1;
          do
            ++v52;
          while ( StringRawBuffer[v52] );
          std::wstring::_Assign<unsigned short>(&v113, StringRawBuffer);
          *((_DWORD *)v2 + 84) = 1;
          *((_DWORD *)v2 + 85) = 1;
        }
      }
      WindowsDeleteString(v49);
      if ( !v114 )
      {
        LOBYTE(v53) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_TailoredScoobeEligibility>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_TailoredScoobeEligibility>::GetImpl'::`2'::impl,
          v53);
        WindowsDeleteString(0);
        string = 0;
        if ( !CLogonTaskFramework::s_ShouldLaunchTailoredScoobe(v2, &string) )
        {
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                   v110,
                                   &v97)
                    + 272LL) = 3;
          tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v97);
          WindowsDeleteString(string);
          goto LABEL_219;
        }
        v54 = WindowsGetStringRawBuffer(string, 0);
        v55 = -1;
        do
          ++v55;
        while ( v54[v55] );
        std::wstring::_Assign<unsigned short>(&v113, v54);
        *((_DWORD *)v2 + 84) = 0;
        WindowsDeleteString(string);
      }
    }
    v56 = tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::ensure_data(v109);
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(
      v100,
      v56);
    v57 = *(_QWORD *)v100;
    *(_DWORD *)(*(_QWORD *)v100 + 272LL) = 2;
    *(_DWORD *)(v57 + 280) = *((_DWORD *)v2 + 84);
    *(_DWORD *)(v57 + 284) = *((_DWORD *)v2 + 85);
    std::wstring::operator=(v57 + 288, &v113);
    v58 = *((_QWORD *)v2 + 44);
    if ( v58 )
    {
      v59 = -1;
      do
        ++v59;
      while ( *(_WORD *)(v58 + 2 * v59) );
      std::wstring::_Assign<unsigned short>(v57 + 320, v58);
    }
    v60 = *((_QWORD *)v2 + 45);
    if ( v60 )
    {
      v61 = -1;
      do
        ++v61;
      while ( *(_WORD *)(v60 + 2 * v61) );
      std::wstring::_Assign<unsigned short>(v57 + 352, v60);
    }
    v62 = *((_QWORD *)v2 + 46);
    if ( v62 )
    {
      v63 = -1;
      do
        ++v63;
      while ( *(_WORD *)(v62 + 2 * v63) );
      std::wstring::_Assign<unsigned short>(v57 + 384, v62);
    }
    v64 = *((_QWORD *)v2 + 47);
    if ( v64 )
    {
      v65 = -1;
      do
        ++v65;
      while ( *(_WORD *)(v64 + 2 * v65) );
      std::wstring::_Assign<unsigned short>(v57 + 416, v64);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinning>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinning>::GetImpl'::`2'::impl) )
    {
      v66 = *((_QWORD *)v2 + 48);
      if ( v66 )
      {
        v67 = -1;
        do
          ++v67;
        while ( *(_WORD *)(v66 + 2 * v67) );
        std::wstring::_Assign<unsigned short>(v57 + 448, v66);
      }
      v68 = *((_QWORD *)v2 + 49);
      if ( v68 )
      {
        v69 = -1;
        do
          ++v69;
        while ( *(_WORD *)(v68 + 2 * v69) );
        std::wstring::_Assign<unsigned short>(v57 + 480, v68);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58374879>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58374879>::GetImpl'::`2'::impl) )
    {
      v70 = *((_QWORD *)v2 + 50);
      if ( v70 )
      {
        v71 = -1;
        do
          ++v71;
        while ( *(_WORD *)(v70 + 2 * v71) );
        std::wstring::_Assign<unsigned short>(v57 + 512, v70);
      }
    }
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::close(v100);
    if ( *((_DWORD *)v2 + 84) == 1 )
    {
      v72 = &v113;
      if ( v115 > 7 )
        v72 = (__int128 *)v113;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v98,
        v72,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 344,
        &v98);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
      if ( !*((_QWORD *)v2 + 43) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18BC,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)0x8007000ELL,
          bIgnoreCasea);
        tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v100);
        goto LABEL_214;
      }
      *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                               v110,
                               &v97)
                + 272LL) = 3;
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v97);
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v100);
LABEL_219:
      wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v101);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v104);
      std::wstring::~wstring(&v113);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v106);
      v75 = *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                     (char *)v2 + 608,
                                     &v107)
                      + 272LL);
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v107);
      if ( v75 != 3 )
      {
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                (char *)v2 + 608,
                                &v97)
                 + 276LL) = 1;
        v6 = (struct CLogonTaskFramework **)&v97;
        goto LABEL_221;
      }
      return 0;
    }
    if ( *((_BYTE *)v2 + 239) )
    {
      v76 = SHRegSetBOOL(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
              L"IsExistingUser",
              (*(_DWORD *)v103 >> 2) & 1);
      if ( v76 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18C3,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v76,
          bIgnoreCasea);
    }
    *((_BYTE *)v2 + 235) = 1;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)v2 + 424, 1, L"CloudExperienceHostFirstWebAppVisible");
    v79 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      v80 = 6345;
      goto LABEL_230;
    }
    if ( *((_BYTE *)v2 + 238) )
    {
      v97 = (PCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v113, v78);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v2 + 416);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = Microsoft::WRL::Details::MakeAndInitialize<CredentialResetHostAppManager,IHostAppManager,unsigned short const *>((char *)v2 + 416, &v97);
      v79 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v80 = 6349;
        goto LABEL_230;
      }
      goto LABEL_239;
    }
    LOBYTE(v81) = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Scoobe_ShellHost>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Scoobe_ShellHost>::GetImpl'::`2'::impl);
    v82 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v113, v81);
    if ( v83 )
    {
      v103 = 0;
      ShellHostComponentIdForLaunchUri = CLogonTaskFramework::s_GetShellHostComponentIdForLaunchUri(v82);
      if ( ShellHostComponentIdForLaunchUri >= 0 )
      {
        v95 = 1;
        v97 = WindowsGetStringRawBuffer(v103, 0);
        v98 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v113, v88);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v2 + 416);
        v86 = Microsoft::WRL::Details::MakeAndInitialize<ShellHostManager,IHostAppManager,unsigned short const *,unsigned short const *,bool>(
                (char *)v2 + 416,
                &v98,
                &v97,
                &v95);
        v79 = v86;
        if ( v86 < 0 )
        {
          v87 = 6360;
          goto LABEL_237;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18D6,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)ShellHostComponentIdForLaunchUri,
          bIgnoreCasea);
        v95 = 1;
        v97 = (PCWSTR)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v113, v85);
        v86 = Microsoft::WRL::Details::MakeAndInitialize<UserOobeHostAppManager,IHostAppManager,unsigned short const *,bool>(
                (char *)v2 + 416,
                &v97,
                &v95);
        v79 = v86;
        if ( v86 < 0 )
        {
          v87 = 6364;
LABEL_237:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v87,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v86,
            bIgnoreCasea);
          Windows::Internal::String::~String((Windows::Internal::String *)&v103);
          goto LABEL_245;
        }
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&v103);
    }
    else
    {
      v95 = 1;
      v97 = v82;
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = Microsoft::WRL::Details::MakeAndInitialize<UserOobeHostAppManager,IHostAppManager,unsigned short const *,bool>((char *)v2 + 416, &v97, &v95);
      v79 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
      {
        v80 = 6369;
        goto LABEL_230;
      }
    }
LABEL_239:
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v2 + 52) + 24LL))(*((_QWORD *)v2 + 52));
    v79 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      v89 = wistd::__compressed_pair<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase *,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase>>::__compressed_pair<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase *,wistd::default_delete<Windows::Internal::AssignedAccess::AssignedAccessConfigStoreBase>>(
              &v97,
              &v107);
      wil::ScopeExit<_lambda_83c54df9492d00a982b24c196f9929d5_>(&v107, v89);
      v90 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v2 + 52) + 40LL))(*((_QWORD *)v2 + 52), 0);
      v79 = v90;
      if ( v90 >= 0 )
      {
        v108 = 0;
        if ( v99 )
        {
          v91 = NgcIncrementPinRetryAttempts();
          if ( v91 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x18F2,
              (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
              (const char *)(unsigned int)v91,
              bIgnoreCasea);
        }
        *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                 v110,
                                 &v97)
                  + 272LL) = 3;
        tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v97);
        wil::details::ScopeExitFn<_lambda_3895cb56bf0d043e3e4e5fa7d0f7f490_>::~ScopeExitFn<_lambda_3895cb56bf0d043e3e4e5fa7d0f7f490_>(&v107);
        tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v100);
        wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v101);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v104);
        std::wstring::~wstring(&v113);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v106);
        wil::details::ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>::~ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>(&v111);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18ED,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v90,
        bIgnoreCasea);
      wil::details::ScopeExitFn<_lambda_3895cb56bf0d043e3e4e5fa7d0f7f490_>::~ScopeExitFn<_lambda_3895cb56bf0d043e3e4e5fa7d0f7f490_>(&v107);
LABEL_245:
      tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(v100);
      wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v101);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v104);
      std::wstring::~wstring(&v113);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v106);
      wil::details::ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>::~ScopeExitFn<_lambda_126a9e8f2c9e3a6f5757eb468b6ab690_>(&v111);
      return v79;
    }
    v80 = 6374;
LABEL_230:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v80,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      bIgnoreCasea);
    goto LABEL_245;
  }
  if ( v26 && !*((_BYTE *)v2 + 239) )
  {
    LOBYTE(v18) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_InitiateNTHPrivacyOnServer>::GetImpl'::`2'::impl,
      v18);
    if ( (*(_BYTE *)v103 & 8) != 0 )
    {
      std::wstring::_Assign<unsigned short>(&v113, L"ms-cxh://NTHPRIVACYONSERVER");
    }
    else if ( v114 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v98,
        L"ms-cxh://NTHPRIVACY",
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 352,
        &v98);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
      if ( !*((_QWORD *)v2 + 44) )
      {
        v32 = 5910;
        goto LABEL_93;
      }
      v33 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)v2 + 144,
              1,
              L"DestroyCloudExperienceHostAppBackgroundEvent");
      if ( v33 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1718,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v33,
          bIgnoreCasea);
    }
    else
    {
      std::wstring::_Assign<unsigned short>(&v113, L"ms-cxh://NTHPRIVACY");
    }
    *((_BYTE *)v2 + 239) = shouldLaunchCloudExperienceHostForPrivacySettings;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_44077960>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_44077960>::GetImpl'::`2'::impl)
    && (unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthWASC(*(_DWORD *)v103) )
  {
    if ( v114 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v98,
        L"ms-cxh://NTHWASC",
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 376,
        &v98);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
      if ( !*((_QWORD *)v2 + 47) )
      {
        v32 = 5933;
        goto LABEL_93;
      }
      v34 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)v2 + 144,
              1,
              L"DestroyCloudExperienceHostAppBackgroundEvent");
      if ( v34 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1730,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v34,
          bIgnoreCasea);
    }
    else
    {
      std::wstring::_Assign<unsigned short>(&v113, L"ms-cxh://NTHWASC");
    }
    *((_BYTE *)v2 + 243) = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56882719>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56882719>::GetImpl'::`2'::impl)
    && (unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthAadCloudBackupRestore(*(_DWORD *)v103) )
  {
    if ( v114 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v98,
        L"ms-cxh://NTH/AADCLOUDBACKUPRESTORE",
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 408,
        &v98);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
      if ( !*((_QWORD *)v2 + 51) )
      {
        v32 = 5994;
        goto LABEL_93;
      }
      IsRestoreAllowedByPolicy = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                                   (char *)v2 + 144,
                                   1,
                                   L"DestroyCloudExperienceHostAppBackgroundEvent");
      v37 = retaddr;
      if ( IsRestoreAllowedByPolicy >= 0 )
        goto LABEL_118;
      v38 = 5997;
    }
    else
    {
      shouldLaunchWebExperienceHostForBioRecallSetup = 0;
      IsRestoreAllowedByPolicy = CloudBackupRestoreLogonTask::IsRestoreAllowedByPolicy(
                                   (CloudBackupRestoreLogonTask *)&shouldLaunchWebExperienceHostForBioRecallSetup,
                                   v35);
      v37 = retaddr;
      if ( IsRestoreAllowedByPolicy >= 0 )
      {
        CloudBackupRestoreTelemetry::CloudBackupRestoreNthAadIsRestoreEnabled<bool &>(&shouldLaunchWebExperienceHostForBioRecallSetup);
        if ( shouldLaunchWebExperienceHostForBioRecallSetup )
          std::wstring::_Assign<unsigned short>(&v113, L"ms-cxh://NTH/AADCLOUDBACKUPRESTORE");
        goto LABEL_118;
      }
      v38 = 5977;
    }
    wil::details::in1diag3::_Log_Hr(
      v37,
      (void *)v38,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)IsRestoreAllowedByPolicy,
      bIgnoreCasea);
LABEL_118:
    *((_BYTE *)v2 + 247) = 1;
  }
  LOBYTE(v35) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnusedBioConsent>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_UnusedBioConsent>::GetImpl'::`2'::impl,
    v35);
  if ( (unsigned __int8)CLogonTaskFramework::s_ShouldLaunchCloudExperienceHostForBiometricUseConsent(*(_DWORD *)v103) )
  {
    if ( v114 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v98,
        L"ms-cxh://NTHBIOCONSENT",
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 360,
        &v98);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
      if ( !*((_QWORD *)v2 + 45) )
      {
        v32 = 6022;
        goto LABEL_93;
      }
      v39 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)v2 + 144,
              1,
              L"DestroyCloudExperienceHostAppBackgroundEvent");
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1788,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v39,
          bIgnoreCasea);
    }
    else
    {
      std::wstring::_Assign<unsigned short>(&v113, L"ms-cxh://NTHBIOCONSENT");
    }
    *((_BYTE *)v2 + 240) = 1;
  }
  v40 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58374879>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58374879>::GetImpl'::`2'::impl) )
  {
    shouldLaunchWebExperienceHostForBioRecallSetup = CLogonTaskFramework::s_shouldLaunchWebExperienceHostForBioRecallSetup(*(_DWORD *)v103);
    if ( shouldLaunchWebExperienceHostForBioRecallSetup )
    {
      if ( v114 )
      {
        if ( *((_BYTE *)v2 + 240) )
        {
          v100[0] = 4;
          v95 = 1;
          NthBioRecallSetupTelemetry::ShouldShowNthBioRecallSetupForUser<bool,enum SnapshotCaptureNthLogonSkipReason>(
            &v95,
            v100);
          goto LABEL_137;
        }
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v98,
          L"ms-cxh://NTH/BIORECALLSETUP",
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          (char *)v2 + 400,
          &v98);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
        if ( !*((_QWORD *)v2 + 50) )
        {
          v32 = 6053;
          goto LABEL_93;
        }
        v41 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                (char *)v2 + 144,
                1,
                L"DestroyCloudExperienceHostAppBackgroundEvent");
        if ( v41 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17A7,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)v41,
            bIgnoreCasea);
      }
      else
      {
        std::wstring::_Assign<unsigned short>(&v113, L"ms-cxh://NTH/BIORECALLSETUP");
      }
      *((_BYTE *)v2 + 246) = 1;
LABEL_137:
      v40 = shouldLaunchWebExperienceHostForBioRecallSetup;
      goto LABEL_140;
    }
    v40 = 0;
  }
LABEL_140:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52601481>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52601481>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v42) = v40;
    v43 = v103;
    if ( !(unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForSnapshotCapture(
                             *(_DWORD *)v103,
                             v42) )
      goto LABEL_157;
    if ( !v114 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54825031>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54825031>::GetImpl'::`2'::impl) )
        v44 = L"ms-cxh://NTH/RECALLSETUP";
      else
        v44 = L"ms-cxh://NTHSNAPSHOTCAPTURE";
      std::wstring::_Assign<unsigned short>(&v113, v44);
LABEL_154:
      *((_BYTE *)v2 + 244) = 1;
      goto LABEL_157;
    }
    if ( !*((_BYTE *)v2 + 240) )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_54825031>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54825031>::GetImpl'::`2'::impl);
      v46 = L"ms-cxh://NTH/RECALLSETUP";
      if ( !IsEnabled )
        v46 = L"ms-cxh://NTHSNAPSHOTCAPTURE";
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v98,
        v46,
        -1);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        (char *)v2 + 384,
        &v98);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
      if ( !*((_QWORD *)v2 + 48) )
      {
        v32 = 6103;
        goto LABEL_93;
      }
      v47 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
              (char *)v2 + 144,
              1,
              L"DestroyCloudExperienceHostAppBackgroundEvent");
      if ( v47 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x17D9,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v47,
          bIgnoreCasea);
      goto LABEL_154;
    }
    v100[0] = 4;
    v95 = 1;
    NthSnapshotCaptureTelemetry::ShouldShowNthSnapshotCaptureConsentForUser<bool,enum SnapshotCaptureNthLogonSkipReason>(
      &v95,
      v100);
  }
  else
  {
    v43 = v103;
  }
LABEL_157:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_M365CopilotPinning>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_M365CopilotPinning>::GetImpl'::`2'::impl)
    || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl'::`2'::impl)
    || (*(_DWORD *)v43 & 0x400000) != 0
    || !(unsigned __int8)CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForM365CopilotPinning(*(_DWORD *)v43) )
  {
    goto LABEL_168;
  }
  if ( !v114 )
  {
    std::wstring::_Assign<unsigned short>(&v113, L"ms-cxh://NTH/M365PINNING");
LABEL_167:
    *((_BYTE *)v2 + 245) = 1;
    goto LABEL_168;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v98,
    L"ms-cxh://NTH/M365PINNING",
    -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)v2 + 392,
    &v98);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v98);
  if ( *((_QWORD *)v2 + 49) )
  {
    v48 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
            (char *)v2 + 144,
            1,
            L"DestroyCloudExperienceHostAppBackgroundEvent");
    if ( v48 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x17FC,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v48,
        bIgnoreCasea);
    goto LABEL_167;
  }
  v32 = 6137;
LABEL_93:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v32,
    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
    (const char *)0x8007000ELL,
    bIgnoreCasea);
LABEL_214:
  wil::details::unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CXH_SCENARIO_INFO *,void (*)(_CXH_SCENARIO_INFO *),&void DsrFreeCxhScenarioInfo(_CXH_SCENARIO_INFO *),wistd::integral_constant<unsigned __int64,0>,_CXH_SCENARIO_INFO *,_CXH_SCENARIO_INFO *,0,std::nullptr_t>>(&v101);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v104);
  std::wstring::~wstring(&v113);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v106);
  v73 = *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                                 (char *)v2 + 608,
                                 &v97)
                  + 272LL);
  tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v97);
  if ( v73 != 3 )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(
                            (char *)v2 + 608,
                            &v97)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(&v97);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1400a08d0  mov     r11, rsp
0x1400a08d3  mov     [r11+10h], rbx
0x1400a08d7  mov     [r11+18h], rsi
0x1400a08db  push    rdi
0x1400a08dc  push    r12
0x1400a08de  push    r13
0x1400a08e0  push    r14
0x1400a08e2  push    r15
0x1400a08e4  sub     rsp, 330h
0x1400a08eb  mov     rax, cs:__security_cookie
0x1400a08f2  xor     rax, rsp
0x1400a08f5  mov     [rsp+358h+var_38], rax
0x1400a08fd  mov     rsi, rcx
0x1400a0900  mov     [r11-2C0h], rcx
0x1400a0907  xor     edi, edi
0x1400a0909  mov     [r11-2A0h], rcx
0x1400a0910  lea     r14d, [rdi+1]
0x1400a0914  mov     [r11-298h], r14b
0x1400a091b  lea     rdx, aPerusersetupti; "PerUserSetupTipTestCorrelationId"
0x1400a0922  lea     rcx, [r11-2C8h]
0x1400a0929  call    ?GetUserLogonTracingCorrelationId@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGPEAUHKEY__@@@Z; GetUserLogonTracingCorrelationId(ushort const *,HKEY__ *)
0x1400a092e  nop
0x1400a092f  mov     rdx, [rsp+358h+var_2C8]
0x1400a0937  lea     rbx, [rsi+260h]
0x1400a093e  mov     [rsp+358h+var_2B0], rbx
0x1400a0946  test    rdx, rdx
0x1400a0949  jz      short loc_1400A0953
0x1400a094b  mov     rcx, rbx
0x1400a094e  call    ??$TryFailPreviousUserLogonTestInstance@V?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@@@YAXPEAV?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@PEBG1PEAUHKEY__@@@Z; TryFailPreviousUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>(tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>> *,ushort const *,ushort const *,HKEY__ *)
0x1400a0953  mov     [rsp+358h+var_308], rbx
0x1400a0958  mov     rdx, rbx
0x1400a095b  lea     rcx, [rsp+358h+lpsz]; lplpsz
0x1400a0963  call    ??$StartUserLogonTestInstance@V?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAV?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@@Z; StartUserLogonTestInstance<tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>>(tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>> *)
0x1400a0968  nop
0x1400a0969  mov     r9, [rsp+358h+lpsz]; unsigned __int16 *
0x1400a0971  lea     r8, aPerusersetupti; "PerUserSetupTipTestCorrelationId"
0x1400a0978  lea     rdx, aSoftwareMicros_123; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a097f  mov     r13, 0FFFFFFFF80000001h
0x1400a0986  mov     rcx, r13; HKEY
0x1400a0989  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1400a098e  mov     rcx, [rsp+358h]; this
0x1400a0996  lea     r15, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x1400a099d  test    eax, eax
0x1400a099f  jns     short loc_1400A09B1
0x1400a09a1  mov     r9d, eax; char *
0x1400a09a4  mov     r8, r15; unsigned int
0x1400a09a7  mov     edx, 1646h; void *
0x1400a09ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a09b1  mov     [rsp+358h+var_2F8], edi
0x1400a09b5  lea     rax, [rsp+358h+var_2F8]
0x1400a09ba  mov     qword ptr [rsp+358h+bIgnoreCase], rax; int
0x1400a09bf  lea     r8, aDisableperuser; "DisablePerUserSetupTask"
0x1400a09c6  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400a09cd  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1400a09d4  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1400a09d9  test    eax, eax
0x1400a09db  js      loc_1400A0A94
0x1400a09e1  cmp     [rsp+358h+var_2F8], edi
0x1400a09e5  jz      loc_1400A0A94
0x1400a09eb  lea     rcx, [rsi+260h]
0x1400a09f2  lea     rdx, [rsp+358h+var_2C0]
0x1400a09fa  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x1400a09ff  mov     rcx, [rax]
0x1400a0a02  mov     dword ptr [rcx+110h], 3
0x1400a0a0c  lea     rcx, [rsp+358h+var_2C0]
0x1400a0a14  call    ??1?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(void)
0x1400a0a19  nop
0x1400a0a1a  lea     rcx, [rsp+358h+lpsz]
0x1400a0a22  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400a0a27  nop
0x1400a0a28  lea     rcx, [rsp+358h+var_2C8]
0x1400a0a30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400a0a35  nop
0x1400a0a36  lea     rdx, [rsp+358h+var_2C0]
0x1400a0a3e  lea     rcx, [rsi+260h]
0x1400a0a45  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x1400a0a4a  mov     rdx, [rax]
0x1400a0a4d  mov     ebx, [rdx+110h]
0x1400a0a53  lea     rcx, [rsp+358h+var_2C0]
0x1400a0a5b  call    ??1?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(void)
0x1400a0a60  cmp     ebx, 3
0x1400a0a63  jz      loc_1400A20AB
0x1400a0a69  lea     rdx, [rsp+358h+var_2C0]
0x1400a0a71  lea     rcx, [rsi+260h]
0x1400a0a78  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x1400a0a7d  mov     rcx, [rax]
0x1400a0a80  mov     [rcx+114h], r14b
0x1400a0a87  lea     rcx, [rsp+358h+var_2C0]
0x1400a0a8f  jmp     loc_1400A1CC7
0x1400a0a94  lea     rax, [rsi+260h]
0x1400a0a9b  mov     [rsp+358h+var_2A8], rax
0x1400a0aa3  lea     rdx, [rsp+358h+string]
0x1400a0aa8  mov     rcx, rax
0x1400a0aab  call    ??C?$tip_test@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::operator->(void)
0x1400a0ab0  mov     rcx, [rax]
0x1400a0ab3  mov     [rcx+110h], r14d
0x1400a0aba  lea     rcx, [rsp+358h+string]
0x1400a0abf  call    ??1?$test_data_control@V?$merged_data@U_tip_PerUserSetupTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>::~test_data_control<tip2::details::merged_data<_tip_PerUserSetupTest,_tip_PerUserSetupTest>>(void)
0x1400a0ac4  xorps   xmm0, xmm0
0x1400a0ac7  movups  [rsp+358h+var_290], xmm0
0x1400a0acf  mov     [rsp+358h+var_280], rdi
0x1400a0ad7  mov     [rsp+358h+var_278], 7
0x1400a0ae3  mov     word ptr [rsp+358h+var_290], di
0x1400a0aeb  mov     [rsp+358h+var_2D8], rdi
0x1400a0af3  mov     [rsp+358h+var_2F0], rdi
0x1400a0af8  mov     al, dil
0x1400a0afb  mov     [rsp+358h+var_300], al
0x1400a0aff  lea     r12, [rsi+0D8h]
0x1400a0b06  mov     [rsp+358h+var_2E0], r12
0x1400a0b0b  mov     eax, [r12]
0x1400a0b0f  and     eax, 1206h
0x1400a0b14  cmp     eax, 2
0x1400a0b17  jnz     short loc_1400A0B3A
0x1400a0b19  call    ?UpdateUserPrivacyConsentVersion@@YAJW4PrivacyConsentPresentationVersion@@W4PrivacyConsentSettingsVersion@@@Z; UpdateUserPrivacyConsentVersion(PrivacyConsentPresentationVersion,PrivacyConsentSettingsVersion)
0x1400a0b1e  mov     rcx, [rsp+358h]; this
0x1400a0b26  test    eax, eax
0x1400a0b28  jns     short loc_1400A0B3A
0x1400a0b2a  mov     r9d, eax; char *
0x1400a0b2d  mov     r8, r15; unsigned int
0x1400a0b30  mov     edx, 166Bh; void *
0x1400a0b35  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a0b3a  mov     ecx, [r12]
0x1400a0b3e  call    ?s_shouldLaunchCloudExperienceHostForPrivacySettings@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@@Z; CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForPrivacySettings(LogonTypeFlags)
0x1400a0b43  mov     [rsp+358h+var_316], al
0x1400a0b47  call    ?IsOobeInEnduserSession@@YA_NXZ; IsOobeInEnduserSession(void)
0x1400a0b4c  test    al, al
0x1400a0b4e  jz      loc_1400A0CFA
0x1400a0b54  call    LUAIsAdminAndIsOSSilentElevationOn
0x1400a0b59  test    eax, eax
0x1400a0b5b  jz      loc_1400A0CFA
0x1400a0b61  mov     [rsp+358h+var_2F8], edi
0x1400a0b65  lea     r9, [rsp+358h+var_2F8]; unsigned int *
0x1400a0b6a  lea     r8, aEnduseroobesta; "EndUserOOBEStartCount"
0x1400a0b71  lea     rbx, aSoftwareMicros_108; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a0b78  mov     rdx, rbx; unsigned __int16 *
0x1400a0b7b  mov     rcx, r13; HKEY
0x1400a0b7e  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400a0b83  test    eax, eax
0x1400a0b85  js      loc_1400A0CD7
0x1400a0b8b  cmp     [rsp+358h+var_2F8], 5
0x1400a0b90  jb      loc_1400A0CD7
0x1400a0b96  mov     [rsp+358h+string], rdi
0x1400a0b9b  lea     r8, [rsp+358h+string]; void **
0x1400a0ba0  lea     rdx, _GUID_93b534b1_db4b_40c7_b912_91401a2ec4f0; struct _GUID *
0x1400a0ba7  lea     rcx, _GUID_1ee026d0_f551_4c71_aea2_f9897b159eaf; struct _GUID *
0x1400a0bae  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x1400a0bb3  mov     rcx, [rsp+358h]; this
0x1400a0bbb  test    eax, eax
0x1400a0bbd  jns     short loc_1400A0BD4
0x1400a0bbf  mov     r9d, eax; char *
0x1400a0bc2  mov     r8, r15; unsigned int
0x1400a0bc5  mov     edx, 1677h; void *
0x1400a0bca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a0bcf  jmp     loc_1400A0CCB
0x1400a0bd4  call    ??$CoreEvent1@AEAY0CD@$$CBDAEAY0BI@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0CD@$$CBDAEAY0BI@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[35],ushort const (&)[24]>(char const (&)[35],ushort const (&)[24])
0x1400a0bd9  mov     rcx, [rsp+358h+string]
0x1400a0bde  mov     rax, [rcx]
0x1400a0be1  mov     rax, [rax+48h]
0x1400a0be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a0bea  mov     rcx, [rsp+358h]; this
0x1400a0bf2  test    eax, eax
0x1400a0bf4  jns     short loc_1400A0C06
0x1400a0bf6  mov     r9d, eax; char *
0x1400a0bf9  mov     r8, r15; unsigned int
0x1400a0bfc  mov     edx, 167Ah; void *
0x1400a0c01  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a0c06  lea     r8, aWillrunoobeend; "WillRunOobeEnduserSession"
0x1400a0c0d  mov     rdx, rbx; pszSubKey
0x1400a0c10  mov     rcx, r13; hkey
0x1400a0c13  call    cs:__imp_SHDeleteValueW
0x1400a0c1a  nop     dword ptr [rax+rax+00h]
0x1400a0c1f  mov     rcx, [rsp+358h]; this
0x1400a0c27  test    eax, eax
0x1400a0c29  jz      short loc_1400A0C3B
0x1400a0c2b  mov     r9d, eax; char *
0x1400a0c2e  mov     r8, r15; unsigned int
0x1400a0c31  mov     edx, 167Bh; void *
0x1400a0c36  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400a0c3b  lea     r8, aEnduseroobesta; "EndUserOOBEStartCount"
0x1400a0c42  mov     rdx, rbx; pszSubKey
0x1400a0c45  mov     rcx, r13; hkey
0x1400a0c48  call    cs:__imp_SHDeleteValueW
0x1400a0c4f  nop     dword ptr [rax+rax+00h]
0x1400a0c54  mov     rcx, [rsp+358h]; this
0x1400a0c5c  test    eax, eax
0x1400a0c5e  jz      short loc_1400A0C70
0x1400a0c60  mov     r9d, eax; char *
0x1400a0c63  mov     r8, r15; unsigned int
0x1400a0c66  mov     edx, 167Ch; void *
0x1400a0c6b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400a0c70  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a0c77  mov     rcx, r13; hkey
0x1400a0c7a  call    cs:__imp_SHDeleteKeyW
0x1400a0c81  nop     dword ptr [rax+rax+00h]
0x1400a0c86  test    eax, eax
0x1400a0c88  jle     short loc_1400A0C92
0x1400a0c8a  movzx   eax, ax
0x1400a0c8d  or      eax, 80070000h
0x1400a0c92  mov     rcx, [rsp+358h]; this
0x1400a0c9a  mov     [rsp+358h+var_320], 80070490h
0x1400a0ca2  mov     [rsp+358h+var_328], 80070003h
0x1400a0caa  mov     dword ptr [rsp+358h+var_330], 80070002h; char
0x1400a0cb2  mov     [rsp+358h+bIgnoreCase], 3; int
0x1400a0cba  mov     r9d, eax; char *
0x1400a0cbd  mov     r8, r15; unsigned int
0x1400a0cc0  mov     edx, 167Fh; void *
0x1400a0cc5  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1400a0cca  nop
0x1400a0ccb  lea     rcx, [rsp+358h+string]
0x1400a0cd0  call    ??1?$com_ptr_t@UIDataObject@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDataObject,wil::err_exception_policy>::~com_ptr_t<IDataObject,wil::err_exception_policy>(void)
0x1400a0cd5  jmp     short loc_1400A0D01
0x1400a0cd7  mov     [rsi+0ECh], r14b
0x1400a0cde  mov     r9d, [rsp+358h+var_2F8]
0x1400a0ce3  inc     r9d; unsigned int
0x1400a0ce6  lea     r8, aEnduseroobesta; "EndUserOOBEStartCount"
0x1400a0ced  mov     rdx, rbx; unsigned __int16 *
0x1400a0cf0  mov     rcx, r13; HKEY
0x1400a0cf3  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400a0cf8  jmp     short loc_1400A0D01
0x1400a0cfa  lea     rbx, aSoftwareMicros_108; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a0d01  lea     r13, [rsi+0ECh]
0x1400a0d08  mov     [rsp+358h+var_310], r13
0x1400a0d0d  cmp     [r13+0], dil
0x1400a0d11  jz      short loc_1400A0D67
0x1400a0d13  mov     r9d, r14d; int
0x1400a0d16  lea     r8, aWillrunoobeend; "WillRunOobeEnduserSession"
0x1400a0d1d  mov     rdx, rbx; unsigned __int16 *
0x1400a0d20  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1400a0d27  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x1400a0d2c  mov     rcx, [rsp+358h]; this
0x1400a0d34  test    eax, eax
0x1400a0d36  jns     short loc_1400A0D48
0x1400a0d38  mov     r9d, eax; char *
0x1400a0d3b  mov     r8, r15; unsigned int
0x1400a0d3e  mov     edx, 168Ch; void *
0x1400a0d43  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400a0d48  mov     r8d, 0Dh
0x1400a0d4e  lea     rdx, aMsCxhOobe_0; "ms-cxh://OOBE"
0x1400a0d55  lea     rcx, [rsp+358h+var_290]
0x1400a0d5d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400a0d62  jmp     loc_1400A114D
0x1400a0d67  mov     dl, [rsi+0EDh]
0x1400a0d6d  mov     ecx, [r12]
0x1400a0d71  call    ?s_shouldLaunchCloudExperienceHostForNthMSA@CLogonTaskFramework@@CA_NW4LogonTypeFlags@@_N@Z; CLogonTaskFramework::s_shouldLaunchCloudExperienceHostForNthMSA(LogonTypeFlags,bool)
0x1400a0d76  test    al, al
0x1400a0d78  jz      short loc_1400A0D9F
0x1400a0d7a  test    byte ptr [r12], 2
0x1400a0d7f  jz      short loc_1400A0D90
0x1400a0d81  lea     rdx, aMsCxhNth; "ms-cxh://NTH"
0x1400a0d88  mov     r8d, 0Ch
0x1400a0d8e  jmp     short loc_1400A0D55
0x1400a0d90  lea     rdx, aMsCxhNthngcups; "ms-cxh://NTHNGCUPSELL"
0x1400a0d97  mov     r8d, 15h
0x1400a0d9d  jmp     short loc_1400A0D55
0x1400a0d9f  xor     edx, edx; Val
0x1400a0da1  mov     r8d, 208h; Size
0x1400a0da7  lea     rcx, [rsp+358h+String1]; void *
0x1400a0daf  call    memset_0
0x1400a0db4  mov     [rsp+358h+var_2F8], edi
0x1400a0db8  mov     dword ptr [rsp+358h+var_330], 104h; unsigned int
0x1400a0dc0  lea     rax, [rsp+358h+String1]
0x1400a0dc8  mov     qword ptr [rsp+358h+bIgnoreCase], rax; int
0x1400a0dcd  mov     r9d, 2; int
0x1400a0dd3  lea     r8, aLastloggedonpr; "LastLoggedOnProvider"
0x1400a0dda  lea     rdx, aSoftwareMicros_126; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400a0de1  mov     rbx, 0FFFFFFFF80000002h
0x1400a0de8  mov     rcx, rbx; HKEY
0x1400a0deb  call    ?SHRegGetStringEx@@YAJPEAUHKEY__@@PEBG1HPEAGK@Z; SHRegGetStringEx(HKEY__ *,ushort const *,ushort const *,int,ushort *,ulong)
0x1400a0df0  or      r12, 0FFFFFFFFFFFFFFFFh
0x1400a0df4  test    eax, eax
0x1400a0df6  js      loc_1400A0F3A
0x1400a0dfc  mov     [rsp+358h+bIgnoreCase], r14d; bIgnoreCase
0x1400a0e01  mov     r9d, r12d; cchCount2
0x1400a0e04  lea     r8, aF8a1793b787340; "{F8A1793B-7873-4046-B2A7-1F318747F427}"
0x1400a0e0b  mov     edx, r12d; cchCount1
0x1400a0e0e  lea     rcx, [rsp+358h+String1]; lpString1
0x1400a0e16  call    cs:__imp_CompareStringOrdinal
0x1400a0e1d  nop     dword ptr [rax+rax+00h]
0x1400a0e22  cmp     eax, 2
0x1400a0e25  jnz     loc_1400A0F3A
0x1400a0e2b  lea     r9, [rsp+358h+var_2F8]; unsigned int *
0x1400a0e30  lea     r8, aEnablewindowsh; "EnableWindowsHelloLogonProvisioningForS"...
0x1400a0e37  lea     rdx, aSoftwarePolici_5; "Software\\Policies\\Microsoft\\FIDO"
0x1400a0e3e  mov     rcx, rbx; HKEY
0x1400a0e41  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400a0e46  test    eax, eax
0x1400a0e48  js      short loc_1400A0E56
0x1400a0e4a  cmp     [rsp+358h+var_2F8], edi
0x1400a0e4e  setz    bl
0x1400a0e51  jmp     loc_1400A0F3D
0x1400a0e56  mov     bl, r14b
0x1400a0e59  mov     [rsp+358h+string], rdi
0x1400a0e5e  lea     rdx, [rsp+358h+string]
0x1400a0e63  xor     ecx, ecx
0x1400a0e65  call    cs:__imp_DsrGetJoinInfo
0x1400a0e6c  nop     dword ptr [rax+rax+00h]
0x1400a0e71  test    eax, eax
0x1400a0e73  js      loc_1400A0F2E
0x1400a0e79  mov     rax, [rsp+358h+string]
0x1400a0e7e  test    rax, rax
  ... truncated ...
```
