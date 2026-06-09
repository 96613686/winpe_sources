# GetCtacPropertyAlloc

- ea: `0x180026690`
- end: `0x180026f2f`
- name: `GetCtacPropertyAlloc`
- size: `2207`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005898`
- `0x18000949c`
- `0x1800104cc`
- `0x1800107b0`
- `0x1800109ac`
- `0x180023038`
- `0x180023218`
- `0x180023718`
- `0x180023c70`
- `0x180023dd0`
- `0x180023fc8`
- `0x180024064`
- `0x180024098`
- `0x180024610`
- `0x18002463c`
- `0x1800246f4`
- `0x1800247e4`
- `0x18002484c`
- `0x180025634`
- `0x1800262c8`
- `0x180026690`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026723`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026836`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026969`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026a9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026c8f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026723`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026836`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026969`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026a9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026c8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002674a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800267ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026873`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800269a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026ced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002674a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800267ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026873`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800269a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026ced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026dac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800268ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800269e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026d28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026785`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800268ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800269e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026d28`

## string_xrefs

- `0x180026efc`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x180026719`: `FeatureConfigs`
- `0x180026b2b`: `onecore\base\flighting\featuremanagement\dll\ctacprovider.cpp`
- `0x180026df2`: `onecore\base\flighting\featuremanagement\dll\ctacprovider.cpp`
- `0x180026e41`: `onecore\base\flighting\featuremanagement\dll\ctacprovider.cpp`
- `0x180026e61`: `onecore\base\flighting\featuremanagement\dll\ctacprovider.cpp`
- `0x180026e81`: `onecore\base\flighting\featuremanagement\dll\ctacprovider.cpp`
- `0x180026ed1`: `onecore\base\flighting\featuremanagement\dll\ctacprovider.cpp`
- `0x180026f11`: `onecore\base\flighting\featuremanagement\dll\ctacprovider.cpp`
- `0x1800267c6`: `reason::valid_featureConfigs`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall GetCtacPropertyAlloc(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // eax
  PCWSTR v7; // rax
  const char *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  __int64 v11; // rax
  const char *v12; // rax
  __int64 v13; // rdx
  const char *v14; // r9
  __int64 result; // rax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  PCWSTR v19; // rax
  const char *v20; // rdx
  unsigned int v21; // r8d
  const char *v22; // r9
  __int64 v23; // rax
  const char *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING *); // rbx
  int v28; // eax
  PCWSTR v29; // rax
  const char *v30; // rdx
  unsigned int v31; // r8d
  const char *v32; // r9
  __int64 v33; // rax
  const char *v34; // rax
  __int64 v35; // rdx
  bool v36; // zf
  __int64 (__fastcall *v37)(_QWORD, HSTRING *); // rax
  const char *v38; // rdx
  int v39; // ebx
  int v40; // eax
  unsigned int v41; // ebx
  const char *v42; // rdx
  unsigned int v43; // r8d
  const char *v44; // r9
  __int64 v45; // rax
  const char *v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  const char *v49; // rdx
  unsigned int v50; // r8d
  const char *v51; // r9
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, HSTRING *); // rbx
  int v56; // eax
  PCWSTR StringRawBuffer; // rax
  const char *v58; // rdx
  unsigned int v59; // r8d
  const char *v60; // r9
  __int64 v61; // rax
  const char *v62; // rax
  __int64 v63; // rdx
  const char *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rcx
  unsigned __int16 v67; // ax
  const char *v68; // r9
  int v69[2]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD v70[3]; // [rsp+28h] [rbp-70h] BYREF
  void **v71; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v72[48]; // [rsp+48h] [rbp-50h] BYREF
  HSTRING v73; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  HSTRING string; // [rsp+A8h] [rbp+10h] BYREF
  int v76; // [rsp+B0h] [rbp+18h]
  __int64 v77; // [rsp+B8h] [rbp+20h] BYREF

  v76 = 0;
  string = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_FconCtacPropertyAlloc_attributes,tip2::test_data_basic>>::start(
    &string,
    v70);
  v71 = &tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v72,
    (struct wil::details::IFailureCallback *)&v71,
    0,
    1);
  v73 = string;
  if ( string )
    _InterlockedIncrement((volatile signed __int32 *)string + 84);
  wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(&string);
  *a2 = 0;
  try
  {
    wil::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>();
    if ( (unsigned int)_o__wcsicmp(a1, L"FeatureConfigs") )
    {
      if ( (unsigned int)_o__wcsicmp(a1, L"MxVersion") )
      {
        if ( (unsigned int)_o__wcsicmp(a1, L"MxState") )
        {
          if ( (unsigned int)_o__wcsicmp(a1, L"IsMicrosoftAAD") )
          {
            if ( (unsigned int)_o__wcsicmp(a1, L"TriggeredFlightIds") )
            {
              tip2::details::shared_data<0,0,1>::complete_without_lock(v73 + 2);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x74,
                (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
                (const char *)0x80070002LL,
                v69[0]);
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
              tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
              result = 2147942402LL;
            }
            else
            {
              string = 0;
              *(_QWORD *)v69 = 0;
              v53 = (**(__int64 (__fastcall ***)(__int64, GUID *, int *))v77)(
                      v77,
                      &GUID_1f2f8cce_c378_439c_af7b_0617a7e0d3ae,
                      v69);
              if ( v53 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1CBE,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
                  (const char *)(unsigned int)v53,
                  v69[0]);
              v54 = *(_QWORD *)v69;
              v55 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v69 + 48LL);
              WindowsDeleteString(string);
              string = 0;
              v56 = v55(v54, &string);
              if ( v56 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x69,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
                  (const char *)(unsigned int)v56,
                  v69[0]);
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v70,
                StringRawBuffer,
                -1);
              v76 = 5120;
              v61 = v70[0];
              if ( !v70[0] )
                wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v59, v60);
              v70[0] = 0;
              *a2 = v61;
              v62 = tip2::details::reason_string((tip2::details *)"reason::valid_triggeredFlightIds", v58);
              LOBYTE(v63) = 1;
              tip2::details::shared_data<0,0,1>::complete_without_lock(v73 + 2, v63, 4, v62);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v70);
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v69);
              WindowsDeleteString(string);
              string = 0;
              wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
              tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
              result = 0;
            }
          }
          else
          {
            wil::GetActivationFactory<Windows::Internal::Flighting::OneSettings::IOneSettingsCTACProvider>(v69);
            LOBYTE(string) = 0;
            v36 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad>::GetImpl'::`2'::impl) == 0;
            v37 = *(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)v69 + 48LL);
            if ( v36 )
            {
              v40 = v37(*(_QWORD *)v69, &string);
              v41 = v40;
              if ( v40 < 0 )
              {
                if ( v40 == -2147024894 || v40 == -2146958592 || v40 == -2147023584 || v40 == -2147023728 )
                {
                  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v69);
                  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
                  tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
                  return v41;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x54,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
                    (const char *)(unsigned int)v40,
                    v69[0]);
                  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v69);
                  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
                  tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
                  return v41;
                }
              }
            }
            else
            {
              v39 = v37(*(_QWORD *)v69, &string);
              if ( v39 < 0 )
              {
                v64 = tip2::details::reason_string((tip2::details *)"reason::isMsftAadCallFailed", v38);
                v67 = tip2::details::validate_reason<enum reason,7>(v66, v65, v64);
                tip2::test_watcher<tip2::details::merged_data<_tip_FconCtacPropertyAlloc_attributes,tip2::test_data_basic>>::complete_and_succeed(
                  &v71,
                  v67);
                v68 = (const char *)(unsigned int)wil::verify_hresult<long>((unsigned int)v39);
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x4A,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
                  v68,
                  v69[0]);
              }
            }
            if ( (_BYTE)string )
            {
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v70,
                L"1",
                -1);
              v76 = 128;
              v45 = v70[0];
              if ( !v70[0] )
                wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v43, v44);
              v70[0] = 0;
              *a2 = v45;
              v46 = tip2::details::reason_string((tip2::details *)"reason::certain_MicrosoftAAD", v42);
              v48 = 5;
            }
            else
            {
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                v70,
                L"0",
                -1);
              v76 = 512;
              v52 = v70[0];
              if ( !v70[0] )
                wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v50, v51);
              v70[0] = 0;
              *a2 = v52;
              v46 = tip2::details::reason_string((tip2::details *)"reason::certain_not_MicrosoftAAD", v49);
              v48 = 6;
            }
            LOBYTE(v47) = 1;
            tip2::details::shared_data<0,0,1>::complete_without_lock(v73 + 2, v47, v48, v46);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v70);
            wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v69);
            wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
            tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
            result = 0;
          }
        }
        else
        {
          string = 0;
          wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,wil::err_exception_policy>::query<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger>(
            &v77,
            v70);
          v26 = v70[0];
          v27 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v70[0] + 72LL);
          WindowsDeleteString(string);
          string = 0;
          v28 = v27(v26, &string);
          if ( v28 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x35,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
              (const char *)(unsigned int)v28,
              v69[0]);
          v29 = WindowsGetStringRawBuffer(string, 0);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            v69,
            v29,
            -1);
          v76 = 32;
          v33 = *(_QWORD *)v69;
          if ( !*(_QWORD *)v69 )
            wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v31, v32);
          *(_QWORD *)v69 = 0;
          *a2 = v33;
          v34 = tip2::details::reason_string((tip2::details *)"reason::valid_mxState", v30);
          LOBYTE(v35) = 1;
          tip2::details::shared_data<0,0,1>::complete_without_lock(v73 + 2, v35, 3, v34);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v69);
          wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v70);
          WindowsDeleteString(string);
          string = 0;
          wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
          tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
          result = 0;
        }
      }
      else
      {
        string = 0;
        wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,wil::err_exception_policy>::query<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger>(
          &v77,
          v70);
        v16 = v70[0];
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v70[0] + 64LL);
        WindowsDeleteString(string);
        string = 0;
        v18 = v17(v16, &string);
        if ( v18 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
            (const char *)(unsigned int)v18,
            v69[0]);
        v19 = WindowsGetStringRawBuffer(string, 0);
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          v69,
          v19,
          -1);
        v76 = 8;
        v23 = *(_QWORD *)v69;
        if ( !*(_QWORD *)v69 )
          wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v21, v22);
        *(_QWORD *)v69 = 0;
        *a2 = v23;
        v24 = tip2::details::reason_string((tip2::details *)"reason::valid_mxVersion", v20);
        LOBYTE(v25) = 1;
        tip2::details::shared_data<0,0,1>::complete_without_lock(v73 + 2, v25, 2, v24);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v69);
        wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(v70);
        WindowsDeleteString(string);
        string = 0;
        wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
        tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
        result = 0;
      }
    }
    else
    {
      string = 0;
      v4 = v77;
      v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v77 + 64LL);
      WindowsDeleteString(0);
      string = 0;
      v6 = v5(v4, &string);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
          (const char *)(unsigned int)v6,
          v69[0]);
      v7 = WindowsGetStringRawBuffer(string, 0);
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        v69,
        v7,
        -1);
      v76 = 2;
      v11 = *(_QWORD *)v69;
      if ( !*(_QWORD *)v69 )
        wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v9, v10);
      *(_QWORD *)v69 = 0;
      *a2 = v11;
      v12 = tip2::details::reason_string((tip2::details *)"reason::valid_featureConfigs", v8);
      LOBYTE(v13) = 1;
      tip2::details::shared_data<0,0,1>::complete_without_lock(v73 + 2, v13, 1, v12);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v69);
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v77);
      tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(&v71);
      result = 0;
    }
  }
  catch ( ... )
  {
    LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x76,
                        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\dll\\ctacprovider.cpp",
                        v14);
    return (unsigned int)string;
  }
  return result;
}

