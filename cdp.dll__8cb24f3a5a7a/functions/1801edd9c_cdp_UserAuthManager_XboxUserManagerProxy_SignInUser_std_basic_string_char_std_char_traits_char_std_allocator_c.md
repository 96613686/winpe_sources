# cdp::UserAuthManager::XboxUserManagerProxy::SignInUser(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,uint &)

- ea: `0x1801edd9c`
- end: `0x1801ee993`
- name: `?SignInUser@XboxUserManagerProxy@UserAuthManager@cdp@@QEAA?AW4SignInResult@3@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAI@Z`
- size: `3063`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1802cb910`

## callees

- `0x18000b724`
- `0x18000d098`
- `0x1800113bc`
- `0x180013da0`
- `0x18001ce80`
- `0x180030190`
- `0x1800624cc`
- `0x1800677f0`
- `0x1800a11bc`
- `0x180114c58`
- `0x18011d8c4`
- `0x180194418`
- `0x1801edd9c`
- `0x1801ee99c`
- `0x1801eefa8`
- `0x1801f6fb0`
- `0x1802ca47c`
- `0x1802ca584`
- `0x1802ca5d4`
- `0x1802cb0a0`
- `0x180354010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ee3df`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801ee3df`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1801edeca`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1801edeca`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1801ee5a6`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1801ee5a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ede53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801edf30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee33c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee95c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ede53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801edf30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee33c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ee95c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801edebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ee3bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801edebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ee3bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801ee69a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1801ee69a`

## string_xrefs

