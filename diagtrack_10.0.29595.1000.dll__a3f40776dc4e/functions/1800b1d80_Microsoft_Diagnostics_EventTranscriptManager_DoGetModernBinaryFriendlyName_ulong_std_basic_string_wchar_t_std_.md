# Microsoft::Diagnostics::EventTranscriptManager::DoGetModernBinaryFriendlyName(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800b1d80`
- end: `0x1800b247a`
- name: `?DoGetModernBinaryFriendlyName@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0V?$basic_string_view@_WU?$char_traits@_W@std@@@5@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z`
- size: `1786`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180032a98`

## callees

- `0x180023ae4`
- `0x18002b318`
- `0x18002df00`
- `0x1800331bc`
- `0x180061f68`
- `0x180062100`
- `0x1800624ac`
- `0x180064e8c`
- `0x18009c8c0`
- `0x1800b0a80`
- `0x1800b1d80`
- `0x1800b2480`
- `0x1800b24d4`
- `0x1800b2534`
- `0x1800bc508`
- `0x1800bc658`
- `0x1800bd47c`
- `0x1800be63c`
- `0x180110780`
- `0x18011d5d8`
- `0x1801210ac`
- `0x1801288a0`
- `0x1801298f8`
- `0x18015b6b8`
- `0x1801cad20`
- `0x1801cb004`
- `0x1801cb460`
- `0x1801cb600`
- `0x1801cb664`
- `0x1801cb7dc`
- `0x1801d0800`
- `0x1801d0950`
- `0x1801d1860`
- `0x18020aac0`
- `0x18030bcec`
- `0x18030bd60`
- `0x18030bde4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b1f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b1f9d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b1f72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800b1f9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b1ec8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800b1ec8`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800b2472`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800b2472`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b23f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b23f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2462`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b1e0a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b1e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b23e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b23e5`

## string_xrefs

- `0x1800b1de8`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800b1e48`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800b207f`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1800b2443`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::EventTranscriptManager::DoGetModernBinaryFriendlyName(
        __int64 a1,
        DWORD a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6)
{
  CallerIdentity *v6; // rdi
  unsigned __int16 **v10; // r8
  int ProcessAppId; // eax
  unsigned int v12; // ebx
  struct Microsoft::Diagnostics::UserManager *UserManager; // rax
  unsigned int v14; // edx
  _QWORD *v15; // rcx
  unsigned __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // r8
  unsigned int v19; // esi
  unsigned int i; // ebx
  int DesktopBinaryFriendlyName; // eax
  unsigned int v22; // ebx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  void *v27; // rbx
  const wchar_t *v28; // rdx
  winrt::impl *v29; // rcx
  unsigned int v30; // r8d
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // [rsp+20h] [rbp-178h] BYREF
  __int64 *v35; // [rsp+28h] [rbp-170h] BYREF
  __int64 v36; // [rsp+30h] [rbp-168h] BYREF
  _DWORD **v37; // [rsp+38h] [rbp-160h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-158h] BYREF
  _BYTE v39[8]; // [rsp+48h] [rbp-150h] BYREF
  __int128 v40; // [rsp+50h] [rbp-148h] BYREF
  _QWORD v41[2]; // [rsp+60h] [rbp-138h] BYREF
  CallerIdentity *v42; // [rsp+70h] [rbp-128h] BYREF
  _DWORD *v43; // [rsp+78h] [rbp-120h] BYREF
  _DWORD v44[4]; // [rsp+80h] [rbp-118h] BYREF
  _QWORD *v45; // [rsp+90h] [rbp-108h]
  _QWORD v46[4]; // [rsp+98h] [rbp-100h] BYREF
  _QWORD v47[2]; // [rsp+B8h] [rbp-E0h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-D0h]
  unsigned __int64 v49; // [rsp+D0h] [rbp-C8h]
  _BYTE v50[32]; // [rsp+D8h] [rbp-C0h] BYREF
  _BYTE v51[32]; // [rsp+F8h] [rbp-A0h] BYREF
  _BYTE v52[32]; // [rsp+118h] [rbp-80h] BYREF
  _BYTE v53[32]; // [rsp+138h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  *(_QWORD *)&v40 = a1;
  if ( *(_QWORD *)(a6 + 16) )
  {
    _o_terminate();
LABEL_9:
    v15 = (_QWORD *)v47[0];
    goto LABEL_10;
  }
  if ( !*(_QWORD *)(a3 + 16) && !a4[2] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1299,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
      (const char *)0x80004005LL,
      v34);
    return 2147500037LL;
  }
  v6 = (CallerIdentity *)OpenProcess(0x1000u, 0, a2);
  v42 = v6;
  if ( (unsigned __int64)v6 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A1,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
      (const char *)0x80004005LL,
      v34);
    return 2147500037LL;
  }
  pv = 0;
  ProcessAppId = CallerIdentity::GetProcessAppId(v6, &pv, v10);
  v12 = ProcessAppId;
  if ( ProcessAppId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
      (const char *)(unsigned int)ProcessAppId,
      v34);
    __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&pv);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
    return v12;
  }
  UserManager = Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::UserManager::GetLoggedInUserSid(UserManager, v47);
  v14 = v48;
  v15 = v47;
  if ( v49 > 7 )
    goto LABEL_9;
