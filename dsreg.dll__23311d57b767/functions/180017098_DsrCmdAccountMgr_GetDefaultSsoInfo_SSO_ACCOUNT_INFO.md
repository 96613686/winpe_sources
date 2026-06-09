# DsrCmdAccountMgr::GetDefaultSsoInfo(SSO_ACCOUNT_INFO &)

- ea: `0x180017098`
- end: `0x18001771b`
- name: `?GetDefaultSsoInfo@DsrCmdAccountMgr@@SAJAEAUSSO_ACCOUNT_INFO@@@Z`
- size: `1667`
- prototype: `__int64 __fastcall(struct SSO_ACCOUNT_INFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180016510`

## callees

- `0x180012948`
- `0x180012c7c`
- `0x18001378c`
- `0x180016b90`
- `0x180017098`
- `0x18002b9b4`
- `0x180031a20`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800abc0c`
- `0x1800abc5c`
- `0x1800abcac`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017136`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017592`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017136`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017592`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800174be`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800174be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800175e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800175e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800175a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800175a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001740c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001744f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017612`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017366`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001740c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001744f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017612`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800174e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001750f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800175b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800174e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001750f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800175b1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001715a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001715a`

## string_xrefs

- `0x180017119`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x180017215`: `%s: tokenBrokerInspectable.As failed 0x%08x.\n`
- `0x18001727b`: `%s: BlockOnCompletionAndGetResults failed 0x%08x.\n`
- `0x180017255`: `%s: tokenBroker->GetDefaultSignInAccountAsync failed 0x%08x.\n`
- `0x1800174cf`: `%s: StringFromCLSID failed 0x%08x.\n`
- `0x1800174a9`: `%s: tokenBroker->GetWebAccountProviderGuid failed 0x%08x.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall DsrCmdAccountMgr::GetDefaultSsoInfo(struct SSO_ACCOUNT_INFO *a1)
{
  HRESULT v2; // eax
  HSTRING v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  int ActivationFactory; // ebx
  _BYTE **CurrentRef; // rax
  const wchar_t *v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rdx
  _QWORD *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, HSTRING *); // rbx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v44)(_QWORD, GUID *, __int64); // rbx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v50)(_QWORD, GUID *, __int64); // rbx
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, HSTRING *); // rbx
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v62; // rax
  PCWSTR v63; // rax
  __int64 v64; // rax
  PCWSTR v65; // rax
  __int64 v66; // rax
  const WCHAR *v67; // rsi
  unsigned __int64 v68; // rdi
  PCWSTR v69; // rax
  __int64 v70; // rax
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 (__fastcall ***v74)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v75; // rcx
  __int64 (__fastcall ***v76)(_QWORD, GUID *, __int64); // rcx
  __int64 v77; // rcx
  __int64 (__fastcall ***v78)(_QWORD, GUID *, __int64); // rcx
  __int64 (__fastcall ***v80)(_QWORD, GUID *, __int64); // [rsp+20h] [rbp-E0h] BYREF
  __int64 (__fastcall ***v81)(_QWORD, GUID *, __int64); // [rsp+28h] [rbp-D8h] BYREF
  HSTRING v82; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v83; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v84; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v85; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v86; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v87)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v88; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v89; // [rsp+68h] [rbp-98h] BYREF
  __int64 v90; // [rsp+70h] [rbp-90h] BYREF
  LPOLESTR lpsz; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v92; // [rsp+80h] [rbp-80h] BYREF
  HSTRING_HEADER v93; // [rsp+88h] [rbp-78h] BYREF
  IID rclsid; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING string; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v97[32]; // [rsp+D0h] [rbp-30h] BYREF

  v81 = 0;
  v90 = 0;
  v80 = 0;
  v89 = 0;
  v87 = 0;
  v85 = 0;
  v88 = 0;
  v86 = 0;
  v84 = 0;
  v83 = 0;
  v82 = 0;
  rclsid = GUID_NULL;
  lpsz = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
    RaiseException(v2, 1u, 0, 0);
  v3 = string;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v87);
  ActivationFactory = RoGetActivationFactory(v3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, &v87);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v5, v4);
    v8 = L"%s: GetActivationFactory failed 0x%08x.\n";
    goto LABEL_5;
  }
  v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
  v17 = **v87;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v85);
  ActivationFactory = v17(v16, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v85);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v19, v18);
    v8 = L"%s: tokenBrokerInspectable.As failed 0x%08x.\n";
    goto LABEL_5;
  }
  v20 = v85;
  v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 232LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v86);
  ActivationFactory = v21(v20, &v86);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v23, v22);
    v8 = L"%s: tokenBroker->GetDefaultSignInAccountAsync failed 0x%08x.\n";
    goto LABEL_5;
  }
  ActivationFactory = BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(
                        v86,
                        (__int64)&v88);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v25, v24);
    v8 = L"%s: BlockOnCompletionAndGetResults failed 0x%08x.\n";
    goto LABEL_5;
  }
  v26 = v88;
  v27 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v88 + 48LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v81);
  ActivationFactory = v27(v26, &v81);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v29, v28);
    v8 = L"%s: defaultAccountResult->get_DefaultWebAccount failed 0x%08x.\n";
    goto LABEL_5;
  }
  if ( !v81 )
  {
    ActivationFactory = -2145648563;
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v29, v28) )
    {
      wprintf(L"get_DefaultWebAccount returned nullptr. Default account is NOT set.\n");
      v32 = (_QWORD *)CmdOptions::GetCurrentRef(v31, v30);
      if ( *(_BYTE *)(*v32 + 12LL) )
      {
        v34 = (_QWORD *)CmdOptions::GetCurrentRef(*v32, v33);
        if ( *(_QWORD *)(*v34 + 184LL) )
        {
          v36 = CmdOptions::GetCurrentRef(v35, *v34);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v36 + 184LL),
            L"get_DefaultWebAccount returned nullptr. Default account is NOT set.\n");
        }
      }
    }
    Logger::TraceInformation(L"get_DefaultWebAccount returned nullptr. Default account is NOT set.\n");
    goto LABEL_45;
  }
  ActivationFactory = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                        &v81,
                        (__int64)&v90);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v38, v37);
    v8 = L"%s: account.As failed 0x%08x.\n";
    goto LABEL_5;
  }
  v39 = v90;
  v40 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v90 + 48LL);
  WindowsDeleteString(v84);
  v84 = 0;
  ActivationFactory = v40(v39, &v84);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v42, v41);
    v8 = L"%s: account2->get_Id failed 0x%08x.\n";
    goto LABEL_5;
  }
  v43 = v81;
  v44 = (*v81)[6];
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v80);
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))v44)(
                        v43,
                        &v80);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v46, v45);
    v8 = L"%s: account->get_WebAccountProvider failed 0x%08x.\n";
    goto LABEL_5;
  }
  ActivationFactory = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(
                        &v80,
                        (__int64)&v89);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v48, v47);
    v8 = L"%s: provider.As failed 0x%08x.\n";
    goto LABEL_5;
  }
  v49 = v80;
  v50 = (*v80)[6];
  WindowsDeleteString(v83);
  v83 = 0;
  ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))v50)(
                        v49,
                        &v83);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v52, v51);
    v8 = L"%s: provider->get_Id failed 0x%08x.\n";
    goto LABEL_5;
  }
  v53 = v89;
  v54 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v89 + 56LL);
  WindowsDeleteString(v82);
  v82 = 0;
  ActivationFactory = v54(v53, &v82);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v56, v55);
    v8 = L"%s: provider2->get_Authority failed 0x%08x.\n";
    goto LABEL_5;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, IID *))(*(_QWORD *)v85 + 264LL))(v85, v80, &rclsid);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v58, v57);
    v8 = L"%s: tokenBroker->GetWebAccountProviderGuid failed 0x%08x.\n";
    goto LABEL_5;
  }
  ActivationFactory = StringFromCLSID(&rclsid, &lpsz);
  if ( ActivationFactory < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v60, v59);
    v8 = L"%s: StringFromCLSID failed 0x%08x.\n";
