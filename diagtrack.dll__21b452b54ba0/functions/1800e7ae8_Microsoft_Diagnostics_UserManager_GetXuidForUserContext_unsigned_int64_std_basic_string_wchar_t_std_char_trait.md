# Microsoft::Diagnostics::UserManager::GetXuidForUserContext(unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800e7ae8`
- end: `0x1800e7ed0`
- name: `?GetXuidForUserContext@UserManager@Diagnostics@Microsoft@@AEBAJ_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `1000`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e778c`

## callees

- `0x18002abec`
- `0x180053ff4`
- `0x1800561a4`
- `0x180064e34`
- `0x180064e8c`
- `0x1800b0a80`
- `0x1800b2534`
- `0x1800bc658`
- `0x1800bd47c`
- `0x1800be63c`
- `0x1800e7ae8`
- `0x1800feca0`
- `0x18010022c`
- `0x180139730`
- `0x180142fcc`
- `0x1801b74e8`
- `0x1801b7bd0`
- `0x1801c2d0c`
- `0x180204810`
- `0x18020aac0`
- `0x18024a548`
- `0x18025b97c`
- `0x180369010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e7d62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e7db8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e7df8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e7d62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e7db8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e7df8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e7d28`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e7d28`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1800e7b2e`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1800e7b2e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800e7cc7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800e7cc7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800e7c98`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800e7c98`

## string_xrefs

- `0x1800e7cde`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800e7d9b`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800e7e99`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800e7eab`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1800e7ebd`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UserManager::GetXuidForUserContext(__int64 a1, wchar_t *a2, __int64 a3)
{
  char *v3; // rdi
  _WORD *v5; // rcx
  __int64 v6; // r8
  _QWORD *v7; // rdx
  unsigned int v8; // eax
  __int64 String; // rax
  CONTEXT *v10; // rbx
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // ebx
  int GamerAccountXuidForImpersonatedUser; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  const char *v18; // r9
  const char *v19; // r9
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // [rsp+20h] [rbp-A8h]
  wchar_t *v24; // [rsp+30h] [rbp-98h] BYREF
  HANDLE hToken; // [rsp+38h] [rbp-90h] BYREF
  int v26; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-80h] BYREF
  const void *v28; // [rsp+50h] [rbp-78h] BYREF
  __int128 v29; // [rsp+58h] [rbp-70h]
  _QWORD v30[7]; // [rsp+70h] [rbp-58h] BYREF
  _QWORD *v31; // [rsp+A8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v3 = (char *)a3;
  *(_QWORD *)(a3 + 16) = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v5 = (_WORD *)a3;
  else
    v5 = *(_WORD **)a3;
  *v5 = 0;
  if ( (unsigned int)XblaIsConsole() )
  {
    winrt::Windows::System::Internal::UserManager::GetUserForContext((unsigned __int64)&v27);
    v30[0] = off_18037D8D0;
    v30[1] = &v27;
    v31 = v30;
    Microsoft::Diagnostics::Utils::Os::GetAsyncResultsOrTimeout<winrt::Windows::Foundation::IInspectable>(
      &hToken,
      v30,
      v6,
      3);
    if ( v31 )
    {
      v7 = v30;
      LOBYTE(v7) = v31 != v30;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v31 + 32LL))(v31, v7);
      v31 = 0;
    }
    v24 = 0;
    if ( hToken )
    {
      LODWORD(v28) = 0;
      v29 = 0;
      v8 = (**(__int64 (__fastcall ***)(HANDLE, __int64 *, wchar_t **))hToken)(
             hToken,
             winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>,
             &v24);
      winrt::check_hresult(&v26, v8, &v28);
    }
    String = winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(
               &v24,
               &v26);
    winrt::hstring::operator std::wstring_view(String, &v28);
    std::wstring::_Assign<wchar_t>((char **)v3, v28, (char *)v29);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v26);
    winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v24);
    if ( hToken )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&hToken);
    winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint((winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint *)&v27);
    goto LABEL_24;
  }
  hToken = 0;
  v10 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
  RtlCaptureContext(v10);
  LOBYTE(v11) = 2;
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(&v28, 240000, v11, v10);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hToken,
    0);
  v12 = UMgrQueryUserToken(a2, &hToken);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      (const char *)(unsigned int)v12,
      v23);
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&v28);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    return v13;
  }
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&v28);
  if ( (char *)hToken - 1 > (char *)0xFFFFFFFFFFFFFFFDLL || !ImpersonateLoggedOnUser(hToken) )
  {
LABEL_23:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
LABEL_24:
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 2304) )
    {
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(char **)v3;
      v27 = (unsigned __int64)v3;
      v24 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
        v20,
        (unsigned int)&unk_1803E62C0,
        v21,
        v22,
        (__int64)&v24,
        (__int64)&v27);
    }
    return 0;
  }
  BYTE1(v26) = 1;
  v24 = 0;
  GamerAccountXuidForImpersonatedUser = XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(&v24);
  v16 = GamerAccountXuidForImpersonatedUser;
  if ( GamerAccountXuidForImpersonatedUser == -2147024894 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v24);
    if ( !RevertToSelf() )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
        v17);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    return 2147942402LL;
  }
  if ( GamerAccountXuidForImpersonatedUser >= 0 )
  {
    std::wstring::assign(v3, v24);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v24);
    if ( !RevertToSelf() )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x2D8,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
        v19);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E0,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
    (const char *)(unsigned int)GamerAccountXuidForImpersonatedUser,
    v23);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v24);
  if ( !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x2D8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      v18);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  return v16;
}

