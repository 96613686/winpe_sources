# Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::RefreshCloudFeatureConfigurations(void)

- ea: `0x1800461bc`
- end: `0x18004647d`
- name: `?RefreshCloudFeatureConfigurations@FeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@AEAAXXZ`
- size: `705`
- prototype: `void __fastcall(Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180037b80`

## callees

- `0x180003220`
- `0x180004100`
- `0x180005bf4`
- `0x180005ec8`
- `0x180005fcc`
- `0x18000627c`
- `0x1800107b0`
- `0x180010810`
- `0x1800109ac`
- `0x180016698`
- `0x1800166d8`
- `0x18001a234`
- `0x18001a2e0`
- `0x18001bae4`
- `0x18001e820`
- `0x18002a9a0`
- `0x18002dfe8`
- `0x180032d64`
- `0x1800450e8`
- `0x180045e20`
- `0x1800461bc`
- `0x1800aef90`
- `0x1800b7010`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x180046299`
- `ntdll!NtQueryWnfStateData` at `0x180046299`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046234`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046246`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046234`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180046246`

## string_xrefs

- `0x1800462ad`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x1800463ad`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x180046418`: `onecore\base\flighting\featuremanagement\libs\featureexperiments\featureconfigurationsmanager.cpp`
- `0x180046228`: `LastUpdated`

## pseudocode

```c
void __fastcall Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::RefreshCloudFeatureConfigurations(
        Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager *this,
        __int64 a2,
        __int64 a3)
{
  unsigned int v4; // r8d
  int v5; // eax
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, __int64, __int64, __int64 *); // rdi
  __int64 v8; // rbx
  int v9; // eax
  unsigned int v10; // r8d
  int v11; // r9d
  wil::details *v12; // rbx
  struct wil::details::wnf_subscription_state_base *v13; // rdx
  int v14; // eax
  _DWORD v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v17; // [rsp+40h] [rbp-C0h] BYREF
  wil *v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h]
  HSTRING_HEADER v24; // [rsp+88h] [rbp-78h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h]
  _BYTE v26[8]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v27[14]; // [rsp+B0h] [rbp-50h] BYREF
  int v28[1024]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1158h] [rbp+1058h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0,
    a3);
  if ( (int)RegWow64Helpers::OpenKey(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Wosc\\Client\\Persistent\\ClientState\\FCON",
              v4,
              0xF003Fu,
              &hKey) >= 0 )
  {
    RegDeleteValueW(hKey, L"LastUpdated");
    RegDeleteValueW(hKey, L"LastRefreshByApp");
  }
  v15[0] = 0;
  memset_0(v28, 0, sizeof(v28));
  v15[1] = 4096;
  v21 = WNF_WOSC_FEATURE_CONFIGURATION_COMPLETED;
  v5 = NtQueryWnfStateData(&v21, 0, 0, v15);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
      (const char *)(unsigned int)v5,
      (int)v28);
  v18 = 0;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v18,
    1);
  v27[0] = off_1800BA748;
  v27[1] = &v18;
  v27[13] = v27;
  wil::make_wnf_subscription<wil::details::empty_wnf_state>(&v17, &v21, v26, v15[0]);
  wistd::function<long (fc::vector_nothrow<fc::change_sequence> &,unsigned __int64 *)>::~function<long (fc::vector_nothrow<fc::change_sequence> &,unsigned __int64 *)>(v26);
  wil::GetActivationFactory<Windows::Internal::Flighting::OneSettings::IOneSettingsManager>(&v20);
  v19 = 0;
  v6 = v20;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v20 + 56LL);
  v19 = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, (PCWSTR)"", 1u, 0);
  v8 = v23;
  v25 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v24, L"FCON", 5u, 4u);
  v9 = v7(v6, v25, v8, &v19);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26D,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
      (const char *)(unsigned int)v9,
      (int)v28);
  if ( !wil::handle_wait(v18, (void *)0x1388, v10, v11) )
  {
    v12 = v17;
    if ( v17 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
      wil::details::delete_wnf_subscription_state(v12, v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v17);
    }
    v17 = 0;
    v14 = Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::ReconcileFeatureConfigurations((Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager *)((char *)this + 48));
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x274,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featureexperiments\\featureconfigurationsmanager.cpp",
        (const char *)(unsigned int)v14,
        (int)v28);
  }
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v19);
  wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(&v20);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v17);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800461bc  push    rbp
