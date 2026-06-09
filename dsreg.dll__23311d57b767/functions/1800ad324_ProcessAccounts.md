# ProcessAccounts

- ea: `0x1800ad324`
- end: `0x1800adb13`
- name: `ProcessAccounts`
- size: `2031`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800acbc8`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x1800318e8`
- `0x180031a20`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800abc5c`
- `0x1800abcf4`
- `0x1800ac0b0`
- `0x1800acd98`
- `0x1800ad324`
- `0x1800ba8f4`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad4cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad55c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad79f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad8ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad4cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad55c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad79f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad8ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ad585`

## string_xrefs

- `0x1800ad370`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x1800ad688`: `ComPtr<IWebAccount>::As`
- `0x1800ad3d2`: `ITokenBrokerInternalStatics::FindAllAccountsAsync`
- `0x1800ada54`: `BlockOnCompletionAndGetResults`
- `0x1800ad7c4`: `ComPtr<IWebAccountProvider>::As`
- `0x1800ad4fd`: `https://login.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ProcessAccounts(int a1, char a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // ebx
  _BYTE **CurrentRef; // rax
  const wchar_t *v8; // r14
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v14; // edx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned int v20; // esi
  unsigned int i; // r14d
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, _QWORD); // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v27)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64); // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, HSTRING *); // rbx
  __int64 v40; // rdx
  __int64 v41; // rcx
  const wchar_t *v42; // rax
  __int64 (__fastcall ***v43)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v44)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  _BYTE **v50; // rax
  const wchar_t *v51; // r14
  __int64 v52; // rdx
  __int64 v53; // rcx
  _QWORD *v54; // rax
  __int64 v55; // rdx
  _QWORD *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  _QWORD *v61; // rax
  __int64 v62; // rdx
  _QWORD *v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rcx
  _QWORD *v68; // rax
  __int64 v69; // rdx
  _QWORD *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rcx
  _QWORD *v75; // rax
  __int64 v76; // rdx
  _QWORD *v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // rdx
  _QWORD *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // rcx
  _QWORD *v89; // rax
  __int64 v90; // rdx
  _QWORD *v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rax
  _QWORD *v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // rax
  __int64 v99; // rdx
  __int64 v100; // rcx
  _QWORD *v101; // rax
  __int64 v102; // rdx
  _QWORD *v103; // rax
  __int64 v104; // rdx
  __int64 v105; // rax
  int v107; // [rsp+20h] [rbp-79h]
  int v108; // [rsp+20h] [rbp-79h]
  int v109; // [rsp+20h] [rbp-79h]
  int v110; // [rsp+20h] [rbp-79h]
  int v111; // [rsp+20h] [rbp-79h]
  int v112; // [rsp+20h] [rbp-79h]
  int v113; // [rsp+20h] [rbp-79h]
  HSTRING string; // [rsp+30h] [rbp-69h] BYREF
  __int64 (__fastcall ***v115)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-61h] BYREF
  HSTRING v116; // [rsp+40h] [rbp-59h] BYREF
  __int64 (__fastcall ***v117)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-51h] BYREF
  __int64 v118; // [rsp+50h] [rbp-49h] BYREF
  __int64 v119; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v120; // [rsp+60h] [rbp-39h] BYREF
  int v121; // [rsp+64h] [rbp-35h] BYREF
  __int64 v122; // [rsp+68h] [rbp-31h] BYREF
  int (__fastcall ***v123)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-29h] BYREF
  __int64 v124; // [rsp+78h] [rbp-21h] BYREF
  __int64 (__fastcall ***v125)(_QWORD, _QWORD, _QWORD); // [rsp+80h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-11h] BYREF
  __int64 v127; // [rsp+A0h] [rbp+7h]

  v124 = 0;
  v123 = 0;
  v122 = 0;
  v120 = 0;
  v127 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
         v127,
         (__int64)&v124);
  if ( v6 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v5, v4);
    v8 = L"GetActivationFactory";
    goto LABEL_70;
  }
  v9 = v124;
  v10 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v124 + 96LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v123);
  v6 = v10(v9, &v123);
  if ( v6 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v12, v11);
    v8 = L"ITokenBrokerInternalStatics::FindAllAccountsAsync";
    goto LABEL_70;
  }
  v13 = v123;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v122);
  v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(
         v13,
         v14,
         v15);
  if ( v6 < 0
    || (v6 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v13)[8])(v13, &v122),
        v6 < 0) )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v17, v16);
    v8 = L"BlockOnCompletionAndGetResults";
