# DeviceTicket::GetMSADeviceTicketImpl(ushort const *,_GUID const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18005b8b8`
- end: `0x18005c6cc`
- name: `?GetMSADeviceTicketImpl@DeviceTicket@@CAJPEBGAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `3604`
- prototype: `__int64 __fastcall(PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005b6c4`

## callees

- `0x1800084f4`
- `0x1800307c4`
- `0x1800318e8`
- `0x1800319ac`
- `0x180044300`
- `0x18004c840`
- `0x18005b534`
- `0x18005b6a4`
- `0x18005b8b8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005c69c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005c69c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005b99c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005b99c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005bab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005bab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c5f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005c5f8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b981`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005ba37`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bbaf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005b981`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005ba37`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bbaf`

## string_xrefs

- `0x18005bde4`: `WaitForCompletionOrTimeoutNoThrow`
- `0x18005bac7`: `WindowsCreateString`
- `0x18005bb2f`: `WindowsCreateString`
- `0x18005b959`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x18005ba0f`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x18005bb87`: `Windows.Security.Authentication.OnlineId.OnlineIdSystemAuthenticator`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall DeviceTicket::GetMSADeviceTicketImpl(PCNZWCH sourceString, __int64 a2, __int64 a3)
{
  char v5; // r12
  char *v6; // rax
  unsigned int ActivationFactory; // ebx
  HRESULT v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rdx
  HRESULT v12; // eax
  __int64 v13; // rax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  DWORD v21; // edx
  int v22; // r8d
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64 *); // r14
  _QWORD *v26; // rcx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned int v39; // [rsp+20h] [rbp-C8h]
  __int64 *v40; // [rsp+28h] [rbp-C0h] BYREF
  char v41; // [rsp+30h] [rbp-B8h] BYREF
  char v42; // [rsp+31h] [rbp-B7h]
  __int64 v43; // [rsp+38h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-A8h] BYREF
  _QWORD *v45; // [rsp+48h] [rbp-A0h] BYREF
  __int64 *v46; // [rsp+50h] [rbp-98h] BYREF
  __int64 *v47; // [rsp+58h] [rbp-90h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-88h] BYREF
  __int64 *v49; // [rsp+68h] [rbp-80h] BYREF
  __int64 *v50; // [rsp+70h] [rbp-78h] BYREF
  int v51; // [rsp+78h] [rbp-70h] BYREF
  HSTRING v52; // [rsp+80h] [rbp-68h] BYREF
  int v53; // [rsp+88h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-58h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-40h]

  v5 = 0;
  v42 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v6 = (char *)a3;
  else
    v6 = *(char **)a3;
  *(_WORD *)v6 = 0;
  if ( !sourceString )
  {
    ActivationFactory = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceTicket::GetMSADeviceTicketImpl", L"pwszScope");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceTicket::GetMSADeviceTicketImpl", L"pwszScope");
    return ActivationFactory;
  }
  v40 = 0;
  v55 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v55, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v40);
  v39 = ActivationFactory;
  if ( ActivationFactory == -2147221008 )
  {
    v8 = CoInitializeEx(0, 0);
    ActivationFactory = v8;
    if ( v8 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DeviceTicket::GetMSADeviceTicketImpl",
        L"CoInitializeEx",
        (unsigned int)v8,
        v8);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
      return ActivationFactory;
    }
    v5 = 1;
    v42 = 1;
    v9 = (__int64)v40;
    v40 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v55 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
      0x46u,
      0x45u);
    ActivationFactory = RoGetActivationFactory(v55, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v40);
    v39 = ActivationFactory;
  }
  if ( ActivationFactory == -2147221164 )
  {
    ActivationFactory = -2145647559;
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  if ( (ActivationFactory & 0x80000000) != 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"GetActivationFactory",
      ActivationFactory,
      v39);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  string = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( sourceString[v11] );
  v12 = WindowsCreateString(sourceString, v11, &string);
  ActivationFactory = v12;
  if ( v12 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"WindowsCreateString",
      (unsigned int)v12,
      v12);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  v43 = 0;
  v13 = *v40;
  v43 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v13 + 56))(v40, string, &v43);
  ActivationFactory = v14;
  if ( v14 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"WindowsCreateString",
      (unsigned int)v14,
      v14);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  v47 = 0;
  v55 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.OnlineId.OnlineIdSystemAuthenticator",
    0x45u,
    0x44u);
  v15 = RoGetActivationFactory(v55, &GUID_85047792_f634_41e3_96a4_5164e902c740, &v47);
  ActivationFactory = v15;
  if ( v15 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"GetActivationFactory",
      (unsigned int)v15,
      v15);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  v46 = 0;
  v16 = *v47;
  v46 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v16 + 48))(v47, &v46);
  ActivationFactory = v17;
  if ( v17 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"get_Default",
      (unsigned int)v17,
      v17);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = xmmword_1800E3B40;
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING_HEADER *))(*v46 + 56))(v46, &hstringHeader);
  ActivationFactory = v18;
  if ( v18 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"put_ApplicationId",
      (unsigned int)v18,
      v18);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  v48 = 0;
  v45 = 0;
  v41 = 0;
  v19 = *v46;
  v48 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v19 + 48))(v46, v43, &v48);
  ActivationFactory = v20;
  if ( v20 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"GetTicketAsync",
      (unsigned int)v20,
      v20);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  v23 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::OnlineId::OnlineIdSystemTicketResult *> *>(
          v48,
          v21,
          v22,
          &v41);
  ActivationFactory = v23;
  if ( v23 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"WaitForCompletionOrTimeoutNoThrow",
      (unsigned int)v23,
      v23);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  if ( v41 )
  {
    ActivationFactory = -2147024638;
    Logger::TraceError(
      L"%s: MSA device ticket request failed with timeout (error code: 0x%08x).",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      2147942658LL);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  v24 = v48;
  v25 = (*v48)[8];
  v26 = v45;
  v45 = 0;
  if ( v26 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v26 + 16LL))(v26, *v26);
  v27 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD **))v25)(v24, &v45);
  ActivationFactory = v27;
  if ( v27 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"GetResults",
      (unsigned int)v27,
      v27);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  v53 = 0;
  v51 = 0;
  v28 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v45 + 56LL))(v45, &v53);
  ActivationFactory = v28;
  if ( v28 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"get_Status",
      (unsigned int)v28,
      v28);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  if ( !v53 )
    goto LABEL_45;
  v29 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v45 + 64LL))(v45, &v51);
  ActivationFactory = v29;
  if ( v29 < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      L"get_ExtendedError",
      (unsigned int)v29,
      v29);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    goto LABEL_64;
  }
  ActivationFactory = v51;
  if ( v51 < 0 )
  {
    Logger::TraceError(
      L"%s: MSA device ticket request failed with error code: 0x%08x.",
      L"DeviceTicket::GetMSADeviceTicketImpl",
      (unsigned int)v51);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
  }
  else
  {
LABEL_45:
    v49 = 0;
    v30 = *v45;
    v49 = 0;
    v31 = (*(__int64 (__fastcall **)(_QWORD *, __int64 **))(v30 + 48))(v45, &v49);
    ActivationFactory = v31;
    if ( v31 >= 0 )
    {
      if ( v49 )
      {
        v50 = 0;
        v32 = *v49;
        v50 = 0;
        v33 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v32 + 48))(v49, &v50);
        ActivationFactory = v33;
        if ( v33 >= 0 )
        {
          if ( v50 )
          {
            v34 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v50 + 64))(v50, &v51);
            ActivationFactory = v34;
            if ( v34 >= 0 )
            {
              ActivationFactory = v51;
              if ( v51 >= 0 )
              {
                v52 = 0;
                v35 = *v50;
                v52 = 0;
                v36 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v35 + 48))(v50, &v52);
                ActivationFactory = v36;
                if ( v36 >= 0 )
                {
                  if ( v52 )
                  {
                    StringRawBuffer = WindowsGetStringRawBuffer(v52, 0);
                    do
                      ++v10;
                    while ( StringRawBuffer[v10] );
                    std::wstring::_Assign<unsigned short>((char **)a3, StringRawBuffer, (char *)v10);
                    ActivationFactory = 0;
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v52);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v50);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
                  }
                  else
                  {
                    ActivationFactory = -2145647558;
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v52);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v50);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
                  }
                }
                else
                {
                  Logger::TraceError(
                    L"%s: %s failed with error code: 0x%08x.",
                    L"DeviceTicket::GetMSADeviceTicketImpl",
                    L"get_Value",
                    (unsigned int)v36,
                    v36);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v52);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v50);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
                }
              }
              else
              {
                Logger::TraceError(
                  L"%s: MSA device ticket request failed with error code in ticket: 0x%08x.",
                  L"DeviceTicket::GetMSADeviceTicketImpl",
                  (unsigned int)v51);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v50);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
              }
            }
            else
            {
              Logger::TraceError(
                L"%s: %s failed with error code: 0x%08x.",
                L"DeviceTicket::GetMSADeviceTicketImpl",
                L"get_ErrorCode",
                (unsigned int)v34,
                v34);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v50);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
              wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
            }
          }
          else
          {
            ActivationFactory = -2145647558;
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v50);
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
          }
        }
        else
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"DeviceTicket::GetMSADeviceTicketImpl",
            L"get_Ticket",
            (unsigned int)v33,
            v33);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v50);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
          wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
        }
      }
      else
      {
        ActivationFactory = -2145647558;
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
        wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
      }
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DeviceTicket::GetMSADeviceTicketImpl",
        L"get_Identity",
        (unsigned int)v31,
        v31);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v49);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v45);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v48);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v47);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v43);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v40);
    }
  }
LABEL_64:
  if ( v5 )
    CoUninitialize();
  return ActivationFactory;
}

```

## disassembly

```asm
0x18005b8b8  mov     [rsp+arg_8], rbx
0x18005b8bd  push    rsi
0x18005b8be  push    rdi
0x18005b8bf  push    r12
0x18005b8c1  push    r14
0x18005b8c3  push    r15
0x18005b8c5  sub     rsp, 0C0h
0x18005b8cc  mov     rax, cs:__security_cookie
0x18005b8d3  xor     rax, rsp
0x18005b8d6  mov     [rsp+0E8h+var_38], rax
0x18005b8de  mov     r15, r8
0x18005b8e1  mov     r14, rcx
0x18005b8e4  xor     edi, edi
0x18005b8e6  mov     r12b, dil
0x18005b8e9  mov     [rsp+0E8h+var_B7], dil
0x18005b8ee  mov     [r8+10h], rdi
0x18005b8f2  cmp     qword ptr [r8+18h], 7
0x18005b8f7  jbe     short loc_18005B8FE
0x18005b8f9  mov     rax, [r8]
0x18005b8fc  jmp     short loc_18005B901
0x18005b8fe  mov     rax, r15
0x18005b901  mov     [rax], di
0x18005b904  test    r14, r14
0x18005b907  jnz     short loc_18005B940
0x18005b909  mov     ebx, 80070057h
0x18005b90e  lea     r8, aPwszscope; "pwszScope"
0x18005b915  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005b91c  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18005b923  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005b928  lea     rdx, aPwszscope; "pwszScope"
0x18005b92f  lea     rcx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005b936  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18005b93b  jmp     loc_18005C6A2
0x18005b940  mov     [rsp+0E8h+var_C0], rdi
0x18005b945  mov     [rsp+0E8h+var_40], rdi
0x18005b94d  mov     esi, 46h ; 'F'
0x18005b952  lea     r9d, [rsi-1]; unsigned int
0x18005b956  mov     r8d, esi; unsigned int
0x18005b959  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18005b960  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x18005b968  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005b96d  lea     r8, [rsp+0E8h+var_C0]
0x18005b972  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x18005b979  mov     rcx, [rsp+0E8h+var_40]
0x18005b981  call    cs:__imp_RoGetActivationFactory
0x18005b987  mov     ebx, eax
0x18005b989  mov     [rsp+0E8h+var_C8], eax
0x18005b98d  cmp     eax, 800401F0h
0x18005b992  jnz     loc_18005BA43
0x18005b998  xor     edx, edx; dwCoInit
0x18005b99a  xor     ecx, ecx; pvReserved
0x18005b99c  call    cs:__imp_CoInitializeEx
0x18005b9a2  mov     ebx, eax
0x18005b9a4  mov     [rsp+0E8h+var_C8], eax
0x18005b9a8  test    eax, eax
0x18005b9aa  jns     short loc_18005B9DA
0x18005b9ac  mov     r9d, eax
0x18005b9af  lea     r8, aCoinitializeex_0; "CoInitializeEx"
0x18005b9b6  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005b9bd  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005b9c4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005b9c9  nop
0x18005b9ca  lea     rcx, [rsp+0E8h+var_C0]
0x18005b9cf  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005b9d4  nop
0x18005b9d5  jmp     loc_18005C6A2
0x18005b9da  mov     r12b, 1
0x18005b9dd  mov     [rsp+0E8h+var_B7], r12b
0x18005b9e2  mov     rcx, [rsp+0E8h+var_C0]
0x18005b9e7  mov     [rsp+0E8h+var_C0], rdi
0x18005b9ec  test    rcx, rcx
0x18005b9ef  jz      short loc_18005B9FE
0x18005b9f1  mov     rax, [rcx]
0x18005b9f4  mov     rax, [rax+10h]
0x18005b9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9fd  nop
0x18005b9fe  mov     [rsp+0E8h+var_40], rdi
0x18005ba06  mov     r9d, 45h ; 'E'; unsigned int
0x18005ba0c  mov     r8d, esi; unsigned int
0x18005ba0f  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18005ba16  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x18005ba1e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005ba23  lea     r8, [rsp+0E8h+var_C0]
0x18005ba28  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x18005ba2f  mov     rcx, [rsp+0E8h+var_40]
0x18005ba37  call    cs:__imp_RoGetActivationFactory
0x18005ba3d  mov     ebx, eax
0x18005ba3f  mov     [rsp+0E8h+var_C8], eax
0x18005ba43  cmp     ebx, 80040154h
0x18005ba49  jnz     short loc_18005BA64
0x18005ba4b  mov     ebx, 801C0439h
0x18005ba50  mov     [rsp+0E8h+var_C8], ebx
0x18005ba54  lea     rcx, [rsp+0E8h+var_C0]
0x18005ba59  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005ba5e  nop
0x18005ba5f  jmp     loc_18005C697
0x18005ba64  test    ebx, ebx
0x18005ba66  jns     short loc_18005BA96
0x18005ba68  mov     r9d, ebx
0x18005ba6b  lea     r8, aGetactivationf; "GetActivationFactory"
0x18005ba72  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005ba79  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005ba80  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005ba85  nop
0x18005ba86  lea     rcx, [rsp+0E8h+var_C0]
0x18005ba8b  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005ba90  nop
0x18005ba91  jmp     loc_18005C697
0x18005ba96  mov     [rsp+0E8h+string], rdi
0x18005ba9b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005ba9f  mov     rdx, rsi
0x18005baa2  inc     rdx; length
0x18005baa5  cmp     [r14+rdx*2], di
0x18005baaa  jnz     short loc_18005BAA2
0x18005baac  lea     r8, [rsp+0E8h+string]; string
0x18005bab1  mov     rcx, r14; sourceString
0x18005bab4  call    cs:__imp_WindowsCreateString
0x18005baba  mov     ebx, eax
0x18005babc  mov     [rsp+0E8h+var_C8], eax
0x18005bac0  test    eax, eax
0x18005bac2  jns     short loc_18005BAFD
0x18005bac4  mov     r9d, eax
0x18005bac7  lea     r8, aWindowscreates_1; "WindowsCreateString"
0x18005bace  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005bad5  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005badc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005bae1  nop
0x18005bae2  lea     rcx, [rsp+0E8h+string]
0x18005bae7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005baec  nop
0x18005baed  lea     rcx, [rsp+0E8h+var_C0]
0x18005baf2  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005baf7  nop
0x18005baf8  jmp     loc_18005C697
0x18005bafd  mov     [rsp+0E8h+var_B0], rdi
0x18005bb02  mov     rcx, [rsp+0E8h+var_C0]
0x18005bb07  mov     rax, [rcx]
0x18005bb0a  mov     [rsp+0E8h+var_B0], rdi
0x18005bb0f  lea     r8, [rsp+0E8h+var_B0]
0x18005bb14  mov     rdx, [rsp+0E8h+string]
0x18005bb19  mov     rax, [rax+38h]
0x18005bb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb22  mov     ebx, eax
0x18005bb24  test    eax, eax
0x18005bb26  jns     short loc_18005BB70
0x18005bb28  mov     [rsp+0E8h+var_C8], eax
0x18005bb2c  mov     r9d, eax
0x18005bb2f  lea     r8, aWindowscreates_1; "WindowsCreateString"
0x18005bb36  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005bb3d  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005bb44  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005bb49  nop
0x18005bb4a  lea     rcx, [rsp+0E8h+var_B0]
0x18005bb4f  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bb54  nop
0x18005bb55  lea     rcx, [rsp+0E8h+string]
0x18005bb5a  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bb5f  nop
0x18005bb60  lea     rcx, [rsp+0E8h+var_C0]
0x18005bb65  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bb6a  nop
0x18005bb6b  jmp     loc_18005C697
0x18005bb70  mov     [rsp+0E8h+var_90], rdi
0x18005bb75  mov     [rsp+0E8h+var_40], rdi
0x18005bb7d  mov     r9d, 44h ; 'D'; unsigned int
0x18005bb83  lea     r8d, [r9+1]; unsigned int
0x18005bb87  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdSystemAuthenticator@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18005bb8e  lea     rcx, [rsp+0E8h+hstringHeader]; hstringHeader
0x18005bb96  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18005bb9b  lea     r8, [rsp+0E8h+var_90]
0x18005bba0  lea     rdx, _GUID_85047792_f634_41e3_96a4_5164e902c740
0x18005bba7  mov     rcx, [rsp+0E8h+var_40]
0x18005bbaf  call    cs:__imp_RoGetActivationFactory
0x18005bbb5  mov     ebx, eax
0x18005bbb7  mov     [rsp+0E8h+var_C8], eax
0x18005bbbb  test    eax, eax
0x18005bbbd  jns     short loc_18005BC0E
0x18005bbbf  mov     r9d, eax
0x18005bbc2  lea     r8, aGetactivationf; "GetActivationFactory"
0x18005bbc9  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005bbd0  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005bbd7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005bbdc  nop
0x18005bbdd  lea     rcx, [rsp+0E8h+var_90]
0x18005bbe2  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bbe7  nop
0x18005bbe8  lea     rcx, [rsp+0E8h+var_B0]
0x18005bbed  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bbf2  nop
0x18005bbf3  lea     rcx, [rsp+0E8h+string]
0x18005bbf8  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bbfd  nop
0x18005bbfe  lea     rcx, [rsp+0E8h+var_C0]
0x18005bc03  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bc08  nop
0x18005bc09  jmp     loc_18005C697
0x18005bc0e  mov     [rsp+0E8h+var_98], rdi
0x18005bc13  mov     rcx, [rsp+0E8h+var_90]
0x18005bc18  mov     rax, [rcx]
0x18005bc1b  mov     [rsp+0E8h+var_98], rdi
0x18005bc20  lea     rdx, [rsp+0E8h+var_98]
0x18005bc25  mov     rax, [rax+30h]
0x18005bc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc2e  mov     ebx, eax
0x18005bc30  mov     [rsp+0E8h+var_C8], eax
0x18005bc34  test    eax, eax
0x18005bc36  jns     short loc_18005BC92
0x18005bc38  mov     r9d, eax
0x18005bc3b  lea     r8, aGetDefault; "get_Default"
0x18005bc42  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005bc49  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005bc50  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005bc55  nop
0x18005bc56  lea     rcx, [rsp+0E8h+var_98]
0x18005bc5b  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bc60  nop
0x18005bc61  lea     rcx, [rsp+0E8h+var_90]
0x18005bc66  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bc6b  nop
0x18005bc6c  lea     rcx, [rsp+0E8h+var_B0]
0x18005bc71  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bc76  nop
0x18005bc77  lea     rcx, [rsp+0E8h+string]
0x18005bc7c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bc81  nop
0x18005bc82  lea     rcx, [rsp+0E8h+var_C0]
0x18005bc87  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bc8c  nop
0x18005bc8d  jmp     loc_18005C697
0x18005bc92  mov     rcx, [rsp+0E8h+var_98]
0x18005bc97  movups  xmm0, cs:xmmword_1800E3B40
0x18005bc9e  movdqu  xmmword ptr [rsp+0E8h+hstringHeader.Reserved], xmm0
0x18005bca7  mov     rax, [rcx]
0x18005bcaa  lea     rdx, [rsp+0E8h+hstringHeader]
0x18005bcb2  mov     rax, [rax+38h]
0x18005bcb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcbb  mov     ebx, eax
0x18005bcbd  mov     [rsp+0E8h+var_C8], eax
0x18005bcc1  test    eax, eax
0x18005bcc3  jns     short loc_18005BD1F
0x18005bcc5  mov     r9d, eax
0x18005bcc8  lea     r8, aPutApplication; "put_ApplicationId"
0x18005bccf  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005bcd6  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005bcdd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005bce2  nop
0x18005bce3  lea     rcx, [rsp+0E8h+var_98]
0x18005bce8  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bced  nop
0x18005bcee  lea     rcx, [rsp+0E8h+var_90]
0x18005bcf3  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bcf8  nop
0x18005bcf9  lea     rcx, [rsp+0E8h+var_B0]
0x18005bcfe  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bd03  nop
0x18005bd04  lea     rcx, [rsp+0E8h+string]
0x18005bd09  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bd0e  nop
0x18005bd0f  lea     rcx, [rsp+0E8h+var_C0]
0x18005bd14  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bd19  nop
0x18005bd1a  jmp     loc_18005C697
0x18005bd1f  mov     [rsp+0E8h+var_88], rdi
0x18005bd24  mov     [rsp+0E8h+var_A0], rdi
0x18005bd29  mov     [rsp+0E8h+var_B8], dil
0x18005bd2e  mov     rcx, [rsp+0E8h+var_98]
0x18005bd33  mov     rax, [rcx]
0x18005bd36  mov     [rsp+0E8h+var_88], rdi
0x18005bd3b  lea     r8, [rsp+0E8h+var_88]
0x18005bd40  mov     rdx, [rsp+0E8h+var_B0]
0x18005bd45  mov     rax, [rax+30h]
0x18005bd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd4e  mov     ebx, eax
0x18005bd50  test    eax, eax
0x18005bd52  jns     short loc_18005BDC8
0x18005bd54  mov     [rsp+0E8h+var_C8], eax
0x18005bd58  mov     r9d, eax
0x18005bd5b  lea     r8, aGetticketasync; "GetTicketAsync"
0x18005bd62  lea     rdx, aDeviceticketGe_0; "DeviceTicket::GetMSADeviceTicketImpl"
0x18005bd69  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18005bd70  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18005bd75  nop
0x18005bd76  lea     rcx, [rsp+0E8h+var_A0]
0x18005bd7b  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bd80  nop
0x18005bd81  lea     rcx, [rsp+0E8h+var_88]
0x18005bd86  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bd8b  nop
0x18005bd8c  lea     rcx, [rsp+0E8h+var_98]
0x18005bd91  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bd96  nop
0x18005bd97  lea     rcx, [rsp+0E8h+var_90]
0x18005bd9c  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bda1  nop
0x18005bda2  lea     rcx, [rsp+0E8h+var_B0]
0x18005bda7  call    ??1?$com_ptr_t@UIWebProviderError@Core@Web@Authentication@Security@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(void)
0x18005bdac  nop
0x18005bdad  lea     rcx, [rsp+0E8h+string]
0x18005bdb2  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18005bdb7  nop
  ... truncated ...
```