0x1800461be  push    rbx
0x1800461bf  push    rsi
0x1800461c0  push    rdi
0x1800461c1  push    r14
0x1800461c3  lea     rbp, [rsp-1030h]
0x1800461cb  mov     eax, 1130h
0x1800461d0  call    _alloca_probe
0x1800461d5  sub     rsp, rax
0x1800461d8  mov     rax, cs:__security_cookie
0x1800461df  xor     rax, rsp
0x1800461e2  mov     [rbp+1050h+var_30], rax
0x1800461e9  mov     r14, rcx
0x1800461ec  mov     [rsp+1150h+hKey], 0
0x1800461f5  xor     edx, edx
0x1800461f7  lea     rcx, [rsp+1150h+hKey]
0x1800461fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180046201  lea     rax, [rsp+1150h+hKey]
0x180046206  mov     [rsp+1150h+var_1130], rax; PHKEY
0x18004620b  mov     r9d, 0F003Fh; unsigned int
0x180046211  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180046218  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18004621f  call    ?OpenKey@RegWow64Helpers@@SAJQEAUHKEY__@@QEBGKKPEAPEAU2@@Z; RegWow64Helpers::OpenKey(HKEY__ * const,ushort const * const,ulong,ulong,HKEY__ * *)
0x180046224  test    eax, eax
0x180046226  js      short loc_18004624C
0x180046228  lea     rdx, ValueName; "LastUpdated"
0x18004622f  mov     rcx, [rsp+1150h+hKey]; hKey
0x180046234  call    cs:__imp_RegDeleteValueW
0x18004623a  lea     rdx, aLastrefreshbya; "LastRefreshByApp"
0x180046241  mov     rcx, [rsp+1150h+hKey]; hKey
0x180046246  call    cs:__imp_RegDeleteValueW
0x18004624c  mov     [rsp+1150h+var_1120], 0
0x180046254  mov     ebx, 1000h
0x180046259  mov     r8d, ebx; Size
0x18004625c  xor     edx, edx; Val
0x18004625e  lea     rcx, [rbp+1050h+var_1030]; void *
0x180046262  call    memset_0
0x180046267  mov     [rsp+1150h+var_111C], ebx
0x18004626b  mov     rax, cs:WNF_WOSC_FEATURE_CONFIGURATION_COMPLETED
0x180046272  mov     [rsp+1150h+var_10F0], rax
0x180046277  lea     rax, [rsp+1150h+var_111C]
0x18004627c  mov     [rsp+1150h+var_1128], rax
0x180046281  lea     rax, [rbp+1050h+var_1030]
0x180046285  mov     [rsp+1150h+var_1130], rax; int
0x18004628a  lea     r9, [rsp+1150h+var_1120]
0x18004628f  xor     r8d, r8d
0x180046292  xor     edx, edx
0x180046294  lea     rcx, [rsp+1150h+var_10F0]
0x180046299  call    cs:__imp_NtQueryWnfStateData
0x18004629f  mov     rcx, [rbp+1058h]; this
0x1800462a6  test    eax, eax
0x1800462a8  jns     short loc_1800462BF
0x1800462aa  mov     r9d, eax; char *
0x1800462ad  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x1800462b4  mov     edx, 261h; void *
0x1800462b9  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800462bf  mov     [rsp+1150h+var_1108], 0
0x1800462c8  mov     ebx, 1
0x1800462cd  mov     edx, ebx
0x1800462cf  lea     rcx, [rsp+1150h+var_1108]
0x1800462d4  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800462d9  nop
0x1800462da  lea     rax, off_1800BA748
0x1800462e1  mov     [rbp+1050h+var_10A0], rax
0x1800462e5  lea     rax, [rsp+1150h+var_1108]
0x1800462ea  mov     [rbp+1050h+var_1098], rax
0x1800462ee  lea     rax, [rbp+1050h+var_10A0]
0x1800462f2  mov     [rbp+1050h+var_1038], rax
0x1800462f6  mov     r9d, [rsp+1150h+var_1120]
0x1800462fb  lea     r8, [rbp+1050h+var_10A8]
0x1800462ff  lea     rdx, [rsp+1150h+var_10F0]
0x180046304  lea     rcx, [rsp+1150h+var_1110]
0x180046309  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18004630e  nop
0x18004630f  lea     rcx, [rbp+1050h+var_10A8]
0x180046313  call    ??1?$function@$$A6AJAEAV?$vector_nothrow@Uchange_sequence@fc@@@fc@@PEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (fc::vector_nothrow<fc::change_sequence> &,unsigned __int64 *)>::~function<long (fc::vector_nothrow<fc::change_sequence> &,unsigned __int64 *)>(void)
0x180046318  lea     rcx, [rsp+1150h+var_10F8]
0x18004631d  call    ??$GetActivationFactory@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIOneSettingsManager@OneSettings@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::Flighting::OneSettings::IOneSettingsManager>(ushort const *)
0x180046322  nop
0x180046323  mov     [rsp+1150h+var_1100], 0
0x18004632c  mov     rsi, [rsp+1150h+var_10F8]
0x180046331  mov     rax, [rsi]
0x180046334  mov     rdi, [rax+38h]
0x180046338  mov     [rsp+1150h+var_1100], 0
0x180046341  mov     [rbp+1050h+var_10D0], 0
0x180046349  xor     r9d, r9d; unsigned int
0x18004634c  mov     r8d, ebx; unsigned int
0x18004634f  lea     rdx, ?cDigitsLut@?1??GetDigitsLut@internal@rapidjson@@YAPEBDXZ@4QBDB+0C8h; sourceString
0x180046356  lea     rcx, [rsp+1150h+hstringHeader]; hstringHeader
0x18004635b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046360  nop
0x180046361  mov     rbx, [rbp+1050h+var_10D0]
0x180046365  mov     [rbp+1050h+var_10B0], 0
0x18004636d  mov     r9d, 4; unsigned int
0x180046373  lea     r8d, [r9+1]; unsigned int
0x180046377  lea     rdx, aFcon; "FCON"
0x18004637e  lea     rcx, [rbp+1050h+var_10C8]; hstringHeader
0x180046382  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180046387  nop
0x180046388  lea     r9, [rsp+1150h+var_1100]
0x18004638d  mov     r8, rbx
0x180046390  mov     rdx, [rbp+1050h+var_10B0]
0x180046394  mov     rcx, rsi
0x180046397  mov     rax, rdi
0x18004639a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004639f  mov     rcx, [rbp+1058h]; this
0x1800463a6  test    eax, eax
0x1800463a8  jns     short loc_1800463BF
0x1800463aa  mov     r9d, eax; char *
0x1800463ad  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x1800463b4  mov     edx, 26Dh; void *
0x1800463b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800463bf  mov     edx, 1388h; void *
0x1800463c4  mov     rcx, [rsp+1150h+var_1108]; this
0x1800463c9  call    ?handle_wait@wil@@YA_NPEAXKH@Z; wil::handle_wait(void *,ulong,int)
0x1800463ce  test    al, al
0x1800463d0  jnz     short loc_18004642A
0x1800463d2  mov     rbx, [rsp+1150h+var_1110]
0x1800463d7  test    rbx, rbx
0x1800463da  jz      short loc_1800463F8
0x1800463dc  lea     rcx, [rsp+1150h+var_1110]; this
0x1800463e1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800463e6  mov     rcx, rbx; this
0x1800463e9  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x1800463ee  lea     rcx, [rsp+1150h+var_1110]; this
0x1800463f3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800463f8  mov     [rsp+1150h+var_1110], 0
0x180046401  lea     rcx, [r14+30h]; this
0x180046405  call    ?ReconcileFeatureConfigurations@FeatureConfigurationsManager@FeatureConfiguration@Flighting@Internal@Windows@@UEAAJXZ; Windows::Internal::Flighting::FeatureConfiguration::FeatureConfigurationsManager::ReconcileFeatureConfigurations(void)
0x18004640a  mov     rcx, [rbp+1058h]; this
0x180046411  test    eax, eax
0x180046413  jns     short loc_18004642A
0x180046415  mov     r9d, eax; char *
0x180046418  lea     r8, aOnecoreBaseFli_67; "onecore\\base\\flighting\\featuremanage"...
0x18004641f  mov     edx, 274h; void *
0x180046424  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004642a  lea     rcx, [rsp+1150h+var_1100]
0x18004642f  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x180046434  nop
0x180046435  lea     rcx, [rsp+1150h+var_10F8]
0x18004643a  call    ??1?$com_ptr_t@UIFeatureConfigurationsLogger@FeatureConfiguration@Flighting@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Flighting::FeatureConfiguration::IFeatureConfigurationsLogger,wil::err_exception_policy>(void)
0x18004643f  nop
0x180046440  lea     rcx, [rsp+1150h+var_1110]
0x180046445  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18004644a  nop
0x18004644b  lea     rcx, [rsp+1150h+var_1108]
0x180046450  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180046455  nop
0x180046456  lea     rcx, [rsp+1150h+hKey]
0x18004645b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180046460  mov     rcx, [rbp+1050h+var_30]
0x180046467  xor     rcx, rsp; StackCookie
0x18004646a  call    __security_check_cookie
0x18004646f  add     rsp, 1130h
0x180046476  pop     r14
0x180046478  pop     rdi
0x180046479  pop     rsi
0x18004647a  pop     rbx
0x18004647b  pop     rbp
0x18004647c  retn
```
