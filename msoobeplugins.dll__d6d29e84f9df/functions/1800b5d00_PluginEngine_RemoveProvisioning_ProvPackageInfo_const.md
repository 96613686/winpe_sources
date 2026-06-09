# PluginEngine::RemoveProvisioning(ProvPackageInfo const &)

- ea: `0x1800b5d00`
- end: `0x1800b64c1`
- name: `?RemoveProvisioning@PluginEngine@@UEAAJAEBVProvPackageInfo@@@Z`
- size: `1985`
- prototype: `__int64 __fastcall(PluginEngine *__hidden this, const struct ProvPackageInfo *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003470`
- `0x180005eb0`
- `0x180007bbc`
- `0x180008544`
- `0x18003e430`
- `0x18003e4d4`
- `0x18003e56c`
- `0x180040898`
- `0x180048340`
- `0x18004a7d4`
- `0x18005e3cc`
- `0x18007198c`
- `0x1800b3e38`
- `0x1800b3eb0`
- `0x1800b3f24`
- `0x1800b3fc4`
- `0x1800b4014`
- `0x1800b49ac`
- `0x1800b5d00`
- `0x1800b7658`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800b5def`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800b5def`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b5f00`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b5fd1`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b60c5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b616f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6214`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b62c4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6375`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b641c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6488`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b5f00`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b5fd1`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b60c5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b616f`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6214`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b62c4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6375`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b641c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6488`

## string_xrefs

- `0x1800b5db8`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b5e06`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b5ead`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b5f70`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6051`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b60fb`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b61a0`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6250`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6301`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b63a8`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b5d3e`: `/delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall PluginEngine::RemoveProvisioning(PluginEngine *this, const struct ProvPackageInfo *a2)
{
  __int64 PackageId; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z; // rax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rsi
  const WCHAR *v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  const unsigned __int16 *v16; // rax
  int v17; // eax
  char v18; // r8
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, int *); // rbx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  void *v24; // rdx
  unsigned int v25; // r8d
  int v26; // r9d
  wil *v27; // rcx
  int v28; // eax
  int v29; // eax
  int v30[2]; // [rsp+20h] [rbp-108h] BYREF
  __int64 v31; // [rsp+28h] [rbp-100h] BYREF
  __int64 v32; // [rsp+30h] [rbp-F8h] BYREF
  int v33; // [rsp+38h] [rbp-F0h] BYREF
  const WCHAR *v34; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v35[2]; // [rsp+48h] [rbp-E0h] BYREF
  char v36; // [rsp+59h] [rbp-CFh]
  __int64 v37; // [rsp+60h] [rbp-C8h]
  _BYTE v38[32]; // [rsp+68h] [rbp-C0h] BYREF
  HSTRING_HEADER v39; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-88h]
  _BYTE v41[32]; // [rsp+A8h] [rbp-80h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-60h] BYREF
  _QWORD v43[4]; // [rsp+E8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  if ( (unsigned __int8)IsShellExecuteExWPresent() )
  {
    std::wstring::wstring(v38, L"/delete");
    std::wstring::append(v38, L" ");
    PackageId = ProvPackageInfo::GetPackageId(a2, &v39);
    std::wstring::append(v38, PackageId);
    std::wstring::_Tidy_deallocate(&v39);
    v5 = (*(__int64 (__fastcall **)(PluginEngine *, _BYTE *, __int64))(*(_QWORD *)this + 104LL))(this, v38, 600000);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v5,
        v30[0]);
      std::wstring::_Tidy_deallocate(v38);
      return v6;
    }
    std::wstring::_Tidy_deallocate(v38);
    return 0;
  }
  v8 = RoInitialize(1);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18B,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v8,
      v30[0]);
    return v9;
  }
  v36 = 1;
  LODWORD(v34) = 0;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v35,
    (int *)&v34);
  v32 = 0;
  V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = ___Make_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(&v34, v35);
  v12 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  v37 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = 0;
  v13 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  *(_QWORD *)v30 = 0;
  Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[47])v11);
  v31 = 0;
  v14 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(
          (__int64)string,
          &v31);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v14,
      v30[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_43;
  }
  (*(void (__fastcall **)(PluginEngine *, _BYTE *, _QWORD))(*(_QWORD *)this + 112LL))(
    this,
    v41,
    *((unsigned int *)this + 14));
  v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v43, v16);
  v17 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 88LL))(v31, v43[0]);
  v15 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v17,
      v30[0]);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_43;
  }
  ProvPackageInfo::GetPackageId(a2, v38);
  v34 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v39, &v34, v18);
  v19 = v31;
  v20 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v31 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
  v21 = v20(v19, v40, v30);
  v15 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v21,
      v30[0]);
    v40 = 0;
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_43;
  }
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v30 + 48LL))(*(_QWORD *)v30, v12);
  v15 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v22,
      v30[0]);
    v40 = 0;
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_43;
  }
  v23 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<unsigned int>>::As<IAsyncInfo>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v30,
          (__int64)&v32);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v23,
      v30[0]);
    v40 = 0;
    std::wstring::_Tidy_deallocate(v38);
    std::wstring::_Tidy_deallocate(v41);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    goto LABEL_43;
  }
  if ( v35[0] )
    v27 = *(wil **)v35[0];
  else
    v27 = 0;
  if ( wil::handle_wait(v27, v24, v25, v26) )
  {
    v33 = 0;
    v28 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v30 + 64LL))(*(_QWORD *)v30, &v33);
    v15 = v28;
    if ( v28 >= 0 )
    {
      v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 80LL))(v32);
      v15 = v29;
      if ( v29 >= 0 )
      {
        v40 = 0;
        std::wstring::_Tidy_deallocate(v38);
        std::wstring::_Tidy_deallocate(v41);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v35);
        RoUninitialize();
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v29,
        v30[0]);
      v40 = 0;
      std::wstring::_Tidy_deallocate(v38);
      std::wstring::_Tidy_deallocate(v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v28,
        v30[0]);
      v40 = 0;
      std::wstring::_Tidy_deallocate(v38);
      std::wstring::_Tidy_deallocate(v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v35);
    RoUninitialize();
    return v15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A7,
    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
    (const char *)0x800705B4LL,
    v30[0]);
  v40 = 0;
  std::wstring::_Tidy_deallocate(v38);
  std::wstring::_Tidy_deallocate(v41);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v35);
  RoUninitialize();
  return 2147943860LL;
}