LABEL_5:
    if ( **CurrentRef )
    {
      wprintf(v8, L"DsrCmdAccountMgr::GetDefaultSsoInfo", (unsigned int)ActivationFactory);
      v11 = (_QWORD *)CmdOptions::GetCurrentRef(v10, v9);
      if ( *(_BYTE *)(*v11 + 12LL) )
      {
        v13 = (_QWORD *)CmdOptions::GetCurrentRef(*v11, v12);
        if ( *(_QWORD *)(*v13 + 184LL) )
        {
          v15 = CmdOptions::GetCurrentRef(*v13, v14);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v15 + 184LL),
            v8,
            L"DsrCmdAccountMgr::GetDefaultSsoInfo",
            (unsigned int)ActivationFactory);
        }
      }
    }
    Logger::TraceInformation(v8, L"DsrCmdAccountMgr::GetDefaultSsoInfo", (unsigned int)ActivationFactory);
    goto LABEL_45;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v84, 0);
  v62 = std::wstring::wstring((__int64)&v92, (__int64)StringRawBuffer);
  std::wstring::operator=((__int64)a1, v62);
  std::wstring::_Tidy_deallocate((__int64)&v92);
  v63 = WindowsGetStringRawBuffer(v82, 0);
  v64 = std::wstring::wstring((__int64)&v92, (__int64)v63);
  std::wstring::operator=((__int64)a1 + 96, v64);
  std::wstring::_Tidy_deallocate((__int64)&v92);
  v65 = WindowsGetStringRawBuffer(v83, 0);
  v66 = std::wstring::wstring((__int64)&v92, (__int64)v65);
  std::wstring::operator=((__int64)a1 + 32, v66);
  std::wstring::_Tidy_deallocate((__int64)&v92);
  v67 = lpsz;
  v68 = -1;
  do
    ++v68;
  while ( lpsz[v68] );
  if ( v68 > 0xFFFFFFFF )
  {
    LODWORD(v68) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v67, v68, &v93, &v92);
  v69 = WindowsGetStringRawBuffer(v92, 0);
  v70 = std::wstring::wstring((__int64)v97, (__int64)v69);
  std::wstring::operator=((__int64)a1 + 64, v70);
  std::wstring::_Tidy_deallocate((__int64)v97);
