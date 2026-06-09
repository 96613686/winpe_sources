# shared::OneCoreAccountProvider::GetTokenResultForAccount(CDPAccountType,Windows::Security::Credentials::IWebAccount *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,CDPStrongAuthenticationRequirement,HWND__ *)

- ea: `0x18009e1ec`
- end: `0x18009f1ce`
- name: `?GetTokenResultForAccount@OneCoreAccountProvider@shared@@AEAA?AV?$tuple@V?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@_N@std@@W4CDPAccountType@@PEAUIWebAccount@Credentials@Security@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@2W4CDPStrongAuthenticationRequirement@@PEAUHWND__@@@Z`
- size: `4066`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009d350`
- `0x180161bc8`
- `0x1801a99dc`

## callees

- `0x180009b48`
- `0x18000b724`
- `0x18000d098`
- `0x180010ee0`
- `0x18001ce80`
- `0x18001ee70`
- `0x180030190`
- `0x180040f6c`
- `0x18005ade0`
- `0x1800624cc`
- `0x18008dbc0`
- `0x180091258`
- `0x18009d1d4`
- `0x18009dcd8`
- `0x18009e1ec`
- `0x1800ac328`
- `0x1800b02f4`
- `0x1800b1074`
- `0x1800b1a38`
- `0x1800d9ff4`
- `0x1800eba84`
- `0x1800fa83c`
- `0x180107568`
- `0x18011d5d0`
- `0x18011d808`
- `0x18011d8c4`
- `0x18011d9a4`
- `0x18011db1c`
- `0x180185cf4`
- `0x1801f6fb0`
- `0x18020b0d0`
- `0x18020b9ac`
- `0x18020fb18`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009e2b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009e32e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009e2b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009e32e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009e29b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009e318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009e29b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009e318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e93b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e93b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e964`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ea1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ea30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ebb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ebca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ecc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ecd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ea1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ea30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ebb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ebca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ecc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ecd4`

## string_xrefs

- `0x18009e272`: `{"text":"GetTokenResultForAccount called with strong auth requirement as %s"}`
- `0x18009e9d2`: `class std::tuple<class Microsoft::WRL::ComPtr<struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>,bool> __cdecl shared::OneCoreAccountProvider::GetTokenResultForAccount(enum CDPAccountType,struct Windows::Security::Credentials::IWebAccount *,const class std::basic_string<unsigned short,struct std::char_traits<unsigned short>,class std::allocator<unsigned short> > &,const class std::basic_string<unsigned short,struct std::char_traits<unsigned short>,class std::allocator<u`
- `0x18009eb6b`: `class std::tuple<class Microsoft::WRL::ComPtr<struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>,bool> __cdecl shared::OneCoreAccountProvider::GetTokenResultForAccount(enum CDPAccountType,struct Windows::Security::Credentials::IWebAccount *,const class std::basic_string<unsigned short,struct std::char_traits<unsigned short>,class std::allocator<unsigned short> > &,const class std::basic_string<unsigned short,struct std::char_traits<unsigned short>,class std::allocator<u`
- `0x18009ec8e`: `{"text":"Attempt to get strong-auth token failed, retrying without strong auth."}`
- `0x18009e294`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x18009eab7`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x18009e311`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x18009e466`: `service::%s::%s`
- `0x18009e4d2`: `service::%s::%s`
- `0x18009f0dd`: `Account type is not supported by TokenBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
char *__fastcall shared::OneCoreAccountProvider::GetTokenResultForAccount(
        __int64 a1,
        char *a2,
        __int16 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        unsigned int a7,
        __int64 a8)
{
  unsigned int v9; // r12d
  HRESULT StringReference; // eax
  int v11; // eax
  __int64 v12; // rax
  HRESULT v13; // eax
  int v14; // eax
  __int64 v15; // rax
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // rax
  __int16 v20; // cx
  char v21; // r13
  char v22; // bl
  __int64 v23; // rax
  __m128i si128; // xmm6
  _QWORD *v25; // r8
  int v26; // eax
  __int64 v27; // rax
  const wchar_t *v28; // r9
  _QWORD *v29; // r8
  int v30; // eax
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *); // rdi
  __int64 v33; // rbx
  _WORD *v34; // r12
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64 *); // rbx
  int v39; // eax
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, __int64, __int64, char *); // rdi
  __int64 v42; // rbx
  int v43; // eax
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 (__fastcall *v46)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *); // rsi
  __int64 v47; // rdi
  _QWORD *v48; // rax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rdi
  __int64 (__fastcall *v52)(__int64, __int64 *); // rbx
  int v53; // eax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64, __int64, char *); // rsi
  _QWORD *v56; // rax
  __int64 v57; // rbx
  int v58; // eax
  __int64 v59; // rsi
  __int64 (__fastcall *v60)(__int64, __int64, __int64, char *); // rdi
  __int64 v61; // rbx
  int v62; // eax
  __int64 v63; // rsi
  __int64 (__fastcall *v64)(__int64, __int64, __int64, char *); // rdi
  __int64 v65; // rbx
  int v66; // eax
  __int64 v67; // rsi
  __int64 (__fastcall *v68)(__int64, __int64, __int64, char *); // rdi
  __int64 v69; // rbx
  int v70; // eax
  __int64 v71; // rdi
  void (__fastcall *v72)(__int64, HSTRING *); // rbx
  __int64 v73; // rsi
  void (__fastcall *v74)(__int64, HSTRING *); // rbx
  __int64 v75; // rdi
  __int64 (__fastcall *v76)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  int v77; // eax
  int v78; // ebx
  __int128 *v79; // rax
  PCWSTR v80; // rax
  __int64 v81; // rax
  _QWORD *v82; // rax
  __int64 (__fastcall ***v83)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v84)(_QWORD, GUID *, __int64 *); // rdi
  int v85; // eax
  __int64 v86; // rdi
  __int64 (__fastcall *v87)(__int64, __int64, __int64, __int64, GUID *, __int64 *); // rbx
  int v88; // eax
  int v89; // ebx
  __int128 *p_hstringHeader; // rax
  PCWSTR v91; // rax
  __int64 v92; // rax
  __int128 *v93; // rax
  int v94; // eax
  __int128 *v95; // rax
  PCWSTR v96; // rax
  __int64 v97; // rax
  __int128 *v98; // rax
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 v102; // rax
  __int64 v103; // rax
  __int64 v104; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rax
  __int64 v111; // rax
  __int64 v112; // rax
  __int64 v113; // rax
  __int64 v114; // rax
  __int64 v115; // rax
  __int64 v116; // rax
  char *v117; // rdi
  __int64 v118; // rcx
  __int64 v119; // rcx
  __int64 v120; // rcx
  __int64 v121; // rcx
  __int64 v122; // rcx
  char *v124; // [rsp+48h] [rbp-C0h] BYREF
  int v125; // [rsp+50h] [rbp-B8h]
  char v126; // [rsp+58h] [rbp-B0h] BYREF
  char v127; // [rsp+59h] [rbp-AFh] BYREF
  char v128; // [rsp+5Ah] [rbp-AEh] BYREF
  char v129; // [rsp+5Bh] [rbp-ADh] BYREF
  __int64 (__fastcall ***v130)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A8h] BYREF
  __int64 v131; // [rsp+68h] [rbp-A0h]
  __int64 v132; // [rsp+70h] [rbp-98h] BYREF
  __int64 v133; // [rsp+78h] [rbp-90h] BYREF
  HSTRING v134; // [rsp+80h] [rbp-88h] BYREF
  __int128 *v135; // [rsp+88h] [rbp-80h] BYREF
  __int64 v136; // [rsp+90h] [rbp-78h] BYREF
  HSTRING v137; // [rsp+98h] [rbp-70h] BYREF
  __int64 v138; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v139; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v140; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v141; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v142; // [rsp+C0h] [rbp-48h] BYREF
  PCWSTR StringRawBuffer; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v144; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v145; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v146; // [rsp+E0h] [rbp-28h] BYREF
  unsigned int v147; // [rsp+E8h] [rbp-20h]
  int v148; // [rsp+ECh] [rbp-1Ch] BYREF
  _WORD *v149; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v150; // [rsp+F8h] [rbp-10h]
  __int64 v151; // [rsp+100h] [rbp-8h]
  __int64 v152; // [rsp+108h] [rbp+0h]
  _QWORD *v153; // [rsp+110h] [rbp+8h]
  __int64 v154; // [rsp+118h] [rbp+10h]
  HSTRING_HEADER v155; // [rsp+128h] [rbp+20h] BYREF
  __int64 v156; // [rsp+140h] [rbp+38h]
  __int128 hstringHeader; // [rsp+160h] [rbp+58h] BYREF
  __m128i hstringHeader_16; // [rsp+170h] [rbp+68h] BYREF
  HSTRING_HEADER v159; // [rsp+180h] [rbp+78h] BYREF
  __int64 v160; // [rsp+198h] [rbp+90h]
  _BYTE v161[336]; // [rsp+1A8h] [rbp+A0h] BYREF

  v154 = a4;
  LOWORD(v131) = a3;
  v124 = a2;
  v153 = a6;
  v133 = (__int64)a2;
  v9 = a7;
  v147 = a7;
  v152 = a8;
  v139 = EnumMapper::ToString(a7);
  Log<unsigned __int64 &>(
    4,
    "{\"text\":\"GetTokenResultForAccount called with strong auth requirement as %s\"}",
    (const char *)&v139);
  v146 = 0;
  hstringHeader_16.m128i_i64[1] = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
                      0x45u,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16.m128i_i64[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
          hstringHeader_16.m128i_i64[1],
          &v146);
  if ( v11 < 0 )
  {
    v124 = ".\\onecoreaccountprovider.cpp";
    v125 = 1641;
    v12 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v11);
    cdp::CdpThrow<cdp::hresult_exception>(&v124, v12);
  }
  v142 = 0;
  hstringHeader_16.m128i_i64[1] = 0;
  v13 = WindowsCreateStringReference(
          L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
          0x38u,
          (HSTRING_HEADER *)&hstringHeader,
          (HSTRING *)&hstringHeader_16.m128i_i64[1]);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
          hstringHeader_16.m128i_i64[1],
          &v142);
  if ( v14 < 0 )
  {
    v124 = ".\\onecoreaccountprovider.cpp";
    v125 = 1645;
    v15 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v14);
    cdp::CdpThrow<cdp::hresult_exception>(&v124, v15);
  }
  v138 = 0;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a4 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v138);
  v17 = v16(a4, &v138);
  v18 = (unsigned int)v17;
  if ( v17 < 0 )
  {
    v124 = ".\\onecoreaccountprovider.cpp";
    v125 = 1648;
    v19 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v17);
    cdp::CdpThrow<cdp::hresult_exception>(&v124, v19);
  }
  v132 = 0;
  v20 = v131;
  if ( (_WORD)v131 != 1 || (v21 = 1, !a7) )
    v21 = 0;
  v127 = v21;
  v22 = 1;
  v23 = 0;
  v140 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v22 )
  {
    hstringHeader = 0;
    hstringHeader_16 = si128;
    LOWORD(hstringHeader) = 0;
    if ( v20 == 1 )
    {
      if ( !a5[2] )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1662;
        v103 = cdp::MakeException<std::invalid_argument,>(&v149, 2, "Scope endpoint name must be specified under MSA.");
        cdp::CdpThrow<std::invalid_argument>(&v124, v103);
      }
      v149 = 0;
      v150 = 0;
      v151 = 0;
      if ( v9 == 3 )
      {
        if ( a5[3] <= 7u )
          v25 = a5;
        else
          v25 = (_QWORD *)*a5;
        v26 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                &v149,
                L"service::%s::%s",
                v25,
                L"PURPOSE_GETKEYDATA_ROAMING");
        if ( v26 < 0 )
        {
          v124 = ".\\onecoreaccountprovider.cpp";
          v125 = 1670;
          v27 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v26);
          cdp::CdpThrow<cdp::hresult_exception>(&v124, v27);
        }
      }
      else
      {
        v28 = L"MBI_SSL_SA";
        if ( !v21 )
          v28 = L"MBI_SSL";
        if ( a5[3] <= 7u )
          v29 = a5;
        else
          v29 = (_QWORD *)*a5;
        v30 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                &v149,
                L"service::%s::%s",
                v29,
                v28);
        if ( v30 < 0 )
        {
          v124 = ".\\onecoreaccountprovider.cpp";
          v125 = 1675;
          v102 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v30);
          cdp::CdpThrow<cdp::hresult_exception>(&v124, v102);
        }
      }
      v31 = v142;
      v32 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v142 + 56LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v132);
      v33 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v155, &off_18037ACA8) + 24);
      v34 = v149;
      v130 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v149;
      v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v159, &v130);
      v36 = v32(v31, v138, *(_QWORD *)(v35 + 24), v33, 0, &v132);
      if ( v36 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1679;
        v101 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v36);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v101);
      }
      v128 = 0;
      v144 = 0;
      v37 = v132;
      v38 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v132 + 80LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
      v39 = v38(v37, &v144);
      if ( v39 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1688;
        v100 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v39);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v100);
      }
      v40 = v144;
      v41 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v144 + 80LL);
      v160 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v159, L"windows", 8u, 7u);
      v42 = v160;
      v156 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v155, L"ssoappgroup", 0xCu, 0xBu);
      v43 = v41(v40, v156, v42, &v128);
      if ( v43 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1690;
        v99 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v43);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v99);
      }
      v149 = 0;
      v151 = 0;
      v150 = 0;
      v44 = -1;
      do
        ++v44;
      while ( v34[v44] );
      std::wstring::_Assign<unsigned short>(&hstringHeader, v34);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v144);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v149);
      v9 = v147;
    }
    else
    {
      if ( v20 != 2 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1726;
        v116 = cdp::MakeException<cdp::HResultException<-2147221246>,>(
                 &v155,
                 &v124,
                 "Account type is not supported by TokenBroker");
        cdp::CdpThrow<cdp::HResultException<-2147221246>>(&v124, v116);
      }
      std::wstring::operator=(&hstringHeader, a5, v18);
      v45 = v142;
      v46 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _DWORD, __int64 *))(*(_QWORD *)v142 + 56LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v132);
      v47 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v155, &off_180357AC0) + 24);
      if ( a5[3] <= 7u )
        v48 = a5;
      else
        v48 = (_QWORD *)*a5;
      v130 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v48;
      v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v159, &v130);
      v50 = v46(v45, v138, *(_QWORD *)(v49 + 24), v47, 0, &v132);
      if ( v50 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1699;
        v115 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v50);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v115);
      }
      v126 = 0;
      v136 = 0;
      v51 = v132;
      v52 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v132 + 80LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v136);
      v53 = v52(v51, &v136);
      if ( v53 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1704;
        v114 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v53);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v114);
      }
      v54 = v136;
      v55 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v136 + 80LL);
      v56 = v153;
      if ( v153[3] > 7u )
        v56 = (_QWORD *)*v153;
      v130 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v56;
      v57 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v159, &v130) + 24);
      v156 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v155, L"resource", 9u, 8u);
      v58 = v55(v54, v156, v57, &v126);
      if ( v58 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1706;
        v113 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v58);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v113);
      }
      v59 = v136;
      v60 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v136 + 80LL);
      v156 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v155, L"0", 2u, 1u);
      v61 = v156;
      v160 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v159, L"msafed", 7u, 6u);
      v62 = v60(v59, v160, v61, &v126);
      if ( v62 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1710;
        v112 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v62);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v112);
      }
      v63 = v136;
      v64 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v136 + 80LL);
      v156 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v155, L"home", 5u, 4u);
      v65 = v156;
      v160 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v159, L"discover", 9u, 8u);
      v66 = v64(v63, v160, v65, &v126);
      if ( v66 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1719;
        v111 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v66);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v111);
      }
      v67 = v136;
      v68 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v136 + 80LL);
      v156 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v155, L"organizations", 0xEu, 0xDu);
      v69 = v156;
      v160 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v159, L"authority", 0xAu, 9u);
      v70 = v68(v67, v160, v69, &v126);
      if ( v70 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1721;
        v110 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v70);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v110);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v136);
    }
    OneCoreAccountTelemetryProvider::TokenResultForAccountActivity::Start<>((OneCoreAccountTelemetryProvider::TokenResultForAccountActivity *)v161);
    v137 = 0;
    v134 = 0;
    v71 = v138;
    v72 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v138 + 56LL);
    WindowsDeleteString(0);
    v137 = 0;
    v72(v71, &v137);
    v73 = v154;
    v74 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v154 + 56LL);
    WindowsDeleteString(v134);
    v134 = 0;
    v74(v73, &v134);
    v130 = 0;
    if ( v152 )
    {
      v156 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &v155,
        L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
        0x46u,
        0x45u);
      Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
        v156,
        &v130);
      v139 = 0;
      v83 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v130;
      v84 = **v130;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v139);
      v85 = v84(v83, &GUID_f4b8e804_811e_4436_b69c_44cb67b72084, &v139);
      if ( v85 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1757;
        v109 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v85);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v109);
      }
      v145 = 0;
      v86 = v139;
      v87 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, GUID *, __int64 *))(*(_QWORD *)v139 + 56LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
      v88 = v87(v86, v152, v132, v73, &GUID_0a815852_7c44_5674_b3d2_fa2e4c1e46c9, &v145);
      if ( v88 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1762;
        v108 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v88);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v108);
      }
      v133 = 1800000;
      std::string::string(
        &v155,
        "class std::tuple<class Microsoft::WRL::ComPtr<struct Windows::Security::Authentication::Web::Core::IWebTokenRequ"
        "estResult>,bool> __cdecl shared::OneCoreAccountProvider::GetTokenResultForAccount(enum CDPAccountType,struct Win"
        "dows::Security::Credentials::IWebAccount *,const class std::basic_string<unsigned short,struct std::char_traits<"
        "unsigned short>,class std::allocator<unsigned short> > &,const class std::basic_string<unsigned short,struct std"
        "::char_traits<unsigned short>,class std::allocator<unsigned short> > &,enum CDPStrongAuthenticationRequirement,struct HWND__ *)");
      v89 = shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
              v145,
              &v155,
              &v133,
              &v140);
      LODWORD(v141) = v89;
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v155);
      p_hstringHeader = &hstringHeader;
      if ( hstringHeader_16.m128i_i64[1] > 7uLL )
        p_hstringHeader = (__int128 *)hstringHeader;
      v133 = (__int64)p_hstringHeader;
      StringRawBuffer = WindowsGetStringRawBuffer(v137, 0);
      v91 = WindowsGetStringRawBuffer(v134, 0);
      v92 = std::wstring::wstring(&v155, v91);
      v93 = (__int128 *)EncryptString(&v159, v92);
      if ( *((_QWORD *)v93 + 3) > 7u )
        v93 = *(__int128 **)v93;
      v135 = v93;
      OneCoreAccountTelemetryProvider::TokenResultForAccountActivity::RequestTokenWithWebAccountForWindow<long &,bool &,unsigned short const *,unsigned short const *,unsigned short const *>(
        (unsigned int)v161,
        (unsigned int)&v141,
        (unsigned int)&v127,
        (unsigned int)&v135,
        (__int64)&StringRawBuffer,
        (__int64)&v133);
      std::wstring::_Tidy_deallocate(&v159);
      if ( v89 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1770;
        v107 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v89);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v107);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v145);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v139);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v130);
    }
    else
    {
      v75 = v146;
      v76 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v146 + 56LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v130);
      v77 = v76(v75, v132, v73, (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v130);
      if ( v77 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1740;
        v105 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v77);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v105);
      }
      v141 = 30000;
      std::string::string(
        &v155,
        "class std::tuple<class Microsoft::WRL::ComPtr<struct Windows::Security::Authentication::Web::Core::IWebTokenRequ"
        "estResult>,bool> __cdecl shared::OneCoreAccountProvider::GetTokenResultForAccount(enum CDPAccountType,struct Win"
        "dows::Security::Credentials::IWebAccount *,const class std::basic_string<unsigned short,struct std::char_traits<"
        "unsigned short>,class std::allocator<unsigned short> > &,const class std::basic_string<unsigned short,struct std"
        "::char_traits<unsigned short>,class std::allocator<unsigned short> > &,enum CDPStrongAuthenticationRequirement,struct HWND__ *)");
      v78 = shared::CancellableBlockingWRLCall<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
              v130,
              &v155,
              &v141,
              &v140);
      LODWORD(v141) = v78;
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v155);
      v79 = &hstringHeader;
      if ( hstringHeader_16.m128i_i64[1] > 7uLL )
        v79 = (__int128 *)hstringHeader;
      v135 = v79;
      StringRawBuffer = WindowsGetStringRawBuffer(v137, 0);
      v80 = WindowsGetStringRawBuffer(v134, 0);
      v81 = std::wstring::wstring(&v155, v80);
      v82 = (_QWORD *)EncryptString(&v159, v81);
      if ( v82[3] > 7u )
        v82 = (_QWORD *)*v82;
      v133 = (__int64)v82;
      OneCoreAccountTelemetryProvider::TokenResultForAccountActivity::GetTokenSilentlyWithWebAccount<long &,bool &,unsigned short const *,unsigned short const *,unsigned short const *>(
        (unsigned int)v161,
        (unsigned int)&v141,
        (unsigned int)&v127,
        (unsigned int)&v133,
        (__int64)&StringRawBuffer,
        (__int64)&v135);
      std::wstring::_Tidy_deallocate(&v159);
      if ( v78 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1748;
        v104 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v78);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v104);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v130);
    }
    v22 = 0;
    if ( v21 )
    {
      v94 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v140 + 56LL))(v140, &v148);
      if ( v94 < 0 )
      {
        v124 = ".\\onecoreaccountprovider.cpp";
        v125 = 1778;
        v106 = cdp::MakeException<cdp::hresult_exception>(&v155, &v124, (unsigned int)v94);
        cdp::CdpThrow<cdp::hresult_exception>(&v124, v106);
      }
      if ( v148 && v9 == 1 )
      {
        Log<>(3, "{\"text\":\"Attempt to get strong-auth token failed, retrying without strong auth.\"}");
        v21 = 0;
        v127 = 0;
        v22 = 1;
        v95 = &hstringHeader;
        if ( hstringHeader_16.m128i_i64[1] > 7uLL )
          v95 = (__int128 *)hstringHeader;
        v133 = (__int64)v95;
        StringRawBuffer = WindowsGetStringRawBuffer(v137, 0);
        v96 = WindowsGetStringRawBuffer(v134, 0);
        v97 = std::wstring::wstring(&v155, v96);
        v98 = (__int128 *)EncryptString(&v159, v97);
        if ( *((_QWORD *)v98 + 3) > 7u )
          v98 = *(__int128 **)v98;
        v135 = v98;
        v129 = 1;
        OneCoreAccountTelemetryProvider::TokenResultForAccountActivity::CanDowngradeAuth<bool,unsigned short const *,unsigned short const *,unsigned short const *>(
          (unsigned int)v161,
          (unsigned int)&v129,
          (unsigned int)&v135,
          (unsigned int)&StringRawBuffer,
          (__int64)&v133);
        std::wstring::_Tidy_deallocate(&v159);
      }
    }
    wil::ActivityBase<OneCoreAccountTelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v161);
    WindowsDeleteString(v134);
    v134 = 0;
    WindowsDeleteString(v137);
    v137 = 0;
    OneCoreAccountTelemetryProvider::TokenResultForAccountActivity::~TokenResultForAccountActivity((OneCoreAccountTelemetryProvider::TokenResultForAccountActivity *)v161);
    std::wstring::_Tidy_deallocate(&hstringHeader);
    v23 = v140;
    v20 = v131;
  }
  v117 = v124;
  *v124 = v21;
  *((_QWORD *)v117 + 1) = v23;
  Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>::InternalAddRef(
    v117 + 8,
    2,
    v18);
  v118 = v140;
  if ( v140 )
  {
    v140 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
  }
  v119 = v132;
  if ( v132 )
  {
    v132 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v119 + 16LL))(v119);
  }
  v120 = v138;
  if ( v138 )
  {
    v138 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
  }
  v121 = v142;
  if ( v142 )
  {
    v142 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
  }
  v122 = v146;
  if ( v146 )
  {
    v146 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
  }
  return v117;
}

```

## disassembly

```asm
0x18009e1ec  mov     rax, rsp
0x18009e1ef  mov     [rax+8], rbx
0x18009e1f3  push    rbp
0x18009e1f4  push    rsi
0x18009e1f5  push    rdi
0x18009e1f6  push    r12
0x18009e1f8  push    r13
0x18009e1fa  push    r14
0x18009e1fc  push    r15
0x18009e1fe  lea     rbp, [rax-248h]
0x18009e205  sub     rsp, 310h
0x18009e20c  movaps  xmmword ptr [rax-48h], xmm6
0x18009e210  mov     rax, cs:__security_cookie
0x18009e217  xor     rax, rsp
0x18009e21a  mov     [rbp+240h+var_50], rax
0x18009e221  mov     rsi, r9
0x18009e224  mov     [rbp+240h+var_230], r9
0x18009e228  mov     word ptr [rsp+340h+var_2E0], r8w
0x18009e22e  mov     [rsp+340h+var_300], rdx
0x18009e233  mov     rax, [rbp+240h+arg_28]
0x18009e23a  mov     [rbp+240h+var_238], rax
0x18009e23e  mov     r15, [rbp+240h+arg_20]
0x18009e245  mov     [rsp+340h+var_2D0], rdx
0x18009e24a  mov     r12d, [rbp+240h+arg_30]
0x18009e251  mov     [rbp+240h+var_260], r12d
0x18009e255  mov     rax, [rbp+240h+arg_38]
0x18009e25c  mov     [rbp+240h+var_240], rax
0x18009e260  xor     edi, edi
0x18009e262  mov     ecx, r12d
0x18009e265  call    ?ToString@EnumMapper@@YAPEBDW4CDPStrongAuthenticationRequirement@@@Z; EnumMapper::ToString(CDPStrongAuthenticationRequirement)
0x18009e26a  mov     [rbp+240h+var_2A0], rax
0x18009e26e  lea     r8, [rbp+240h+var_2A0]
0x18009e272  lea     rdx, aTextGettokenre; "{\"text\":\"GetTokenResultForAccount ca"...
0x18009e279  lea     ecx, [rdi+4]
0x18009e27c  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x18009e281  mov     [rbp+240h+var_268], rdi
0x18009e285  mov     [rbp+240h+string], rdi
0x18009e289  lea     r9, [rbp+240h+string]; string
0x18009e28d  lea     r8, [rbp+240h+hstringHeader]; hstringHeader
0x18009e291  lea     edx, [rdi+45h]; length
0x18009e294  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18009e29b  call    cs:__imp_WindowsCreateStringReference
0x18009e2a1  test    eax, eax
0x18009e2a3  jns     short loc_18009E2B7
0x18009e2a5  xor     r9d, r9d; lpArguments
0x18009e2a8  xor     r8d, r8d; nNumberOfArguments
0x18009e2ab  lea     edx, [rdi+1]; dwExceptionFlags
0x18009e2ae  mov     ecx, eax; dwExceptionCode
0x18009e2b0  call    cs:__imp_RaiseException
0x18009e2b6  int     3; Trap to Debugger
0x18009e2b7  lea     rdx, [rbp+240h+var_268]
0x18009e2bb  mov     rcx, [rbp+240h+string]
0x18009e2bf  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x18009e2c4  mov     r8d, eax
0x18009e2c7  test    eax, eax
0x18009e2c9  jns     short loc_18009E2FC
0x18009e2cb  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009e2d2  mov     [rsp+340h+var_300], rax
0x18009e2d7  mov     [rsp+340h+var_2F8], 669h
0x18009e2df  lea     rdx, [rsp+340h+var_300]
0x18009e2e4  lea     rcx, [rbp+240h+var_220]
0x18009e2e8  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009e2ed  nop
0x18009e2ee  mov     rdx, rax
0x18009e2f1  lea     rcx, [rsp+340h+var_300]
0x18009e2f6  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009e2fc  mov     [rbp+240h+var_288], rdi
0x18009e300  mov     [rbp+240h+string], rdi
0x18009e304  lea     r9, [rbp+240h+string]; string
0x18009e308  lea     r8, [rbp+240h+hstringHeader]; hstringHeader
0x18009e30c  mov     edx, 38h ; '8'; length
0x18009e311  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18009e318  call    cs:__imp_WindowsCreateStringReference
0x18009e31e  test    eax, eax
0x18009e320  jns     short loc_18009E335
0x18009e322  xor     r9d, r9d; lpArguments
0x18009e325  xor     r8d, r8d; nNumberOfArguments
0x18009e328  lea     edx, [r9+1]; dwExceptionFlags
0x18009e32c  mov     ecx, eax; dwExceptionCode
0x18009e32e  call    cs:__imp_RaiseException
0x18009e334  int     3; Trap to Debugger
0x18009e335  lea     rdx, [rbp+240h+var_288]
0x18009e339  mov     rcx, [rbp+240h+string]
0x18009e33d  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x18009e342  mov     r8d, eax
0x18009e345  test    eax, eax
0x18009e347  jns     short loc_18009E37A
0x18009e349  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009e350  mov     [rsp+340h+var_300], rax
0x18009e355  mov     [rsp+340h+var_2F8], 66Dh
0x18009e35d  lea     rdx, [rsp+340h+var_300]
0x18009e362  lea     rcx, [rbp+240h+var_220]
0x18009e366  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009e36b  nop
0x18009e36c  mov     rdx, rax
0x18009e36f  lea     rcx, [rsp+340h+var_300]
0x18009e374  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009e37a  mov     [rbp+240h+var_2A8], rdi
0x18009e37e  mov     rax, [rsi]
0x18009e381  mov     rbx, [rax+30h]
0x18009e385  lea     rcx, [rbp+240h+var_2A8]
0x18009e389  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009e38e  lea     rdx, [rbp+240h+var_2A8]
0x18009e392  mov     rcx, rsi
0x18009e395  mov     rax, rbx
0x18009e398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e39d  mov     r8d, eax
0x18009e3a0  test    eax, eax
0x18009e3a2  jns     short loc_18009E3D5
0x18009e3a4  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009e3ab  mov     [rsp+340h+var_300], rax
0x18009e3b0  mov     [rsp+340h+var_2F8], 670h
0x18009e3b8  lea     rdx, [rsp+340h+var_300]
0x18009e3bd  lea     rcx, [rbp+240h+var_220]
0x18009e3c1  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009e3c6  nop
0x18009e3c7  mov     rdx, rax
0x18009e3ca  lea     rcx, [rsp+340h+var_300]
0x18009e3cf  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009e3d5  mov     [rsp+340h+var_2D8], rdi
0x18009e3da  mov     r14d, 1
0x18009e3e0  movzx   ecx, word ptr [rsp+340h+var_2E0]
0x18009e3e5  cmp     cx, r14w
0x18009e3e9  jnz     short loc_18009E3F3
0x18009e3eb  test    r12d, r12d
0x18009e3ee  mov     r13b, r14b
0x18009e3f1  jnz     short loc_18009E3F6
0x18009e3f3  mov     r13b, dil
0x18009e3f6  mov     byte ptr [rsp+340h+var_2F0+1], r13b
0x18009e3fb  mov     bl, r14b
0x18009e3fe  mov     rax, rdi
0x18009e401  mov     [rbp+240h+var_298], rax
0x18009e405  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18009e40d  mov     edx, 2
0x18009e412  test    bl, bl
0x18009e414  jz      loc_18009F101
0x18009e41a  xorps   xmm0, xmm0
0x18009e41d  movups  xmmword ptr [rbp+240h+hstringHeader.Reserved], xmm0
0x18009e421  movdqu  xmmword ptr [rbp+68h], xmm6
0x18009e426  mov     word ptr [rbp+240h+hstringHeader.Reserved], di
0x18009e42a  cmp     cx, r14w
0x18009e42e  jnz     loc_18009E65E
0x18009e434  cmp     [r15+10h], rdi
0x18009e438  jz      loc_18009EE44
0x18009e43e  mov     [rbp+240h+var_258], rdi
0x18009e442  mov     [rbp+240h+var_250], rdi
0x18009e446  mov     [rbp+240h+var_248], rdi
0x18009e44a  cmp     r12d, 3
0x18009e44e  jnz     short loc_18009E4AE
0x18009e450  cmp     qword ptr [r15+18h], 7
0x18009e455  jbe     short loc_18009E45C
0x18009e457  mov     r8, [r15]
0x18009e45a  jmp     short loc_18009E45F
0x18009e45c  mov     r8, r15
0x18009e45f  lea     r9, aPurposeGetkeyd_0; "PURPOSE_GETKEYDATA_ROAMING"
0x18009e466  lea     rdx, aServiceSS; "service::%s::%s"
0x18009e46d  lea     rcx, [rbp+240h+var_258]
0x18009e471  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18009e476  mov     r8d, eax
0x18009e479  test    eax, eax
0x18009e47b  jns     short loc_18009E4ED
0x18009e47d  lea     rax, aOnecoreaccount; ".\\onecoreaccountprovider.cpp"
0x18009e484  mov     [rsp+340h+var_300], rax
0x18009e489  mov     [rsp+340h+var_2F8], 686h
0x18009e491  lea     rdx, [rsp+340h+var_300]
0x18009e496  lea     rcx, [rbp+240h+var_220]
0x18009e49a  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x18009e49f  nop
0x18009e4a0  mov     rdx, rax
0x18009e4a3  lea     rcx, [rsp+340h+var_300]
0x18009e4a8  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x18009e4ae  lea     r9, aMbiSslSa; "MBI_SSL_SA"
0x18009e4b5  lea     rax, aMbiSsl; "MBI_SSL"
0x18009e4bc  test    r13b, r13b
0x18009e4bf  cmovz   r9, rax
0x18009e4c3  cmp     qword ptr [r15+18h], 7
0x18009e4c8  jbe     short loc_18009E4CF
0x18009e4ca  mov     r8, [r15]
0x18009e4cd  jmp     short loc_18009E4D2
0x18009e4cf  mov     r8, r15
0x18009e4d2  lea     rdx, aServiceSS; "service::%s::%s"
0x18009e4d9  lea     rcx, [rbp+240h+var_258]
0x18009e4dd  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18009e4e2  mov     r8d, eax
0x18009e4e5  test    eax, eax
0x18009e4e7  js      loc_18009EE13
0x18009e4ed  mov     rsi, [rbp+240h+var_288]
0x18009e4f1  mov     rax, [rsi]
0x18009e4f4  mov     rdi, [rax+38h]
0x18009e4f8  lea     rcx, [rsp+340h+var_2D8]
0x18009e4fd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009e502  lea     rdx, off_18037ACA8; "{12E984BD-5803-4D78-9EFB-BED7B9212C26}"
0x18009e509  lea     rcx, [rbp+240h+var_220]
0x18009e50d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009e512  nop
0x18009e513  mov     rbx, [rax+18h]
0x18009e517  mov     r12, [rbp+240h+var_258]
0x18009e51b  mov     [rsp+340h+var_2E8], r12
0x18009e520  lea     rdx, [rsp+340h+var_2E8]
0x18009e525  lea     rcx, [rbp+240h+var_1C8]
0x18009e529  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009e52e  nop
0x18009e52f  lea     rcx, [rsp+340h+var_2D8]
0x18009e534  mov     [rsp+340h+var_318], rcx
0x18009e539  mov     dword ptr [rsp+340h+var_320], 0
0x18009e541  mov     r9, rbx
0x18009e544  mov     r8, [rax+18h]
0x18009e548  mov     rdx, [rbp+240h+var_2A8]
0x18009e54c  mov     rcx, rsi
0x18009e54f  mov     rax, rdi
0x18009e552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e557  mov     r8d, eax
0x18009e55a  xor     esi, esi
0x18009e55c  test    eax, eax
0x18009e55e  js      loc_18009EDE2
0x18009e564  mov     byte ptr [rsp+340h+var_2F0+2], sil
0x18009e569  mov     [rbp+240h+var_278], rsi
0x18009e56d  mov     rdi, [rsp+340h+var_2D8]
0x18009e572  mov     rax, [rdi]
0x18009e575  mov     rbx, [rax+50h]
0x18009e579  lea     rcx, [rbp+240h+var_278]
0x18009e57d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009e582  lea     rdx, [rbp+240h+var_278]
0x18009e586  mov     rcx, rdi
0x18009e589  mov     rax, rbx
0x18009e58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e591  mov     r8d, eax
0x18009e594  test    eax, eax
0x18009e596  js      loc_18009EDB1
0x18009e59c  mov     rsi, [rbp+240h+var_278]
0x18009e5a0  mov     rax, [rsi]
0x18009e5a3  mov     rdi, [rax+50h]
0x18009e5a7  mov     [rbp+240h+var_1B0], 0
0x18009e5b2  mov     r9d, 7; unsigned int
0x18009e5b8  lea     r8d, [r9+1]; unsigned int
0x18009e5bc  lea     rdx, aWindows_0; "windows"
0x18009e5c3  lea     rcx, [rbp+240h+var_1C8]; hstringHeader
0x18009e5c7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009e5cc  nop
0x18009e5cd  mov     rbx, [rbp+240h+var_1B0]
0x18009e5d4  mov     [rbp+240h+var_208], 0
0x18009e5dc  mov     r9d, 0Bh; unsigned int
0x18009e5e2  lea     r8d, [r9+1]; unsigned int
0x18009e5e6  lea     rdx, aSsoappgroup; "ssoappgroup"
0x18009e5ed  lea     rcx, [rbp+240h+var_220]; hstringHeader
0x18009e5f1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009e5f6  nop
0x18009e5f7  lea     r9, [rsp+340h+var_2F0+2]
0x18009e5fc  mov     r8, rbx
0x18009e5ff  mov     rdx, [rbp+240h+var_208]
0x18009e603  mov     rcx, rsi
0x18009e606  mov     rax, rdi
0x18009e609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e60e  mov     r8d, eax
0x18009e611  xor     esi, esi
0x18009e613  test    eax, eax
0x18009e615  js      loc_18009ED80
0x18009e61b  mov     [rbp+240h+var_258], rsi
0x18009e61f  mov     [rbp+240h+var_248], rsi
0x18009e623  mov     [rbp+240h+var_250], rsi
0x18009e627  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009e62b  inc     r8
0x18009e62e  cmp     [r12+r8*2], si
0x18009e633  jnz     short loc_18009E62B
0x18009e635  mov     rdx, r12
0x18009e638  lea     rcx, [rbp+240h+hstringHeader]
0x18009e63c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009e641  nop
0x18009e642  lea     rcx, [rbp+240h+var_278]
0x18009e646  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009e64b  nop
0x18009e64c  lea     rcx, [rbp+240h+var_258]
0x18009e650  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18009e655  mov     r12d, [rbp+240h+var_260]
0x18009e659  jmp     loc_18009E918
0x18009e65e  cmp     cx, dx
0x18009e661  jnz     loc_18009F0C9
0x18009e667  mov     rdx, r15
0x18009e66a  lea     rcx, [rbp+240h+hstringHeader]
0x18009e66e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009e673  mov     rbx, [rbp+240h+var_288]
0x18009e677  mov     rax, [rbx]
0x18009e67a  mov     rsi, [rax+38h]
0x18009e67e  lea     rcx, [rsp+340h+var_2D8]
0x18009e683  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18009e688  lea     rdx, off_180357AC0; "{6F7E0F60-9401-4F5b-98E2-CF15BD5Fd5E3}"
0x18009e68f  lea     rcx, [rbp+240h+var_220]
0x18009e693  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009e698  nop
0x18009e699  mov     rdi, [rax+18h]
0x18009e69d  cmp     qword ptr [r15+18h], 7
0x18009e6a2  jbe     short loc_18009E6A9
0x18009e6a4  mov     rax, [r15]
0x18009e6a7  jmp     short loc_18009E6AC
0x18009e6a9  mov     rax, r15
0x18009e6ac  mov     [rsp+340h+var_2E8], rax
0x18009e6b1  lea     rdx, [rsp+340h+var_2E8]
0x18009e6b6  lea     rcx, [rbp+240h+var_1C8]
0x18009e6ba  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009e6bf  nop
  ... truncated ...
```
