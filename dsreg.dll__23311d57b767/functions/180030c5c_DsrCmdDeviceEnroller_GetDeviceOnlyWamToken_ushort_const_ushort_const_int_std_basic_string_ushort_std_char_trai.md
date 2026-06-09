# DsrCmdDeviceEnroller::GetDeviceOnlyWamToken(ushort const *,ushort const *,int,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180030c5c`
- end: `0x1800318e1`
- name: `?GetDeviceOnlyWamToken@DsrCmdDeviceEnroller@@QEAAJPEBG0HAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `3205`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, void *Src)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099424`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18002dd24`
- `0x180030c5c`
- `0x1800318e8`
- `0x1800319ac`
- `0x180044300`
- `0x180044d30`
- `0x18004bc80`
- `0x18004bdf0`
- `0x18004c840`
- `0x180067c6c`
- `0x18009fbc0`
- `0x18009ffe4`
- `0x1800a0c14`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800314e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031545`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800316a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003179b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003180a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003183e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800314e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180031545`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800316a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003179b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003180a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003183e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180031521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800316d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800317e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180031521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800316d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800317e6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030dc8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030f7d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030dc8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180030f7d`

## string_xrefs

- `0x180030d25`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x180030dde`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x180030ed8`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x1800310a1`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x18003129b`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x18003133f`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x1800317ca`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x180031816`: `DsrCmdDeviceEnroller::GetDeviceOnlyWamToken`
- `0x180030ebc`: `WaitForCompletionOrTimeoutNoThrow`
- `0x18003127f`: `WaitForCompletionOrTimeoutNoThrow`
- `0x180030ff6`: `IWebTokenRequestFactory::Create`
- `0x180031259`: `IWebAuthenticationCoreManager::GetTokenSilentlyAsync`
- `0x1800312a2`: `%s: GetTokenSilentlyAsync failed with timeout (error code: 0x%08x).`
- `0x1800312f4`: `GetTokenSilentlyAsync::GetResults`
- `0x180030f5e`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x180030da9`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x18003102d`: `IWebTokenRequest::get_Properties`
- `0x1800310fe`: `client_TokenType`
- `0x18003131c`: `WebTokenRequestResult::get_ResponseStatus`
- `0x180031346`: `%s: GetTokenSilently WAM call failed. Status: %ld`
- `0x1800315a2`: `WebTokenRequestResult::InvalidateCacheAsync`
- `0x1800316c6`: `WebTokenResponse::get_Token`
- `0x180031607`: `WebTokenRequestResult::get_ResponseData`
- `0x180031745`: `WebTokenResponse::get_Properties`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall DsrCmdDeviceEnroller::GetDeviceOnlyWamToken(
        _QWORD *a1,
        HSTRING a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        _QWORD *Src)
{
  char *v7; // rcx
  char *v8; // rcx
  _WORD *v9; // rcx
  __int64 v10; // rcx
  int ActivationFactory; // eax
  unsigned int v12; // esi
  const wchar_t *v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64, _QWORD); // rdi
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  int v18; // edx
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, __int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  __int64 v28; // rsi
  __int64 (__fastcall *v29)(__int64, __int64, __int64, char *); // rdi
  __int64 v30; // rbx
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, __int64, __int64, char *); // rdi
  __int64 v33; // rbx
  __int64 v34; // rsi
  __int64 (__fastcall *v35)(__int64, __int64, __int64, char *); // rdi
  HSTRING v36; // rax
  __int64 v37; // rbx
  __int64 v38; // rsi
  __int64 (__fastcall *v39)(__int64, __int64, __int64, char *); // rdi
  __int64 v40; // rbx
  __int64 v41; // rbx
  __int64 (__fastcall *v42)(__int64, __int64, _QWORD); // rdi
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rcx
  int v44; // edx
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v46)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v47; // rcx
  __int64 v48; // rbx
  int (__fastcall *v49)(__int64, _QWORD **); // rdi
  __int64 v50; // rcx
  __int64 v51; // r14
  __int64 v52; // r8
  _QWORD *v53; // rdi
  int (__fastcall *v54)(_QWORD *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v56; // rbx
  __int64 (__fastcall *v57)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rdi
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // rcx
  int v59; // edx
  __int64 v60; // rbx
  __int64 (__fastcall *v61)(__int64, __int64 *); // rdi
  __int64 v62; // rcx
  __int64 v63; // rbx
  __int64 (__fastcall *v64)(__int64, _QWORD, __int64 *); // rdi
  __int64 v65; // rcx
  __int64 v66; // rdi
  __int64 (__fastcall *v67)(__int64, HSTRING *); // rbx
  PCWSTR v68; // rax
  __int64 v69; // r14
  __int64 v70; // r8
  __int64 v71; // rdi
  __int64 (__fastcall *v72)(__int64, __int64 *); // rbx
  __int64 v73; // rdi
  __int64 (__fastcall *v74)(__int64, __int64, HSTRING *); // rbx
  int v75; // eax
  PCWSTR v76; // rax
  char v78; // [rsp+40h] [rbp-C0h] BYREF
  char v79; // [rsp+41h] [rbp-BFh] BYREF
  _BYTE v80[6]; // [rsp+42h] [rbp-BEh] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v82; // [rsp+50h] [rbp-B0h] BYREF
  int v83; // [rsp+58h] [rbp-A8h] BYREF
  int v84; // [rsp+5Ch] [rbp-A4h] BYREF
  __int64 v85; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v86; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v87; // [rsp+70h] [rbp-90h] BYREF
  __int64 v88; // [rsp+78h] [rbp-88h] BYREF
  __int64 v89; // [rsp+80h] [rbp-80h] BYREF
  __int64 v90; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 *); // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall ***v92)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-68h] BYREF
  __int64 v93; // [rsp+A0h] [rbp-60h] BYREF
  int v94; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v95)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-50h] BYREF
  __int64 v96; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v97; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v98; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v99; // [rsp+D0h] [rbp-30h]
  __int64 v100; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v101; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v102; // [rsp+F8h] [rbp-8h]
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp+0h] BYREF
  __int64 v104; // [rsp+118h] [rbp+18h]
  HSTRING_HEADER v105; // [rsp+120h] [rbp+20h] BYREF
  __int64 v106; // [rsp+138h] [rbp+38h]

  v84 = a4;
  v99 = a3;
  v86 = a1;
  string = a2;
  v100 = a3;
  v98 = 0;
  v93 = 0;
  v97 = 0;
  v92 = 0;
  v91 = 0;
  v96 = 0;
  v90 = 0;
  v85 = 0;
  v89 = 0;
  v88 = 0;
  v95 = 0;
  v87 = 0;
  v94 = 0;
  v78 = 0;
  v104 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"mdm_enrollment_url", 0x13u, 0x12u);
  v80[0] = 0;
  v82 = 0;
  v79 = 0;
  v83 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"DsrCmdDeviceEnroller::GetDeviceOnlyWamToken");
  *(_QWORD *)(a5 + 16) = 0;
  if ( *(_QWORD *)(a5 + 24) <= 7u )
    v7 = (char *)a5;
  else
    v7 = *(char **)a5;
  *(_WORD *)v7 = 0;
  *(_QWORD *)(a6 + 16) = 0;
  if ( *(_QWORD *)(a6 + 24) <= 7u )
    v8 = (char *)a6;
  else
    v8 = *(char **)a6;
  *(_WORD *)v8 = 0;
  Src[2] = 0;
  if ( Src[3] <= 7u )
    v9 = Src;
  else
    v9 = (_WORD *)*Src;
  *v9 = 0;
  v10 = v93;
  v93 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v102 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v101,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  ActivationFactory = RoGetActivationFactory(v102, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, &v93);
  v12 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
LABEL_13:
    v13 = L"GetActivationFactory";
LABEL_41:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrCmdDeviceEnroller::GetDeviceOnlyWamToken",
      v13,
      (unsigned int)ActivationFactory);
    goto LABEL_124;
  }
  v14 = v97;
  v97 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  ActivationFactory = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v93)(
                        v93,
                        &GUID_54e633fe_96e0_41e8_9832_1298897c2aaf,
                        &v97);
  v12 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v13 = L"QueryInterface";
    goto LABEL_41;
  }
  v15 = v97;
  v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v97 + 64LL);
  v17 = v92;
  v92 = 0;
  if ( v17 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v17)[2])(v17);
  v102 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v101, L"https://login.windows.net", 0x1Au, 0x19u);
  ActivationFactory = v16(v15, v102, &v92);
  v12 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v13 = L"IWebAuthenticationCoreManager::FindSystemAccountProviderAsync";
    goto LABEL_41;
  }
  ActivationFactory = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(
                        v92,
                        v18,
                        0xEA60u,
                        &v78);
  v12 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
LABEL_23:
    v13 = L"WaitForCompletionOrTimeoutNoThrow";
    goto LABEL_41;
  }
  if ( v78 )
  {
    v12 = -2147024638;
    Logger::TraceError(
      L"%s: FindSystemAccountProviderAsync failed with timeout (error code: 0x%08x).",
      L"DsrCmdDeviceEnroller::GetDeviceOnlyWamToken");
  }
  else
  {
    v19 = v92;
    v20 = (*v92)[8];
    v21 = v96;
    v96 = 0;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v20)(
                          v19,
                          &v96);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v13 = L"FindAccountProviderAsync::GetResults";
      goto LABEL_41;
    }
    v22 = v98;
    v98 = 0;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v102 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v101,
      L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
      0x39u,
      0x38u);
    ActivationFactory = RoGetActivationFactory(v102, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v98);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
      goto LABEL_13;
    v23 = v98;
    v24 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v98 + 48LL);
    v25 = v90;
    v90 = 0;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v102 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v101,
      L"dd762716-544d-4aeb-a526-687b73838a22",
      0x25u,
      0x24u);
    ActivationFactory = v24(v23, v96, 0, v102, &v90);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v13 = L"IWebTokenRequestFactory::Create";
      goto LABEL_41;
    }
    v26 = v90;
    v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v90 + 80LL);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,wil::err_returncode_policy>::reset(&v82);
    ActivationFactory = v27(v26, &v82);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v13 = L"IWebTokenRequest::get_Properties";
      goto LABEL_41;
    }
    v28 = v82;
    v29 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v82 + 80LL);
    v30 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v105, &string) + 24);
    v102 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v101, L"resource", 9u, 8u);
    ActivationFactory = v29(v28, v102, v30, &v79);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
      goto LABEL_40;
    v31 = v82;
    v32 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v82 + 80LL);
    v102 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v101, L"DeviceAuth", 0xBu, 0xAu);
    v33 = v102;
    v106 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v105, L"client_TokenType", 0x11u, 0x10u);
    ActivationFactory = v32(v31, v106, v33, &v79);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
      goto LABEL_40;
    v34 = v82;
    v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v82 + 80LL);
    v36 = (HSTRING)&cchOriginalDestLength;
    if ( v86[3] )
      v36 = (HSTRING)v86[3];
    string = v36;
    v37 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v101, &string) + 24);
    v106 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v105, L"correlationId", 0xEu, 0xDu);
    ActivationFactory = v35(v34, v106, v37, &v79);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0
      || v99
      && (v38 = v82,
          v39 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v82 + 80LL),
          v40 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v101, &v100) + 24),
          v106 = 0,
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v105, L"CloudAssignedMdmId", 0x13u, 0x12u),
          ActivationFactory = v39(v38, v106, v40, &v79),
          v12 = ActivationFactory,
          ActivationFactory < 0) )
    {
LABEL_40:
      v13 = L"IMap<HSTRING::HSTRING>::Insert";
      goto LABEL_41;
    }
    v41 = v93;
    v42 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v93 + 48LL);
    v43 = v91;
    v91 = 0;
    if ( v43 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v43)[2])(v43);
    ActivationFactory = v42(v41, v90, &v91);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v13 = L"IWebAuthenticationCoreManager::GetTokenSilentlyAsync";
      goto LABEL_41;
    }
    ActivationFactory = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *> *>(
                          v91,
                          v44,
                          0xEA60u,
                          &v78);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v13 = L"WaitForCompletionOrTimeoutNoThrow";
      goto LABEL_41;
    }
    if ( v78 )
    {
      v12 = -2147024638;
      Logger::TraceError(
        L"%s: GetTokenSilentlyAsync failed with timeout (error code: 0x%08x).",
        L"DsrCmdDeviceEnroller::GetDeviceOnlyWamToken");
      goto LABEL_124;
    }
    v45 = v91;
    v46 = (*v91)[8];
    v47 = v85;
    v85 = 0;
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    ActivationFactory = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v46)(
                          v45,
                          &v85);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v13 = L"GetTokenSilentlyAsync::GetResults";
      goto LABEL_41;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v85 + 56LL))(v85, &v83);
    v12 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v13 = L"WebTokenRequestResult::get_ResponseStatus";
      goto LABEL_41;
    }
    if ( v83 )
    {
      v86 = 0;
      Logger::TraceError(
        L"%s: GetTokenSilently WAM call failed. Status: %ld",
        L"DsrCmdDeviceEnroller::GetDeviceOnlyWamToken");
      std::wstring::_Append<unsigned short>(Src);
      switch ( v83 )
      {
        case 1:
          v12 = -2145647537;
          break;
        case 2:
          v12 = -2145648520;
          break;
        case 3:
          v12 = -2145648519;
          break;
        case 4:
          v12 = -2145648521;
          break;
        case 5:
          v12 = -2145648528;
          break;
        default:
          v12 = -2145648518;
          break;
      }
      std::wstring::_Append<unsigned short>(Src);
      if ( ((v83 - 3) & 0xFFFFFFFD) == 0 )
      {
        v48 = v85;
        v49 = *(int (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v85 + 64LL);
        v50 = (__int64)v86;
        v86 = 0;
        if ( v50 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        if ( v49(v48, &v86) >= 0 )
        {
          memset_0(&v105, 0, 0x40u);
          v84 = 0;
          string = 0;
          v51 = -1;
          if ( (*(int (__fastcall **)(_QWORD *, int *))(*v86 + 48LL))(v86, &v84) >= 0
            && (int)StringCchPrintfExW((wchar_t *)&v105, 0x1Fu, 0, 0, 0, L"; Error code: 0x%08x", v84) >= 0 )
          {
            v52 = -1;
            do
              ++v52;
            while ( *(_WORD *)&v105.Reserved.Reserved2[2 * v52] );
            std::wstring::_Append<unsigned short>(Src);
          }
          v53 = v86;
          v54 = *(int (__fastcall **)(_QWORD *, HSTRING *))(*v86 + 56LL);
          WindowsDeleteString(string);
          string = 0;
          if ( v54(v53, &string) >= 0 )
          {
            std::wstring::_Append<unsigned short>(Src);
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            do
              ++v51;
            while ( StringRawBuffer[v51] );
            std::wstring::_Append<unsigned short>(Src);
          }
          WindowsDeleteString(string);
        }
      }
      wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v86);
    }
    else
    {
      if ( !v84 )
      {
        v56 = v85;
        v57 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v85 + 72LL);
        v58 = v95;
        v95 = 0;
        if ( v58 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v58)[2])(v58);
        ActivationFactory = v57(v56, &v95);
        v12 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          v13 = L"WebTokenRequestResult::InvalidateCacheAsync";
          goto LABEL_41;
        }
        ActivationFactory = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(
                              v95,
                              v59,
                              0xEA60u,
                              &v78);
        v12 = ActivationFactory;
        if ( ActivationFactory < 0 )
          goto LABEL_23;
      }
      v60 = v85;
      v61 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v85 + 48LL);
      v62 = v89;
      v89 = 0;
      if ( v62 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
      ActivationFactory = v61(v60, &v89);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v13 = L"WebTokenRequestResult::get_ResponseData";
        goto LABEL_41;
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v89 + 56LL))(v89, &v94);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v13 = L"VectorView::get_Size";
        goto LABEL_41;
      }
      if ( !v94 )
      {
        v12 = -2145648527;
        goto LABEL_124;
      }
      v63 = v89;
      v64 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v89 + 48LL);
      v65 = v88;
      v88 = 0;
      if ( v65 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      ActivationFactory = v64(v63, 0, &v88);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v13 = L"VectorView::GetAt";
        goto LABEL_41;
      }
      v66 = v88;
      v67 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v88 + 48LL);
      WindowsDeleteString(v87);
      v87 = 0;
      ActivationFactory = v67(v66, &v87);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v13 = L"WebTokenResponse::get_Token";
        goto LABEL_41;
      }
      v68 = WindowsGetStringRawBuffer(v87, 0);
      v69 = -1;
      v70 = -1;
      do
        ++v70;
      while ( v68[v70] );
      std::wstring::_Assign<unsigned short>((char **)a6, v68, (char *)v70);
      if ( !*(_QWORD *)(a6 + 16) )
      {
        v12 = -2145648517;
        goto LABEL_124;
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,wil::err_returncode_policy>::reset(&v82);
      v71 = v88;
      v72 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 72LL);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,wil::err_returncode_policy>::reset(&v82);
      ActivationFactory = v72(v71, &v82);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v13 = L"WebTokenResponse::get_Properties";
        goto LABEL_41;
      }
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v82 + 64LL))(v82, v104, v80);
      v12 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        v13 = L"Map<HSTRING::HSTRING>::HasKey";
        goto LABEL_41;
      }
      if ( v80[0] )
      {
        string = 0;
        v73 = v82;
        v74 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v82 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v75 = v74(v73, v104, &string);
        v12 = v75;
        if ( v75 >= 0 )
        {
          v76 = WindowsGetStringRawBuffer(string, 0);
          do
            ++v69;
          while ( v76[v69] );
          std::wstring::_Assign<unsigned short>((char **)a5, v76, (char *)v69);
        }
        else
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"DsrCmdDeviceEnroller::GetDeviceOnlyWamToken",
            L"Map<HSTRING::HSTRING>::Lookup",
            (unsigned int)v75);
        }
        WindowsDeleteString(string);
      }
    }
  }
LABEL_124:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DsrCmdDeviceEnroller::GetDeviceOnlyWamToken", v12);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v82);
  v104 = 0;
  WindowsDeleteString(v87);
  v87 = 0;
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v95);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v88);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v89);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v85);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v90);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v96);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v91);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v92);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v97);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v93);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v98);
  return v12;
}

```