- `0x1801ee068`: `Couldn't copy xbox user data out`
- `0x1801ee573`: `Couldn't put signInContext's agent`
- `0x1801ee50b`: `Couldn't create signInContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall cdp::UserAuthManager::XboxUserManagerProxy::SignInUser(__int64 a1, const char *a2, unsigned int *a3)
{
  const char *v4; // r15
  unsigned int v6; // esi
  _QWORD *v7; // rdx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rdi
  int v10; // eax
  __int64 v11; // rax
  const wchar_t *StringRawBuffer; // rax
  HSTRING v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  unsigned int i; // r14d
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, __int64 *); // rbx
  const unsigned __int16 (*v32)[11]; // rdx
  _QWORD *v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, HSTRING *); // rbx
  int v40; // eax
  __int64 v41; // rax
  PCWSTR v42; // rax
  _QWORD *v43; // rcx
  __int64 v44; // rcx
  HSTRING v45; // rcx
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, _QWORD, _QWORD); // rbx
  int v48; // eax
  __int64 v49; // rax
  int v50; // eax
  __int64 v51; // rax
  struct tm *v52; // rax
  __int64 v53; // r8
  struct tm *v54; // rax
  int tm_sec; // edx
  int tm_min; // r8d
  int tm_hour; // r9d
  int tm_mday; // r10d
  int v59; // r11d
  int tm_mon; // eax
  PCNZWCH *v61; // rax
  __int64 v62; // rdx
  const WCHAR *v63; // rcx
  HRESULT v64; // eax
  __int64 v65; // rdx
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v67)(_QWORD, GUID *, __int64 *); // rdi
  int v68; // eax
  __int64 v69; // rdx
  int v70; // eax
  __int64 v71; // rax
  __int64 v72; // rdi
  __int64 (__fastcall *v73)(__int64, _QWORD, const char **); // rbx
  int v74; // eax
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v79; // rax
  int v80; // [rsp+28h] [rbp-1A0h]
  __int64 v81; // [rsp+30h] [rbp-198h]
  _BYTE v82[8]; // [rsp+50h] [rbp-178h] BYREF
  HSTRING string; // [rsp+58h] [rbp-170h] BYREF
  int v84; // [rsp+60h] [rbp-168h]
  unsigned int v85; // [rsp+64h] [rbp-164h] BYREF
  __int64 v86; // [rsp+68h] [rbp-160h] BYREF
  const char *v87; // [rsp+70h] [rbp-158h] BYREF
  int v88; // [rsp+78h] [rbp-150h]
  __int64 v89; // [rsp+80h] [rbp-148h] BYREF
  HSTRING v90; // [rsp+88h] [rbp-140h] BYREF
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-138h] BYREF
  __int64 v92; // [rsp+98h] [rbp-130h] BYREF
  int v93; // [rsp+A0h] [rbp-128h] BYREF
  HSTRING v94; // [rsp+A8h] [rbp-120h] BYREF
  __int64 v95; // [rsp+B0h] [rbp-118h] BYREF
  __int64 v96; // [rsp+B8h] [rbp-110h] BYREF
  __int64 v97; // [rsp+C0h] [rbp-108h] BYREF
  __int64 v98; // [rsp+C8h] [rbp-100h] BYREF
  _BYTE v99[56]; // [rsp+D0h] [rbp-F8h] BYREF
  HSTRING v100; // [rsp+108h] [rbp-C0h] BYREF
  std::_Ref_count_base *v101; // [rsp+110h] [rbp-B8h]
  PCNZWCH sourceString[3]; // [rsp+130h] [rbp-98h] BYREF
  unsigned __int64 v103; // [rsp+148h] [rbp-80h]
  _QWORD v104[3]; // [rsp+168h] [rbp-60h] BYREF
  unsigned __int64 v105; // [rsp+180h] [rbp-48h]

  try
  {
    v4 = a2;
    v93 = 0;
    v6 = 1;
    v84 = 1;
    cdp::ToWstring(v104, a2);
    v7 = v104;
    if ( v105 > 7 )
      v7 = (_QWORD *)v104[0];
    std::wstring::wstring(sourceString, v7);
    cdp::UserAuthManager::XboxUserManagerProxy::GetSignedInUserForXuid(a1, &v98, sourceString);
    std::wstring::_Tidy_deallocate(sourceString);
    v8 = v98;
    string = 0;
    if ( v98 )
    {
      v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v98 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v10 = v9(v8, &string);
      if ( v10 < 0 )
      {
        v87 = ".\\userauthmanager.cpp";
        v88 = 142;
        v11 = cdp::MakeException<cdp::hresult_exception,>(
                sourceString,
                &v87,
                (unsigned int)v10,
                "Couldn't get nonRoamableUserId from existing user");
        cdp::CdpThrow<cdp::hresult_exception>(&v87, v11);
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      *a3 = wcstoul(StringRawBuffer, 0, 0);
      v6 = 0;
      v84 = 0;
      std::weak_ptr<cdp::ProximalConnector>::lock(a1, &v100);
      v13 = v100;
      if ( v100 )
      {
        v14 = std::string::string(sourceString, v4);
        cdp::UserAuthManager::OnXboxUserSignIn(v13, *a3, v14);
      }
      if ( v101 )
        std::_Ref_count_base::_Decref(v101);
      WindowsDeleteString(string);
    }
    else
    {
      v85 = 0;
      v15 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)(a1 + 128) + 88LL))(
              *(_QWORD *)(a1 + 128),
              &string);
      if ( v15 < 0 )
      {
        v87 = ".\\userauthmanager.cpp";
        v88 = 67;
        v16 = cdp::MakeException<cdp::hresult_exception,>(
                sourceString,
                &v87,
                (unsigned int)v15,
                "Couldn't get console users");
        cdp::CdpThrow<cdp::hresult_exception>(&v87, v16);
      }
      v17 = (*(__int64 (__fastcall **)(HSTRING, unsigned int *))(*(_QWORD *)string + 56LL))(string, &v85);
      if ( v17 < 0 )
      {
        v87 = ".\\userauthmanager.cpp";
        v88 = 68;
        v18 = cdp::MakeException<cdp::hresult_exception,>(
                sourceString,
                &v87,
                (unsigned int)v17,
                "Couldn't get console users size");
        cdp::CdpThrow<cdp::hresult_exception>(&v87, v18);
      }
      for ( i = 0; i < v85; ++i )
      {
        v90 = 0;
        v89 = 0;
        v86 = 0;
        v96 = 0;
        v92 = 0;
        v95 = 0;
        v20 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, __int64 *))(*(_QWORD *)string + 48LL))(string, i, &v89);
        if ( v20 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 80;
          v21 = cdp::MakeException<cdp::hresult_exception,>(
                  v99,
                  &v100,
                  (unsigned int)v20,
                  "Couldn't copy xbox user data out");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v21);
        }
        v22 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v89 + 48LL))(v89, a3);
        if ( v22 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 81;
          v23 = cdp::MakeException<cdp::hresult_exception,>(v99, &v100, (unsigned int)v22, "Couldn't get consoleUserId");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v23);
        }
        v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v89 + 80LL))(v89, v82);
        if ( v24 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 82;
          v25 = cdp::MakeException<cdp::hresult_exception,>(
                  v99,
                  &v100,
                  (unsigned int)v24,
                  "Couldn't get credentials persisted flag");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v25);
        }
        v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v89 + 88LL))(v89, &v86);
        if ( v26 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 84;
          v27 = cdp::MakeException<cdp::hresult_exception,>(v99, &v100, (unsigned int)v26, "Couldn't get Properties");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v27);
        }
        v28 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                &v86,
                &v96);
        if ( v28 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 85;
          v29 = cdp::MakeException<cdp::hresult_exception,>(
                  v99,
                  &v100,
                  (unsigned int)v28,
                  "Couldn't get Properties as PropertyMap");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v29);
        }
        v30 = v96;
        v31 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v96 + 48LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
        v33 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v100, v32);
        v34 = v31(v30, *v33, &v92);
        if ( v34 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 86;
          v35 = cdp::MakeException<cdp::hresult_exception,>(v99, &v100, (unsigned int)v34, "Couldn't get xuid");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v35);
        }
        v36 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v92, &v95);
        if ( v36 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 87;
          v37 = cdp::MakeException<cdp::hresult_exception,>(
                  v99,
                  &v100,
                  (unsigned int)v36,
                  "Couldn't convert inspectable to propvalue");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v37);
        }
        v38 = v95;
        v39 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v95 + 152LL);
        WindowsDeleteString(v90);
        v90 = 0;
        v40 = v39(v38, &v90);
        if ( v40 < 0 )
        {
          v100 = (HSTRING)".\\userauthmanager.cpp";
          LODWORD(v101) = 88;
          v41 = cdp::MakeException<cdp::hresult_exception,>(v99, &v100, (unsigned int)v40, "Couldn't get xuid string.");
          cdp::CdpThrow<cdp::hresult_exception>(&v100, v41);
        }
        v42 = WindowsGetStringRawBuffer(v90, 0);
        v43 = v104;
        if ( v105 > 7 )
          v43 = (_QWORD *)v104[0];
        if ( !(unsigned int)_o__wcsicmp(v43, v42) && *a3 )
        {
          if ( v82[0] )
          {
            v87 = 0;
            v91 = 0;
            v46 = *(_QWORD *)(a1 + 136);
            v47 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v46 + 64LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v91);
            v48 = v47(v46, *a3, &v91);
            if ( v48 < 0 )
            {
              v100 = (HSTRING)".\\userauthmanager.cpp";
              LODWORD(v101) = 105;
              v49 = cdp::MakeException<cdp::hresult_exception,>(
                      v99,
                      &v100,
                      (unsigned int)v48,
                      "Couldn't create signInContext");
              cdp::CdpThrow<cdp::hresult_exception>(&v100, v49);
            }
            v50 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v91)[9])(
                    v91,
                    3);
            if ( v50 < 0 )
            {
              v100 = (HSTRING)".\\userauthmanager.cpp";
              LODWORD(v101) = 106;
              v51 = cdp::MakeException<cdp::hresult_exception,>(
                      v99,
                      &v100,
                      (unsigned int)v50,
                      "Couldn't put signInContext's agent");
              cdp::CdpThrow<cdp::hresult_exception>(&v100, v51);
            }
            v52 = (struct tm *)_time64(0);
            v54 = cdp::TimeTToLocalTimeTm((cdp *)&v100, v52, v53);
            tm_sec = v54->tm_sec;
            tm_min = v54->tm_min;
            tm_hour = v54->tm_hour;
            tm_mday = v54->tm_mday;
            v59 = v54->tm_year + 1900;
            tm_mon = v54->tm_mon;
            if ( *((_QWORD *)v4 + 3) > 0xFu )
              v4 = *(const char **)v4;
            cdp::detail::StringFormat(
              &v100,
              "SG:X=%s@%02d/%02d/%d %02d:%02d:%02d",
              v4,
              tm_mon + 1,
              tm_mday,
              v59,
              tm_hour,
              tm_min,
              tm_sec);
            cdp::ToWstring(sourceString, &v100);
            std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v100);
            v94 = 0;
            WindowsDeleteString(0);
            v94 = 0;
            v61 = sourceString;
            if ( v103 > 7 )
              v61 = (PCNZWCH *)sourceString[0];
            v62 = -1;
            do
              ++v62;
            while ( *((_WORD *)v61 + v62) );
            v63 = (const WCHAR *)sourceString;
            if ( v103 > 7 )
              v63 = sourceString[0];
            v64 = WindowsCreateString(v63, v62, &v94);
            if ( v64 < 0 )
            {
              v100 = (HSTRING)".\\userauthmanager.cpp";
              LODWORD(v101) = 117;
              v65 = cdp::MakeException<cdp::hresult_exception>(v99, &v100, (unsigned int)v64);
              cdp::CdpThrow<cdp::hresult_exception>(&v100, v65);
            }
            v97 = 0;
            v66 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v91;
            v67 = **v91;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
            v68 = v67(v66, &GUID_5da3f048_82e8_4c82_8bfd_c389baeda720, &v97);
            if ( v68 < 0 )
            {
              v100 = (HSTRING)".\\userauthmanager.cpp";
              LODWORD(v101) = 120;
              v69 = cdp::MakeException<cdp::hresult_exception,>(
                      v99,
                      &v100,
                      (unsigned int)v68,
                      "Couldn't convert ISignInContext to ISignInContext2");
              cdp::CdpThrow<cdp::hresult_exception>(&v100, v69);
            }
            v70 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v97 + 56LL))(v97, v94);
            if ( v70 < 0 )
            {
              v100 = (HSTRING)".\\userauthmanager.cpp";
              LODWORD(v101) = 122;
              v71 = cdp::MakeException<cdp::hresult_exception,>(
                      v99,
                      &v100,
                      (unsigned int)v70,
                      "Couldn't put correlationId into signInContext");
              cdp::CdpThrow<cdp::hresult_exception>(&v100, v71);
            }
            v72 = *(_QWORD *)(a1 + 136);
            v73 = *(__int64 (__fastcall **)(__int64, _QWORD, const char **))(*(_QWORD *)v72 + 56LL);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
            v74 = v73(v72, v91, &v87);
            if ( v74 < 0 )
            {
              v100 = (HSTRING)".\\userauthmanager.cpp";
              LODWORD(v101) = 125;
              v75 = cdp::MakeException<cdp::hresult_exception,>(
                      v99,
                      &v100,
                      (unsigned int)v74,
                      "Failed to register callback for user sign in");
              cdp::CdpThrow<cdp::hresult_exception>(&v100, v75);
            }
            v6 = 5;
            v84 = 5;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v97);
            WindowsDeleteString(v94);
            v94 = 0;
            std::wstring::_Tidy_deallocate(sourceString);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v91);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v87);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
            v76 = v86;
            if ( v86 )
            {
              v86 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
            }
          }
          else
          {
            v6 = 2;
            v84 = 2;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v95);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
            v44 = v86;
            if ( v86 )
            {
              v86 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            }
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
          WindowsDeleteString(v90);
          break;
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v95);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v92);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v96);
        v77 = v86;
        if ( v86 )
        {
          v86 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v89);
        WindowsDeleteString(v90);
      }
      *a3 = 0;
      v45 = string;
      if ( string )
      {
        string = 0;
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v45 + 16LL))(v45);
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v98);
    std::wstring::_Tidy_deallocate(v104);
  }
  catch ( ... )
  {
    LODWORD(v79) = GetCurrentThreadId();
    v98 = v79;
    v85 = 153;
    cdp::CatchAllToHR<char const (&)[36],int,unsigned __int64>(
      &v93,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Failed to pair user\"}",
      (unsigned int)".\\userauthmanager.cpp",
      (const char *)&v85,
      (const char *)&v98,
      v80,
      v81);
  }
  return v6;
}

```