LABEL_70:
    if ( **CurrentRef )
    {
      wprintf(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccounts", v8, (unsigned int)v6);
      v101 = (_QWORD *)CmdOptions::GetCurrentRef(v100, v99);
      if ( *(_BYTE *)(*v101 + 12LL) )
      {
        v103 = (_QWORD *)CmdOptions::GetCurrentRef(*v101, v102);
        if ( *(_QWORD *)(*v103 + 184LL) )
        {
          v105 = CmdOptions::GetCurrentRef(*v103, v104);
          v113 = v6;
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v105 + 184LL),
            L"%s: %s failed with error code: 0x%08x.\n",
            L"ProcessAccounts",
            v8,
            v113);
        }
      }
    }
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccounts", v8, (unsigned int)v6);
    goto LABEL_75;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v122 + 56LL))(v122, &v120);
  if ( v6 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v19, v18);
    v8 = L"IVectorView::get_Size";
    goto LABEL_70;
  }
  v20 = 0;
  for ( i = 0; i < v120; ++i )
  {
    v115 = 0;
    v22 = v122;
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v122 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
    v6 = v23(v22, i, &v115);
    if ( v6 < 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v25, v24) )
      {
        wprintf(
          L"%s: %s failed with error code: 0x%08x.\n",
          L"ProcessAccounts",
          L"IVectorView::GetAt",
          (unsigned int)v6);
        v89 = (_QWORD *)CmdOptions::GetCurrentRef(v88, v87);
        if ( *(_BYTE *)(*v89 + 12LL) )
        {
          v91 = (_QWORD *)CmdOptions::GetCurrentRef(*v89, v90);
          if ( *(_QWORD *)(*v91 + 184LL) )
          {
            v93 = CmdOptions::GetCurrentRef(*v91, v92);
            v112 = v6;
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v93 + 184LL),
              L"%s: %s failed with error code: 0x%08x.\n",
              L"ProcessAccounts",
              L"IVectorView::GetAt",
              v112);
          }
        }
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.\n",
        L"ProcessAccounts",
        L"IVectorView::GetAt",
        (unsigned int)v6);
      goto LABEL_64;
    }
    v117 = 0;
    v26 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v115;
    v27 = (*v115)[6];
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v117);
    v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))v27)(
           v26,
           &v117);
    if ( v6 < 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v29, v28) )
      {
        wprintf(
          L"%s: %s failed with error code: 0x%08x.\n",
          L"ProcessAccounts",
          L"IWebAccount::get_WebAccountProvider",
          (unsigned int)v6);
        v82 = (_QWORD *)CmdOptions::GetCurrentRef(v81, v80);
        if ( *(_BYTE *)(*v82 + 12LL) )
        {
          v84 = (_QWORD *)CmdOptions::GetCurrentRef(*v82, v83);
          if ( *(_QWORD *)(*v84 + 184LL) )
          {
            v86 = CmdOptions::GetCurrentRef(*v84, v85);
            v111 = v6;
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v86 + 184LL),
              L"%s: %s failed with error code: 0x%08x.\n",
              L"ProcessAccounts",
              L"IWebAccount::get_WebAccountProvider",
              v111);
          }
        }
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.\n",
        L"ProcessAccounts",
        L"IWebAccount::get_WebAccountProvider",
        (unsigned int)v6);
      goto LABEL_58;
    }
    string = 0;
    v30 = v117;
    v31 = (*v117)[6];
    WindowsDeleteString(0);
    string = 0;
    v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))v31)(v30, &string);
    if ( v6 < 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v33, v32) )
      {
        wprintf(
          L"%s: %s failed with error code: 0x%08x.\n",
          L"ProcessAccounts",
          L"IWebAccountProvider::get_Id",
          (unsigned int)v6);
        v75 = (_QWORD *)CmdOptions::GetCurrentRef(v74, v73);
        if ( *(_BYTE *)(*v75 + 12LL) )
        {
          v77 = (_QWORD *)CmdOptions::GetCurrentRef(*v75, v76);
          if ( *(_QWORD *)(*v77 + 184LL) )
          {
            v79 = CmdOptions::GetCurrentRef(*v77, v78);
            v110 = v6;
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v79 + 184LL),
              L"%s: %s failed with error code: 0x%08x.\n",
              L"ProcessAccounts",
              L"IWebAccountProvider::get_Id",
              v110);
          }
        }
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.\n",
        L"ProcessAccounts",
        L"IWebAccountProvider::get_Id",
        (unsigned int)v6);
      goto LABEL_52;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !wcscmp_0(StringRawBuffer, L"https://login.microsoft.com")
      || (v35 = WindowsGetStringRawBuffer(string, 0), !wcscmp_0(v35, L"https://login.windows.local")) )
    {
      v118 = 0;
      v6 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(
             &v117,
             (__int64)&v118);
      if ( v6 < 0 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v37, v36) )
        {
          wprintf(
            L"%s: %s failed with error code: 0x%08x.\n",
            L"ProcessAccounts",
            L"ComPtr<IWebAccountProvider>::As",
            (unsigned int)v6);
          v68 = (_QWORD *)CmdOptions::GetCurrentRef(v67, v66);
          if ( *(_BYTE *)(*v68 + 12LL) )
          {
            v70 = (_QWORD *)CmdOptions::GetCurrentRef(*v68, v69);
            if ( *(_QWORD *)(*v70 + 184LL) )
            {
              v72 = CmdOptions::GetCurrentRef(*v70, v71);
              v109 = v6;
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v72 + 184LL),
                L"%s: %s failed with error code: 0x%08x.\n",
                L"ProcessAccounts",
                L"ComPtr<IWebAccountProvider>::As",
                v109);
            }
          }
        }
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.\n",
          L"ProcessAccounts",
          L"ComPtr<IWebAccountProvider>::As",
          (unsigned int)v6);
        goto LABEL_46;
      }
      v116 = 0;
      v38 = v118;
      v39 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v118 + 56LL);
      WindowsDeleteString(0);
      v116 = 0;
      v6 = v39(v38, &v116);
      if ( v6 < 0 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v41, v40) )
        {
          wprintf(
            L"%s: %s failed with error code: 0x%08x.\n",
            L"ProcessAccounts",
            L"IWebAccountProvider2::get_Authority",
            (unsigned int)v6);
          v61 = (_QWORD *)CmdOptions::GetCurrentRef(v60, v59);
          if ( *(_BYTE *)(*v61 + 12LL) )
          {
            v63 = (_QWORD *)CmdOptions::GetCurrentRef(*v61, v62);
            if ( *(_QWORD *)(*v63 + 184LL) )
            {
              v65 = CmdOptions::GetCurrentRef(*v63, v64);
              v108 = v6;
              fwprintf_s(
                *(FILE *const *)(*(_QWORD *)v65 + 184LL),
                L"%s: %s failed with error code: 0x%08x.\n",
                L"ProcessAccounts",
                L"IWebAccountProvider2::get_Authority",
                v108);
            }
          }
        }
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.\n",
          L"ProcessAccounts",
          L"IWebAccountProvider2::get_Authority",
          (unsigned int)v6);
        goto LABEL_40;
      }
      v42 = WindowsGetStringRawBuffer(v116, 0);
      if ( !wcscmp_0(v42, L"organizations") )
      {
        v121 = 0;
        v119 = 0;
        v43 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v115;
        v44 = **v115;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v119);
        v6 = v44(v43, &GUID_40285a2b_65d5_41f5_b904_76c860d86e26, &v119);
        if ( v6 < 0 )
        {
          v50 = (_BYTE **)CmdOptions::GetCurrentRef(v46, v45);
          v51 = L"ComPtr<IWebAccount>::As";
          goto LABEL_30;
        }
        v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v119 + 48LL))(v119, &v121);
        if ( v6 < 0 )
        {
          v50 = (_BYTE **)CmdOptions::GetCurrentRef(v48, v47);
          v51 = L"IWebAccountSystemInformation::get_Scope";
LABEL_30:
          if ( **v50 )
          {
            wprintf(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccounts", v51, (unsigned int)v6);
            v54 = (_QWORD *)CmdOptions::GetCurrentRef(v53, v52);
            if ( *(_BYTE *)(*v54 + 12LL) )
            {
              v56 = (_QWORD *)CmdOptions::GetCurrentRef(*v54, v55);
              if ( *(_QWORD *)(*v56 + 184LL) )
              {
                v58 = CmdOptions::GetCurrentRef(*v56, v57);
                v107 = v6;
                fwprintf_s(
                  *(FILE *const *)(*(_QWORD *)v58 + 184LL),
                  L"%s: %s failed with error code: 0x%08x.\n",
                  L"ProcessAccounts",
                  v51,
                  v107);
              }
            }
          }
          Logger::TraceError(L"%s: %s failed with error code: 0x%08x.\n", L"ProcessAccounts", v51, (unsigned int)v6);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v119);
LABEL_40:
          WindowsDeleteString(v116);
          v116 = 0;
LABEL_46:
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v118);
LABEL_52:
          WindowsDeleteString(string);
          string = 0;