LABEL_45:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  string = 0;
  WindowsDeleteString(v82);
  v82 = 0;
  WindowsDeleteString(v83);
  v83 = 0;
  WindowsDeleteString(v84);
  v84 = 0;
  v71 = v86;
  if ( v86 )
  {
    v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  }
  v72 = v88;
  if ( v88 )
  {
    v88 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
  }
  v73 = v85;
  if ( v85 )
  {
    v85 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
  }
  v74 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v87;
  if ( v87 )
  {
    v87 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v74)[2])(v74);
  }
  v75 = v89;
  if ( v89 )
  {
    v89 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  }
  v76 = v80;
  if ( v80 )
  {
    v80 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v76)[2])(v76);
  }
  v77 = v90;
  if ( v90 )
  {
    v90 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
  }
  v78 = v81;
  if ( v81 )
  {
    v81 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v78)[2])(v78);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180017098  push    rbp
0x18001709a  push    rbx
0x18001709b  push    rsi
0x18001709c  push    rdi
0x18001709d  push    r14
0x18001709f  push    r15
0x1800170a1  lea     rbp, [rsp-8]
0x1800170a6  sub     rsp, 108h
0x1800170ad  mov     rax, cs:__security_cookie
0x1800170b4  xor     rax, rsp
0x1800170b7  mov     [rbp+30h+var_40], rax
0x1800170bb  mov     r14, rcx
0x1800170be  xor     r15d, r15d
0x1800170c1  mov     [rsp+130h+var_108], r15
0x1800170c6  mov     [rsp+130h+var_C0], r15
0x1800170cb  mov     [rsp+130h+var_110], r15
0x1800170d0  mov     [rsp+130h+var_C8], r15
0x1800170d5  mov     [rsp+130h+var_D8], r15
0x1800170da  mov     [rsp+130h+var_E8], r15
0x1800170df  mov     [rsp+130h+var_D0], r15
0x1800170e4  mov     [rsp+130h+var_E0], r15
0x1800170e9  mov     [rsp+130h+var_F0], r15
0x1800170ee  mov     [rsp+130h+var_F8], r15
0x1800170f3  mov     [rsp+130h+var_100], r15
0x1800170f8  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800170ff  movdqu  xmmword ptr [rbp+30h+rclsid.Data1], xmm0
0x180017104  mov     [rsp+130h+lpsz], r15
0x180017109  mov     [rbp+30h+string], r15
0x18001710d  lea     r9, [rbp+30h+string]; string
0x180017111  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180017115  lea     edx, [r15+40h]; length
0x180017119  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180017120  call    cs:__imp_WindowsCreateStringReference
0x180017126  test    eax, eax
0x180017128  jns     short loc_18001713D
0x18001712a  xor     r9d, r9d; lpArguments
0x18001712d  xor     r8d, r8d; nNumberOfArguments
0x180017130  lea     edx, [r15+1]; dwExceptionFlags
0x180017134  mov     ecx, eax; dwExceptionCode
0x180017136  call    cs:__imp_RaiseException
0x18001713c  nop
0x18001713d  mov     rbx, [rbp+30h+string]
0x180017141  lea     rcx, [rsp+130h+var_D8]
0x180017146  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18001714b  lea     r8, [rsp+130h+var_D8]
0x180017150  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180017157  mov     rcx, rbx
0x18001715a  call    cs:__imp_RoGetActivationFactory
0x180017160  mov     ebx, eax
0x180017162  test    eax, eax
0x180017164  jns     short loc_1800171DE
0x180017166  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18001716b  lea     rsi, aSGetactivation; "%s: GetActivationFactory failed 0x%08x."...
0x180017172  mov     rcx, [rax]
0x180017175  lea     rdi, aDsrcmdaccountm_0; "DsrCmdAccountMgr::GetDefaultSsoInfo"
0x18001717c  cmp     [rcx], r15b
0x18001717f  jz      short loc_1800171CB
0x180017181  mov     r8d, ebx
0x180017184  mov     rdx, rdi
0x180017187  mov     rcx, rsi; Format
0x18001718a  call    wprintf
0x18001718f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180017194  mov     rcx, [rax]
0x180017197  cmp     [rcx+0Ch], r15b
0x18001719b  jz      short loc_1800171CB
0x18001719d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800171a2  mov     rcx, [rax]
0x1800171a5  cmp     [rcx+0B8h], r15
0x1800171ac  jz      short loc_1800171CB
0x1800171ae  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800171b3  mov     rcx, [rax]
0x1800171b6  mov     r9d, ebx
0x1800171b9  mov     r8, rdi
0x1800171bc  mov     rdx, rsi; Format
0x1800171bf  mov     rcx, [rcx+0B8h]; Stream
0x1800171c6  call    fwprintf_s
0x1800171cb  mov     r8d, ebx
0x1800171ce  mov     rdx, rdi
0x1800171d1  mov     rcx, rsi; unsigned __int16 *
0x1800171d4  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800171d9  jmp     loc_1800175D8
0x1800171de  mov     rbx, [rsp+130h+var_D8]
0x1800171e3  mov     rax, [rbx]
0x1800171e6  mov     rdi, [rax]
0x1800171e9  lea     rcx, [rsp+130h+var_E8]
0x1800171ee  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800171f3  lea     r8, [rsp+130h+var_E8]
0x1800171f8  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x1800171ff  mov     rcx, rbx
0x180017202  mov     rax, rdi
0x180017205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001720a  mov     ebx, eax
0x18001720c  test    eax, eax
0x18001720e  jns     short loc_180017221
0x180017210  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180017215  lea     rsi, aSTokenbrokerin; "%s: tokenBrokerInspectable.As failed 0x"...
0x18001721c  jmp     loc_180017172
0x180017221  mov     rdi, [rsp+130h+var_E8]
0x180017226  mov     rax, [rdi]
0x180017229  mov     rbx, [rax+0E8h]
0x180017230  lea     rcx, [rsp+130h+var_E0]
0x180017235  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18001723a  lea     rdx, [rsp+130h+var_E0]
0x18001723f  mov     rcx, rdi
0x180017242  mov     rax, rbx
0x180017245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001724a  mov     ebx, eax
0x18001724c  test    eax, eax
0x18001724e  jns     short loc_180017261
0x180017250  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180017255  lea     rsi, aSTokenbrokerGe; "%s: tokenBroker->GetDefaultSignInAccoun"...
0x18001725c  jmp     loc_180017172
0x180017261  lea     rdx, [rsp+130h+var_D0]
0x180017266  mov     rcx, [rsp+130h+var_E0]
0x18001726b  call    ??$BlockOnCompletionAndGetResults@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@UIGetDefaultSignInAccountResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>>,tagCOWAIT_FLAGS,void *)
0x180017270  mov     ebx, eax
0x180017272  test    eax, eax
0x180017274  jns     short loc_180017287
0x180017276  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18001727b  lea     rsi, aSBlockoncomple; "%s: BlockOnCompletionAndGetResults fail"...
0x180017282  jmp     loc_180017172
0x180017287  mov     rdi, [rsp+130h+var_D0]
0x18001728c  mov     rax, [rdi]
0x18001728f  mov     rbx, [rax+30h]
0x180017293  lea     rcx, [rsp+130h+var_108]
0x180017298  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18001729d  lea     rdx, [rsp+130h+var_108]
0x1800172a2  mov     rcx, rdi
0x1800172a5  mov     rax, rbx
0x1800172a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ad  mov     ebx, eax
0x1800172af  test    eax, eax
0x1800172b1  jns     short loc_1800172C4
0x1800172b3  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800172b8  lea     rsi, aSDefaultaccoun; "%s: defaultAccountResult->get_DefaultWe"...
0x1800172bf  jmp     loc_180017172
0x1800172c4  cmp     [rsp+130h+var_108], r15
0x1800172c9  jnz     short loc_18001732F
0x1800172cb  mov     ebx, 801C004Dh
0x1800172d0  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800172d5  mov     rcx, [rax]
0x1800172d8  lea     rdi, aGetDefaultweba; "get_DefaultWebAccount returned nullptr."...
0x1800172df  cmp     [rcx], r15b
0x1800172e2  jz      short loc_180017322
0x1800172e4  mov     rcx, rdi; Format
0x1800172e7  call    wprintf
0x1800172ec  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800172f1  mov     rcx, [rax]
0x1800172f4  cmp     [rcx+0Ch], r15b
0x1800172f8  jz      short loc_180017322
0x1800172fa  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800172ff  mov     rdx, [rax]
0x180017302  cmp     [rdx+0B8h], r15
0x180017309  jz      short loc_180017322
0x18001730b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180017310  mov     rcx, [rax]
0x180017313  mov     rdx, rdi; Format
0x180017316  mov     rcx, [rcx+0B8h]; Stream
0x18001731d  call    fwprintf_s
0x180017322  mov     rcx, rdi; unsigned __int16 *
0x180017325  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18001732a  jmp     loc_1800175D8
0x18001732f  lea     rdx, [rsp+130h+var_C0]
0x180017334  lea     rcx, [rsp+130h+var_108]
0x180017339  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x18001733e  mov     ebx, eax
0x180017340  test    eax, eax
0x180017342  jns     short loc_180017355
0x180017344  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180017349  lea     rsi, aSAccountAsFail; "%s: account.As failed 0x%08x.\n"
0x180017350  jmp     loc_180017172
0x180017355  mov     rdi, [rsp+130h+var_C0]
0x18001735a  mov     rax, [rdi]
0x18001735d  mov     rbx, [rax+30h]
0x180017361  mov     rcx, [rsp+130h+var_F0]; string
0x180017366  call    cs:__imp_WindowsDeleteString
0x18001736c  mov     [rsp+130h+var_F0], r15
0x180017371  lea     rdx, [rsp+130h+var_F0]
0x180017376  mov     rcx, rdi
0x180017379  mov     rax, rbx
0x18001737c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017381  mov     ebx, eax
0x180017383  test    eax, eax
0x180017385  jns     short loc_180017398
0x180017387  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18001738c  lea     rsi, aSAccount2GetId; "%s: account2->get_Id failed 0x%08x.\n"
0x180017393  jmp     loc_180017172
0x180017398  mov     rdi, [rsp+130h+var_108]
0x18001739d  mov     rax, [rdi]
0x1800173a0  mov     rbx, [rax+30h]
0x1800173a4  lea     rcx, [rsp+130h+var_110]
0x1800173a9  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800173ae  lea     rdx, [rsp+130h+var_110]
0x1800173b3  mov     rcx, rdi
0x1800173b6  mov     rax, rbx
0x1800173b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173be  mov     ebx, eax
0x1800173c0  test    eax, eax
0x1800173c2  jns     short loc_1800173D5
0x1800173c4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800173c9  lea     rsi, aSAccountGetWeb; "%s: account->get_WebAccountProvider fai"...
0x1800173d0  jmp     loc_180017172
0x1800173d5  lea     rdx, [rsp+130h+var_C8]
0x1800173da  lea     rcx, [rsp+130h+var_110]
0x1800173df  call    ??$As@UIWebAccountProvider2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProvider2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider2>>)
0x1800173e4  mov     ebx, eax
0x1800173e6  test    eax, eax
0x1800173e8  jns     short loc_1800173FB
0x1800173ea  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800173ef  lea     rsi, aSProviderAsFai; "%s: provider.As failed 0x%08x.\n"
0x1800173f6  jmp     loc_180017172
0x1800173fb  mov     rdi, [rsp+130h+var_110]
0x180017400  mov     rax, [rdi]
0x180017403  mov     rbx, [rax+30h]
0x180017407  mov     rcx, [rsp+130h+var_F8]; string
0x18001740c  call    cs:__imp_WindowsDeleteString
0x180017412  mov     [rsp+130h+var_F8], r15
0x180017417  lea     rdx, [rsp+130h+var_F8]
0x18001741c  mov     rcx, rdi
0x18001741f  mov     rax, rbx
0x180017422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017427  mov     ebx, eax
0x180017429  test    eax, eax
0x18001742b  jns     short loc_18001743E
0x18001742d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180017432  lea     rsi, aSProviderGetId; "%s: provider->get_Id failed 0x%08x.\n"
0x180017439  jmp     loc_180017172
0x18001743e  mov     rdi, [rsp+130h+var_C8]
0x180017443  mov     rax, [rdi]
0x180017446  mov     rbx, [rax+38h]
0x18001744a  mov     rcx, [rsp+130h+var_100]; string
0x18001744f  call    cs:__imp_WindowsDeleteString
0x180017455  mov     [rsp+130h+var_100], r15
0x18001745a  lea     rdx, [rsp+130h+var_100]
0x18001745f  mov     rcx, rdi
0x180017462  mov     rax, rbx
0x180017465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001746a  mov     ebx, eax
0x18001746c  test    eax, eax
0x18001746e  jns     short loc_180017481
0x180017470  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180017475  lea     rsi, aSProvider2GetA; "%s: provider2->get_Authority failed 0x%"...
0x18001747c  jmp     loc_180017172
0x180017481  mov     rcx, [rsp+130h+var_E8]
0x180017486  mov     rax, [rcx]
0x180017489  lea     r8, [rbp+30h+rclsid]
0x18001748d  mov     rdx, [rsp+130h+var_110]
0x180017492  mov     rax, [rax+108h]
0x180017499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001749e  mov     ebx, eax
0x1800174a0  test    eax, eax
0x1800174a2  jns     short loc_1800174B5
0x1800174a4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800174a9  lea     rsi, aSTokenbrokerGe_0; "%s: tokenBroker->GetWebAccountProviderG"...
0x1800174b0  jmp     loc_180017172
0x1800174b5  lea     rdx, [rsp+130h+lpsz]; lplpsz
0x1800174ba  lea     rcx, [rbp+30h+rclsid]; rclsid
0x1800174be  call    cs:__imp_StringFromCLSID
0x1800174c4  mov     ebx, eax
0x1800174c6  test    eax, eax
0x1800174c8  jns     short loc_1800174DB
0x1800174ca  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800174cf  lea     rsi, aSStringfromcls; "%s: StringFromCLSID failed 0x%08x.\n"
0x1800174d6  jmp     loc_180017172
0x1800174db  xor     edx, edx; length
0x1800174dd  mov     rcx, [rsp+130h+var_F0]; string
0x1800174e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800174e8  mov     rdx, rax
0x1800174eb  lea     rcx, [rbp+30h+var_B0]
0x1800174ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800174f4  mov     rdx, rax
0x1800174f7  mov     rcx, r14
0x1800174fa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800174ff  lea     rcx, [rbp+30h+var_B0]
0x180017503  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017508  xor     edx, edx; length
0x18001750a  mov     rcx, [rsp+130h+var_100]; string
0x18001750f  call    cs:__imp_WindowsGetStringRawBuffer
0x180017515  mov     rdx, rax
0x180017518  lea     rcx, [rbp+30h+var_B0]
0x18001751c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180017521  lea     rcx, [r14+60h]
0x180017525  mov     rdx, rax
0x180017528  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001752d  lea     rcx, [rbp+30h+var_B0]
0x180017531  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017536  xor     edx, edx; length
0x180017538  mov     rcx, [rsp+130h+var_F8]; string
0x18001753d  call    cs:__imp_WindowsGetStringRawBuffer
0x180017543  mov     rdx, rax
0x180017546  lea     rcx, [rbp+30h+var_B0]
0x18001754a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001754f  lea     rcx, [r14+20h]
0x180017553  mov     rdx, rax
0x180017556  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001755b  lea     rcx, [rbp+30h+var_B0]
0x18001755f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017564  mov     rsi, [rsp+130h+lpsz]
0x180017569  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001756d  inc     rdi
  ... truncated ...
```