## disassembly

```asm
0x1801edd9c  mov     r11, rsp
0x1801edd9f  push    rbx
0x1801edda0  push    rsi
0x1801edda1  push    rdi
0x1801edda2  push    r12
0x1801edda4  push    r13
0x1801edda6  push    r14
0x1801edda8  push    r15
0x1801eddaa  sub     rsp, 190h
0x1801eddb1  mov     rax, cs:__security_cookie
0x1801eddb8  xor     rax, rsp
0x1801eddbb  mov     [rsp+1C8h+var_40], rax
0x1801eddc3  mov     r12, r8
0x1801eddc6  mov     r15, rdx
0x1801eddc9  mov     r13, rcx
0x1801eddcc  xor     edi, edi
0x1801eddce  mov     [rsp+1C8h+var_128], edi
0x1801eddd5  lea     esi, [rdi+1]
0x1801eddd8  mov     [rsp+1C8h+var_168], esi
0x1801edddc  lea     rcx, [r11-60h]
0x1801edde0  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x1801edde5  nop
0x1801edde6  lea     rdx, [rsp+1C8h+var_60]
0x1801eddee  cmp     [rsp+1C8h+var_48], 7
0x1801eddf7  cmova   rdx, [rsp+1C8h+var_60]
0x1801ede00  lea     rcx, [rsp+1C8h+sourceString]
0x1801ede08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801ede0d  nop
0x1801ede0e  lea     r8, [rsp+1C8h+sourceString]
0x1801ede16  lea     rdx, [rsp+1C8h+var_100]
0x1801ede1e  mov     rcx, r13
0x1801ede21  call    ?GetSignedInUserForXuid@XboxUserManagerProxy@UserAuthManager@cdp@@QEAA?AV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; cdp::UserAuthManager::XboxUserManagerProxy::GetSignedInUserForXuid(std::wstring const &)
0x1801ede26  nop
0x1801ede27  lea     rcx, [rsp+1C8h+sourceString]
0x1801ede2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ede34  mov     rbx, [rsp+1C8h+var_100]
0x1801ede3c  mov     [rsp+1C8h+string], rdi
0x1801ede41  test    rbx, rbx
0x1801ede44  jz      loc_1801EDF3B
0x1801ede4a  mov     rax, [rbx]
0x1801ede4d  mov     rdi, [rax+30h]
0x1801ede51  xor     ecx, ecx; string
0x1801ede53  call    cs:__imp_WindowsDeleteString
0x1801ede59  mov     [rsp+1C8h+string], 0
0x1801ede62  lea     rdx, [rsp+1C8h+string]
0x1801ede67  mov     rcx, rbx
0x1801ede6a  mov     rax, rdi
0x1801ede6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ede72  test    eax, eax
0x1801ede74  jns     short loc_1801EDEB5
0x1801ede76  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ede7d  mov     [rsp+1C8h+var_158], rcx
0x1801ede82  mov     [rsp+1C8h+var_150], 8Eh
0x1801ede8a  lea     r9, aCouldnTGetNonr; "Couldn't get nonRoamableUserId from exi"...
0x1801ede91  mov     r8d, eax
0x1801ede94  lea     rdx, [rsp+1C8h+var_158]
0x1801ede99  lea     rcx, [rsp+1C8h+sourceString]
0x1801edea1  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801edea6  nop
0x1801edea7  mov     rdx, rax
0x1801edeaa  lea     rcx, [rsp+1C8h+var_158]
0x1801edeaf  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801edeb5  xor     edx, edx; length
0x1801edeb7  mov     rcx, [rsp+1C8h+string]; string
0x1801edebc  call    cs:__imp_WindowsGetStringRawBuffer
0x1801edec2  xor     r8d, r8d; Radix
0x1801edec5  xor     edx, edx; EndPtr
0x1801edec7  mov     rcx, rax; String
0x1801edeca  call    cs:__imp_wcstoul
0x1801eded0  mov     [r12], eax
0x1801eded4  xor     esi, esi
0x1801eded6  mov     [rsp+1C8h+var_168], esi
0x1801ededa  lea     rdx, [rsp+1C8h+var_C0]
0x1801edee2  mov     rcx, r13
0x1801edee5  call    ?lock@?$weak_ptr@VProximalConnector@cdp@@@std@@QEBA?AV?$shared_ptr@VProximalConnector@cdp@@@2@XZ; std::weak_ptr<cdp::ProximalConnector>::lock(void)
0x1801edeea  nop
0x1801edeeb  mov     rbx, [rsp+1C8h+var_C0]
0x1801edef3  test    rbx, rbx
0x1801edef6  jz      short loc_1801EDF18
0x1801edef8  mov     rdx, r15
0x1801edefb  lea     rcx, [rsp+1C8h+sourceString]
0x1801edf03  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1801edf08  mov     r8, rax
0x1801edf0b  mov     edx, [r12]
0x1801edf0f  mov     rcx, rbx
0x1801edf12  call    ?OnXboxUserSignIn@UserAuthManager@cdp@@AEAAXIV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::UserAuthManager::OnXboxUserSignIn(uint,std::string)
0x1801edf17  nop
0x1801edf18  mov     rcx, [rsp+1C8h+var_B8]; this
0x1801edf20  test    rcx, rcx
0x1801edf23  jz      short loc_1801EDF2B
0x1801edf25  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801edf2a  nop
0x1801edf2b  mov     rcx, [rsp+1C8h+string]; string
0x1801edf30  call    cs:__imp_WindowsDeleteString
0x1801edf36  jmp     loc_1801EE48B
0x1801edf3b  mov     [rsp+1C8h+var_164], edi
0x1801edf3f  mov     rcx, [r13+80h]
0x1801edf46  mov     rax, [rcx]
0x1801edf49  lea     rdx, [rsp+1C8h+string]
0x1801edf4e  mov     rax, [rax+58h]
0x1801edf52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801edf57  test    eax, eax
0x1801edf59  jns     short loc_1801EDF9A
0x1801edf5b  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801edf62  mov     [rsp+1C8h+var_158], rcx
0x1801edf67  mov     [rsp+1C8h+var_150], 43h ; 'C'
0x1801edf6f  lea     r9, aCouldnTGetCons_0; "Couldn't get console users"
0x1801edf76  mov     r8d, eax
0x1801edf79  lea     rdx, [rsp+1C8h+var_158]
0x1801edf7e  lea     rcx, [rsp+1C8h+sourceString]
0x1801edf86  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801edf8b  nop
0x1801edf8c  mov     rdx, rax
0x1801edf8f  lea     rcx, [rsp+1C8h+var_158]
0x1801edf94  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801edf9a  mov     rcx, [rsp+1C8h+string]
0x1801edf9f  mov     rax, [rcx]
0x1801edfa2  lea     rdx, [rsp+1C8h+var_164]
0x1801edfa7  mov     rax, [rax+38h]
0x1801edfab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801edfb0  test    eax, eax
0x1801edfb2  jns     short loc_1801EDFF3
0x1801edfb4  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801edfbb  mov     [rsp+1C8h+var_158], rcx
0x1801edfc0  mov     [rsp+1C8h+var_150], 44h ; 'D'
0x1801edfc8  lea     r9, aCouldnTGetCons; "Couldn't get console users size"
0x1801edfcf  mov     r8d, eax
0x1801edfd2  lea     rdx, [rsp+1C8h+var_158]
0x1801edfd7  lea     rcx, [rsp+1C8h+sourceString]
0x1801edfdf  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801edfe4  nop
0x1801edfe5  mov     rdx, rax
0x1801edfe8  lea     rcx, [rsp+1C8h+var_158]
0x1801edfed  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801edff3  mov     r14d, edi
0x1801edff6  cmp     r14d, [rsp+1C8h+var_164]
0x1801edffb  jnb     loc_1801EE46B
0x1801ee001  mov     [rsp+1C8h+var_140], rdi
0x1801ee009  mov     [rsp+1C8h+var_148], rdi
0x1801ee011  mov     [rsp+1C8h+var_160], rdi
0x1801ee016  mov     [rsp+1C8h+var_110], rdi
0x1801ee01e  mov     [rsp+1C8h+var_130], rdi
0x1801ee026  mov     [rsp+1C8h+var_118], rdi
0x1801ee02e  mov     rcx, [rsp+1C8h+string]
0x1801ee033  mov     rax, [rcx]
0x1801ee036  lea     r8, [rsp+1C8h+var_148]
0x1801ee03e  mov     edx, r14d
0x1801ee041  mov     rax, [rax+30h]
0x1801ee045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee04a  test    eax, eax
0x1801ee04c  jns     short loc_1801EE099
0x1801ee04e  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee055  mov     [rsp+1C8h+var_C0], rcx
0x1801ee05d  mov     dword ptr [rsp+1C8h+var_B8], 50h ; 'P'
0x1801ee068  lea     r9, aCouldnTCopyXbo; "Couldn't copy xbox user data out"
0x1801ee06f  mov     r8d, eax
0x1801ee072  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee07a  lea     rcx, [rsp+1C8h+var_F8]
0x1801ee082  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801ee087  nop
0x1801ee088  mov     rdx, rax
0x1801ee08b  lea     rcx, [rsp+1C8h+var_C0]
0x1801ee093  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801ee099  mov     rcx, [rsp+1C8h+var_148]
0x1801ee0a1  mov     rax, [rcx]
0x1801ee0a4  mov     rdx, r12
0x1801ee0a7  mov     rax, [rax+30h]
0x1801ee0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee0b0  test    eax, eax
0x1801ee0b2  jns     short loc_1801EE0FF
0x1801ee0b4  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee0bb  mov     [rsp+1C8h+var_C0], rcx
0x1801ee0c3  mov     dword ptr [rsp+1C8h+var_B8], 51h ; 'Q'
0x1801ee0ce  lea     r9, aCouldnTGetCons_1; "Couldn't get consoleUserId"
0x1801ee0d5  mov     r8d, eax
0x1801ee0d8  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee0e0  lea     rcx, [rsp+1C8h+var_F8]
0x1801ee0e8  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801ee0ed  nop
0x1801ee0ee  mov     rdx, rax
0x1801ee0f1  lea     rcx, [rsp+1C8h+var_C0]
0x1801ee0f9  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801ee0ff  mov     rcx, [rsp+1C8h+var_148]
0x1801ee107  mov     rax, [rcx]
0x1801ee10a  lea     rdx, [rsp+1C8h+var_178]
0x1801ee10f  mov     rax, [rax+50h]
0x1801ee113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee118  test    eax, eax
0x1801ee11a  jns     short loc_1801EE167
0x1801ee11c  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee123  mov     [rsp+1C8h+var_C0], rcx
0x1801ee12b  mov     dword ptr [rsp+1C8h+var_B8], 52h ; 'R'
0x1801ee136  lea     r9, aCouldnTGetCred; "Couldn't get credentials persisted flag"
0x1801ee13d  mov     r8d, eax
0x1801ee140  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee148  lea     rcx, [rsp+1C8h+var_F8]
0x1801ee150  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801ee155  nop
0x1801ee156  mov     rdx, rax
0x1801ee159  lea     rcx, [rsp+1C8h+var_C0]
0x1801ee161  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801ee167  mov     rcx, [rsp+1C8h+var_148]
0x1801ee16f  mov     rax, [rcx]
0x1801ee172  lea     rdx, [rsp+1C8h+var_160]
0x1801ee177  mov     rax, [rax+58h]
0x1801ee17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee180  test    eax, eax
0x1801ee182  jns     short loc_1801EE1CF
0x1801ee184  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee18b  mov     [rsp+1C8h+var_C0], rcx
0x1801ee193  mov     dword ptr [rsp+1C8h+var_B8], 54h ; 'T'
0x1801ee19e  lea     r9, aCouldnTGetProp_0; "Couldn't get Properties"
0x1801ee1a5  mov     r8d, eax
0x1801ee1a8  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee1b0  lea     rcx, [rsp+1C8h+var_F8]
0x1801ee1b8  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801ee1bd  nop
0x1801ee1be  mov     rdx, rax
0x1801ee1c1  lea     rcx, [rsp+1C8h+var_C0]
0x1801ee1c9  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801ee1cf  lea     rdx, [rsp+1C8h+var_110]
0x1801ee1d7  lea     rcx, [rsp+1C8h+var_160]
0x1801ee1dc  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1801ee1e1  test    eax, eax
0x1801ee1e3  jns     short loc_1801EE230
0x1801ee1e5  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee1ec  mov     [rsp+1C8h+var_C0], rcx
0x1801ee1f4  mov     dword ptr [rsp+1C8h+var_B8], 55h ; 'U'
0x1801ee1ff  lea     r9, aCouldnTGetProp; "Couldn't get Properties as PropertyMap"
0x1801ee206  mov     r8d, eax
0x1801ee209  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee211  lea     rcx, [rsp+1C8h+var_F8]
0x1801ee219  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801ee21e  nop
0x1801ee21f  mov     rdx, rax
0x1801ee222  lea     rcx, [rsp+1C8h+var_C0]
0x1801ee22a  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801ee230  mov     rdi, [rsp+1C8h+var_110]
0x1801ee238  mov     rax, [rdi]
0x1801ee23b  mov     rbx, [rax+30h]
0x1801ee23f  lea     rcx, [rsp+1C8h+var_130]
0x1801ee247  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1801ee24c  lea     rcx, [rsp+1C8h+var_C0]; string
0x1801ee254  call    ??$?0$0L@@StringReference@Internal@Windows@@QEAA@AEAY0L@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[11])
0x1801ee259  lea     r8, [rsp+1C8h+var_130]
0x1801ee261  mov     rdx, [rax]
0x1801ee264  mov     rcx, rdi
0x1801ee267  mov     rax, rbx
0x1801ee26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee26f  test    eax, eax
0x1801ee271  jns     short loc_1801EE2BE
0x1801ee273  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee27a  mov     [rsp+1C8h+var_C0], rcx
0x1801ee282  mov     dword ptr [rsp+1C8h+var_B8], 56h ; 'V'
0x1801ee28d  lea     r9, aCouldnTGetXuid_0; "Couldn't get xuid"
0x1801ee294  mov     r8d, eax
0x1801ee297  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee29f  lea     rcx, [rsp+1C8h+var_F8]
0x1801ee2a7  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801ee2ac  nop
0x1801ee2ad  mov     rdx, rax
0x1801ee2b0  lea     rcx, [rsp+1C8h+var_C0]
0x1801ee2b8  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801ee2be  lea     rdx, [rsp+1C8h+var_118]
0x1801ee2c6  lea     rcx, [rsp+1C8h+var_130]
0x1801ee2ce  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x1801ee2d3  test    eax, eax
0x1801ee2d5  jns     short loc_1801EE322
0x1801ee2d7  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee2de  mov     [rsp+1C8h+var_C0], rcx
0x1801ee2e6  mov     dword ptr [rsp+1C8h+var_B8], 57h ; 'W'
0x1801ee2f1  lea     r9, aCouldnTConvert_0; "Couldn't convert inspectable to propval"...
0x1801ee2f8  mov     r8d, eax
0x1801ee2fb  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee303  lea     rcx, [rsp+1C8h+var_F8]
0x1801ee30b  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1801ee310  nop
0x1801ee311  mov     rdx, rax
0x1801ee314  lea     rcx, [rsp+1C8h+var_C0]
0x1801ee31c  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1801ee322  mov     rdi, [rsp+1C8h+var_118]
0x1801ee32a  mov     rax, [rdi]
0x1801ee32d  mov     rbx, [rax+98h]
0x1801ee334  mov     rcx, [rsp+1C8h+var_140]; string
0x1801ee33c  call    cs:__imp_WindowsDeleteString
0x1801ee342  mov     [rsp+1C8h+var_140], 0
0x1801ee34e  lea     rdx, [rsp+1C8h+var_140]
0x1801ee356  mov     rcx, rdi
0x1801ee359  mov     rax, rbx
0x1801ee35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ee361  xor     edi, edi
0x1801ee363  test    eax, eax
0x1801ee365  jns     short loc_1801EE3B2
0x1801ee367  lea     rcx, aUserauthmanage; ".\\userauthmanager.cpp"
0x1801ee36e  mov     [rsp+1C8h+var_C0], rcx
0x1801ee376  mov     dword ptr [rsp+1C8h+var_B8], 58h ; 'X'
0x1801ee381  lea     r9, aCouldnTGetXuid; "Couldn't get xuid string."
0x1801ee388  mov     r8d, eax
0x1801ee38b  lea     rdx, [rsp+1C8h+var_C0]
0x1801ee393  lea     rcx, [rsp+1C8h+var_F8]
  ... truncated ...
```