```

## disassembly

```asm
0x1800e7ae8  mov     [rsp+arg_0], rbx
0x1800e7aed  mov     [rsp+arg_18], rsi
0x1800e7af2  push    rdi
0x1800e7af3  sub     rsp, 0C0h
0x1800e7afa  mov     rax, cs:__security_cookie
0x1800e7b01  xor     rax, rsp
0x1800e7b04  mov     [rsp+0C8h+var_18], rax
0x1800e7b0c  mov     rdi, r8
0x1800e7b0f  mov     rsi, rdx
0x1800e7b12  mov     qword ptr [r8+10h], 0
0x1800e7b1a  cmp     qword ptr [r8+18h], 7
0x1800e7b1f  jbe     short loc_1800E7B26
0x1800e7b21  mov     rcx, [r8]
0x1800e7b24  jmp     short loc_1800E7B29
0x1800e7b26  mov     rcx, rdi
0x1800e7b29  xor     eax, eax
0x1800e7b2b  mov     [rcx], ax
0x1800e7b2e  call    cs:__imp_XblaIsConsole
0x1800e7b34  test    eax, eax
0x1800e7b36  jz      loc_1800E7C71
0x1800e7b3c  mov     rdx, rsi
0x1800e7b3f  lea     rcx, [rsp+0C8h+var_80]; unsigned __int64
0x1800e7b44  call    ?GetUserForContext@UserManager@Internal@System@Windows@winrt@@SA@_K@Z; winrt::Windows::System::Internal::UserManager::GetUserForContext(unsigned __int64)
0x1800e7b49  nop
0x1800e7b4a  lea     rax, off_18037D8D0
0x1800e7b51  mov     [rsp+0C8h+var_58], rax
0x1800e7b56  lea     rax, [rsp+0C8h+var_80]
0x1800e7b5b  mov     [rsp+0C8h+var_50], rax
0x1800e7b60  lea     rax, [rsp+0C8h+var_58]
0x1800e7b65  mov     [rsp+0C8h+var_20], rax
0x1800e7b6d  mov     r9d, 3
0x1800e7b73  lea     rdx, [rsp+0C8h+var_58]
0x1800e7b78  lea     rcx, [rsp+0C8h+hToken]
0x1800e7b7d  call    ??$GetAsyncResultsOrTimeout@UIInspectable@Foundation@Windows@winrt@@@Os@Utils@Diagnostics@Microsoft@@SA?AUIInspectable@Foundation@Windows@winrt@@AEBV?$function@$$A6A?AU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@XZ@std@@KVAsyncOperationBucket@EnumDetails@123@KK@Z; Microsoft::Diagnostics::Utils::Os::GetAsyncResultsOrTimeout<winrt::Windows::Foundation::IInspectable>(std::function<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::IInspectable> (void)> const &,ulong,Microsoft::Diagnostics::Utils::EnumDetails::AsyncOperationBucket,ulong,ulong)
0x1800e7b82  nop
0x1800e7b83  mov     rcx, [rsp+0C8h+var_20]
0x1800e7b8b  test    rcx, rcx
0x1800e7b8e  jz      short loc_1800E7BB3
0x1800e7b90  mov     rax, [rcx]
0x1800e7b93  lea     rdx, [rsp+0C8h+var_58]
0x1800e7b98  cmp     rcx, rdx
0x1800e7b9b  setnz   dl
0x1800e7b9e  mov     rax, [rax+20h]
0x1800e7ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7ba7  mov     [rsp+0C8h+var_20], 0
0x1800e7bb3  mov     rcx, [rsp+0C8h+hToken]
0x1800e7bb8  mov     [rsp+0C8h+var_98], 0
0x1800e7bc1  test    rcx, rcx
0x1800e7bc4  jz      short loc_1800E7C09
0x1800e7bc6  mov     dword ptr [rsp+0C8h+var_78], 0
0x1800e7bce  xorps   xmm0, xmm0
0x1800e7bd1  movdqu  [rsp+0C8h+var_70], xmm0
0x1800e7bd7  mov     rax, [rcx]
0x1800e7bda  lea     r8, [rsp+0C8h+var_98]
0x1800e7bdf  lea     rdx, ??$guid_v@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValue>
0x1800e7be6  mov     rax, [rax]
0x1800e7be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7bee  lea     r8, [rsp+0C8h+var_78]
0x1800e7bf3  mov     edx, eax
0x1800e7bf5  lea     rcx, [rsp+0C8h+var_88]
0x1800e7bfa  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800e7bff  mov     rax, [rsp+0C8h+var_98]
0x1800e7c04  mov     [rsp+0C8h+var_98], rax
0x1800e7c09  lea     rdx, [rsp+0C8h+var_88]
0x1800e7c0e  lea     rcx, [rsp+0C8h+var_98]
0x1800e7c13  call    ?GetString@?$consume_Windows_Foundation_IPropertyValue@UIPropertyValue@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IPropertyValue<winrt::Windows::Foundation::IPropertyValue>::GetString(void)
0x1800e7c18  nop
0x1800e7c19  lea     rdx, [rsp+0C8h+var_78]
0x1800e7c1e  mov     rcx, rax
0x1800e7c21  call    ??Bhstring@winrt@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; winrt::hstring::operator std::wstring_view(void)
0x1800e7c26  mov     r8, qword ptr [rsp+0C8h+var_70]
0x1800e7c2b  mov     rdx, [rsp+0C8h+var_78]
0x1800e7c30  mov     rcx, rdi
0x1800e7c33  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800e7c38  nop
0x1800e7c39  lea     rcx, [rsp+0C8h+var_88]
0x1800e7c3e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800e7c43  nop
0x1800e7c44  lea     rcx, [rsp+0C8h+var_98]; this
0x1800e7c49  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800e7c4e  nop
0x1800e7c4f  cmp     [rsp+0C8h+hToken], 0
0x1800e7c55  jz      short loc_1800E7C62
0x1800e7c57  lea     rcx, [rsp+0C8h+hToken]
0x1800e7c5c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800e7c61  nop
0x1800e7c62  lea     rcx, [rsp+0C8h+var_80]; this
0x1800e7c67  call    ??1IGeocoordinateWithPoint@Geolocation@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Geolocation::IGeocoordinateWithPoint::~IGeocoordinateWithPoint(void)
0x1800e7c6c  jmp     loc_1800E7E18
0x1800e7c71  mov     [rsp+0C8h+hToken], 0
0x1800e7c7a  mov     ecx, cs:_tls_index
0x1800e7c80  mov     rax, gs:58h
0x1800e7c89  mov     edx, 40h ; '@'
0x1800e7c8e  mov     rbx, [rax+rcx*8]
0x1800e7c92  add     rbx, rdx
0x1800e7c95  mov     rcx, rbx; ContextRecord
0x1800e7c98  call    cs:__imp_RtlCaptureContext
0x1800e7c9e  mov     r9, rbx
0x1800e7ca1  mov     r8b, 2
0x1800e7ca4  mov     edx, 3A980h
0x1800e7ca9  lea     rcx, [rsp+0C8h+var_78]
0x1800e7cae  call    ??0ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@KVExternalHangBucket@EnumDetails@23@AEBU_CONTEXT@@@Z; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(ulong,Microsoft::Diagnostics::EnumDetails::ExternalHangBucket,_CONTEXT const &)
0x1800e7cb3  xor     edx, edx
0x1800e7cb5  lea     rcx, [rsp+0C8h+hToken]
0x1800e7cba  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800e7cbf  lea     rdx, [rsp+0C8h+hToken]
0x1800e7cc4  mov     rcx, rsi
0x1800e7cc7  call    cs:__imp_UMgrQueryUserToken
0x1800e7ccd  mov     ebx, eax
0x1800e7ccf  test    eax, eax
0x1800e7cd1  jns     short loc_1800E7D0B
0x1800e7cd3  mov     rcx, [rsp+0C8h]; this
0x1800e7cdb  mov     r9d, eax; char *
0x1800e7cde  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7ce5  mov     edx, 2CDh; void *
0x1800e7cea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7cef  lea     rcx, [rsp+0C8h+var_78]; this
0x1800e7cf4  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x1800e7cf9  nop
0x1800e7cfa  lea     rcx, [rsp+0C8h+hToken]
0x1800e7cff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7d04  mov     eax, ebx
0x1800e7d06  jmp     loc_1800E7E74
0x1800e7d0b  lea     rcx, [rsp+0C8h+var_78]; this
0x1800e7d10  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x1800e7d15  mov     rcx, [rsp+0C8h+hToken]; hToken
0x1800e7d1a  lea     rax, [rcx-1]
0x1800e7d1e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e7d22  ja      loc_1800E7E0E
0x1800e7d28  call    cs:__imp_ImpersonateLoggedOnUser
0x1800e7d2e  test    eax, eax
0x1800e7d30  jz      loc_1800E7E0E
0x1800e7d36  mov     byte ptr [rsp+0C8h+var_88+1], 1
0x1800e7d3b  mov     [rsp+0C8h+var_98], 0
0x1800e7d44  lea     rcx, [rsp+0C8h+var_98]; wchar_t **
0x1800e7d49  call    ?GetGamerAccountXuidForImpersonatedUser@XblAuthConfig@@SAJPEAPEA_W@Z; XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(wchar_t * *)
0x1800e7d4e  mov     ebx, eax
0x1800e7d50  cmp     eax, 80070002h
0x1800e7d55  jnz     short loc_1800E7D8C
0x1800e7d57  lea     rcx, [rsp+0C8h+var_98]
0x1800e7d5c  call    ??1?$unique_storage@U?$resource_policy@PEA_W$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800e7d61  nop
0x1800e7d62  call    cs:__imp_RevertToSelf
0x1800e7d68  mov     rcx, [rsp+0C8h]; this
0x1800e7d70  test    eax, eax
0x1800e7d72  jz      loc_1800E7E99
0x1800e7d78  lea     rcx, [rsp+0C8h+hToken]
0x1800e7d7d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7d82  mov     eax, 80070002h
0x1800e7d87  jmp     loc_1800E7E74
0x1800e7d8c  test    ebx, ebx
0x1800e7d8e  jns     short loc_1800E7DDF
0x1800e7d90  mov     rcx, [rsp+0C8h]; this
0x1800e7d98  mov     r9d, ebx; char *
0x1800e7d9b  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7da2  mov     edx, 2E0h; void *
0x1800e7da7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7dac  nop
0x1800e7dad  lea     rcx, [rsp+0C8h+var_98]
0x1800e7db2  call    ??1?$unique_storage@U?$resource_policy@PEA_W$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800e7db7  nop
0x1800e7db8  call    cs:__imp_RevertToSelf
0x1800e7dbe  mov     rcx, [rsp+0C8h]; this
0x1800e7dc6  test    eax, eax
0x1800e7dc8  jz      loc_1800E7EAB
0x1800e7dce  lea     rcx, [rsp+0C8h+hToken]
0x1800e7dd3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7dd8  mov     eax, ebx
0x1800e7dda  jmp     loc_1800E7E74
0x1800e7ddf  mov     rdx, [rsp+0C8h+var_98]
0x1800e7de4  mov     rcx, rdi
0x1800e7de7  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800e7dec  nop
0x1800e7ded  lea     rcx, [rsp+0C8h+var_98]
0x1800e7df2  call    ??1?$unique_storage@U?$resource_policy@PEA_W$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1800e7df7  nop
0x1800e7df8  call    cs:__imp_RevertToSelf
0x1800e7dfe  mov     rcx, [rsp+0C8h]; this
0x1800e7e06  test    eax, eax
0x1800e7e08  jz      loc_1800E7EBD
0x1800e7e0e  lea     rcx, [rsp+0C8h+hToken]
0x1800e7e13  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e7e18  mov     eax, cs:dword_1804543B0
0x1800e7e1e  cmp     eax, 4
0x1800e7e21  jbe     short loc_1800E7E6C
0x1800e7e23  mov     edx, 900h
0x1800e7e28  lea     rcx, dword_1804543B0
0x1800e7e2f  call    _tlgKeywordOn
0x1800e7e34  test    al, al
0x1800e7e36  jz      short loc_1800E7E6C
0x1800e7e38  cmp     qword ptr [rdi+18h], 7
0x1800e7e3d  jbe     short loc_1800E7E42
0x1800e7e3f  mov     rdi, [rdi]
0x1800e7e42  mov     [rsp+0C8h+var_80], rdi
0x1800e7e47  mov     [rsp+0C8h+var_98], rsi
0x1800e7e4c  lea     rax, [rsp+0C8h+var_80]
0x1800e7e51  mov     [rsp+0C8h+var_A0], rax
0x1800e7e56  lea     rax, [rsp+0C8h+var_98]
0x1800e7e5b  mov     [rsp+0C8h+var_A8], rax
0x1800e7e60  lea     rdx, unk_1803E62C0
0x1800e7e67  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &)
0x1800e7e6c  xor     eax, eax
0x1800e7e6e  jmp     short loc_1800E7E74
0x1800e7e70  mov     eax, [rsp+0C8h+var_88]
0x1800e7e74  mov     rcx, [rsp+0C8h+var_18]
0x1800e7e7c  xor     rcx, rsp; StackCookie
0x1800e7e7f  call    __security_check_cookie
0x1800e7e84  lea     r11, [rsp+0C8h+var_8]
0x1800e7e8c  mov     rbx, [r11+10h]
0x1800e7e90  mov     rsi, [r11+28h]
0x1800e7e94  mov     rsp, r11
0x1800e7e97  pop     rdi
0x1800e7e98  retn
0x1800e7e99  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7ea0  mov     edx, 2D8h; void *
0x1800e7ea5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e7eab  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7eb2  mov     edx, 2D8h; void *
0x1800e7eb7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800e7ebd  lea     r8, aOnecoreBaseTel_119; "onecore\\base\\telemetry\\utc\\service"...
0x1800e7ec4  mov     edx, 2D8h; void *
0x1800e7ec9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