## disassembly

```asm
0x180030c5c  mov     [rsp-8+arg_18], rbx
0x180030c61  push    rbp
0x180030c62  push    rsi
0x180030c63  push    rdi
0x180030c64  push    r12
0x180030c66  push    r13
0x180030c68  push    r14
0x180030c6a  push    r15
0x180030c6c  lea     rbp, [rsp-70h]
0x180030c71  sub     rsp, 170h
0x180030c78  mov     rax, cs:__security_cookie
0x180030c7f  xor     rax, rsp
0x180030c82  mov     [rbp+0A0h+var_40], rax
0x180030c86  mov     [rsp+1A0h+var_144], r9d
0x180030c8b  mov     rax, r8
0x180030c8e  mov     [rbp+0A0h+var_D0], rax
0x180030c92  mov     [rsp+1A0h+var_138], rcx
0x180030c97  mov     r15, [rbp+0A0h+Src]
0x180030c9e  mov     r12, [rbp+0A0h+arg_28]
0x180030ca5  mov     r13, [rbp+0A0h+arg_20]
0x180030cac  mov     [rsp+1A0h+string], rdx
0x180030cb1  mov     [rbp+0A0h+var_C8], rax
0x180030cb5  xor     r14d, r14d
0x180030cb8  mov     [rbp+0A0h+var_D8], r14
0x180030cbc  mov     [rbp+0A0h+var_100], r14
0x180030cc0  mov     [rbp+0A0h+var_E0], r14
0x180030cc4  mov     [rbp+0A0h+var_108], r14
0x180030cc8  mov     [rbp+0A0h+var_110], r14
0x180030ccc  mov     [rbp+0A0h+var_E8], r14
0x180030cd0  mov     [rbp+0A0h+var_118], r14
0x180030cd4  mov     [rsp+1A0h+var_140], r14
0x180030cd9  mov     [rbp+0A0h+var_120], r14
0x180030cdd  mov     [rsp+1A0h+var_128], r14
0x180030ce2  mov     [rbp+0A0h+var_F0], r14
0x180030ce6  mov     [rsp+1A0h+var_130], r14
0x180030ceb  mov     [rbp+0A0h+var_F8], r14d
0x180030cef  mov     [rsp+1A0h+var_160], r14b
0x180030cf4  mov     [rbp+0A0h+var_88], r14
0x180030cf8  lea     r9d, [r14+12h]; unsigned int
0x180030cfc  lea     r8d, [r14+13h]; unsigned int
0x180030d00  lea     rdx, sourceString; "mdm_enrollment_url"
0x180030d07  lea     rcx, [rbp+0A0h+hstringHeader]; hstringHeader
0x180030d0b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030d10  nop
0x180030d11  mov     [rsp+1A0h+var_15E], r14b
0x180030d16  mov     [rsp+1A0h+var_150], r14
0x180030d1b  mov     [rsp+1A0h+var_15F], r14b
0x180030d20  mov     [rsp+1A0h+var_148], r14d
0x180030d25  lea     rdx, aDsrcmddeviceen; "DsrCmdDeviceEnroller::GetDeviceOnlyWamT"...
0x180030d2c  lea     rcx, aSStarted; "%s started"
0x180030d33  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180030d38  mov     [r13+10h], r14
0x180030d3c  cmp     qword ptr [r13+18h], 7
0x180030d41  jbe     short loc_180030D49
0x180030d43  mov     rcx, [r13+0]
0x180030d47  jmp     short loc_180030D4C
0x180030d49  mov     rcx, r13
0x180030d4c  mov     [rcx], r14w
0x180030d50  mov     [r12+10h], r14
0x180030d55  cmp     qword ptr [r12+18h], 7
0x180030d5b  jbe     short loc_180030D63
0x180030d5d  mov     rcx, [r12]
0x180030d61  jmp     short loc_180030D66
0x180030d63  mov     rcx, r12
0x180030d66  mov     [rcx], r14w
0x180030d6a  mov     [r15+10h], r14
0x180030d6e  cmp     qword ptr [r15+18h], 7
0x180030d73  jbe     short loc_180030D7A
0x180030d75  mov     rcx, [r15]
0x180030d78  jmp     short loc_180030D7D
0x180030d7a  mov     rcx, r15
0x180030d7d  mov     [rcx], r14w
0x180030d81  mov     rcx, [rbp+0A0h+var_100]
0x180030d85  mov     [rbp+0A0h+var_100], r14
0x180030d89  test    rcx, rcx
0x180030d8c  jz      short loc_180030D9B
0x180030d8e  mov     rax, [rcx]
0x180030d91  mov     rax, [rax+10h]
0x180030d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d9a  nop
0x180030d9b  mov     [rbp+0A0h+var_A8], r14
0x180030d9f  mov     r9d, 45h ; 'E'; unsigned int
0x180030da5  lea     r8d, [r9+1]; unsigned int
0x180030da9  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180030db0  lea     rcx, [rbp+0A0h+var_C0]; hstringHeader
0x180030db4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030db9  lea     r8, [rbp+0A0h+var_100]
0x180030dbd  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180030dc4  mov     rcx, [rbp+0A0h+var_A8]
0x180030dc8  call    cs:__imp_RoGetActivationFactory
0x180030dce  mov     esi, eax
0x180030dd0  test    eax, eax
0x180030dd2  jns     short loc_180030DF6
0x180030dd4  lea     r8, aGetactivationf; "GetActivationFactory"
0x180030ddb  mov     r9d, eax
0x180030dde  lea     rdx, aDsrcmddeviceen; "DsrCmdDeviceEnroller::GetDeviceOnlyWamT"...
0x180030de5  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180030dec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180030df1  jmp     loc_180031813
0x180030df6  mov     rcx, [rbp+0A0h+var_E0]
0x180030dfa  mov     [rbp+0A0h+var_E0], r14
0x180030dfe  test    rcx, rcx
0x180030e01  jz      short loc_180030E10
0x180030e03  mov     rax, [rcx]
0x180030e06  mov     rax, [rax+10h]
0x180030e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e0f  nop
0x180030e10  mov     rcx, [rbp+0A0h+var_100]
0x180030e14  mov     rax, [rcx]
0x180030e17  lea     r8, [rbp+0A0h+var_E0]
0x180030e1b  lea     rdx, _GUID_54e633fe_96e0_41e8_9832_1298897c2aaf
0x180030e22  mov     rax, [rax]
0x180030e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e2a  mov     esi, eax
0x180030e2c  test    eax, eax
0x180030e2e  jns     short loc_180030E39
0x180030e30  lea     r8, aQueryinterface; "QueryInterface"
0x180030e37  jmp     short loc_180030DDB
0x180030e39  mov     rbx, [rbp+0A0h+var_E0]
0x180030e3d  mov     rax, [rbx]
0x180030e40  mov     rdi, [rax+40h]
0x180030e44  mov     rcx, [rbp+0A0h+var_108]
0x180030e48  mov     [rbp+0A0h+var_108], r14
0x180030e4c  test    rcx, rcx
0x180030e4f  jz      short loc_180030E5E
0x180030e51  mov     rax, [rcx]
0x180030e54  mov     rax, [rax+10h]
0x180030e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e5d  nop
0x180030e5e  mov     [rbp+0A0h+var_A8], r14
0x180030e62  mov     r9d, 19h; unsigned int
0x180030e68  lea     r8d, [r9+1]; unsigned int
0x180030e6c  lea     rdx, aHttpsLoginWind_0; "https://login.windows.net"
0x180030e73  lea     rcx, [rbp+0A0h+var_C0]; hstringHeader
0x180030e77  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030e7c  nop
0x180030e7d  lea     r8, [rbp+0A0h+var_108]
0x180030e81  mov     rdx, [rbp+0A0h+var_A8]
0x180030e85  mov     rcx, rbx
0x180030e88  mov     rax, rdi
0x180030e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e90  mov     esi, eax
0x180030e92  test    eax, eax
0x180030e94  jns     short loc_180030EA2
0x180030e96  lea     r8, aIwebauthentica; "IWebAuthenticationCoreManager::FindSyst"...
0x180030e9d  jmp     loc_180030DDB
0x180030ea2  lea     r9, [rsp+1A0h+var_160]
0x180030ea7  mov     r8d, 0EA60h
0x180030ead  mov     rcx, [rbp+0A0h+var_108]
0x180030eb1  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180030eb6  mov     esi, eax
0x180030eb8  test    eax, eax
0x180030eba  jns     short loc_180030EC8
0x180030ebc  lea     r8, aWaitforcomplet_1; "WaitForCompletionOrTimeoutNoThrow"
0x180030ec3  jmp     loc_180030DDB
0x180030ec8  cmp     [rsp+1A0h+var_160], r14b
0x180030ecd  jz      short loc_180030EF0
0x180030ecf  mov     r8d, 80070102h
0x180030ed5  mov     esi, r8d
0x180030ed8  lea     rdx, aDsrcmddeviceen; "DsrCmdDeviceEnroller::GetDeviceOnlyWamT"...
0x180030edf  lea     rcx, aSFindsystemacc; "%s: FindSystemAccountProviderAsync fail"...
0x180030ee6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180030eeb  jmp     loc_180031813
0x180030ef0  mov     rbx, [rbp+0A0h+var_108]
0x180030ef4  mov     rax, [rbx]
0x180030ef7  mov     rdi, [rax+40h]
0x180030efb  mov     rcx, [rbp+0A0h+var_E8]
0x180030eff  mov     [rbp+0A0h+var_E8], r14
0x180030f03  test    rcx, rcx
0x180030f06  jz      short loc_180030F15
0x180030f08  mov     rdx, [rcx]
0x180030f0b  mov     rax, [rdx+10h]
0x180030f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f14  nop
0x180030f15  lea     rdx, [rbp+0A0h+var_E8]
0x180030f19  mov     rcx, rbx
0x180030f1c  mov     rax, rdi
0x180030f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f24  mov     esi, eax
0x180030f26  test    eax, eax
0x180030f28  jns     short loc_180030F36
0x180030f2a  lea     r8, aFindaccountpro; "FindAccountProviderAsync::GetResults"
0x180030f31  jmp     loc_180030DDB
0x180030f36  mov     rcx, [rbp+0A0h+var_D8]
0x180030f3a  mov     [rbp+0A0h+var_D8], r14
0x180030f3e  test    rcx, rcx
0x180030f41  jz      short loc_180030F50
0x180030f43  mov     rax, [rcx]
0x180030f46  mov     rax, [rax+10h]
0x180030f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f4f  nop
0x180030f50  mov     [rbp+0A0h+var_A8], r14
0x180030f54  mov     r9d, 38h ; '8'; unsigned int
0x180030f5a  lea     r8d, [r9+1]; unsigned int
0x180030f5e  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180030f65  lea     rcx, [rbp+0A0h+var_C0]; hstringHeader
0x180030f69  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030f6e  lea     r8, [rbp+0A0h+var_D8]
0x180030f72  lea     rdx, _GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9
0x180030f79  mov     rcx, [rbp+0A0h+var_A8]
0x180030f7d  call    cs:__imp_RoGetActivationFactory
0x180030f83  mov     esi, eax
0x180030f85  test    eax, eax
0x180030f87  js      loc_180030DD4
0x180030f8d  mov     rbx, [rbp+0A0h+var_D8]
0x180030f91  mov     rax, [rbx]
0x180030f94  mov     rdi, [rax+30h]
0x180030f98  mov     rcx, [rbp+0A0h+var_118]
0x180030f9c  mov     [rbp+0A0h+var_118], r14
0x180030fa0  test    rcx, rcx
0x180030fa3  jz      short loc_180030FB2
0x180030fa5  mov     rax, [rcx]
0x180030fa8  mov     rax, [rax+10h]
0x180030fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fb1  nop
0x180030fb2  mov     [rbp+0A0h+var_A8], r14
0x180030fb6  mov     r9d, 24h ; '$'; unsigned int
0x180030fbc  lea     r8d, [r9+1]; unsigned int
0x180030fc0  lea     rdx, aDd762716544d4a; "dd762716-544d-4aeb-a526-687b73838a22"
0x180030fc7  lea     rcx, [rbp+0A0h+var_C0]; hstringHeader
0x180030fcb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180030fd0  nop
0x180030fd1  lea     rax, [rbp+0A0h+var_118]
0x180030fd5  mov     qword ptr [rsp+1A0h+var_180], rax
0x180030fda  mov     r9, [rbp+0A0h+var_A8]
0x180030fde  xor     r8d, r8d
0x180030fe1  mov     rdx, [rbp+0A0h+var_E8]
0x180030fe5  mov     rcx, rbx
0x180030fe8  mov     rax, rdi
0x180030feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ff0  mov     esi, eax
0x180030ff2  test    eax, eax
0x180030ff4  jns     short loc_180031002
0x180030ff6  lea     r8, aIwebtokenreque; "IWebTokenRequestFactory::Create"
0x180030ffd  jmp     loc_180030DDB
0x180031002  mov     rdi, [rbp+0A0h+var_118]
0x180031006  mov     rax, [rdi]
0x180031009  mov     rbx, [rax+50h]
0x18003100d  lea     rcx, [rsp+1A0h+var_150]
0x180031012  call    ?reset@?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>,wil::err_returncode_policy>::reset(void)
0x180031017  lea     rdx, [rsp+1A0h+var_150]
0x18003101c  mov     rcx, rdi
0x18003101f  mov     rax, rbx
0x180031022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031027  mov     esi, eax
0x180031029  test    eax, eax
0x18003102b  jns     short loc_180031039
0x18003102d  lea     r8, aIwebtokenreque_0; "IWebTokenRequest::get_Properties"
0x180031034  jmp     loc_180030DDB
0x180031039  mov     rsi, [rsp+1A0h+var_150]
0x18003103e  mov     rax, [rsi]
0x180031041  mov     rdi, [rax+50h]
0x180031045  lea     rdx, [rsp+1A0h+string]
0x18003104a  lea     rcx, [rbp+0A0h+var_80]
0x18003104e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180031053  nop
0x180031054  mov     rbx, [rax+18h]
0x180031058  mov     [rbp+0A0h+var_A8], r14
0x18003105c  mov     r9d, 8; unsigned int
0x180031062  lea     r14d, [r9+1]
0x180031066  mov     r8d, r14d; unsigned int
0x180031069  lea     rdx, aResource; "resource"
0x180031070  lea     rcx, [rbp+0A0h+var_C0]; hstringHeader
0x180031074  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180031079  nop
0x18003107a  lea     r9, [rsp+1A0h+var_15F]
0x18003107f  mov     r8, rbx
0x180031082  mov     rdx, [rbp+0A0h+var_A8]
0x180031086  mov     rcx, rsi
0x180031089  mov     rax, rdi
0x18003108c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031091  mov     esi, eax
0x180031093  test    eax, eax
0x180031095  jns     short loc_1800310B9
0x180031097  lea     r8, aImapHstringHst; "IMap<HSTRING::HSTRING>::Insert"
0x18003109e  mov     r9d, eax
0x1800310a1  lea     rdx, aDsrcmddeviceen; "DsrCmdDeviceEnroller::GetDeviceOnlyWamT"...
0x1800310a8  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800310af  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800310b4  jmp     loc_180031810
0x1800310b9  mov     rsi, [rsp+1A0h+var_150]
0x1800310be  mov     rax, [rsi]
0x1800310c1  mov     rdi, [rax+50h]
0x1800310c5  mov     [rbp+0A0h+var_A8], 0
0x1800310cd  mov     r9d, 0Ah; unsigned int
0x1800310d3  lea     r8d, [r9+1]; unsigned int
0x1800310d7  lea     rdx, aDeviceauth; "DeviceAuth"
0x1800310de  lea     rcx, [rbp+0A0h+var_C0]; hstringHeader
0x1800310e2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800310e7  nop
0x1800310e8  mov     rbx, [rbp+0A0h+var_A8]
0x1800310ec  mov     [rbp+0A0h+var_68], 0
0x1800310f4  mov     r9d, 10h; unsigned int
0x1800310fa  lea     r8d, [r9+1]; unsigned int
0x1800310fe  lea     rdx, aClientTokentyp; "client_TokenType"
0x180031105  lea     rcx, [rbp+0A0h+var_80]; hstringHeader
0x180031109  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003110e  nop
0x18003110f  lea     r9, [rsp+1A0h+var_15F]
0x180031114  mov     r8, rbx
  ... truncated ...
```