```

## disassembly

```asm
0x180026690  mov     rax, rsp
0x180026693  mov     [rax+8], rbx
0x180026697  push    rsi
0x180026698  push    rdi
0x180026699  push    r14
0x18002669b  sub     rsp, 80h
0x1800266a2  mov     rsi, rdx
0x1800266a5  mov     rbx, rcx
0x1800266a8  xor     r14d, r14d
0x1800266ab  mov     [rax+18h], r14d
0x1800266af  mov     [rax+10h], r14
0x1800266b3  lea     rdx, [rax-70h]
0x1800266b7  lea     rcx, [rax+10h]
0x1800266bb  call    ?start@?$tip_test@V?$merged_data@U_tip_FconCtacPropertyAlloc_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FconCtacPropertyAlloc_attributes,tip2::test_data_basic>>::start(void)
0x1800266c0  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_FCON_WinCSApplyFlagsByKeys_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_FCON_WinCSApplyFlagsByKeys_attributes,tip2::test_data_basic>>::`vftable'
0x1800266c7  mov     [rsp+98h+var_58], rax
0x1800266cc  mov     r9b, 1; bool
0x1800266cf  xor     r8d, r8d; struct wil::CallContextInfo *
0x1800266d2  lea     rdx, [rsp+98h+var_58]; struct wil::details::IFailureCallback *
0x1800266d7  lea     rcx, [rsp+98h+var_50]; this
0x1800266dc  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x1800266e1  mov     rax, [rsp+98h+string]
0x1800266e9  mov     [rsp+98h+var_20], rax
0x1800266ee  test    rax, rax
0x1800266f1  jz      short loc_1800266FA
0x1800266f3  lock inc dword ptr [rax+150h]
0x1800266fa  lea     rcx, [rsp+98h+string]
0x180026702  call    ??1?$com_ptr_t@V?$merged_data@U_tip_FCON_ProcessGovernedFeatureUsage_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_FCON_ProcessGovernedFeatureUsage_attributes,tip2::test_data_basic>,wil::err_returncode_policy>(void)
0x180026707  nop
0x180026708  mov     [rsi], r14
0x18002670b  lea     rcx, [rsp+98h+arg_18]
0x180026713  call    ??$ActivateInstance@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::ActivateInstance<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager>(ushort const *)
0x180026718  nop
0x180026719  lea     rdx, aFeatureconfigs; "FeatureConfigs"
0x180026720  mov     rcx, rbx
0x180026723  call    cs:__imp__o__wcsicmp
0x180026729  test    eax, eax
0x18002672b  jnz     loc_18002682C
0x180026731  mov     [rsp+98h+string], r14
0x180026739  mov     rdi, [rsp+98h+arg_18]
0x180026741  mov     rax, [rdi]
0x180026744  mov     rbx, [rax+40h]
0x180026748  xor     ecx, ecx; string
0x18002674a  call    cs:__imp_WindowsDeleteString
0x180026750  mov     [rsp+98h+string], r14
0x180026758  lea     rdx, [rsp+98h+string]
0x180026760  mov     rcx, rdi
0x180026763  mov     rax, rbx
0x180026766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002676b  mov     rcx, [rsp+98h]; this
0x180026773  test    eax, eax
0x180026775  js      loc_180026E3E
0x18002677b  xor     edx, edx; length
0x18002677d  mov     rcx, [rsp+98h+string]; string
0x180026785  call    cs:__imp_WindowsGetStringRawBuffer
0x18002678b  nop
0x18002678c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026790  mov     rdx, rax
0x180026793  lea     rcx, [rsp+98h+var_78]
0x180026798  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002679d  mov     [rsp+98h+arg_10], 2
0x1800267a8  mov     rcx, [rsp+98h]; this
0x1800267b0  mov     rax, qword ptr [rsp+98h+var_78]
0x1800267b5  test    rax, rax
0x1800267b8  jz      loc_180026E53
0x1800267be  mov     qword ptr [rsp+98h+var_78], r14
0x1800267c3  mov     [rsi], rax
0x1800267c6  lea     rcx, aReasonValidFea; "reason::valid_featureConfigs"
0x1800267cd  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800267d2  mov     r9, rax
0x1800267d5  mov     r8d, 1
0x1800267db  mov     rcx, [rsp+98h+var_20]
0x1800267e0  add     rcx, 8
0x1800267e4  mov     dl, r8b
0x1800267e7  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800267ec  lea     rcx, [rsp+98h+var_78]
0x1800267f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800267f6  nop
0x1800267f7  mov     rcx, [rsp+98h+string]; string
0x1800267ff  call    cs:__imp_WindowsDeleteString
0x180026805  mov     [rsp+98h+string], r14
0x18002680d  lea     rcx, [rsp+98h+arg_18]
0x180026815  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x18002681a  nop
0x18002681b  lea     rcx, [rsp+98h+var_58]
0x180026820  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180026825  xor     eax, eax
0x180026827  jmp     loc_180026E2A
0x18002682c  lea     rdx, aMxversion; "MxVersion"
0x180026833  mov     rcx, rbx
0x180026836  call    cs:__imp__o__wcsicmp
0x18002683c  test    eax, eax
0x18002683e  jnz     loc_18002695F
0x180026844  mov     [rsp+98h+string], r14
0x18002684c  lea     rdx, [rsp+98h+var_70]
0x180026851  lea     rcx, [rsp+98h+arg_18]
0x180026859  call    ??$query@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@@?$com_ptr_t@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,wil::err_exception_policy>::query<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger>(void)
0x18002685e  nop
0x18002685f  mov     rdi, [rsp+98h+var_70]
0x180026864  mov     rax, [rdi]
0x180026867  mov     rbx, [rax+40h]
0x18002686b  mov     rcx, [rsp+98h+string]; string
0x180026873  call    cs:__imp_WindowsDeleteString
0x180026879  mov     [rsp+98h+string], r14
0x180026881  lea     rdx, [rsp+98h+string]
0x180026889  mov     rcx, rdi
0x18002688c  mov     rax, rbx
0x18002688f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026894  mov     rcx, [rsp+98h]; this
0x18002689c  test    eax, eax
0x18002689e  js      loc_180026E5E
0x1800268a4  xor     edx, edx; length
0x1800268a6  mov     rcx, [rsp+98h+string]; string
0x1800268ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800268b4  nop
0x1800268b5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800268b9  mov     rdx, rax
0x1800268bc  lea     rcx, [rsp+98h+var_78]
0x1800268c1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800268c6  mov     [rsp+98h+arg_10], 8
0x1800268d1  mov     rcx, [rsp+98h]; this
0x1800268d9  mov     rax, qword ptr [rsp+98h+var_78]
0x1800268de  test    rax, rax
0x1800268e1  jz      loc_180026E73
0x1800268e7  mov     qword ptr [rsp+98h+var_78], r14
0x1800268ec  mov     [rsi], rax
0x1800268ef  lea     rcx, aReasonValidMxv; "reason::valid_mxVersion"
0x1800268f6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800268fb  mov     r9, rax
0x1800268fe  mov     r8d, 2
0x180026904  mov     rcx, [rsp+98h+var_20]
0x180026909  add     rcx, 8
0x18002690d  mov     dl, 1
0x18002690f  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x180026914  lea     rcx, [rsp+98h+var_78]
0x180026919  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002691e  nop
0x18002691f  lea     rcx, [rsp+98h+var_70]
0x180026924  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180026929  nop
0x18002692a  mov     rcx, [rsp+98h+string]; string
0x180026932  call    cs:__imp_WindowsDeleteString
0x180026938  mov     [rsp+98h+string], r14
0x180026940  lea     rcx, [rsp+98h+arg_18]
0x180026948  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x18002694d  nop
0x18002694e  lea     rcx, [rsp+98h+var_58]
0x180026953  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180026958  xor     eax, eax
0x18002695a  jmp     loc_180026E2A
0x18002695f  lea     rdx, aMxstate; "MxState"
0x180026966  mov     rcx, rbx
0x180026969  call    cs:__imp__o__wcsicmp
0x18002696f  test    eax, eax
0x180026971  jnz     loc_180026A92
0x180026977  mov     [rsp+98h+string], r14
0x18002697f  lea     rdx, [rsp+98h+var_70]
0x180026984  lea     rcx, [rsp+98h+arg_18]
0x18002698c  call    ??$query@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@@?$com_ptr_t@UIFeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsManager,wil::err_exception_policy>::query<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger>(void)
0x180026991  nop
0x180026992  mov     rdi, [rsp+98h+var_70]
0x180026997  mov     rax, [rdi]
0x18002699a  mov     rbx, [rax+48h]
0x18002699e  mov     rcx, [rsp+98h+string]; string
0x1800269a6  call    cs:__imp_WindowsDeleteString
0x1800269ac  mov     [rsp+98h+string], r14
0x1800269b4  lea     rdx, [rsp+98h+string]
0x1800269bc  mov     rcx, rdi
0x1800269bf  mov     rax, rbx
0x1800269c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269c7  mov     rcx, [rsp+98h]; this
0x1800269cf  test    eax, eax
0x1800269d1  js      loc_180026E7E
0x1800269d7  xor     edx, edx; length
0x1800269d9  mov     rcx, [rsp+98h+string]; string
0x1800269e1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800269e7  nop
0x1800269e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800269ec  mov     rdx, rax
0x1800269ef  lea     rcx, [rsp+98h+var_78]
0x1800269f4  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800269f9  mov     [rsp+98h+arg_10], 20h ; ' '
0x180026a04  mov     rcx, [rsp+98h]; this
0x180026a0c  mov     rax, qword ptr [rsp+98h+var_78]
0x180026a11  test    rax, rax
0x180026a14  jz      loc_180026E93
0x180026a1a  mov     qword ptr [rsp+98h+var_78], r14
0x180026a1f  mov     [rsi], rax
0x180026a22  lea     rcx, aReasonValidMxs; "reason::valid_mxState"
0x180026a29  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180026a2e  mov     r9, rax
0x180026a31  mov     r8d, 3
0x180026a37  mov     rcx, [rsp+98h+var_20]
0x180026a3c  add     rcx, 8
0x180026a40  mov     dl, 1
0x180026a42  call    ?complete_without_lock@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<0,0,1>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x180026a47  lea     rcx, [rsp+98h+var_78]
0x180026a4c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180026a51  nop
0x180026a52  lea     rcx, [rsp+98h+var_70]
0x180026a57  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180026a5c  nop
0x180026a5d  mov     rcx, [rsp+98h+string]; string
0x180026a65  call    cs:__imp_WindowsDeleteString
0x180026a6b  mov     [rsp+98h+string], r14
0x180026a73  lea     rcx, [rsp+98h+arg_18]
0x180026a7b  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180026a80  nop
0x180026a81  lea     rcx, [rsp+98h+var_58]
0x180026a86  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180026a8b  xor     eax, eax
0x180026a8d  jmp     loc_180026E2A
0x180026a92  lea     rdx, aIsmicrosoftaad; "IsMicrosoftAAD"
0x180026a99  mov     rcx, rbx
0x180026a9c  call    cs:__imp__o__wcsicmp
0x180026aa2  test    eax, eax
0x180026aa4  jnz     loc_180026C85
0x180026aaa  lea     rcx, [rsp+98h+var_78]
0x180026aaf  call    ??$GetActivationFactory@UIOneSettingsCTACProvider@OneSettings@Flighting@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIOneSettingsCTACProvider@OneSettings@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Flighting::OneSettings::IOneSettingsCTACProvider>(ushort const *)
0x180026ab4  nop
0x180026ab5  mov     byte ptr [rsp+98h+string], r14b
0x180026abd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad>::GetImpl(void)'::`2'::impl
0x180026ac4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FconVerifyMicrosoftAad>::__private_IsEnabled(void)
0x180026ac9  mov     rcx, qword ptr [rsp+98h+var_78]
0x180026ace  lea     rdx, [rsp+98h+string]
0x180026ad6  test    al, al
0x180026ad8  mov     rax, [rcx]
0x180026adb  mov     rax, [rax+30h]
0x180026adf  jz      short loc_180026AF5
0x180026ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ae6  mov     ebx, eax
0x180026ae8  test    eax, eax
0x180026aea  js      loc_180026E9E
0x180026af0  jmp     loc_180026B91
0x180026af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026afa  mov     ebx, eax
0x180026afc  test    eax, eax
0x180026afe  jns     loc_180026B91
0x180026b04  cmp     eax, 80070002h
0x180026b09  jz      short loc_180026B67
0x180026b0b  cmp     eax, 80080300h
0x180026b10  jz      short loc_180026B67
0x180026b12  cmp     eax, 80070520h
0x180026b17  jz      short loc_180026B67
0x180026b19  cmp     eax, 80070490h
0x180026b1e  jz      short loc_180026B67
0x180026b20  mov     rcx, [rsp+98h]; this
0x180026b28  mov     r9d, eax; char *
0x180026b2b  lea     r8, aOnecoreBaseFli_9; "onecore\\base\\flighting\\featuremanage"...
0x180026b32  mov     edx, 54h ; 'T'; void *
0x180026b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026b3c  nop
0x180026b3d  lea     rcx, [rsp+98h+var_78]
0x180026b42  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180026b47  nop
0x180026b48  lea     rcx, [rsp+98h+arg_18]
0x180026b50  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180026b55  nop
0x180026b56  lea     rcx, [rsp+98h+var_58]
0x180026b5b  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180026b60  mov     eax, ebx
0x180026b62  jmp     loc_180026E2A
0x180026b67  lea     rcx, [rsp+98h+var_78]
0x180026b6c  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180026b71  nop
0x180026b72  lea     rcx, [rsp+98h+arg_18]
0x180026b7a  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180026b7f  nop
0x180026b80  lea     rcx, [rsp+98h+var_58]
0x180026b85  call    ??1?$test_watcher@V?$merged_data@U_tip_FCON_StagingControlsSetFeatureEnabledState_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_FCON_StagingControlsSetFeatureEnabledState_attributes,tip2::test_data_basic>>(void)
0x180026b8a  mov     eax, ebx
0x180026b8c  jmp     loc_180026E2A
0x180026b91  cmp     byte ptr [rsp+98h+string], r14b
0x180026b99  jz      short loc_180026BED
0x180026b9b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026b9f  lea     rdx, a1; "1"
0x180026ba6  lea     rcx, [rsp+98h+var_70]
0x180026bab  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026bb0  mov     [rsp+98h+arg_10], 80h
0x180026bbb  mov     rcx, [rsp+98h]; this
0x180026bc3  mov     rax, [rsp+98h+var_70]
0x180026bc8  test    rax, rax
0x180026bcb  jz      loc_180026EE3
0x180026bd1  mov     [rsp+98h+var_70], r14
0x180026bd6  mov     [rsi], rax
0x180026bd9  lea     rcx, aReasonCertainM; "reason::certain_MicrosoftAAD"
0x180026be0  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180026be5  mov     r8d, 5
0x180026beb  jmp     short loc_180026C3D
0x180026bed  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026bf1  lea     rdx, a0; "0"
0x180026bf8  lea     rcx, [rsp+98h+var_70]
0x180026bfd  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180026c02  mov     [rsp+98h+arg_10], 200h
0x180026c0d  mov     rcx, [rsp+98h]; this
0x180026c15  mov     rax, [rsp+98h+var_70]
0x180026c1a  test    rax, rax
0x180026c1d  jz      loc_180026EEE
0x180026c23  mov     [rsp+98h+var_70], r14
0x180026c28  mov     [rsi], rax
  ... truncated ...
```