LABEL_10:
  if ( v14 )
  {
    if ( *((_WORD *)v15 + v14) )
      abort();
    v44[0] = 1;
    v44[1] = v14;
    v45 = v15;
    v43 = v44;
  }
  else
  {
    v43 = 0;
  }
  v37 = &v43;
  v35 = &qword_180461A48;
  _InterlockedIncrement64(&qword_180461A48);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics> )
  {
    winrt::impl::consume_Windows_Internal_StateRepository_IUserStatics<winrt::Windows::Internal::StateRepository::IUserStatics>::GetByUserSid(
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics>,
      &v36,
      &v43);
    _InterlockedDecrement64(&qword_180461A48);
  }
  else
  {
    _InterlockedDecrement64(&qword_180461A48);
    ___call_AEAV_lambda_1___1__GetByUserSid_User_StateRepository_Internal_Windows_winrt__SA_AEBUhstring_param_7__Z____factory_cache_entry_UUser_StateRepository_Internal_Windows_winrt__UIUserStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetByUserSid_User_StateRepository_Internal_Windows_2_SA_AEBUhstring_param_2__Z__Z(
      v15,
      &v36,
      &v37);
  }
  v16 = a5[1];
  v17 = 17;
  if ( v16 <= 0x11 )
    v17 = a5[1];
  if ( !(unsigned int)_o__wcsnicmp(*a5, L"runtimebroker.exe", v17) && (_DWORD)v16 == 17 )
    goto LABEL_26;
  v18 = 22;
  if ( v16 <= 0x16 )
    v18 = v16;
  if ( (unsigned int)_o__wcsnicmp(*a5, L"backgroundtaskhost.exe", v18) || (_DWORD)v16 != 22 )
  {
    v27 = pv;
    v28 = (const wchar_t *)(unsigned int)std::_WChar_traits<wchar_t>::length(pv);
    *(_QWORD *)&v40 = winrt::impl::create_hstring_on_heap(v29, v28, v30);
    v46[0] = v40;
    v41[0] = &v36;
    v41[1] = v46;
    v35 = &qword_1804619E8;
    _InterlockedIncrement64(&qword_1804619E8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics> )
    {
      winrt::impl::consume_Windows_Internal_StateRepository_IApplicationStatics<winrt::Windows::Internal::StateRepository::IApplicationStatics>::GetByUserAndApplicationUserModelId(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>,
        &v34,
        &v36,
        v46);
      _InterlockedDecrement64(&qword_1804619E8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1804619E8);
      ___call_AEAV_lambda_1___1__GetByUserAndApplicationUserModelId_Application_StateRepository_Internal_Windows_winrt__SA_AEBUUser_4567_AEBUhstring_param_7__Z____factory_cache_entry_UApplication_StateRepository_Internal_Windows_winrt__UIApplicationStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__GetByUserAndApplicationUserModelId_Application_StateRepository_Internal_Windows_2_SA_AEBUUser_6782_AEBUhstring_param_2__Z__Z(
        v31,
        &v34,
        v41);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v40);
    *(_QWORD *)&v40 = &v34;
    v41[0] = &qword_180461A08;
    _InterlockedIncrement64(&qword_180461A08);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationResourceResolver,winrt::Windows::Internal::StateRepository::IApplicationResourceResolverStatics> )
    {
      winrt::impl::consume_Windows_Internal_StateRepository_IApplicationResourceResolverStatics<winrt::Windows::Internal::StateRepository::IApplicationResourceResolverStatics>::Create(
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::ApplicationResourceResolver,winrt::Windows::Internal::StateRepository::IApplicationResourceResolverStatics>,
        &v35,
        &v34);
      _InterlockedDecrement64(&qword_180461A08);
    }
    else
    {
      _InterlockedDecrement64(&qword_180461A08);
      ___call_AEAV_lambda_1___1__Create_ApplicationResourceResolver_StateRepository_Internal_Windows_winrt__SA_AEBUApplication_4567__Z____factory_cache_entry_UApplicationResourceResolver_StateRepository_Internal_Windows_winrt__UIApplicationResourceResolverStatics_2345__impl_winrt__QEAA_A_PAEAV_lambda_1___1__Create_ApplicationResourceResolver_StateRepository_Internal_Windows_2_SA_AEBUApplication_6782__Z__Z(
        v32,
        &v35,
        &v40);
    }
    winrt::impl::consume_Windows_Security_Credentials_IWebAccountProvider<winrt::Windows::Security::Credentials::IWebAccountProvider>::Id(
      &v35,
      &v37);
    if ( v37 )
    {
      v40 = *(_OWORD *)winrt::hstring::operator std::wstring_view(&v37, &v43);
      v33 = Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(v50, &v40);
      std::string::operator=(a6, v33);
      std::string::_Tidy_deallocate(v50);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v37);
    if ( v35 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v35);
    if ( v34 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v34);
  }
  else
  {
LABEL_26:
    winrt::param::hstring::hstring(v46, a3);
    winrt::Windows::Internal::StateRepository::Package::GetByUserAndPackageFullName(
      (const struct winrt::Windows::Internal::StateRepository::User *)&v37,
      (const struct winrt::param::hstring *)&v36);
    winrt::Windows::Internal::StateRepository::Application::FindByPackage((const struct winrt::Windows::Internal::StateRepository::Package *)&v35);
    v19 = winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::AuthenticationStatus(&v35);
    for ( i = 0; i < v19; ++i )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::Application>,winrt::Windows::Internal::StateRepository::Application>::GetAt(
        &v35,
        v41,
        i);
      winrt::Windows::Internal::StateRepository::ApplicationResourceResolver::Create((const struct Application *)v39);
      winrt::impl::consume_Windows_Security_Credentials_IWebAccountProvider<winrt::Windows::Security::Credentials::IWebAccountProvider>::Id(
        v39,
        &v34);
      if ( v34 )
      {
        std::string::string(v46);
        DesktopBinaryFriendlyName = Microsoft::Diagnostics::EventTranscriptManager::DoGetDesktopBinaryFriendlyName(
                                      v40,
                                      a4,
                                      (__int64)v46);
        v22 = DesktopBinaryFriendlyName;
        if ( DesktopBinaryFriendlyName < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x12BE,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)DesktopBinaryFriendlyName,
            v34);
          std::string::_Tidy_deallocate(v46);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v34);
          winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)v39);
          winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)v41);
          winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v35);
          winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v37);
          winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v36);
          std::wstring::_Tidy_deallocate(v47);
          __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&pv);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v42);
          return v22;
        }
        v23 = std::wstring::wstring(v50, &v34);
        v40 = *(_OWORD *)std::wstring::operator std::wstring_view(v23, &v43);
        v24 = Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(v53, &v40);
        v25 = std::operator+<char>(v52, v24, " ");
        v26 = std::operator+<char>(v51, v25, v46);
        std::string::operator=(a6, v26);
        std::string::_Tidy_deallocate(v51);
        std::string::_Tidy_deallocate(v52);
        std::string::_Tidy_deallocate(v53);
        std::wstring::_Tidy_deallocate(v50);
        std::string::_Tidy_deallocate(v46);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v34);
        winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)v39);
        winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)v41);
        break;
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v34);
      winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)v39);
      winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)v41);
    }
    winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v35);
    winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v37);
    v27 = pv;
  }
  if ( v36 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v36);
  std::wstring::_Tidy_deallocate(v47);
  if ( v27 )
    CoTaskMemFree(v27);
  if ( (unsigned __int64)v6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  return *(_QWORD *)(a6 + 16) == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800b1d80  push    rbx
0x1800b1d82  push    rsi
0x1800b1d83  push    rdi
0x1800b1d84  push    r12
0x1800b1d86  push    r13
0x1800b1d88  push    r14
0x1800b1d8a  push    r15
0x1800b1d8c  sub     rsp, 160h
0x1800b1d93  mov     rax, cs:__security_cookie
0x1800b1d9a  xor     rax, rsp
0x1800b1d9d  mov     [rsp+198h+var_40], rax
0x1800b1da5  mov     r12, r9
0x1800b1da8  mov     r14, r8
0x1800b1dab  mov     qword ptr [rsp+198h+var_148], rcx
0x1800b1db0  mov     r15, [rsp+198h+arg_28]
0x1800b1db8  mov     r13, [rsp+198h+arg_20]
0x1800b1dc0  xor     esi, esi
0x1800b1dc2  cmp     [r15+10h], rsi
0x1800b1dc6  jnz     loc_1800B2472
0x1800b1dcc  cmp     [r8+10h], rsi
0x1800b1dd0  jnz     short loc_1800B1E00
0x1800b1dd2  cmp     [r9+10h], rsi
0x1800b1dd6  jnz     short loc_1800B1E00
0x1800b1dd8  mov     rcx, [rsp+198h]; this
0x1800b1de0  mov     ebx, 80004005h
0x1800b1de5  mov     r9d, ebx; char *
0x1800b1de8  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x1800b1def  mov     edx, 1299h; void *
0x1800b1df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1df9  mov     eax, ebx
0x1800b1dfb  jmp     loc_1800B2410
0x1800b1e00  mov     r8d, edx; dwProcessId
0x1800b1e03  xor     edx, edx; bInheritHandle
0x1800b1e05  mov     ecx, 1000h; dwDesiredAccess
0x1800b1e0a  call    cs:__imp_OpenProcess
0x1800b1e10  mov     rdi, rax
0x1800b1e13  mov     [rsp+198h+var_128], rax
0x1800b1e18  dec     rax
0x1800b1e1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800b1e1f  ja      loc_1800B2433
0x1800b1e25  mov     [rsp+198h+pv], rsi
0x1800b1e2a  lea     rdx, [rsp+198h+pv]; void *
0x1800b1e2f  mov     rcx, rdi; this
0x1800b1e32  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800b1e37  mov     ebx, eax
0x1800b1e39  test    eax, eax
0x1800b1e3b  jns     short loc_1800B1E76
0x1800b1e3d  mov     rcx, [rsp+198h]; this
0x1800b1e45  mov     r9d, eax; char *
0x1800b1e48  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x1800b1e4f  mov     edx, 12A4h; void *
0x1800b1e54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1e59  nop
0x1800b1e5a  lea     rcx, [rsp+198h+pv]
0x1800b1e5f  call    ??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
0x1800b1e64  nop
0x1800b1e65  lea     rcx, [rsp+198h+var_128]
0x1800b1e6a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b1e6f  mov     eax, ebx
0x1800b1e71  jmp     loc_1800B2410
0x1800b1e76  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1800b1e7d  call    ?GetUserManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVUserManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetUserManager(void)
0x1800b1e82  lea     rdx, [rsp+198h+var_E0]
0x1800b1e8a  mov     rcx, rax
0x1800b1e8d  call    ?GetLoggedInUserSid@UserManager@Diagnostics@Microsoft@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::UserManager::GetLoggedInUserSid(void)
0x1800b1e92  nop
0x1800b1e93  mov     rdx, [rsp+198h+var_D0]
0x1800b1e9b  lea     rcx, [rsp+198h+var_E0]
0x1800b1ea3  cmp     [rsp+198h+var_C8], 7
0x1800b1eac  cmova   rcx, [rsp+198h+var_E0]
0x1800b1eb5  test    edx, edx
0x1800b1eb7  jnz     short loc_1800B1EC0
0x1800b1eb9  mov     [rsp+198h+var_120], rsi
0x1800b1ebe  jmp     short loc_1800B1EF6
0x1800b1ec0  mov     eax, edx
0x1800b1ec2  cmp     [rcx+rax*2], si
0x1800b1ec6  jz      short loc_1800B1ECF
0x1800b1ec8  call    cs:__imp_abort
0x1800b1ecf  mov     [rsp+198h+var_118], 1
0x1800b1eda  mov     [rsp+198h+var_114], edx
0x1800b1ee1  mov     [rsp+198h+var_108], rcx
0x1800b1ee9  lea     rax, [rsp+198h+var_118]
0x1800b1ef1  mov     [rsp+198h+var_120], rax
0x1800b1ef6  lea     rax, [rsp+198h+var_120]
0x1800b1efb  mov     [rsp+198h+var_160], rax
0x1800b1f00  lea     rax, qword_180461A48
0x1800b1f07  mov     [rsp+198h+var_170], rax
0x1800b1f0c  lock inc cs:qword_180461A48
0x1800b1f14  cmp     cs:??$factory_cache_entry_v@UUser@StateRepository@Internal@Windows@winrt@@UIUserStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UUser@StateRepository@Internal@Windows@winrt@@UIUserStatics@2345@@12@A, rsi; factory_cache_entry<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics>
0x1800b1f1b  jz      short loc_1800B1F3E
0x1800b1f1d  lea     r8, [rsp+198h+var_120]
0x1800b1f22  lea     rdx, [rsp+198h+var_168]
0x1800b1f27  lea     rcx, ??$factory_cache_entry_v@UUser@StateRepository@Internal@Windows@winrt@@UIUserStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UUser@StateRepository@Internal@Windows@winrt@@UIUserStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::User,winrt::Windows::Internal::StateRepository::IUserStatics>
0x1800b1f2e  call    ?GetByUserSid@?$consume_Windows_Internal_StateRepository_IUserStatics@UIUserStatics@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_StateRepository_IUserStatics<winrt::Windows::Internal::StateRepository::IUserStatics>::GetByUserSid(winrt::param::hstring const &)
0x1800b1f33  nop
0x1800b1f34  lock dec cs:qword_180461A48
0x1800b1f3c  jmp     short loc_1800B1F56
0x1800b1f3e  lock dec cs:qword_180461A48
0x1800b1f46  lea     r8, [rsp+198h+var_160]
0x1800b1f4b  lea     rdx, [rsp+198h+var_168]
0x1800b1f50  call    ??$call@AEAV_lambda_1_@?1??GetByUserSid@User@StateRepository@Internal@Windows@winrt@@SA@AEBUhstring@param@7@@Z@@?$factory_cache_entry@UUser@StateRepository@Internal@Windows@winrt@@UIUserStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??GetByUserSid@User@StateRepository@Internal@Windows@2@SA@AEBUhstring@param@2@@Z@@Z
0x1800b1f55  nop
0x1800b1f56  mov     rbx, [r13+8]
0x1800b1f5a  mov     r8d, 11h
0x1800b1f60  cmp     rbx, r8
0x1800b1f63  cmovbe  r8, rbx
0x1800b1f67  mov     rdx, cs:off_18036D250; "runtimebroker.exe"
0x1800b1f6e  mov     rcx, [r13+0]
0x1800b1f72  call    cs:__imp__o__wcsnicmp
0x1800b1f78  test    eax, eax
0x1800b1f7a  jnz     short loc_1800B1F83
0x1800b1f7c  lea     eax, [rbx-11h]
0x1800b1f7f  test    eax, eax
0x1800b1f81  jz      short loc_1800B1FB8
0x1800b1f83  mov     esi, ebx
0x1800b1f85  mov     r8d, 16h
0x1800b1f8b  cmp     rbx, r8
0x1800b1f8e  cmovbe  r8, rbx
0x1800b1f92  mov     rdx, cs:off_18036D260; "backgroundtaskhost.exe"
0x1800b1f99  mov     rcx, [r13+0]
0x1800b1f9d  call    cs:__imp__o__wcsnicmp
0x1800b1fa3  test    eax, eax
0x1800b1fa5  jnz     loc_1800B2232
0x1800b1fab  lea     eax, [rbx-16h]
0x1800b1fae  xor     esi, esi
0x1800b1fb0  test    eax, eax
0x1800b1fb2  jnz     loc_1800B2234
0x1800b1fb8  mov     rdx, r14
0x1800b1fbb  lea     rcx, [rsp+198h+var_100]
0x1800b1fc3  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800b1fc8  lea     r8, [rsp+198h+var_100]
0x1800b1fd0  lea     rdx, [rsp+198h+var_168]; struct winrt::param::hstring *
0x1800b1fd5  lea     rcx, [rsp+198h+var_160]; struct winrt::Windows::Internal::StateRepository::User *
0x1800b1fda  call    ?GetByUserAndPackageFullName@Package@StateRepository@Internal@Windows@winrt@@SA@AEBUUser@2345@AEBUhstring@param@5@@Z; winrt::Windows::Internal::StateRepository::Package::GetByUserAndPackageFullName(winrt::Windows::Internal::StateRepository::User const &,winrt::param::hstring const &)
0x1800b1fdf  nop
0x1800b1fe0  lea     rdx, [rsp+198h+var_160]
0x1800b1fe5  lea     rcx, [rsp+198h+var_170]; struct winrt::Windows::Internal::StateRepository::Package *
0x1800b1fea  call    ?FindByPackage@Application@StateRepository@Internal@Windows@winrt@@SA@AEBUPackage@2345@@Z; winrt::Windows::Internal::StateRepository::Application::FindByPackage(winrt::Windows::Internal::StateRepository::Package const &)
0x1800b1fef  nop
0x1800b1ff0  lea     rcx, [rsp+198h+var_170]
0x1800b1ff5  call    ?AuthenticationStatus@?$consume_Windows_System_IUser@UIUser@System@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_System_IUser<winrt::Windows::System::IUser>::AuthenticationStatus(void)
0x1800b1ffa  mov     esi, eax
0x1800b1ffc  xor     ebx, ebx
0x1800b1ffe  cmp     ebx, esi
0x1800b2000  jnb     loc_1800B2211
0x1800b2006  mov     r8d, ebx
0x1800b2009  lea     rdx, [rsp+198h+var_138]
0x1800b200e  lea     rcx, [rsp+198h+var_170]
0x1800b2013  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UApplication@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UApplication@StateRepository@Internal@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::Application>,winrt::Windows::Internal::StateRepository::Application>::GetAt(uint)
0x1800b2018  nop
0x1800b2019  lea     rdx, [rsp+198h+var_138]
0x1800b201e  lea     rcx, [rsp+198h+var_150]; struct Application *
0x1800b2023  call    ?Create@ApplicationResourceResolver@StateRepository@Internal@Windows@winrt@@SA@AEBUApplication@2345@@Z; winrt::Windows::Internal::StateRepository::ApplicationResourceResolver::Create(winrt::Windows::Internal::StateRepository::Application const &)
0x1800b2028  nop
0x1800b2029  lea     rdx, [rsp+198h+var_178]
0x1800b202e  lea     rcx, [rsp+198h+var_150]
0x1800b2033  call    ?Id@?$consume_Windows_Security_Credentials_IWebAccountProvider@UIWebAccountProvider@Credentials@Security@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Security_Credentials_IWebAccountProvider<winrt::Windows::Security::Credentials::IWebAccountProvider>::Id(void)
0x1800b2038  nop
0x1800b2039  cmp     [rsp+198h+var_178], 0
0x1800b203f  jz      loc_1800B21EA
0x1800b2045  lea     rcx, [rsp+198h+var_100]
0x1800b204d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800b2052  nop
0x1800b2053  lea     r8, [rsp+198h+var_100]
0x1800b205b  mov     rdx, r12
0x1800b205e  mov     rcx, qword ptr [rsp+198h+var_148]
0x1800b2063  call    ?DoGetDesktopBinaryFriendlyName@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Diagnostics::EventTranscriptManager::DoGetDesktopBinaryFriendlyName(std::wstring const &,std::string &)
0x1800b2068  mov     ebx, eax
0x1800b206a  xor     esi, esi
0x1800b206c  test    eax, eax
0x1800b206e  jns     loc_1800B210B
0x1800b2074  mov     rcx, [rsp+198h]; this
0x1800b207c  mov     r9d, eax; char *
0x1800b207f  lea     r8, aOnecoreBaseTel_213; "onecore\\base\\telemetry\\utc\\service"...
0x1800b2086  mov     edx, 12BEh; void *
0x1800b208b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2090  nop
0x1800b2091  lea     rcx, [rsp+198h+var_100]
0x1800b2099  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b209e  nop
0x1800b209f  lea     rcx, [rsp+198h+var_178]
0x1800b20a4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800b20a9  nop
0x1800b20aa  lea     rcx, [rsp+198h+var_150]; this
0x1800b20af  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b20b4  nop
0x1800b20b5  lea     rcx, [rsp+198h+var_138]; this
0x1800b20ba  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b20bf  nop
0x1800b20c0  lea     rcx, [rsp+198h+var_170]; this
0x1800b20c5  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b20ca  nop
0x1800b20cb  lea     rcx, [rsp+198h+var_160]; this
0x1800b20d0  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b20d5  nop
0x1800b20d6  lea     rcx, [rsp+198h+var_168]; this
0x1800b20db  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b20e0  nop
0x1800b20e1  lea     rcx, [rsp+198h+var_E0]
0x1800b20e9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b20ee  nop
0x1800b20ef  lea     rcx, [rsp+198h+pv]
0x1800b20f4  call    ??1?$unique_ptr@$$BY0A@_WU?$generic_delete@$$BY0A@_WU?$generic_deallocate@$MP6AXPEAX@Z1?CoTaskMemFree@@YAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
0x1800b20f9  nop
0x1800b20fa  lea     rcx, [rsp+198h+var_128]
0x1800b20ff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b2104  mov     eax, ebx
0x1800b2106  jmp     loc_1800B2410
0x1800b210b  lea     rdx, [rsp+198h+var_178]
0x1800b2110  lea     rcx, [rsp+198h+var_C0]
0x1800b2118  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<wchar_t> const &)
0x1800b211d  nop
0x1800b211e  lea     rdx, [rsp+198h+var_120]
0x1800b2123  mov     rcx, rax
0x1800b2126  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800b212b  movups  xmm0, xmmword ptr [rax]
0x1800b212e  movdqu  [rsp+198h+var_148], xmm0
0x1800b2134  lea     rdx, [rsp+198h+var_148]
0x1800b2139  lea     rcx, [rsp+198h+var_60]
0x1800b2141  call    ?WideStringToMultiByteString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(std::wstring_view,ulong)
0x1800b2146  nop
0x1800b2147  lea     r8, asc_1803D4940; " "
0x1800b214e  mov     rdx, rax
0x1800b2151  lea     rcx, [rsp+198h+var_80]
0x1800b2159  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800b215e  nop
0x1800b215f  lea     r8, [rsp+198h+var_100]
0x1800b2167  mov     rdx, rax
0x1800b216a  lea     rcx, [rsp+198h+var_A0]
0x1800b2172  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x1800b2177  mov     rdx, rax
0x1800b217a  mov     rcx, r15
0x1800b217d  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800b2182  lea     rcx, [rsp+198h+var_A0]
0x1800b218a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b218f  nop
0x1800b2190  lea     rcx, [rsp+198h+var_80]
0x1800b2198  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b219d  nop
0x1800b219e  lea     rcx, [rsp+198h+var_60]
0x1800b21a6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b21ab  nop
0x1800b21ac  lea     rcx, [rsp+198h+var_C0]
0x1800b21b4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b21b9  nop
0x1800b21ba  lea     rcx, [rsp+198h+var_100]
0x1800b21c2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800b21c7  nop
0x1800b21c8  lea     rcx, [rsp+198h+var_178]
0x1800b21cd  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800b21d2  nop
0x1800b21d3  lea     rcx, [rsp+198h+var_150]; this
0x1800b21d8  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b21dd  nop
0x1800b21de  lea     rcx, [rsp+198h+var_138]; this
0x1800b21e3  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b21e8  jmp     short loc_1800B2213
0x1800b21ea  lea     rcx, [rsp+198h+var_178]
0x1800b21ef  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800b21f4  nop
0x1800b21f5  lea     rcx, [rsp+198h+var_150]; this
0x1800b21fa  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b21ff  nop
0x1800b2200  lea     rcx, [rsp+198h+var_138]; this
0x1800b2205  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b220a  inc     ebx
0x1800b220c  jmp     loc_1800B1FFE
0x1800b2211  xor     esi, esi
0x1800b2213  lea     rcx, [rsp+198h+var_170]; this
0x1800b2218  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b221d  nop
0x1800b221e  lea     rcx, [rsp+198h+var_160]; this
0x1800b2223  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800b2228  mov     rbx, [rsp+198h+pv]
0x1800b222d  jmp     loc_1800B23BD
0x1800b2232  xor     esi, esi
0x1800b2234  mov     rbx, [rsp+198h+pv]
0x1800b2239  mov     rcx, rbx
0x1800b223c  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1800b2241  mov     edx, eax; wchar_t *
0x1800b2243  call    ?create_hstring_on_heap@impl@winrt@@YAPEAUhstring_header@12@PEB_WI@Z; winrt::impl::create_hstring_on_heap(wchar_t const *,uint)
0x1800b2248  mov     qword ptr [rsp+198h+var_148], rax
0x1800b224d  mov     [rsp+198h+var_100], rax
0x1800b2255  lea     rax, [rsp+198h+var_168]
0x1800b225a  mov     [rsp+198h+var_138], rax
0x1800b225f  lea     rax, [rsp+198h+var_100]
0x1800b2267  mov     [rsp+198h+var_130], rax
0x1800b226c  lea     rax, qword_1804619E8
0x1800b2273  mov     [rsp+198h+var_170], rax
0x1800b2278  lock inc cs:qword_1804619E8
0x1800b2280  cmp     cs:??$factory_cache_entry_v@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@12@A, rsi; factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>
0x1800b2287  jz      short loc_1800B22B2
0x1800b2289  lea     r9, [rsp+198h+var_100]
0x1800b2291  lea     r8, [rsp+198h+var_168]
0x1800b2296  lea     rdx, [rsp+198h+var_178]
0x1800b229b  lea     rcx, ??$factory_cache_entry_v@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UApplication@StateRepository@Internal@Windows@winrt@@UIApplicationStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>::winrt::factory_cache_entry<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::StateRepository::Application,winrt::Windows::Internal::StateRepository::IApplicationStatics>
0x1800b22a2  call    ?GetByUserAndApplicationUserModelId@?$consume_Windows_Internal_StateRepository_IApplicationStatics@UIApplicationStatics@StateRepository@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUUser@StateRepository@Internal@Windows@3@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_StateRepository_IApplicationStatics<winrt::Windows::Internal::StateRepository::IApplicationStatics>::GetByUserAndApplicationUserModelId(winrt::Windows::Internal::StateRepository::User const &,winrt::param::hstring const &)
0x1800b22a7  nop
0x1800b22a8  lock dec cs:qword_1804619E8
0x1800b22b0  jmp     short loc_1800B22CA
  ... truncated ...
```
