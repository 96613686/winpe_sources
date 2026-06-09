# shared::OneCoreAccountProvider::GetDeviceIdAndTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180009c6c`
- end: `0x18000a958`
- name: `?GetDeviceIdAndTicket@OneCoreAccountProvider@shared@@AEAA?AV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `3308`
- prototype: ``
- caller_count: `2`
- callee_count: `36`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d7478`
- `0x18020d008`

## callees

- `0x180009b48`
- `0x180009b94`
- `0x180009c6c`
- `0x18000acdc`
- `0x18000b7b0`
- `0x18000d02c`
- `0x18000d070`
- `0x18000d350`
- `0x180010fb4`
- `0x180011058`
- `0x1800117f8`
- `0x18001ce80`
- `0x18003eb80`
- `0x1800624cc`
- `0x180094c70`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x18009dd04`
- `0x18009de78`
- `0x18009df5c`
- `0x18009dfc0`
- `0x18009e080`
- `0x18009f2dc`
- `0x1800d9b80`
- `0x18010741c`
- `0x18011d8c4`
- `0x180143248`
- `0x1801942bc`
- `0x180199618`
- `0x1801f6fb0`
- `0x1801fc5e8`
- `0x1801fcb36`
- `0x1801fcb4e`
- `0x1801fcb72`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a541`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a541`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009dfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a2a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a641`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a6ad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009dfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a2a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a641`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a6ad`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a89e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a8d8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a89e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a8d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a035`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a07d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a035`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a07d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009f29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009f29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a4b2`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009d9f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009d9f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180009cf0`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180009cf0`

## string_xrefs

- `0x180009cc0`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x180009d6f`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x18000a56a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=38
_OWORD *__fastcall shared::OneCoreAccountProvider::GetDeviceIdAndTicket(__int64 a1, _OWORD *a2, const WCHAR *a3)
{
  HRESULT StringReference; // eax
  __int64 v6; // rbx
  int v7; // ebx
  int v8; // eax
  HRESULT v9; // eax
  __int64 v10; // rbx
  int ActivationFactory; // eax
  __int64 v12; // rdi
  __int64 v13; // r14
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // r9
  __int64 v16; // rsi
  unsigned __int64 v17; // r14
  __int64 size_of; // rax
  char *v19; // rdi
  size_t v20; // rbx
  __int128 *p_hstringHeader; // rbx
  __int128 *i; // r9
  PCWSTR v23; // rax
  PCWSTR v24; // r14
  __int64 v25; // rax
  void *v26; // rdi
  _BYTE *v27; // rbx
  _WORD *j; // r9
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  __int64 (__fastcall *v37)(__int64, _QWORD, __int64 *); // rdi
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, HSTRING *); // rbx
  int v42; // eax
  PCWSTR StringRawBuffer; // r12
  unsigned __int64 v44; // rbx
  const WCHAR *v45; // rdx
  unsigned __int64 v46; // r9
  __int64 v47; // rbx
  int v48; // eax
  unsigned __int64 v49; // rdi
  __int64 (__fastcall *v50)(unsigned __int64, __int64, __int64 *); // rbx
  int v51; // eax
  _OWORD *v52; // rax
  _OWORD *v53; // r8
  const char *v54; // rcx
  __int64 v55; // rdx
  int v56; // ebx
  const struct std::nothrow_t *v57; // rdx
  void *v58; // rcx
  __int64 v59; // rbx
  __int64 (__fastcall *v60)(__int64, HSTRING *); // rdi
  int v61; // eax
  __int64 v62; // rdi
  __int64 (__fastcall *v63)(__int64, __int64 *); // rbx
  int v64; // eax
  __int64 v65; // rbx
  int v66; // ecx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rax
  __int64 v83; // rax
  size_t v84; // rbx
  char v85; // bl
  void *v86[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v87; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v88; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v89; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v90; // [rsp+58h] [rbp-A8h] BYREF
  int v91; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v92; // [rsp+68h] [rbp-98h] BYREF
  __int64 v93; // [rsp+70h] [rbp-90h] BYREF
  __int64 v94; // [rsp+78h] [rbp-88h] BYREF
  __int64 v95; // [rsp+80h] [rbp-80h] BYREF
  __int64 v96; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v97[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v98[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 hstringHeader; // [rsp+C0h] [rbp-40h] BYREF
  __m128i hstringHeader_16; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD pExceptionObject[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v102[128]; // [rsp+120h] [rbp+20h] BYREF
  void **v103; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v104[264]; // [rsp+1A8h] [rbp+A8h] BYREF
  _DWORD *v105; // [rsp+2B0h] [rbp+1B0h]
  _DWORD *v106; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v107[24]; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v108; // [rsp+2D8h] [rbp+1D8h]

  v86[0] = a2;
  v88 = 0;
  hstringHeader_16.m128i_i64[1] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
                      0x41u,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16.m128i_i64[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v6 = hstringHeader_16.m128i_i64[1];
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v88);
  v88 = 0;
  v7 = RoActivateInstance(v6, &v87);
  if ( v7 >= 0 )
  {
    if ( memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      goto LABEL_13;
    v88 = v87;
  }
  while ( 1 )
  {
    if ( v7 < 0 )
    {
      *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
      *(_DWORD *)&v98[8] = 1892;
      v72 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v7);
      cdp::CdpThrow<cdp::hresult_exception>(v98, v72);
    }
    *(_OWORD *)v98 = xmmword_180398820;
    v8 = (*(__int64 (__fastcall **)(unsigned __int64, _BYTE *))(*(_QWORD *)v88 + 72LL))(v88, v98);
    if ( v8 < 0 )
    {
      *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
      *(_DWORD *)&v98[8] = 1894;
      v73 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v8);
      cdp::CdpThrow<cdp::hresult_exception>(v98, v73);
    }
    v97[0] = 0;
    hstringHeader_16.m128i_i64[1] = 0;
    v9 = WindowsCreateStringReference(
           L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
           0x45u,
           (HSTRING_HEADER *)&hstringHeader,
           (HSTRING *)&hstringHeader_16.m128i_i64[1]);
    if ( v9 < 0 )
    {
      RaiseException(v9, 1u, 0, 0);
      __debugbreak();
    }
    v10 = hstringHeader_16.m128i_i64[1];
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v97);
    ActivationFactory = RoGetActivationFactory(v10, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, v97);
    if ( ActivationFactory < 0 )
    {
      *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
      *(_DWORD *)&v98[8] = 1898;
      v74 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)ActivationFactory);
      cdp::CdpThrow<cdp::hresult_exception>(v98, v74);
    }
    v96 = 0;
    v12 = v97[0];
    v13 = *(_QWORD *)v97[0];
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
    hstringHeader_16.m128i_i64[1] = 0;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( aMbiSsl[v15] );
    if ( v15 <= 0xFFFFFFFF && (int)v15 + 1 >= (unsigned int)v15 )
      break;
    RaiseException(0x80070216, 1u, 0, 0);
LABEL_13:
    v7 = (**(__int64 (__fastcall ***)(unsigned __int64, GUID *, unsigned __int64 *))v87)(
           v87,
           &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
           &v88);
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v87 + 16LL))(v87);
  }
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&hstringHeader,
    L"MBI_SSL",
    v15 + 1,
    v15);
  if ( *((_QWORD *)a3 + 3) > 7u )
    v45 = *(const WCHAR **)a3;
  else
    v45 = a3;
  *(_QWORD *)&v98[24] = 0;
  v46 = -1;
  do
    ++v46;
  while ( v45[v46] );
  if ( v46 > 0xFFFFFFFF || (int)v46 + 1 < (unsigned int)v46 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v47 = hstringHeader_16.m128i_i64[1];
  Microsoft::WRL::Wrappers::HStringReference::CreateReference((HSTRING_HEADER *)v98, v45, v46 + 1, v46);
  v48 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(v13 + 48))(v12, *(_QWORD *)&v98[24], v47, &v96);
  if ( v48 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1902;
    v75 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v48);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v75);
  }
  v95 = 0;
  v49 = v88;
  v50 = *(__int64 (__fastcall **)(unsigned __int64, __int64, __int64 *))(*(_QWORD *)v88 + 56LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v95);
  v51 = v50(v49, v96, &v95);
  if ( v51 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1905;
    v76 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v51);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v76);
  }
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &v103,
    "GetDeviceIdAndTicketActivity",
    (unsigned int)v51);
  v103 = &OneCoreAccountTelemetryProvider::GetDeviceIdAndTicketActivity::`vftable';
  OneCoreAccountTelemetryProvider::GetDeviceIdAndTicketActivity::StartActivity((OneCoreAccountTelemetryProvider::GetDeviceIdAndTicketActivity *)&v103);
  v94 = 0;
  v86[0] = (void *)30000;
  hstringHeader = 0;
  hstringHeader_16 = 0;
  v52 = (_OWORD *)std::allocator<char>::allocate(&hstringHeader, 384);
  v53 = v52;
  *(_QWORD *)&hstringHeader = v52;
  hstringHeader_16 = _mm_load_si128((const __m128i *)&_xmm);
  v54 = "class std::tuple<class std::basic_string<char,struct std::char_traits<char>,class std::allocator<char> >,class s"
        "td::basic_string<char,struct std::char_traits<char>,class std::allocator<char> > > __cdecl shared::OneCoreAccoun"
        "tProvider::GetDeviceIdAndTicket(const class std::basic_string<unsigned short,struct std::char_traits<unsigned sh"
        "ort>,class std::allocator<unsigned short> > &)";
  v55 = 2;
  do
  {
    *v52 = *(_OWORD *)v54;
    v52[1] = *((_OWORD *)v54 + 1);
    v52[2] = *((_OWORD *)v54 + 2);
    v52[3] = *((_OWORD *)v54 + 3);
    v52[4] = *((_OWORD *)v54 + 4);
    v52[5] = *((_OWORD *)v54 + 5);
    v52[6] = *((_OWORD *)v54 + 6);
    v52[7] = *((_OWORD *)v54 + 7);
    v52 += 8;
    v54 += 128;
    --v55;
  }
  while ( v55 );
  *v52 = *(_OWORD *)v54;
  v52[1] = *((_OWORD *)v54 + 1);
  v52[2] = *((_OWORD *)v54 + 2);
  v52[3] = *((_OWORD *)v54 + 3);
  v52[4] = *((_OWORD *)v54 + 4);
  v52[5] = *((_OWORD *)v54 + 5);
  v52[6] = *((_OWORD *)v54 + 6);
  *(_OWORD *)((char *)v52 + 110) = *(_OWORD *)(v54 + 110);
  *((_BYTE *)v53 + 382) = 0;
  v56 = shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Internal::Security::WebAuthentication::IUserHostIdentity>(
          v95,
          &hstringHeader,
          v86,
          &v94);
  if ( hstringHeader_16.m128i_i64[1] > 0xFuLL )
  {
    v57 = (const struct std::nothrow_t *)(hstringHeader_16.m128i_i64[1] + 1);
    v87 = hstringHeader_16.m128i_i64[1] + 1;
    v58 = (void *)hstringHeader;
    v86[0] = (void *)hstringHeader;
    if ( (unsigned __int64)(hstringHeader_16.m128i_i64[1] + 1) >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(v86, &v87);
      v57 = (const struct std::nothrow_t *)v87;
      v58 = v86[0];
    }
    operator delete(v58, v57);
  }
  if ( v56 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1912;
    v77 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v56);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v77);
  }
  v59 = v94;
  if ( !v94 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1913;
    v71 = cdp::MakeException<cdp::HResultException<-2147418113>,>(
            pExceptionObject,
            v98,
            "Unexpected null result from async operation");
    cdp::CdpThrow<cdp::HResultException<-2147418113>>(v98, v71);
  }
  v90 = 0;
  v60 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v94 + 56LL);
  WindowsDeleteString(0);
  v90 = 0;
  v61 = v60(v59, &v90);
  if ( v61 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1916;
    v78 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v61);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v78);
  }
  v86[0] = (void *)WindowsGetStringRawBuffer(v90, 0);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v87 = (unsigned __int64)a3;
  OneCoreAccountTelemetryProvider::GetDeviceIdAndTicketActivity::AuthenticateUserHost<unsigned short const *,unsigned short const *>(
    &v103,
    &v87,
    v86);
  v93 = 0;
  v62 = v94;
  v63 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v94 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v93);
  v64 = v63(v62, &v93);
  if ( v64 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1921;
    v79 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v64);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v79);
  }
  v65 = v93;
  if ( !v93 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1924;
    LODWORD(v87) = -2147024883;
    v86[0] = (void *)GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v66,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v87,
      (unsigned int)v98,
      (__int64)&v98[8],
      (__int64)v86);
    v67 = cdp::ExceptionStackFromSourceLocationInfo(&hstringHeader, v98);
    v70 = cdp::ErrorCodeToString(2147942413LL, v68, v69, v67);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942413LL, v70);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v89 = 0;
  v37 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v93 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
  v38 = v37(v65, 0, &v89);
  if ( v38 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1928;
    v80 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v38);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v80);
  }
  v91 = 0;
  v39 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v89 + 64LL))(v89, &v91, (unsigned int)v38);
  if ( v39 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1931;
    v81 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v39);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v81);
  }
  if ( v91 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1932;
    v82 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v91);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v82);
  }
  v92 = 0;
  v40 = v89;
  v41 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v89 + 48LL);
  WindowsDeleteString(0);
  v92 = 0;
  v42 = v41(v40, &v92);
  if ( v42 < 0 )
  {
    *(_QWORD *)v98 = ".\\onecoreaccountprovider.cpp";
    *(_DWORD *)&v98[8] = 1935;
    v83 = cdp::MakeException<cdp::hresult_exception>(pExceptionObject, v98, (unsigned int)v42);
    cdp::CdpThrow<cdp::hresult_exception>(v98, v83);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v90, 0);
  hstringHeader = 0;
  hstringHeader_16 = 0;
  v44 = -1;
  do
    ++v44;
  while ( StringRawBuffer[v44] );
  v16 = 0x7FFFFFFFFFFFFFFELL;
  if ( v44 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v44 <= 7 )
  {
    hstringHeader_16.m128i_i64[0] = v44;
    hstringHeader_16.m128i_i64[1] = 7;
    v84 = 2 * v44;
    memcpy_0(&hstringHeader, StringRawBuffer, v84);
    *(_WORD *)((char *)&hstringHeader + v84) = 0;
  }
  else
  {
    v17 = v44 | 7;
    if ( (v44 | 7) > 0x7FFFFFFFFFFFFFFELL )
    {
      v17 = 0x7FFFFFFFFFFFFFFELL;
    }
    else if ( v17 < 0xA )
    {
      v17 = 10;
    }
    size_of = std::_Get_size_of_n<2>(v17 + 1);
    v19 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    *(_QWORD *)&hstringHeader = v19;
    hstringHeader_16.m128i_i64[0] = v44;
    hstringHeader_16.m128i_i64[1] = v17;
    v20 = 2 * v44;
    memcpy_0(v19, StringRawBuffer, v20);
    *(_WORD *)&v19[v20] = 0;
  }
  p_hstringHeader = &hstringHeader;
  if ( hstringHeader_16.m128i_i64[1] > 7uLL )
    p_hstringHeader = (__int128 *)hstringHeader;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v102);
  for ( i = p_hstringHeader; *(_WORD *)i; i = (__int128 *)((char *)i + 2) )
    ;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v102,
    pExceptionObject,
    p_hstringHeader,
    i);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v102);
  if ( hstringHeader_16.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(hstringHeader, 2 * hstringHeader_16.m128i_i64[1] + 2);
  hstringHeader_16 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(hstringHeader) = 0;
  v23 = WindowsGetStringRawBuffer(v92, 0);
  v24 = v23;
  memset(v98, 0, sizeof(v98));
  do
    ++v14;
  while ( v23[v14] );
  if ( v14 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v14 <= 7 )
  {
    *(_QWORD *)&v98[16] = v14;
    *(_QWORD *)&v98[24] = 7;
    memcpy_0(v98, v23, 2 * v14);
    *(_WORD *)&v98[2 * v14] = 0;
  }
  else
  {
    if ( (v14 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v16 = v14 | 7;
      if ( (v14 | 7) < 0xA )
        v16 = 10;
    }
    v25 = std::_Get_size_of_n<2>(v16 + 1);
    v26 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(v25);
    *(_QWORD *)v98 = v26;
    *(_QWORD *)&v98[16] = v14;
    *(_QWORD *)&v98[24] = v16;
    memcpy_0(v26, v24, 2 * v14);
    *((_WORD *)v26 + v14) = 0;
  }
  v27 = v98;
  if ( *(_QWORD *)&v98[24] > 7u )
    v27 = *(_BYTE **)v98;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v102);
  for ( j = v27; *j; ++j )
    ;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v102,
    &hstringHeader,
    v27,
    j);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v102);
  if ( *(_QWORD *)&v98[24] > 7u )
    std::_Deallocate<16>(*(_QWORD *)v98, 2LL * *(_QWORD *)&v98[24] + 2);
  *a2 = hstringHeader;
  a2[1] = hstringHeader_16;
  a2[2] = pExceptionObject[0];
  a2[3] = pExceptionObject[1];
  WindowsDeleteString(v92);
  v92 = 0;
  v29 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v93;
  if ( v93 )
  {
    v93 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  WindowsDeleteString(v90);
  v90 = 0;
  v31 = v94;
  if ( v94 )
  {
    v94 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  }
  v103 = &OneCoreAccountTelemetryProvider::GetDeviceIdAndTicketActivity::`vftable';
  if ( !v106 )
    goto LABEL_47;
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    &v103,
    v86);
  if ( v106 && *v106 == 1 )
  {
    v85 = 1;
  }
  else
  {
    v85 = 0;
    wil::details::shared_object<wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v106);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v86);
  if ( v85 )
  {
LABEL_47:
    if ( *v105 == 1 )
    {
      wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException();
       cdp::IHostBrokerObserver::`vcall'{8,{flat}}(&v103);
    }
  }
  if ( v108 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v107);
  wil::details::shared_object<wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v106);
  wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(v104);
  v32 = v95;
  if ( v95 )
  {
    v95 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v96;
  if ( v96 )
  {
    v96 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v97[0];
  if ( v97[0] )
  {
    v97[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  return a2;
}

```

## disassembly

```asm
0x180009c6c  mov     [rsp-8+arg_0], rbx
0x180009c71  push    rbp
0x180009c72  push    rsi
0x180009c73  push    rdi
0x180009c74  push    r12
0x180009c76  push    r13
0x180009c78  push    r14
0x180009c7a  push    r15
0x180009c7c  lea     rbp, [rsp-200h]
0x180009c84  sub     rsp, 300h
0x180009c8b  mov     rax, cs:__security_cookie
0x180009c92  xor     rax, rsp
0x180009c95  mov     [rbp+230h+var_40], rax
0x180009c9c  mov     rsi, r8
0x180009c9f  mov     r13, rdx
0x180009ca2  mov     [rsp+330h+var_300], rdx
0x180009ca7  xor     r12d, r12d
0x180009caa  mov     [rsp+330h+var_2E8], r12
0x180009caf  mov     [rbp+230h+string], r12
0x180009cb3  lea     r9, [rbp+230h+string]; string
0x180009cb7  lea     r8, [rbp+230h+hstringHeader]; hstringHeader
0x180009cbb  lea     edx, [r12+41h]; length
0x180009cc0  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x180009cc7  call    cs:__imp_WindowsCreateStringReference
0x180009ccd  test    eax, eax
0x180009ccf  js      loc_18000A635
0x180009cd5  mov     rbx, [rbp+230h+string]
0x180009cd9  lea     rcx, [rsp+330h+var_2E8]
0x180009cde  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180009ce3  mov     [rsp+330h+var_2E8], r12
0x180009ce8  lea     rdx, [rsp+330h+var_2F0]
0x180009ced  mov     rcx, rbx
0x180009cf0  call    cs:__imp_RoActivateInstance
0x180009cf6  mov     ebx, eax
0x180009cf8  test    eax, eax
0x180009cfa  js      short loc_180009D26
0x180009cfc  lea     r8d, [r12+10h]; Size
0x180009d01  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180009d08  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x180009d0f  call    memcmp_0
0x180009d14  test    eax, eax
0x180009d16  jnz     loc_180009E04
0x180009d1c  mov     rax, [rsp+330h+var_2F0]
0x180009d21  mov     [rsp+330h+var_2E8], rax
0x180009d26  lea     rdx, [rbp+230h+var_290]
0x180009d2a  test    ebx, ebx
0x180009d2c  js      loc_18000A648
0x180009d32  mov     rcx, [rsp+330h+var_2E8]
0x180009d37  movups  xmm0, cs:xmmword_180398820
0x180009d3e  movdqu  xmmword ptr [rbp+230h+var_290], xmm0
0x180009d43  mov     rax, [rcx]
0x180009d46  mov     rax, [rax+48h]
0x180009d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d4f  mov     r8d, eax
0x180009d52  test    eax, eax
0x180009d54  js      loc_18000A674
0x180009d5a  mov     [rbp+230h+var_2A0], r12
0x180009d5e  mov     [rbp+230h+string], r12
0x180009d62  lea     r9, [rbp+230h+string]; string
0x180009d66  lea     r8, [rbp+230h+hstringHeader]; hstringHeader
0x180009d6a  mov     edx, 45h ; 'E'; length
0x180009d6f  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x180009d76  call    cs:__imp_WindowsCreateStringReference
0x180009d7c  test    eax, eax
0x180009d7e  js      loc_18000A6A1
0x180009d84  mov     rbx, [rbp+230h+string]
0x180009d88  lea     rcx, [rbp+230h+var_2A0]
0x180009d8c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180009d91  lea     r8, [rbp+230h+var_2A0]
0x180009d95  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x180009d9c  mov     rcx, rbx
0x180009d9f  call    cs:__imp_RoGetActivationFactory
0x180009da5  mov     r8d, eax
0x180009da8  test    eax, eax
0x180009daa  js      loc_18000A6B4
0x180009db0  mov     [rbp+230h+var_2A8], r12
0x180009db4  mov     rdi, [rbp+230h+var_2A0]
0x180009db8  mov     r14, [rdi]
0x180009dbb  lea     rcx, [rbp+230h+var_2A8]
0x180009dbf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180009dc4  mov     [rbp+230h+string], r12
0x180009dc8  mov     rdx, cs:off_180355500; sourceString
0x180009dcf  or      r15, 0FFFFFFFFFFFFFFFFh
0x180009dd3  mov     r9, r15
0x180009dd6  inc     r9; unsigned int
0x180009dd9  cmp     [rdx+r9*2], r12w
0x180009dde  jnz     short loc_180009DD6
0x180009de0  mov     ebx, 0FFFFFFFFh
0x180009de5  cmp     r9, rbx
0x180009de8  jbe     loc_18000A614
0x180009dee  xor     r9d, r9d; lpArguments
0x180009df1  xor     r8d, r8d; nNumberOfArguments
0x180009df4  lea     edx, [r9+1]; dwExceptionFlags
0x180009df8  mov     ecx, 80070216h; dwExceptionCode
0x180009dfd  call    cs:__imp_RaiseException
0x180009e03  nop
0x180009e04  mov     rcx, [rsp+330h+var_2F0]
0x180009e09  mov     rax, [rcx]
0x180009e0c  lea     r8, [rsp+330h+var_2E8]
0x180009e11  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x180009e18  mov     rax, [rax]
0x180009e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e20  mov     ebx, eax
0x180009e22  mov     rcx, [rsp+330h+var_2F0]
0x180009e27  mov     rax, [rcx]
0x180009e2a  mov     rax, [rax+10h]
0x180009e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e33  jmp     loc_180009D26
0x180009e38  mov     rsi, 7FFFFFFFFFFFFFFEh
0x180009e42  cmp     rbx, rsi
0x180009e45  ja      loc_18000A897
0x180009e4b  mov     edi, 0Ah
0x180009e50  cmp     rbx, 7
0x180009e54  jbe     loc_18000A8A5
0x180009e5a  mov     r14, rbx
0x180009e5d  or      r14, 7
0x180009e61  cmp     r14, rsi
0x180009e64  ja      loc_18000A19A
0x180009e6a  cmp     r14, rdi
0x180009e6d  cmovb   r14, rdi
0x180009e71  lea     rcx, [r14+1]
0x180009e75  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x180009e7a  mov     rcx, rax
0x180009e7d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009e82  mov     rdi, rax
0x180009e85  mov     qword ptr [rbp+230h+hstringHeader.Reserved], rax
0x180009e89  mov     qword ptr [rbp+230h+hstringHeader.Reserved+10h], rbx
0x180009e8d  mov     [rbp+230h+string], r14
0x180009e91  add     rbx, rbx
0x180009e94  mov     r8, rbx; Size
0x180009e97  mov     rdx, r12; Src
0x180009e9a  mov     rcx, rax; void *
0x180009e9d  call    memcpy_0
0x180009ea2  xor     r12d, r12d
0x180009ea5  mov     [rdi+rbx], r12w
0x180009eaa  lea     edi, [r12+0Ah]
0x180009eaf  lea     rbx, [rbp+230h+hstringHeader]
0x180009eb3  cmp     [rbp+230h+string], 7
0x180009eb8  cmova   rbx, qword ptr [rbp+230h+hstringHeader.Reserved]
0x180009ebd  lea     rcx, [rbp+230h+var_210]
0x180009ec1  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180009ec6  nop
0x180009ec7  mov     r9, rbx
0x180009eca  cmp     [rbx], r12w
0x180009ece  jz      short loc_180009EDA
0x180009ed0  add     r9, 2
0x180009ed4  cmp     [r9], r12w
0x180009ed8  jnz     short loc_180009ED0
0x180009eda  mov     r8, rbx
0x180009edd  lea     rdx, [rbp+230h+pExceptionObject]
0x180009ee1  lea     rcx, [rbp+230h+var_210]
0x180009ee5  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x180009eea  nop
0x180009eeb  lea     rcx, [rbp+230h+var_210]
0x180009eef  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180009ef4  nop
0x180009ef5  mov     rdx, [rbp+230h+string]
0x180009ef9  cmp     rdx, 7
0x180009efd  jbe     short loc_180009F10
0x180009eff  lea     rdx, ds:2[rdx*2]
0x180009f07  mov     rcx, qword ptr [rbp+230h+hstringHeader.Reserved]
0x180009f0b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009f10  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180009f18  movdqu  xmmword ptr [rbp+230h+hstringHeader.Reserved+10h], xmm0
0x180009f1d  mov     word ptr [rbp+230h+hstringHeader.Reserved], r12w
0x180009f22  xor     edx, edx; length
0x180009f24  mov     rcx, [rsp+330h+var_2C8]; string
0x180009f29  call    cs:__imp_WindowsGetStringRawBuffer
0x180009f2f  mov     r14, rax
0x180009f32  xorps   xmm0, xmm0
0x180009f35  movups  xmmword ptr [rbp+230h+var_290], xmm0
0x180009f39  xorps   xmm1, xmm1
0x180009f3c  movdqu  xmmword ptr [rbp+230h+var_290+10h], xmm1
0x180009f41  inc     r15
0x180009f44  cmp     [rax+r15*2], r12w
0x180009f49  jnz     short loc_180009F41
0x180009f4b  cmp     r15, rsi
0x180009f4e  ja      loc_18000A8D1
0x180009f54  cmp     r15, 7
0x180009f58  jbe     loc_18000A8DF
0x180009f5e  mov     rax, r15
0x180009f61  or      rax, 7
0x180009f65  cmp     rax, rsi
0x180009f68  ja      short loc_180009F74
0x180009f6a  mov     rsi, rax
0x180009f6d  cmp     rax, rdi
0x180009f70  cmovb   rsi, rdi
0x180009f74  lea     rcx, [rsi+1]
0x180009f78  call    ??$_Get_size_of_n@$01@std@@YA_K_K@Z; std::_Get_size_of_n<2>(unsigned __int64)
0x180009f7d  mov     rcx, rax
0x180009f80  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009f85  mov     rdi, rax
0x180009f88  mov     qword ptr [rbp+230h+var_290], rax
0x180009f8c  mov     qword ptr [rbp+230h+var_290+10h], r15
0x180009f90  mov     qword ptr [rbp+230h+var_290+18h], rsi
0x180009f94  lea     rbx, [r15+r15]
0x180009f98  mov     r8, rbx; Size
0x180009f9b  mov     rdx, r14; Src
0x180009f9e  mov     rcx, rax; void *
0x180009fa1  call    memcpy_0
0x180009fa6  mov     [rbx+rdi], r12w
0x180009fab  lea     rbx, [rbp+230h+var_290]
0x180009faf  cmp     qword ptr [rbp+230h+var_290+18h], 7
0x180009fb4  cmova   rbx, qword ptr [rbp+230h+var_290]
0x180009fb9  lea     rcx, [rbp+230h+var_210]
0x180009fbd  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180009fc2  nop
0x180009fc3  mov     r9, rbx
0x180009fc6  cmp     [rbx], r12w
0x180009fca  jz      short loc_180009FD6
0x180009fcc  add     r9, 2
0x180009fd0  cmp     [r9], r12w
0x180009fd4  jnz     short loc_180009FCC
0x180009fd6  mov     r8, rbx
0x180009fd9  lea     rdx, [rbp+230h+hstringHeader]
0x180009fdd  lea     rcx, [rbp+230h+var_210]
0x180009fe1  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x180009fe6  nop
0x180009fe7  lea     rcx, [rbp+230h+var_210]
0x180009feb  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180009ff0  nop
0x180009ff1  mov     rdx, qword ptr [rbp+230h+var_290+18h]
0x180009ff5  cmp     rdx, 7
0x180009ff9  jbe     short loc_18000A00C
0x180009ffb  lea     rdx, ds:2[rdx*2]
0x18000a003  mov     rcx, qword ptr [rbp+230h+var_290]
0x18000a007  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a00c  movups  xmm0, xmmword ptr [rbp+230h+hstringHeader.Reserved]
0x18000a010  movups  xmmword ptr [r13+0], xmm0
0x18000a015  movups  xmm1, xmmword ptr [rbp+230h+hstringHeader.Reserved+10h]
0x18000a019  movups  xmmword ptr [r13+10h], xmm1
0x18000a01e  movups  xmm0, [rbp+230h+pExceptionObject]
0x18000a022  movups  xmmword ptr [r13+20h], xmm0
0x18000a027  movups  xmm1, [rbp+230h+var_240]
0x18000a02b  movups  xmmword ptr [r13+30h], xmm1
0x18000a030  mov     rcx, [rsp+330h+var_2C8]; string
0x18000a035  call    cs:__imp_WindowsDeleteString
0x18000a03b  mov     [rsp+330h+var_2C8], r12
0x18000a040  mov     rcx, [rsp+330h+var_2E0]
0x18000a045  test    rcx, rcx
0x18000a048  jz      short loc_18000A05C
0x18000a04a  mov     [rsp+330h+var_2E0], r12
0x18000a04f  mov     rax, [rcx]
0x18000a052  mov     rax, [rax+10h]
0x18000a056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a05b  nop
0x18000a05c  mov     rcx, [rsp+330h+var_2C0]
0x18000a061  test    rcx, rcx
0x18000a064  jz      short loc_18000A078
0x18000a066  mov     [rsp+330h+var_2C0], r12
0x18000a06b  mov     rax, [rcx]
0x18000a06e  mov     rax, [rax+10h]
0x18000a072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a077  nop
0x18000a078  mov     rcx, [rsp+330h+var_2D8]; string
0x18000a07d  call    cs:__imp_WindowsDeleteString
0x18000a083  mov     [rsp+330h+var_2D8], r12
0x18000a088  mov     rcx, [rsp+330h+var_2B8]
0x18000a08d  test    rcx, rcx
0x18000a090  jz      short loc_18000A0A4
0x18000a092  mov     [rsp+330h+var_2B8], r12
0x18000a097  mov     rax, [rcx]
0x18000a09a  mov     rax, [rax+10h]
0x18000a09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a3  nop
0x18000a0a4  lea     rax, ??_7GetDeviceIdAndTicketActivity@OneCoreAccountTelemetryProvider@@6B@; const OneCoreAccountTelemetryProvider::GetDeviceIdAndTicketActivity::`vftable'
0x18000a0ab  mov     [rbp+230h+var_190], rax
0x18000a0b2  cmp     [rbp+230h+var_78], r12
0x18000a0b9  jnz     loc_18000A909
0x18000a0bf  mov     rcx, [rbp+230h+var_80]
0x18000a0c6  cmp     dword ptr [rcx], 1
0x18000a0c9  jnz     short loc_18000A0DD
0x18000a0cb  call    ?SetUnhandledException@?$ActivityData@VOneCoreAccountTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAJXZ; wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException(void)
0x18000a0d0  lea     rcx, [rbp+230h+var_190]
0x18000a0d7  call    ??_9IHostBrokerObserver@cdp@@$B7AA; [thunk]: cdp::IHostBrokerObserver::`vcall'{8,{flat}}
0x18000a0dc  nop
0x18000a0dd  cmp     [rbp+230h+var_58], r12d
0x18000a0e4  jnz     loc_18000A946
0x18000a0ea  lea     rcx, [rbp+230h+var_78]
0x18000a0f1  call    ?reset@?$shared_object@V?$ActivityData@VOneCoreAccountTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18000a0f6  lea     rcx, [rbp+230h+var_188]
0x18000a0fd  call    ??1?$ActivityData@VOneCoreAccountTelemetryProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VOneCoreAccountTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<OneCoreAccountTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000a102  nop
0x18000a103  mov     rcx, [rbp+230h+var_2B0]
0x18000a107  test    rcx, rcx
0x18000a10a  jz      short loc_18000A11D
0x18000a10c  mov     [rbp+230h+var_2B0], r12
0x18000a110  mov     rax, [rcx]
0x18000a113  mov     rax, [rax+10h]
0x18000a117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a11c  nop
0x18000a11d  mov     rcx, [rbp+230h+var_2A8]
0x18000a121  test    rcx, rcx
0x18000a124  jz      short loc_18000A137
0x18000a126  mov     [rbp+230h+var_2A8], r12
0x18000a12a  mov     rax, [rcx]
0x18000a12d  mov     rax, [rax+10h]
0x18000a131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a136  nop
0x18000a137  mov     rcx, [rbp+230h+var_2A0]
  ... truncated ...
```