```

## disassembly

```asm
0x1800b5d00  mov     [rsp+arg_10], rbx
0x1800b5d05  mov     [rsp+arg_18], rsi
0x1800b5d0a  push    rdi
0x1800b5d0b  push    r14
0x1800b5d0d  push    r15
0x1800b5d0f  sub     rsp, 110h
0x1800b5d16  mov     rax, cs:__security_cookie
0x1800b5d1d  xor     rax, rsp
0x1800b5d20  mov     [rsp+128h+var_20], rax
0x1800b5d28  mov     r14, rdx
0x1800b5d2b  mov     rdi, rcx
0x1800b5d2e  call    IsShellExecuteExWPresent
0x1800b5d33  xor     r15d, r15d
0x1800b5d36  test    al, al
0x1800b5d38  jz      loc_1800B5DEA
0x1800b5d3e  lea     rdx, aDelete; "/delete"
0x1800b5d45  lea     rcx, [rsp+128h+var_C0]
0x1800b5d4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b5d4f  nop
0x1800b5d50  lea     rdx, asc_1800FC130; " "
0x1800b5d57  lea     rcx, [rsp+128h+var_C0]
0x1800b5d5c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800b5d61  lea     rdx, [rsp+128h+var_A0]
0x1800b5d69  mov     rcx, r14
0x1800b5d6c  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x1800b5d71  nop
0x1800b5d72  mov     rdx, rax
0x1800b5d75  lea     rcx, [rsp+128h+var_C0]
0x1800b5d7a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800b5d7f  nop
0x1800b5d80  lea     rcx, [rsp+128h+var_A0]
0x1800b5d88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5d8d  mov     rax, [rdi]
0x1800b5d90  mov     r8d, 927C0h
0x1800b5d96  lea     rdx, [rsp+128h+var_C0]
0x1800b5d9b  mov     rcx, rdi
0x1800b5d9e  mov     rax, [rax+68h]
0x1800b5da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5da7  mov     ebx, eax
0x1800b5da9  test    eax, eax
0x1800b5dab  jns     short loc_1800B5DDB
0x1800b5dad  mov     rcx, [rsp+128h]; this
0x1800b5db5  mov     r9d, eax; char *
0x1800b5db8  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b5dbf  mov     edx, 187h; void *
0x1800b5dc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5dc9  nop
0x1800b5dca  lea     rcx, [rsp+128h+var_C0]
0x1800b5dcf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5dd4  mov     eax, ebx
0x1800b5dd6  jmp     loc_1800B6497
0x1800b5ddb  lea     rcx, [rsp+128h+var_C0]
0x1800b5de0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5de5  jmp     loc_1800B648F
0x1800b5dea  mov     ecx, 1
0x1800b5def  call    cs:__imp_RoInitialize
0x1800b5df5  mov     ebx, eax
0x1800b5df7  test    eax, eax
0x1800b5df9  jns     short loc_1800B5E1E
0x1800b5dfb  mov     rcx, [rsp+128h]; this
0x1800b5e03  mov     r9d, eax; char *
0x1800b5e06  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b5e0d  mov     edx, 18Bh; void *
0x1800b5e12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5e17  mov     eax, ebx
0x1800b5e19  jmp     loc_1800B6497
0x1800b5e1e  mov     [rsp+128h+var_CF], 1
0x1800b5e23  mov     dword ptr [rsp+128h+var_E8], r15d
0x1800b5e28  lea     rdx, [rsp+128h+var_E8]
0x1800b5e2d  lea     rcx, [rsp+128h+var_E0]
0x1800b5e32  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800b5e37  nop
0x1800b5e38  mov     [rsp+128h+var_F8], r15
0x1800b5e3d  lea     rdx, [rsp+128h+var_E0]
0x1800b5e42  lea     rcx, [rsp+128h+var_E8]
0x1800b5e47  call    ??$Make@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@@12@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x1800b5e4c  mov     rsi, [rax]
0x1800b5e4f  mov     [rsp+128h+var_C8], rsi
0x1800b5e54  mov     [rax], r15
0x1800b5e57  mov     rcx, [rsp+128h+var_E8]
0x1800b5e5c  test    rcx, rcx
0x1800b5e5f  jz      short loc_1800B5E73
0x1800b5e61  mov     [rsp+128h+var_E8], r15
0x1800b5e66  mov     rax, [rcx]
0x1800b5e69  mov     rax, [rax+10h]
0x1800b5e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5e72  nop
0x1800b5e73  mov     qword ptr [rsp+128h+var_108], r15; int
0x1800b5e78  lea     rcx, [rsp+128h+string]; string
0x1800b5e80  call    ??$?0$0CP@@StringReference@Internal@Windows@@QEAA@AEAY0CP@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[47])
0x1800b5e85  mov     [rsp+128h+var_100], r15
0x1800b5e8a  lea     rdx, [rsp+128h+var_100]
0x1800b5e8f  mov     rcx, [rsp+128h+string]
0x1800b5e97  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>)
0x1800b5e9c  mov     ebx, eax
0x1800b5e9e  test    eax, eax
0x1800b5ea0  jns     short loc_1800B5F0D
0x1800b5ea2  mov     rcx, [rsp+128h]; this
0x1800b5eaa  mov     r9d, eax; char *
0x1800b5ead  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b5eb4  mov     edx, 199h; void *
0x1800b5eb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5ebe  nop
0x1800b5ebf  lea     rcx, [rsp+128h+var_100]
0x1800b5ec4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5ec9  nop
0x1800b5eca  lea     rcx, [rsp+128h+var_108]
0x1800b5ecf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5ed4  nop
0x1800b5ed5  test    rsi, rsi
0x1800b5ed8  jz      short loc_1800B5EEA
0x1800b5eda  mov     rax, [rsi]
0x1800b5edd  mov     rcx, rsi
0x1800b5ee0  mov     rax, [rax+10h]
0x1800b5ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5ee9  nop
0x1800b5eea  lea     rcx, [rsp+128h+var_F8]
0x1800b5eef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5ef4  nop
0x1800b5ef5  lea     rcx, [rsp+128h+var_E0]
0x1800b5efa  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b5eff  nop
0x1800b5f00  call    cs:__imp_RoUninitialize
0x1800b5f06  mov     eax, ebx
0x1800b5f08  jmp     loc_1800B6497
0x1800b5f0d  mov     rax, [rdi]
0x1800b5f10  mov     r8d, [rdi+38h]
0x1800b5f14  lea     rdx, [rsp+128h+var_80]
0x1800b5f1c  mov     rcx, rdi
0x1800b5f1f  mov     rax, [rax+70h]
0x1800b5f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5f28  nop
0x1800b5f29  lea     rcx, [rsp+128h+var_80]
0x1800b5f31  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b5f36  mov     rdx, rax; unsigned __int16 *
0x1800b5f39  lea     rcx, [rsp+128h+var_40]; this
0x1800b5f41  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800b5f46  mov     rcx, [rsp+128h+var_100]
0x1800b5f4b  mov     rax, [rcx]
0x1800b5f4e  mov     rdx, [rsp+128h+var_40]
0x1800b5f56  mov     rax, [rax+58h]
0x1800b5f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5f5f  mov     ebx, eax
0x1800b5f61  test    eax, eax
0x1800b5f63  jns     short loc_1800B5FDE
0x1800b5f65  mov     rcx, [rsp+128h]; this
0x1800b5f6d  mov     r9d, eax; char *
0x1800b5f70  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b5f77  mov     edx, 19Dh; void *
0x1800b5f7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5f81  nop
0x1800b5f82  lea     rcx, [rsp+128h+var_80]
0x1800b5f8a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b5f8f  nop
0x1800b5f90  lea     rcx, [rsp+128h+var_100]
0x1800b5f95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5f9a  nop
0x1800b5f9b  lea     rcx, [rsp+128h+var_108]
0x1800b5fa0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5fa5  nop
0x1800b5fa6  test    rsi, rsi
0x1800b5fa9  jz      short loc_1800B5FBB
0x1800b5fab  mov     rax, [rsi]
0x1800b5fae  mov     rcx, rsi
0x1800b5fb1  mov     rax, [rax+10h]
0x1800b5fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5fba  nop
0x1800b5fbb  lea     rcx, [rsp+128h+var_F8]
0x1800b5fc0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b5fc5  nop
0x1800b5fc6  lea     rcx, [rsp+128h+var_E0]
0x1800b5fcb  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b5fd0  nop
0x1800b5fd1  call    cs:__imp_RoUninitialize
0x1800b5fd7  mov     eax, ebx
0x1800b5fd9  jmp     loc_1800B6497
0x1800b5fde  lea     rdx, [rsp+128h+var_C0]
0x1800b5fe3  mov     rcx, r14
0x1800b5fe6  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x1800b5feb  nop
0x1800b5fec  lea     rcx, [rsp+128h+var_C0]
0x1800b5ff1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b5ff6  mov     [rsp+128h+var_E8], rax
0x1800b5ffb  lea     rdx, [rsp+128h+var_E8]
0x1800b6000  lea     rcx, [rsp+128h+var_A0]
0x1800b6008  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800b600d  nop
0x1800b600e  mov     rdi, [rsp+128h+var_100]
0x1800b6013  mov     rax, [rdi]
0x1800b6016  mov     rbx, [rax+38h]
0x1800b601a  lea     rcx, [rsp+128h+var_108]
0x1800b601f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6024  lea     r8, [rsp+128h+var_108]
0x1800b6029  mov     rdx, [rsp+128h+var_88]
0x1800b6031  mov     rcx, rdi
0x1800b6034  mov     rax, rbx
0x1800b6037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b603c  mov     ebx, eax
0x1800b603e  test    eax, eax
0x1800b6040  jns     loc_1800B60D2
0x1800b6046  mov     rcx, [rsp+128h]; this
0x1800b604e  mov     r9d, eax; char *
0x1800b6051  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6058  mov     edx, 1A2h; void *
0x1800b605d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6062  nop
0x1800b6063  mov     [rsp+128h+var_88], r15
0x1800b606b  lea     rcx, [rsp+128h+var_C0]
0x1800b6070  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6075  nop
0x1800b6076  lea     rcx, [rsp+128h+var_80]
0x1800b607e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6083  nop
0x1800b6084  lea     rcx, [rsp+128h+var_100]
0x1800b6089  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b608e  nop
0x1800b608f  lea     rcx, [rsp+128h+var_108]
0x1800b6094  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6099  nop
0x1800b609a  test    rsi, rsi
0x1800b609d  jz      short loc_1800B60AF
0x1800b609f  mov     rax, [rsi]
0x1800b60a2  mov     rcx, rsi
0x1800b60a5  mov     rax, [rax+10h]
0x1800b60a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b60ae  nop
0x1800b60af  lea     rcx, [rsp+128h+var_F8]
0x1800b60b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b60b9  nop
0x1800b60ba  lea     rcx, [rsp+128h+var_E0]
0x1800b60bf  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b60c4  nop
0x1800b60c5  call    cs:__imp_RoUninitialize
0x1800b60cb  mov     eax, ebx
0x1800b60cd  jmp     loc_1800B6497
0x1800b60d2  mov     rcx, qword ptr [rsp+128h+var_108]
0x1800b60d7  mov     rax, [rcx]
0x1800b60da  mov     rdx, rsi
0x1800b60dd  mov     rax, [rax+30h]
0x1800b60e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b60e6  mov     ebx, eax
0x1800b60e8  test    eax, eax
0x1800b60ea  jns     loc_1800B617C
0x1800b60f0  mov     rcx, [rsp+128h]; this
0x1800b60f8  mov     r9d, eax; char *
0x1800b60fb  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6102  mov     edx, 1A5h; void *
0x1800b6107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b610c  nop
0x1800b610d  mov     [rsp+128h+var_88], r15
0x1800b6115  lea     rcx, [rsp+128h+var_C0]
0x1800b611a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b611f  nop
0x1800b6120  lea     rcx, [rsp+128h+var_80]
0x1800b6128  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b612d  nop
0x1800b612e  lea     rcx, [rsp+128h+var_100]
0x1800b6133  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6138  nop
0x1800b6139  lea     rcx, [rsp+128h+var_108]
0x1800b613e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6143  nop
0x1800b6144  test    rsi, rsi
0x1800b6147  jz      short loc_1800B6159
0x1800b6149  mov     rax, [rsi]
0x1800b614c  mov     rcx, rsi
0x1800b614f  mov     rax, [rax+10h]
0x1800b6153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6158  nop
0x1800b6159  lea     rcx, [rsp+128h+var_F8]
0x1800b615e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6163  nop
0x1800b6164  lea     rcx, [rsp+128h+var_E0]
0x1800b6169  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b616e  nop
0x1800b616f  call    cs:__imp_RoUninitialize
0x1800b6175  mov     eax, ebx
0x1800b6177  jmp     loc_1800B6497
0x1800b617c  lea     rdx, [rsp+128h+var_F8]
0x1800b6181  lea     rcx, [rsp+128h+var_108]
0x1800b6186  call    ??$As@UIAsyncInfo@@@?$ComPtr@U?$IAsyncOperation@I@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<uint>>::As<IAsyncInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800b618b  mov     ebx, eax
0x1800b618d  test    eax, eax
0x1800b618f  jns     loc_1800B6221
0x1800b6195  mov     rcx, [rsp+128h]; this
0x1800b619d  mov     r9d, eax; char *
0x1800b61a0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b61a7  mov     edx, 1A6h; void *
0x1800b61ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b61b1  nop
0x1800b61b2  mov     [rsp+128h+var_88], r15
0x1800b61ba  lea     rcx, [rsp+128h+var_C0]
0x1800b61bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b61c4  nop
0x1800b61c5  lea     rcx, [rsp+128h+var_80]
0x1800b61cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b61d2  nop
0x1800b61d3  lea     rcx, [rsp+128h+var_100]
0x1800b61d8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b61dd  nop
  ... truncated ...
```
