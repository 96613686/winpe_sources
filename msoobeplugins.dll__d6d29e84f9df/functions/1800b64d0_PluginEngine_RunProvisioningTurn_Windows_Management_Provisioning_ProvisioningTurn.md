# PluginEngine::RunProvisioningTurn(Windows::Management::Provisioning::ProvisioningTurn)

- ea: `0x1800b64d0`
- end: `0x1800b6bac`
- name: `?RunProvisioningTurn@PluginEngine@@UEAAJW4ProvisioningTurn@Provisioning@Management@Windows@@@Z`
- size: `1756`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003470`
- `0x180005eb0`
- `0x180007bbc`
- `0x180008544`
- `0x18003a9c4`
- `0x18003e430`
- `0x18003e4d4`
- `0x18003e56c`
- `0x18004a7d4`
- `0x18005e3cc`
- `0x18007198c`
- `0x1800b3e38`
- `0x1800b3eb0`
- `0x1800b3f24`
- `0x1800b3fc4`
- `0x1800b4014`
- `0x1800b49ac`
- `0x1800b64d0`
- `0x1800b75ec`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800b65b6`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800b65b6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b66de`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b67a6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b684b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b68db`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6966`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b69fb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6a95`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6b22`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6b78`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b66de`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b67a6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b684b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b68db`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6966`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b69fb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6a95`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6b22`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800b6b78`

## string_xrefs

- `0x1800b657f`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b65cd`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b668b`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6748`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b67ed`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b687d`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6908`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b699d`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6a37`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800b6ac4`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PluginEngine::RunProvisioningTurn(unsigned int *a1, unsigned int a2)
{
  __int64 v4; // rax
  __int64 v5; // r8
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z; // rax
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rsi
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  const unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, int *); // rbx
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // eax
  int v24; // eax
  void *v25; // rdx
  unsigned int v26; // r8d
  int v27; // r9d
  wil *v28; // rcx
  int v29; // eax
  int v30; // eax
  int v31[2]; // [rsp+20h] [rbp-D8h] BYREF
  __int64 v32; // [rsp+28h] [rbp-D0h] BYREF
  __int64 v33; // [rsp+30h] [rbp-C8h] BYREF
  int v34; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-B8h] BYREF
  char v36; // [rsp+49h] [rbp-AFh]
  __int64 v37; // [rsp+50h] [rbp-A8h]
  _BYTE v38[32]; // [rsp+58h] [rbp-A0h] BYREF
  _QWORD v39[4]; // [rsp+78h] [rbp-80h] BYREF
  HSTRING string; // [rsp+98h] [rbp-60h] BYREF
  _QWORD v41[4]; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( (unsigned __int8)IsShellExecuteExWPresent() )
  {
    std::wstring::wstring(v38);
    std::wstring::append(v38, L"/Turn ");
    v4 = std::to_wstring(v39, a2);
    std::wstring::append(v38, v4);
    std::wstring::_Tidy_deallocate(v39);
    v5 = 1800000;
    if ( a2 != 3 )
      v5 = 600000;
    v6 = (*(__int64 (__fastcall **)(unsigned int *, _BYTE *, __int64))(*(_QWORD *)a1 + 104LL))(a1, v38, v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v6,
        v31[0]);
      std::wstring::_Tidy_deallocate(v38);
      return v7;
    }
    std::wstring::_Tidy_deallocate(v38);
    return 0;
  }
  v9 = RoInitialize(1);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v9,
      v31[0]);
    return v10;
  }
  v36 = 1;
  LODWORD(v35) = 0;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v39,
    &v35);
  *(_QWORD *)v31 = 0;
  v33 = 0;
  V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = (__int64 *)___Make_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z(&v35, v39);
  v13 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  v37 = *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z;
  *V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23___AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Details_WRL_Microsoft__YA_AV__ComPtr_V__EventCompletedHandler_U__IAsyncOperation_I_Foundation_Windows__U__IAsyncOperationCompletedHandler_I_23____12_AEAV__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___Z = 0;
  v14 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[47])v12);
  v32 = 0;
  v15 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(
          string,
          &v32);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v15,
      v31[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_14:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v39);
    RoUninitialize();
    return v16;
  }
  (*(void (__fastcall **)(unsigned int *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v38, a1[14]);
  v17 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v41, v17);
  v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 88LL))(v32, v41[0]);
  v16 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v18,
      v31[0]);
    std::wstring::_Tidy_deallocate(v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_14;
  }
  v19 = v32;
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v32 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
  v21 = v20(v19, a2, v31);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v21,
      v31[0]);
    std::wstring::_Tidy_deallocate(v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_45;
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v31 + 48LL))(*(_QWORD *)v31, v13);
  v22 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v23,
      v31[0]);
    std::wstring::_Tidy_deallocate(v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_45;
  }
  v24 = Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<unsigned int>>::As<IAsyncInfo>(v31, &v33);
  v22 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)(unsigned int)v24,
      v31[0]);
    std::wstring::_Tidy_deallocate(v38);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    goto LABEL_45;
  }
  if ( v39[0] )
    v28 = *(wil **)v39[0];
  else
    v28 = 0;
  if ( wil::handle_wait(v28, v25, v26, v27) )
  {
    v34 = 0;
    v29 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v31 + 64LL))(*(_QWORD *)v31, &v34);
    v22 = v29;
    if ( v29 >= 0 )
    {
      v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 80LL))(v33);
      v22 = v30;
      if ( v30 >= 0 )
      {
        std::wstring::_Tidy_deallocate(v38);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
        __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v39);
        RoUninitialize();
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v30,
        v31[0]);
      std::wstring::_Tidy_deallocate(v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12D,
        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
        (const char *)(unsigned int)v29,
        v31[0]);
      std::wstring::_Tidy_deallocate(v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
LABEL_45:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
    __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v39);
    RoUninitialize();
    return v22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x129,
    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
    (const char *)0x800705B4LL,
    v31[0]);
  std::wstring::_Tidy_deallocate(v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
  __1__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAA_XZ(v39);
  RoUninitialize();
  return 2147943860LL;
}

```