LABEL_58:
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v117);
LABEL_64:
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
          goto LABEL_75;
        }
        if ( v121 == a1 )
        {
          ++v20;
          v125 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v115;
          if ( v115 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v115)[1])(v115);
          LOBYTE(v49) = a2;
          ProcessAccount(v124, &v125, v49);
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v119);
      }
      WindowsDeleteString(v116);
      v116 = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v118);
    }
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v117);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v115);
  }
  v94 = (_QWORD *)CmdOptions::GetCurrentRef(v19, v18);
  if ( *(_BYTE *)(*v94 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v94, v95) + 184LL) )
  {
    v98 = CmdOptions::GetCurrentRef(v97, v96);
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v98 + 184LL), L"Accounts found: %d.\n", v20);
  }
  wprintf(L"Accounts found: %d.\n", v20);
LABEL_75:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v122);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v123);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v124);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ad324  push    rbp
0x1800ad326  push    rbx
0x1800ad327  push    rsi
0x1800ad328  push    rdi
0x1800ad329  push    r12
0x1800ad32b  push    r13
0x1800ad32d  push    r14
0x1800ad32f  push    r15
0x1800ad331  lea     rbp, [rsp-1Fh]
0x1800ad336  sub     rsp, 0B8h
0x1800ad33d  mov     rax, cs:__security_cookie
0x1800ad344  xor     rax, rsp
0x1800ad347  mov     [rbp+57h+var_48], rax
0x1800ad34b  mov     r12b, dl
0x1800ad34e  mov     r15d, ecx
0x1800ad351  xor     r13d, r13d
0x1800ad354  mov     [rbp+57h+var_78], r13
0x1800ad358  mov     [rbp+57h+var_80], r13
0x1800ad35c  mov     [rbp+57h+var_88], r13
0x1800ad360  mov     [rbp+57h+var_90], r13d
0x1800ad364  mov     [rbp+57h+var_50], r13
0x1800ad368  lea     r9d, [r13+40h]; unsigned int
0x1800ad36c  lea     r8d, [r13+41h]; unsigned int
0x1800ad370  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800ad377  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ad37b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ad380  lea     rdx, [rbp+57h+var_78]
0x1800ad384  mov     rcx, [rbp+57h+var_50]
0x1800ad388  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x1800ad38d  mov     ebx, eax
0x1800ad38f  test    eax, eax
0x1800ad391  jns     short loc_1800AD3A4
0x1800ad393  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad398  lea     r14, aGetactivationf; "GetActivationFactory"
0x1800ad39f  jmp     loc_1800ADA5B
0x1800ad3a4  mov     rdi, [rbp+57h+var_78]
0x1800ad3a8  mov     rax, [rdi]
0x1800ad3ab  mov     rbx, [rax+60h]
0x1800ad3af  lea     rcx, [rbp+57h+var_80]
0x1800ad3b3  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad3b8  lea     rdx, [rbp+57h+var_80]
0x1800ad3bc  mov     rcx, rdi
0x1800ad3bf  mov     rax, rbx
0x1800ad3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3c7  mov     ebx, eax
0x1800ad3c9  test    eax, eax
0x1800ad3cb  jns     short loc_1800AD3DE
0x1800ad3cd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad3d2  lea     r14, aItokenbrokerin_0; "ITokenBrokerInternalStatics::FindAllAcc"...
0x1800ad3d9  jmp     loc_1800ADA5B
0x1800ad3de  mov     rdi, [rbp+57h+var_80]
0x1800ad3e2  lea     rcx, [rbp+57h+var_88]
0x1800ad3e6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad3eb  mov     rcx, rdi
0x1800ad3ee  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)
0x1800ad3f3  mov     ebx, eax
0x1800ad3f5  test    eax, eax
0x1800ad3f7  js      loc_1800ADA4F
0x1800ad3fd  mov     rax, [rdi]
0x1800ad400  lea     rdx, [rbp+57h+var_88]
0x1800ad404  mov     rcx, rdi
0x1800ad407  mov     rax, [rax+40h]
0x1800ad40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad410  mov     ebx, eax
0x1800ad412  test    eax, eax
0x1800ad414  js      loc_1800ADA4F
0x1800ad41a  mov     rcx, [rbp+57h+var_88]
0x1800ad41e  mov     rax, [rcx]
0x1800ad421  lea     rdx, [rbp+57h+var_90]
0x1800ad425  mov     rax, [rax+38h]
0x1800ad429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad42e  mov     ebx, eax
0x1800ad430  test    eax, eax
0x1800ad432  jns     short loc_1800AD445
0x1800ad434  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad439  lea     r14, aIvectorviewGet; "IVectorView::get_Size"
0x1800ad440  jmp     loc_1800ADA5B
0x1800ad445  mov     esi, r13d
0x1800ad448  mov     r14d, r13d
0x1800ad44b  cmp     r14d, [rbp+57h+var_90]
0x1800ad44f  jnb     loc_1800AD9FF
0x1800ad455  mov     [rbp+57h+var_B8], r13
0x1800ad459  mov     rdi, [rbp+57h+var_88]
0x1800ad45d  mov     rax, [rdi]
0x1800ad460  mov     rbx, [rax+30h]
0x1800ad464  lea     rcx, [rbp+57h+var_B8]
0x1800ad468  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad46d  lea     r8, [rbp+57h+var_B8]
0x1800ad471  mov     edx, r14d
0x1800ad474  mov     rcx, rdi
0x1800ad477  mov     rax, rbx
0x1800ad47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad47f  mov     ebx, eax
0x1800ad481  test    eax, eax
0x1800ad483  js      loc_1800AD96C
0x1800ad489  mov     [rbp+57h+var_A8], r13
0x1800ad48d  mov     rdi, [rbp+57h+var_B8]
0x1800ad491  mov     rax, [rdi]
0x1800ad494  mov     rbx, [rax+30h]
0x1800ad498  lea     rcx, [rbp+57h+var_A8]
0x1800ad49c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad4a1  lea     rdx, [rbp+57h+var_A8]
0x1800ad4a5  mov     rcx, rdi
0x1800ad4a8  mov     rax, rbx
0x1800ad4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad4b0  mov     ebx, eax
0x1800ad4b2  test    eax, eax
0x1800ad4b4  js      loc_1800AD8D9
0x1800ad4ba  mov     [rbp+57h+string], r13
0x1800ad4be  mov     rdi, [rbp+57h+var_A8]
0x1800ad4c2  mov     rax, [rdi]
0x1800ad4c5  mov     rbx, [rax+30h]
0x1800ad4c9  xor     ecx, ecx; string
0x1800ad4cb  call    cs:__imp_WindowsDeleteString
0x1800ad4d1  mov     [rbp+57h+string], r13
0x1800ad4d5  lea     rdx, [rbp+57h+string]
0x1800ad4d9  mov     rcx, rdi
0x1800ad4dc  mov     rax, rbx
0x1800ad4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad4e4  mov     ebx, eax
0x1800ad4e6  test    eax, eax
0x1800ad4e8  js      loc_1800AD841
0x1800ad4ee  xor     edx, edx; length
0x1800ad4f0  mov     rcx, [rbp+57h+string]; string
0x1800ad4f4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad4fa  mov     rcx, rax; String1
0x1800ad4fd  lea     rdx, aHttpsLoginMicr_1; "https://login.microsoft.com"
0x1800ad504  call    wcscmp_0
0x1800ad509  test    eax, eax
0x1800ad50b  jz      short loc_1800AD530
0x1800ad50d  xor     edx, edx; length
0x1800ad50f  mov     rcx, [rbp+57h+string]; string
0x1800ad513  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad519  mov     rcx, rax; String1
0x1800ad51c  lea     rdx, aHttpsLoginWind; "https://login.windows.local"
0x1800ad523  call    wcscmp_0
0x1800ad528  test    eax, eax
0x1800ad52a  jnz     loc_1800AD64C
0x1800ad530  mov     [rbp+57h+var_A0], r13
0x1800ad534  lea     rdx, [rbp+57h+var_A0]
0x1800ad538  lea     rcx, [rbp+57h+var_A8]
0x1800ad53c  call    ??$As@UIWebAccountProvider2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProvider2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider2>>)
0x1800ad541  mov     ebx, eax
0x1800ad543  test    eax, eax
0x1800ad545  js      loc_1800AD7AE
0x1800ad54b  mov     [rbp+57h+var_B0], r13
0x1800ad54f  mov     rdi, [rbp+57h+var_A0]
0x1800ad553  mov     rax, [rdi]
0x1800ad556  mov     rbx, [rax+38h]
0x1800ad55a  xor     ecx, ecx; string
0x1800ad55c  call    cs:__imp_WindowsDeleteString
0x1800ad562  mov     [rbp+57h+var_B0], r13
0x1800ad566  lea     rdx, [rbp+57h+var_B0]
0x1800ad56a  mov     rcx, rdi
0x1800ad56d  mov     rax, rbx
0x1800ad570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad575  mov     ebx, eax
0x1800ad577  test    eax, eax
0x1800ad579  js      loc_1800AD716
0x1800ad57f  xor     edx, edx; length
0x1800ad581  mov     rcx, [rbp+57h+var_B0]; string
0x1800ad585  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ad58b  mov     rcx, rax; String1
0x1800ad58e  lea     rdx, aOrganizations; "organizations"
0x1800ad595  call    wcscmp_0
0x1800ad59a  test    eax, eax
0x1800ad59c  jnz     loc_1800AD634
0x1800ad5a2  mov     [rbp+57h+var_8C], r13d
0x1800ad5a6  mov     [rbp+57h+var_98], r13
0x1800ad5aa  mov     rbx, [rbp+57h+var_B8]
0x1800ad5ae  mov     rax, [rbx]
0x1800ad5b1  mov     rdi, [rax]
0x1800ad5b4  lea     rcx, [rbp+57h+var_98]
0x1800ad5b8  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad5bd  lea     r8, [rbp+57h+var_98]
0x1800ad5c1  lea     rdx, _GUID_40285a2b_65d5_41f5_b904_76c860d86e26
0x1800ad5c8  mov     rcx, rbx
0x1800ad5cb  mov     rax, rdi
0x1800ad5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5d3  mov     ebx, eax
0x1800ad5d5  test    eax, eax
0x1800ad5d7  js      loc_1800AD683
0x1800ad5dd  mov     rcx, [rbp+57h+var_98]
0x1800ad5e1  mov     rax, [rcx]
0x1800ad5e4  lea     rdx, [rbp+57h+var_8C]
0x1800ad5e8  mov     rax, [rax+30h]
0x1800ad5ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5f1  mov     ebx, eax
0x1800ad5f3  test    eax, eax
0x1800ad5f5  js      short loc_1800AD675
0x1800ad5f7  cmp     [rbp+57h+var_8C], r15d
0x1800ad5fb  jnz     short loc_1800AD62A
0x1800ad5fd  inc     esi
0x1800ad5ff  mov     rcx, [rbp+57h+var_B8]
0x1800ad603  mov     [rbp+57h+var_70], rcx
0x1800ad607  test    rcx, rcx
0x1800ad60a  jz      short loc_1800AD619
0x1800ad60c  mov     rax, [rcx]
0x1800ad60f  mov     rax, [rax+8]
0x1800ad613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad618  nop
0x1800ad619  mov     r8b, r12b
0x1800ad61c  lea     rdx, [rbp+57h+var_70]
0x1800ad620  mov     rcx, [rbp+57h+var_78]
0x1800ad624  call    ProcessAccount
0x1800ad629  nop
0x1800ad62a  lea     rcx, [rbp+57h+var_98]
0x1800ad62e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad633  nop
0x1800ad634  mov     rcx, [rbp+57h+var_B0]; string
0x1800ad638  call    cs:__imp_WindowsDeleteString
0x1800ad63e  mov     [rbp+57h+var_B0], r13
0x1800ad642  lea     rcx, [rbp+57h+var_A0]
0x1800ad646  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad64b  nop
0x1800ad64c  mov     rcx, [rbp+57h+string]; string
0x1800ad650  call    cs:__imp_WindowsDeleteString
0x1800ad656  mov     [rbp+57h+string], r13
0x1800ad65a  lea     rcx, [rbp+57h+var_A8]
0x1800ad65e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad663  nop
0x1800ad664  lea     rcx, [rbp+57h+var_B8]
0x1800ad668  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad66d  inc     r14d
0x1800ad670  jmp     loc_1800AD44B
0x1800ad675  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad67a  lea     r14, aIwebaccountsys; "IWebAccountSystemInformation::get_Scope"
0x1800ad681  jmp     short loc_1800AD68F
0x1800ad683  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad688  lea     r14, aComptrIwebacco_0; "ComPtr<IWebAccount>::As"
0x1800ad68f  mov     rcx, [rax]
0x1800ad692  cmp     [rcx], r13b
0x1800ad695  lea     rsi, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."...
0x1800ad69c  lea     rdi, aProcessaccount; "ProcessAccounts"
0x1800ad6a3  jz      short loc_1800AD6F6
0x1800ad6a5  mov     r9d, ebx
0x1800ad6a8  mov     r8, r14
0x1800ad6ab  mov     rdx, rdi
0x1800ad6ae  mov     rcx, rsi; Format
0x1800ad6b1  call    wprintf
0x1800ad6b6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad6bb  mov     rcx, [rax]
0x1800ad6be  cmp     [rcx+0Ch], r13b
0x1800ad6c2  jz      short loc_1800AD6F6
0x1800ad6c4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad6c9  mov     rcx, [rax]
0x1800ad6cc  cmp     [rcx+0B8h], r13
0x1800ad6d3  jz      short loc_1800AD6F6
0x1800ad6d5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad6da  mov     rcx, [rax]
0x1800ad6dd  mov     [rsp+0F0h+var_D0], ebx
0x1800ad6e1  mov     r9, r14
0x1800ad6e4  mov     r8, rdi
0x1800ad6e7  mov     rdx, rsi; Format
0x1800ad6ea  mov     rcx, [rcx+0B8h]; Stream
0x1800ad6f1  call    fwprintf_s
0x1800ad6f6  mov     r9d, ebx
0x1800ad6f9  mov     r8, r14
0x1800ad6fc  mov     rdx, rdi
0x1800ad6ff  mov     rcx, rsi; unsigned __int16 *
0x1800ad702  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ad707  nop
0x1800ad708  lea     rcx, [rbp+57h+var_98]
0x1800ad70c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ad711  jmp     loc_1800AD79B
0x1800ad716  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad71b  mov     rcx, [rax]
0x1800ad71e  lea     rdi, aProcessaccount; "ProcessAccounts"
0x1800ad725  lea     rsi, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."...
0x1800ad72c  lea     r14, aIwebaccountpro; "IWebAccountProvider2::get_Authority"
0x1800ad733  cmp     [rcx], r13b
0x1800ad736  jz      short loc_1800AD789
0x1800ad738  mov     r9d, ebx
0x1800ad73b  mov     r8, r14
0x1800ad73e  mov     rdx, rdi
0x1800ad741  mov     rcx, rsi; Format
0x1800ad744  call    wprintf
0x1800ad749  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad74e  mov     rcx, [rax]
0x1800ad751  cmp     [rcx+0Ch], r13b
0x1800ad755  jz      short loc_1800AD789
0x1800ad757  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad75c  mov     rcx, [rax]
0x1800ad75f  cmp     [rcx+0B8h], r13
0x1800ad766  jz      short loc_1800AD789
0x1800ad768  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ad76d  mov     rcx, [rax]
0x1800ad770  mov     [rsp+0F0h+var_D0], ebx
0x1800ad774  mov     r9, r14
0x1800ad777  mov     r8, rdi
0x1800ad77a  mov     rdx, rsi; Format
0x1800ad77d  mov     rcx, [rcx+0B8h]; Stream
0x1800ad784  call    fwprintf_s
0x1800ad789  mov     r9d, ebx
0x1800ad78c  mov     r8, r14
0x1800ad78f  mov     rdx, rdi
0x1800ad792  mov     rcx, rsi; unsigned __int16 *
0x1800ad795  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ad79a  nop
0x1800ad79b  mov     rcx, [rbp+57h+var_B0]; string
  ... truncated ...
```