## disassembly

```asm
0x1800b64d0  mov     [rsp+arg_10], rbx
0x1800b64d5  push    rsi
0x1800b64d6  push    rdi
0x1800b64d7  push    r14
0x1800b64d9  sub     rsp, 0E0h
0x1800b64e0  mov     rax, cs:__security_cookie
0x1800b64e7  xor     rax, rsp
0x1800b64ea  mov     [rsp+0F8h+var_20], rax
0x1800b64f2  mov     r14d, edx
0x1800b64f5  mov     rdi, rcx
0x1800b64f8  call    IsShellExecuteExWPresent
0x1800b64fd  test    al, al
0x1800b64ff  jz      loc_1800B65B1
0x1800b6505  lea     rcx, [rsp+0F8h+var_A0]
0x1800b650a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800b650f  nop
0x1800b6510  lea     rdx, aTurn; "/Turn "
0x1800b6517  lea     rcx, [rsp+0F8h+var_A0]
0x1800b651c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800b6521  mov     edx, r14d
0x1800b6524  lea     rcx, [rsp+0F8h+var_80]
0x1800b6529  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x1800b652e  nop
0x1800b652f  mov     rdx, rax
0x1800b6532  lea     rcx, [rsp+0F8h+var_A0]
0x1800b6537  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800b653c  nop
0x1800b653d  lea     rcx, [rsp+0F8h+var_80]
0x1800b6542  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6547  mov     rax, [rdi]
0x1800b654a  mov     ecx, 927C0h
0x1800b654f  mov     r8d, 1B7740h
0x1800b6555  cmp     r14d, 3
0x1800b6559  cmovnz  r8d, ecx
0x1800b655d  lea     rdx, [rsp+0F8h+var_A0]
0x1800b6562  mov     rcx, rdi
0x1800b6565  mov     rax, [rax+68h]
0x1800b6569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b656e  mov     ebx, eax
0x1800b6570  test    eax, eax
0x1800b6572  jns     short loc_1800B65A2
0x1800b6574  mov     rcx, [rsp+0F8h]; this
0x1800b657c  mov     r9d, eax; char *
0x1800b657f  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6586  mov     edx, 109h; void *
0x1800b658b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6590  nop
0x1800b6591  lea     rcx, [rsp+0F8h+var_A0]
0x1800b6596  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b659b  mov     eax, ebx
0x1800b659d  jmp     loc_1800B6B87
0x1800b65a2  lea     rcx, [rsp+0F8h+var_A0]
0x1800b65a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b65ac  jmp     loc_1800B6B7F
0x1800b65b1  mov     ecx, 1
0x1800b65b6  call    cs:__imp_RoInitialize
0x1800b65bc  mov     ebx, eax
0x1800b65be  test    eax, eax
0x1800b65c0  jns     short loc_1800B65E5
0x1800b65c2  mov     rcx, [rsp+0F8h]; this
0x1800b65ca  mov     r9d, eax; char *
0x1800b65cd  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b65d4  mov     edx, 10Eh; void *
0x1800b65d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b65de  mov     eax, ebx
0x1800b65e0  jmp     loc_1800B6B87
0x1800b65e5  mov     [rsp+0F8h+var_AF], 1
0x1800b65ea  mov     dword ptr [rsp+0F8h+var_B8], 0
0x1800b65f2  lea     rdx, [rsp+0F8h+var_B8]
0x1800b65f7  lea     rcx, [rsp+0F8h+var_80]
0x1800b65fc  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800b6601  nop
0x1800b6602  mov     qword ptr [rsp+0F8h+var_D8], 0; int
0x1800b660b  mov     [rsp+0F8h+var_C8], 0
0x1800b6614  lea     rdx, [rsp+0F8h+var_80]
0x1800b6619  lea     rcx, [rsp+0F8h+var_B8]
0x1800b661e  call    ??$Make@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@@12@AEAV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x1800b6623  mov     rsi, [rax]
0x1800b6626  mov     [rsp+0F8h+var_A8], rsi
0x1800b662b  mov     qword ptr [rax], 0
0x1800b6632  mov     rcx, [rsp+0F8h+var_B8]
0x1800b6637  test    rcx, rcx
0x1800b663a  jz      short loc_1800B6652
0x1800b663c  mov     [rsp+0F8h+var_B8], 0
0x1800b6645  mov     rax, [rcx]
0x1800b6648  mov     rax, [rax+10h]
0x1800b664c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6651  nop
0x1800b6652  lea     rcx, [rsp+0F8h+string]; string
0x1800b665a  call    ??$?0$0CP@@StringReference@Internal@Windows@@QEAA@AEAY0CP@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[47])
0x1800b665f  mov     [rsp+0F8h+var_D0], 0
0x1800b6668  lea     rdx, [rsp+0F8h+var_D0]
0x1800b666d  mov     rcx, [rsp+0F8h+string]
0x1800b6675  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Provisioning@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Provisioning::IPackageManager>>)
0x1800b667a  mov     ebx, eax
0x1800b667c  test    eax, eax
0x1800b667e  jns     short loc_1800B66EB
0x1800b6680  mov     rcx, [rsp+0F8h]; this
0x1800b6688  mov     r9d, eax; char *
0x1800b668b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6692  mov     edx, 11Dh; void *
0x1800b6697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b669c  nop
0x1800b669d  lea     rcx, [rsp+0F8h+var_D0]
0x1800b66a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b66a7  nop
0x1800b66a8  test    rsi, rsi
0x1800b66ab  jz      short loc_1800B66BD
0x1800b66ad  mov     rax, [rsi]
0x1800b66b0  mov     rcx, rsi
0x1800b66b3  mov     rax, [rax+10h]
0x1800b66b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b66bc  nop
0x1800b66bd  lea     rcx, [rsp+0F8h+var_C8]
0x1800b66c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b66c7  nop
0x1800b66c8  lea     rcx, [rsp+0F8h+var_D8]
0x1800b66cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b66d2  nop
0x1800b66d3  lea     rcx, [rsp+0F8h+var_80]
0x1800b66d8  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b66dd  nop
0x1800b66de  call    cs:__imp_RoUninitialize
0x1800b66e4  mov     eax, ebx
0x1800b66e6  jmp     loc_1800B6B87
0x1800b66eb  mov     rax, [rdi]
0x1800b66ee  mov     r8d, [rdi+38h]
0x1800b66f2  lea     rdx, [rsp+0F8h+var_A0]
0x1800b66f7  mov     rcx, rdi
0x1800b66fa  mov     rax, [rax+70h]
0x1800b66fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6703  nop
0x1800b6704  lea     rcx, [rsp+0F8h+var_A0]
0x1800b6709  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b670e  mov     rdx, rax; unsigned __int16 *
0x1800b6711  lea     rcx, [rsp+0F8h+var_40]; this
0x1800b6719  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800b671e  mov     rcx, [rsp+0F8h+var_D0]
0x1800b6723  mov     rax, [rcx]
0x1800b6726  mov     rdx, [rsp+0F8h+var_40]
0x1800b672e  mov     rax, [rax+58h]
0x1800b6732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6737  mov     ebx, eax
0x1800b6739  test    eax, eax
0x1800b673b  jns     short loc_1800B67B3
0x1800b673d  mov     rcx, [rsp+0F8h]; this
0x1800b6745  mov     r9d, eax; char *
0x1800b6748  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b674f  mov     edx, 121h; void *
0x1800b6754  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6759  nop
0x1800b675a  lea     rcx, [rsp+0F8h+var_A0]
0x1800b675f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6764  nop
0x1800b6765  lea     rcx, [rsp+0F8h+var_D0]
0x1800b676a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b676f  nop
0x1800b6770  test    rsi, rsi
0x1800b6773  jz      short loc_1800B6785
0x1800b6775  mov     rax, [rsi]
0x1800b6778  mov     rcx, rsi
0x1800b677b  mov     rax, [rax+10h]
0x1800b677f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6784  nop
0x1800b6785  lea     rcx, [rsp+0F8h+var_C8]
0x1800b678a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b678f  nop
0x1800b6790  lea     rcx, [rsp+0F8h+var_D8]
0x1800b6795  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b679a  nop
0x1800b679b  lea     rcx, [rsp+0F8h+var_80]
0x1800b67a0  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b67a5  nop
0x1800b67a6  call    cs:__imp_RoUninitialize
0x1800b67ac  mov     eax, ebx
0x1800b67ae  jmp     loc_1800B6B87
0x1800b67b3  mov     rdi, [rsp+0F8h+var_D0]
0x1800b67b8  mov     rax, [rdi]
0x1800b67bb  mov     rbx, [rax+40h]
0x1800b67bf  lea     rcx, [rsp+0F8h+var_D8]
0x1800b67c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b67c9  lea     r8, [rsp+0F8h+var_D8]
0x1800b67ce  mov     edx, r14d
0x1800b67d1  mov     rcx, rdi
0x1800b67d4  mov     rax, rbx
0x1800b67d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b67dc  mov     ebx, eax
0x1800b67de  test    eax, eax
0x1800b67e0  jns     short loc_1800B6858
0x1800b67e2  mov     rcx, [rsp+0F8h]; this
0x1800b67ea  mov     r9d, eax; char *
0x1800b67ed  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b67f4  mov     edx, 124h; void *
0x1800b67f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b67fe  nop
0x1800b67ff  lea     rcx, [rsp+0F8h+var_A0]
0x1800b6804  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6809  nop
0x1800b680a  lea     rcx, [rsp+0F8h+var_D0]
0x1800b680f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6814  nop
0x1800b6815  test    rsi, rsi
0x1800b6818  jz      short loc_1800B682A
0x1800b681a  mov     rax, [rsi]
0x1800b681d  mov     rcx, rsi
0x1800b6820  mov     rax, [rax+10h]
0x1800b6824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6829  nop
0x1800b682a  lea     rcx, [rsp+0F8h+var_C8]
0x1800b682f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b6834  nop
0x1800b6835  lea     rcx, [rsp+0F8h+var_D8]
0x1800b683a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b683f  nop
0x1800b6840  lea     rcx, [rsp+0F8h+var_80]
0x1800b6845  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b684a  nop
0x1800b684b  call    cs:__imp_RoUninitialize
0x1800b6851  mov     eax, ebx
0x1800b6853  jmp     loc_1800B6B87
0x1800b6858  mov     rcx, qword ptr [rsp+0F8h+var_D8]
0x1800b685d  mov     rax, [rcx]
0x1800b6860  mov     rdx, rsi
0x1800b6863  mov     rax, [rax+30h]
0x1800b6867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b686c  mov     ebx, eax
0x1800b686e  test    eax, eax
0x1800b6870  jns     short loc_1800B68E8
0x1800b6872  mov     rcx, [rsp+0F8h]; this
0x1800b687a  mov     r9d, eax; char *
0x1800b687d  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b6884  mov     edx, 127h; void *
0x1800b6889  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b688e  nop
0x1800b688f  lea     rcx, [rsp+0F8h+var_A0]
0x1800b6894  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6899  nop
0x1800b689a  lea     rcx, [rsp+0F8h+var_D0]
0x1800b689f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b68a4  nop
0x1800b68a5  test    rsi, rsi
0x1800b68a8  jz      short loc_1800B68BA
0x1800b68aa  mov     rax, [rsi]
0x1800b68ad  mov     rcx, rsi
0x1800b68b0  mov     rax, [rax+10h]
0x1800b68b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b68b9  nop
0x1800b68ba  lea     rcx, [rsp+0F8h+var_C8]
0x1800b68bf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b68c4  nop
0x1800b68c5  lea     rcx, [rsp+0F8h+var_D8]
0x1800b68ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b68cf  nop
0x1800b68d0  lea     rcx, [rsp+0F8h+var_80]
0x1800b68d5  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b68da  nop
0x1800b68db  call    cs:__imp_RoUninitialize
0x1800b68e1  mov     eax, ebx
0x1800b68e3  jmp     loc_1800B6B87
0x1800b68e8  lea     rdx, [rsp+0F8h+var_C8]
0x1800b68ed  lea     rcx, [rsp+0F8h+var_D8]
0x1800b68f2  call    ??$As@UIAsyncInfo@@@?$ComPtr@U?$IAsyncOperation@I@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<uint>>::As<IAsyncInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1800b68f7  mov     ebx, eax
0x1800b68f9  test    eax, eax
0x1800b68fb  jns     short loc_1800B6973
0x1800b68fd  mov     rcx, [rsp+0F8h]; this
0x1800b6905  mov     r9d, eax; char *
0x1800b6908  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800b690f  mov     edx, 128h; void *
0x1800b6914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6919  nop
0x1800b691a  lea     rcx, [rsp+0F8h+var_A0]
0x1800b691f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b6924  nop
0x1800b6925  lea     rcx, [rsp+0F8h+var_D0]
0x1800b692a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b692f  nop
0x1800b6930  test    rsi, rsi
0x1800b6933  jz      short loc_1800B6945
0x1800b6935  mov     rax, [rsi]
0x1800b6938  mov     rcx, rsi
0x1800b693b  mov     rax, [rax+10h]
0x1800b693f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6944  nop
0x1800b6945  lea     rcx, [rsp+0F8h+var_C8]
0x1800b694a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b694f  nop
0x1800b6950  lea     rcx, [rsp+0F8h+var_D8]
0x1800b6955  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b695a  nop
0x1800b695b  lea     rcx, [rsp+0F8h+var_80]
0x1800b6960  call    ??1?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA@XZ
0x1800b6965  nop
0x1800b6966  call    cs:__imp_RoUninitialize
0x1800b696c  mov     eax, ebx
0x1800b696e  jmp     loc_1800B6B87
0x1800b6973  mov     rax, [rsp+0F8h+var_80]
0x1800b6978  test    rax, rax
0x1800b697b  jz      short loc_1800B6982
0x1800b697d  mov     rcx, [rax]
  ... truncated ...
```
