# RdpEdpPolicyManager::IsClipboardCopyAllowedInternal(HWND__ *,ushort const *,int *)

- ea: `0x18064ba60`
- end: `0x18064c99d`
- name: `?IsClipboardCopyAllowedInternal@RdpEdpPolicyManager@@AEAAJPEAUHWND__@@PEBGPEAH@Z`
- size: `3901`
- prototype: `__int64 __fastcall(RdpEdpPolicyManager *__hidden this, HWND, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18064b9ac`
- `0x18064c9a4`

## callees

- `0x1800d11a8`
- `0x1800fdc84`
- `0x180101d30`
- `0x18023979c`
- `0x18039f4f0`
- `0x1805d6904`
- `0x18064a268`
- `0x18064ab90`
- `0x18064b04c`
- `0x18064ba60`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18064c02e`
- `OLE32!CoTaskMemFree` at `0x18064c1dd`
- `OLE32!CoTaskMemFree` at `0x18064c362`
- `OLE32!CoTaskMemFree` at `0x18064c4e7`
- `OLE32!CoTaskMemFree` at `0x18064c02e`
- `OLE32!CoTaskMemFree` at `0x18064c1dd`
- `OLE32!CoTaskMemFree` at `0x18064c362`
- `OLE32!CoTaskMemFree` at `0x18064c4e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064bf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064c137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064c2bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064c441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064bf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064c137`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064c2bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18064c441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c93c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c972`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c93c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18064c972`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18064bcea`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18064bcea`

## string_xrefs

- `0x18064bb36`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`
- `0x18064bcb4`: `Windows.Security.EnterpriseData.ProtectionPolicyAuditInfo`
- `0x18064bace`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064bb7b`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064bc34`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064bd0f`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064be03`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064bec8`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064bfad`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c0a8`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c15c`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c22d`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c2e1`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c3b2`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c466`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c56b`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c62f`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c70b`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c7a2`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c848`: `onecoreuap\termsrv\rdpplatform\common\rdplibs\edp\rdpedppolicymanager.cpp`
- `0x18064c14b`: `WindowsCreateString (source identity) failed. hr[0x%x]`
- `0x18064c2d0`: `WindowsCreateString (target identity) failed. hr[0x%x]`
- `0x18064c455`: `WindowsCreateString (data description) failed. hr[0x%x]`
- `0x18064c55a`: `Create audit info failed. hr[0x%x]`
- `0x18064bada`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064bb87`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064bc40`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064bd1b`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064be0f`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064bed4`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064bfb9`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c0b4`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c168`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c239`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c2ed`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c3be`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c472`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c577`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c63b`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c717`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c7ae`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064c854`: `RdpEdpPolicyManager::IsClipboardCopyAllowedInternal`
- `0x18064bcfe`: `GetActivationFactory<ComPtr<IProtectionPolicyAuditInfoFactory>> failed. hr[0x%x]`
- `0x18064bf9c`: `WindowsCreateString (data enterprise id) failed. hr[0x%x]`
- `0x18064c791`: `wil::WaitForCompletionNoThrow failed hr[0x%x]`
- `0x18064c6fa`: `RequestAccessWithAuditingInfoForWindowAsync failed. hr[0x%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall RdpEdpPolicyManager::IsClipboardCopyAllowedInternal(
        RdpEdpPolicyManager *this,
        HWND a2,
        const unsigned __int16 *a3,
        int *a4)
{
  unsigned int v8; // ebx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  int v12; // eax
  __int64 v13; // rbx
  int ActivationFactory; // eax
  int ClipboardWithEnterpriseInfo; // eax
  int v16; // eax
  HRESULT v17; // eax
  int v18; // eax
  HRESULT v19; // eax
  int v20; // eax
  HRESULT v21; // eax
  int v22; // eax
  HRESULT v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, HSTRING, HSTRING, HSTRING, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  int v26; // eax
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rdi
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HWND, HSTRING, _QWORD, __int64, GUID *, __int64 *); // rbx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  char v36; // [rsp+38h] [rbp-100h]
  __int64 v37; // [rsp+40h] [rbp-F8h] BYREF
  __int64 v38; // [rsp+48h] [rbp-F0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-E8h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-E0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-D8h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-D0h] BYREF
  struct IDataObject *v43; // [rsp+70h] [rbp-C8h] BYREF
  unsigned __int64 v44; // [rsp+78h] [rbp-C0h] BYREF
  int v45; // [rsp+80h] [rbp-B8h] BYREF
  PCNZWCH sourceString; // [rsp+88h] [rbp-B0h] BYREF
  PCNZWCH v47; // [rsp+90h] [rbp-A8h] BYREF
  PCNZWCH v48; // [rsp+98h] [rbp-A0h] BYREF
  PCNZWCH v49; // [rsp+A0h] [rbp-98h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-90h] BYREF
  HSTRING v51; // [rsp+B0h] [rbp-88h] BYREF
  HSTRING v52; // [rsp+B8h] [rbp-80h] BYREF
  HSTRING v53; // [rsp+C0h] [rbp-78h] BYREF
  unsigned __int64 v54[2]; // [rsp+C8h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v56; // [rsp+F0h] [rbp-48h]

  v54[1] = -2;
  v44 = (unsigned __int64)a3;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  string = 0;
  if ( !a4 )
  {
    TRC_TraceBufferW(
      3,
      512,
      492,
      (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
      (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
      0,
      L"Unexpected NULL pointer",
      v36);
    v8 = -2147467261;
    goto LABEL_63;
  }
  try
  {
    *a4 = 0;
    v45 = 0;
    v41 = 0;
    v40 = 0;
    v42 = 0;
    v39 = 0;
    v38 = 0;
    v37 = 0;
    v56 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.EnterpriseData.ProtectionPolicyManager",
      0x38u,
      0x37u);
    v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>>(
           v56,
           &v42);
    v8 = v9;
    if ( v9 < 0 )
    {
      TRC_TraceBufferW(
        3,
        512,
        515,
        (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
        (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        L"GetActivationFactory<IProtectionPolicyManagerStatics2> failed. hr[0x%x]",
        v9);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
      goto LABEL_63;
    }
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
    v11 = **v42;
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
    v12 = v11(v10, &GUID_157cfbe4_a78d_4156_b384_61fdac41e686, &v39);
    v8 = v12;
    if ( v12 < 0 )
    {
      TRC_TraceBufferW(
        3,
        512,
        520,
        (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
        (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        L"As (IProtectionPolicyManagerInterop2) failed. hr[0x%x]",
        v12);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
      goto LABEL_63;
    }
    v56 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.EnterpriseData.ProtectionPolicyAuditInfo",
      0x3Au,
      0x39u);
    v13 = v56;
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
    ActivationFactory = RoGetActivationFactory(v13, &GUID_7ed4180b_92e8_42d5_83d4_25440b423549, &v41);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      TRC_TraceBufferW(
        3,
        512,
        526,
        (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
        (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        L"GetActivationFactory<ComPtr<IProtectionPolicyAuditInfoFactory>> failed. hr[0x%x]",
        ActivationFactory);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
      goto LABEL_63;
    }
    v43 = 0;
    sourceString = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
    ClipboardWithEnterpriseInfo = EnterpriseClipboardApi::GetClipboardWithEnterpriseInfo(
                                    (RdpEdpPolicyManager *)((char *)this + 48),
                                    &v43,
                                    (unsigned __int16 **)&sourceString,
                                    (unsigned __int16 **)&v47,
                                    (unsigned __int16 **)&v48,
                                    (unsigned __int16 **)&v49);
    v8 = ClipboardWithEnterpriseInfo;
    if ( ClipboardWithEnterpriseInfo < 0 )
    {
      TRC_TraceBufferW(
        3,
        512,
        542,
        (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
        (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        L"GetClipboardWithEnterpriseInfo failed. hr[0x%x]",
        ClipboardWithEnterpriseInfo);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
      goto LABEL_63;
    }
    if ( sourceString )
    {
      v54[0] = 0;
      v16 = StringCchLengthW(sourceString, 0x100u, v54);
      v8 = v16;
      if ( v16 < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          549,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"StringCchLengthW (data enterprise id) failed hr[0x%x]",
          v16);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        goto LABEL_63;
      }
      if ( v54[0] || !a3 )
      {
        v17 = WindowsCreateString(sourceString, LODWORD(v54[0]) + 1, &string);
        v8 = v17;
        if ( v17 < 0 )
        {
          TRC_TraceBufferW(
            3,
            512,
            558,
            (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
            (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
            0,
            L"WindowsCreateString (data enterprise id) failed. hr[0x%x]",
            v17);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
          goto LABEL_63;
        }
      }
      else
      {
        string = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v44) + 24);
      }
      CoTaskMemFree((LPVOID)sourceString);
      sourceString = 0;
    }
    else if ( a3 )
    {
      string = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v44) + 24);
    }
    if ( v47 )
    {
      v44 = 0;
      v18 = StringCchLengthW(v47, 0x100u, &v44);
      v8 = v18;
      if ( v18 < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          574,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"StringCchLengthW (source identity) failed hr[0x%x]",
          v18);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        goto LABEL_63;
      }
      v19 = WindowsCreateString(v47, v44 + 1, &v51);
      v8 = v19;
      if ( v19 < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          577,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"WindowsCreateString (source identity) failed. hr[0x%x]",
          v19);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        goto LABEL_63;
      }
      CoTaskMemFree((LPVOID)v47);
      v47 = 0;
    }
    if ( v48 )
    {
      v44 = 0;
      v20 = StringCchLengthW(v48, 0x100u, &v44);
      v8 = v20;
      if ( v20 < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          588,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"StringCchLengthW (target identity) failed hr[0x%x]",
          v20);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        goto LABEL_63;
      }
      v21 = WindowsCreateString(v48, v44 + 1, &v52);
      v8 = v21;
      if ( v21 < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          591,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"WindowsCreateString (target identity) failed. hr[0x%x]",
          v21);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        goto LABEL_63;
      }
      CoTaskMemFree((LPVOID)v48);
      v48 = 0;
    }
    if ( v49 )
    {
      v44 = 0;
      v22 = StringCchLengthW(v49, 0x100u, &v44);
      v8 = v22;
      if ( v22 < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          602,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"StringCchLengthW (data description) failed hr[0x%x]",
          v22);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        goto LABEL_63;
      }
      v23 = WindowsCreateString(v49, v44 + 1, &v53);
      v8 = v23;
      if ( v23 < 0 )
      {
        TRC_TraceBufferW(
          3,
          512,
          605,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"WindowsCreateString (data description) failed. hr[0x%x]",
          v23);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        goto LABEL_63;
      }
      CoTaskMemFree((LPVOID)v49);
      v49 = 0;
    }
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v43);
    v24 = v41;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, HSTRING, HSTRING, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v41 + 48LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
    v26 = v25(v24, 2, v53, v51, v52, (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v40);
    v8 = v26;
    if ( v26 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
      v28 = **v40;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      v29 = v28(v27, &GUID_00000000_0000_0000_c000_000000000046, &v38);
      v8 = v29;
      if ( v29 >= 0 )
      {
        v30 = v39;
        v31 = *(__int64 (__fastcall **)(__int64, HWND, HSTRING, _QWORD, __int64, GUID *, __int64 *))(*(_QWORD *)v39 + 56LL);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        v32 = v31(v30, a2, string, 0, v38, &GUID_e8d81715_c56c_5a6b_b738_5df6c2775b7b, &v37);
        v8 = v32;
        if ( v32 >= 0 )
        {
          v33 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> *>(v37);
          v8 = v33;
          if ( v33 >= 0 )
          {
            v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v37 + 64LL))(v37, &v45);
            v8 = v34;
            if ( v34 >= 0 )
            {
              *a4 = v45 == 0;
              v8 = 0;
            }
            else
            {
              TRC_TraceBufferW(
                3,
                512,
                640,
                (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
                (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
                0,
                L"GetResults failed. hr[0x%x]",
                v34);
            }
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
          }
          else
          {
            TRC_TraceBufferW(
              3,
              512,
              637,
              (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
              (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
              0,
              L"wil::WaitForCompletionNoThrow failed hr[0x%x]",
              v33);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
            Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
          }
        }
        else
        {
          TRC_TraceBufferW(
            3,
            512,
            634,
            (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
            (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
            0,
            L"RequestAccessWithAuditingInfoForWindowAsync failed. hr[0x%x]",
            v32);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
          Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
        }
      }
      else
      {
        TRC_TraceBufferW(
          3,
          512,
          625,
          (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
          (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
          0,
          L"AsIID(IID_IUnknown) failed. hr[0x%x]",
          v29);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
      }
    }
    else
    {
      TRC_TraceBufferW(
        3,
        512,
        619,
        (int)L"RdpEdpPolicyManager::IsClipboardCopyAllowedInternal",
        (int)L"onecoreuap\\termsrv\\rdpplatform\\common\\rdplibs\\edp\\rdpedppolicymanager.cpp",
        0,
        L"Create audit info failed. hr[0x%x]",
        v26);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v41);
    }
  }
  catch ( ... )
  {
    v45 = -2147467259;
    v8 = -2147467259;
  }
LABEL_63:
  if ( v51 )
  {
    WindowsDeleteString(v51);
    v51 = 0;
  }
  if ( v52 )
  {
    WindowsDeleteString(v52);
    v52 = 0;
  }
  if ( v53 )
  {
    WindowsDeleteString(v53);
    v53 = 0;
  }
  if ( string )
    WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x18064ba60  mov     r11, rsp
0x18064ba63  push    rbx
0x18064ba64  push    rsi
0x18064ba65  push    rdi
0x18064ba66  push    r12
0x18064ba68  push    r13
0x18064ba6a  push    r14
0x18064ba6c  push    r15
0x18064ba6e  sub     rsp, 100h
0x18064ba75  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x18064ba7d  mov     rax, cs:__security_cookie
0x18064ba84  xor     rax, rsp
0x18064ba87  mov     [rsp+138h+var_40], rax
0x18064ba8f  mov     r12, r9
0x18064ba92  mov     r14, r8
0x18064ba95  mov     r13, rdx
0x18064ba98  mov     r15, rcx
0x18064ba9b  mov     [rsp+138h+var_C0], r8
0x18064baa0  xor     esi, esi
0x18064baa2  mov     [r11-88h], rsi
0x18064baa9  mov     [r11-80h], rsi
0x18064baad  mov     [r11-78h], rsi
0x18064bab1  mov     [r11-90h], rsi
0x18064bab8  test    r9, r9
0x18064babb  jnz     short loc_18064BAFC
0x18064babd  lea     rax, aUnexpectedNull; "Unexpected NULL pointer"
0x18064bac4  mov     [rsp+138h+pszFormat], rax; pszFormat
0x18064bac9  mov     [rsp+138h+var_110], rsi; int
0x18064bace  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x18064bad5  mov     [rsp+138h+var_118], rax; int
0x18064bada  lea     r9, aRdpedppolicyma; "RdpEdpPolicyManager::IsClipboardCopyAll"...
0x18064bae1  mov     edx, 200h; int
0x18064bae6  lea     ecx, [rsi+3]; int
0x18064bae9  lea     r8d, [rdx-14h]; int
0x18064baed  call    TRC_TraceBufferW
0x18064baf2  mov     ebx, 80004003h
0x18064baf7  jmp     loc_18064C914
0x18064bafc  mov     [r9], esi
0x18064baff  mov     [rsp+138h+var_B8], esi
0x18064bb06  mov     [rsp+138h+var_D8], rsi
0x18064bb0b  mov     [rsp+138h+var_E0], rsi
0x18064bb10  mov     [rsp+138h+var_D0], rsi
0x18064bb15  mov     [rsp+138h+var_E8], rsi
0x18064bb1a  mov     [rsp+138h+var_F0], rsi
0x18064bb1f  mov     [rsp+138h+var_F8], rsi
0x18064bb24  mov     [rsp+138h+var_48], rsi
0x18064bb2c  mov     r9d, 37h ; '7'; unsigned int
0x18064bb32  lea     r8d, [r9+1]; unsigned int
0x18064bb36  lea     rdx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyManager@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x18064bb3d  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x18064bb45  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18064bb4a  lea     rdx, [rsp+138h+var_D0]
0x18064bb4f  mov     rcx, [rsp+138h+var_48]
0x18064bb57  call    ??$GetActivationFactory@V?$ComPtr@UIProtectionPolicyManagerStatics2@EnterpriseData@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIProtectionPolicyManagerStatics2@EnterpriseData@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics2>>)
0x18064bb5c  mov     ebx, eax
0x18064bb5e  test    eax, eax
0x18064bb60  jns     loc_18064BBE9
0x18064bb66  mov     dword ptr [rsp+138h+var_100], eax; char
0x18064bb6a  lea     rax, aGetactivationf_5; "GetActivationFactory<IProtectionPolicyM"...
0x18064bb71  mov     [rsp+138h+pszFormat], rax; pszFormat
0x18064bb76  mov     [rsp+138h+var_110], rsi; int
0x18064bb7b  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x18064bb82  mov     [rsp+138h+var_118], rax; int
0x18064bb87  lea     r9, aRdpedppolicyma; "RdpEdpPolicyManager::IsClipboardCopyAll"...
0x18064bb8e  mov     edx, 200h; int
0x18064bb93  mov     ecx, 3; int
0x18064bb98  lea     r8d, [rdx+3]; int
0x18064bb9c  call    TRC_TraceBufferW
0x18064bba1  nop
0x18064bba2  lea     rcx, [rsp+138h+var_F8]
0x18064bba7  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bbac  nop
0x18064bbad  lea     rcx, [rsp+138h+var_F0]
0x18064bbb2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18064bbb7  nop
0x18064bbb8  lea     rcx, [rsp+138h+var_E8]
0x18064bbbd  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bbc2  nop
0x18064bbc3  lea     rcx, [rsp+138h+var_D0]
0x18064bbc8  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bbcd  nop
0x18064bbce  lea     rcx, [rsp+138h+var_E0]
0x18064bbd3  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bbd8  nop
0x18064bbd9  lea     rcx, [rsp+138h+var_D8]
0x18064bbde  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bbe3  nop
0x18064bbe4  jmp     loc_18064C914
0x18064bbe9  mov     rbx, [rsp+138h+var_D0]
0x18064bbee  mov     rax, [rbx]
0x18064bbf1  mov     rdi, [rax]
0x18064bbf4  lea     rcx, [rsp+138h+var_E8]
0x18064bbf9  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bbfe  lea     r8, [rsp+138h+var_E8]
0x18064bc03  lea     rdx, _GUID_157cfbe4_a78d_4156_b384_61fdac41e686
0x18064bc0a  mov     rcx, rbx
0x18064bc0d  mov     rax, rdi
0x18064bc10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18064bc15  mov     ebx, eax
0x18064bc17  test    eax, eax
0x18064bc19  jns     loc_18064BCA2
0x18064bc1f  mov     dword ptr [rsp+138h+var_100], eax; char
0x18064bc23  lea     rax, aAsIprotectionp; "As (IProtectionPolicyManagerInterop2) f"...
0x18064bc2a  mov     [rsp+138h+pszFormat], rax; pszFormat
0x18064bc2f  mov     [rsp+138h+var_110], rsi; int
0x18064bc34  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x18064bc3b  mov     [rsp+138h+var_118], rax; int
0x18064bc40  lea     r9, aRdpedppolicyma; "RdpEdpPolicyManager::IsClipboardCopyAll"...
0x18064bc47  mov     edx, 200h; int
0x18064bc4c  mov     ecx, 3; int
0x18064bc51  lea     r8d, [rdx+8]; int
0x18064bc55  call    TRC_TraceBufferW
0x18064bc5a  nop
0x18064bc5b  lea     rcx, [rsp+138h+var_F8]
0x18064bc60  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bc65  nop
0x18064bc66  lea     rcx, [rsp+138h+var_F0]
0x18064bc6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18064bc70  nop
0x18064bc71  lea     rcx, [rsp+138h+var_E8]
0x18064bc76  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bc7b  nop
0x18064bc7c  lea     rcx, [rsp+138h+var_D0]
0x18064bc81  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bc86  nop
0x18064bc87  lea     rcx, [rsp+138h+var_E0]
0x18064bc8c  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bc91  nop
0x18064bc92  lea     rcx, [rsp+138h+var_D8]
0x18064bc97  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bc9c  nop
0x18064bc9d  jmp     loc_18064C914
0x18064bca2  mov     [rsp+138h+var_48], rsi
0x18064bcaa  mov     r9d, 39h ; '9'; unsigned int
0x18064bcb0  lea     r8d, [r9+1]; unsigned int
0x18064bcb4  lea     rdx, ?RuntimeClass_Windows_Security_EnterpriseData_ProtectionPolicyAuditInfo@@3QBGB; "Windows.Security.EnterpriseData.Protect"...
0x18064bcbb  lea     rcx, [rsp+138h+hstringHeader]; hstringHeader
0x18064bcc3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18064bcc8  nop
0x18064bcc9  mov     rbx, [rsp+138h+var_48]
0x18064bcd1  lea     rcx, [rsp+138h+var_D8]
0x18064bcd6  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bcdb  lea     r8, [rsp+138h+var_D8]
0x18064bce0  lea     rdx, _GUID_7ed4180b_92e8_42d5_83d4_25440b423549
0x18064bce7  mov     rcx, rbx
0x18064bcea  call    cs:__imp_RoGetActivationFactory
0x18064bcf0  mov     ebx, eax
0x18064bcf2  test    eax, eax
0x18064bcf4  jns     loc_18064BD7D
0x18064bcfa  mov     dword ptr [rsp+138h+var_100], eax; char
0x18064bcfe  lea     rax, aGetactivationf_4; "GetActivationFactory<ComPtr<IProtection"...
0x18064bd05  mov     [rsp+138h+pszFormat], rax; pszFormat
0x18064bd0a  mov     [rsp+138h+var_110], rsi; int
0x18064bd0f  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x18064bd16  mov     [rsp+138h+var_118], rax; int
0x18064bd1b  lea     r9, aRdpedppolicyma; "RdpEdpPolicyManager::IsClipboardCopyAll"...
0x18064bd22  mov     edx, 200h; int
0x18064bd27  mov     ecx, 3; int
0x18064bd2c  lea     r8d, [rdx+0Eh]; int
0x18064bd30  call    TRC_TraceBufferW
0x18064bd35  nop
0x18064bd36  lea     rcx, [rsp+138h+var_F8]
0x18064bd3b  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bd40  nop
0x18064bd41  lea     rcx, [rsp+138h+var_F0]
0x18064bd46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18064bd4b  nop
0x18064bd4c  lea     rcx, [rsp+138h+var_E8]
0x18064bd51  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bd56  nop
0x18064bd57  lea     rcx, [rsp+138h+var_D0]
0x18064bd5c  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bd61  nop
0x18064bd62  lea     rcx, [rsp+138h+var_E0]
0x18064bd67  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bd6c  nop
0x18064bd6d  lea     rcx, [rsp+138h+var_D8]
0x18064bd72  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bd77  nop
0x18064bd78  jmp     loc_18064C914
0x18064bd7d  mov     [rsp+138h+var_C8], rsi
0x18064bd82  mov     [rsp+138h+sourceString], rsi
0x18064bd8a  mov     [rsp+138h+var_A8], rsi
0x18064bd92  mov     [rsp+138h+var_A0], rsi
0x18064bd9a  mov     [rsp+138h+var_98], rsi
0x18064bda2  lea     rcx, [rsp+138h+var_C8]
0x18064bda7  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bdac  lea     rcx, [r15+30h]; this
0x18064bdb0  lea     rax, [rsp+138h+var_98]
0x18064bdb8  mov     [rsp+138h+var_110], rax; unsigned __int16 **
0x18064bdbd  lea     rax, [rsp+138h+var_A0]
0x18064bdc5  mov     [rsp+138h+var_118], rax; unsigned __int16 **
0x18064bdca  lea     r9, [rsp+138h+var_A8]; unsigned __int16 **
0x18064bdd2  lea     r8, [rsp+138h+sourceString]; unsigned __int16 **
0x18064bdda  lea     rdx, [rsp+138h+var_C8]; struct IDataObject **
0x18064bddf  call    ?GetClipboardWithEnterpriseInfo@EnterpriseClipboardApi@@QEAAJPEAPEAUIDataObject@@PEAPEAG111@Z; EnterpriseClipboardApi::GetClipboardWithEnterpriseInfo(IDataObject * *,ushort * *,ushort * *,ushort * *,ushort * *)
0x18064bde4  mov     ebx, eax
0x18064bde6  test    eax, eax
0x18064bde8  jns     loc_18064BE7C
0x18064bdee  mov     dword ptr [rsp+138h+var_100], eax; char
0x18064bdf2  lea     rax, aGetclipboardwi; "GetClipboardWithEnterpriseInfo failed. "...
0x18064bdf9  mov     [rsp+138h+pszFormat], rax; pszFormat
0x18064bdfe  mov     [rsp+138h+var_110], rsi; int
0x18064be03  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x18064be0a  mov     [rsp+138h+var_118], rax; int
0x18064be0f  lea     r9, aRdpedppolicyma; "RdpEdpPolicyManager::IsClipboardCopyAll"...
0x18064be16  mov     edx, 200h; int
0x18064be1b  mov     ecx, 3; int
0x18064be20  lea     r8d, [rdx+1Eh]; int
0x18064be24  call    TRC_TraceBufferW
0x18064be29  nop
0x18064be2a  lea     rcx, [rsp+138h+var_C8]
0x18064be2f  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064be34  nop
0x18064be35  lea     rcx, [rsp+138h+var_F8]
0x18064be3a  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064be3f  nop
0x18064be40  lea     rcx, [rsp+138h+var_F0]
0x18064be45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18064be4a  nop
0x18064be4b  lea     rcx, [rsp+138h+var_E8]
0x18064be50  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064be55  nop
0x18064be56  lea     rcx, [rsp+138h+var_D0]
0x18064be5b  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064be60  nop
0x18064be61  lea     rcx, [rsp+138h+var_E0]
0x18064be66  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064be6b  nop
0x18064be6c  lea     rcx, [rsp+138h+var_D8]
0x18064be71  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064be76  nop
0x18064be77  jmp     loc_18064C914
0x18064be7c  mov     rcx, [rsp+138h+sourceString]; unsigned __int16 *
0x18064be84  test    rcx, rcx
0x18064be87  jz      loc_18064C03E
0x18064be8d  mov     [rsp+138h+var_70], rsi
0x18064be95  lea     r8, [rsp+138h+var_70]; unsigned __int64 *
0x18064be9d  mov     edi, 100h
0x18064bea2  mov     edx, edi; unsigned __int64
0x18064bea4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18064bea9  mov     ebx, eax
0x18064beab  test    eax, eax
0x18064bead  jns     loc_18064BF41
0x18064beb3  mov     dword ptr [rsp+138h+var_100], eax; char
0x18064beb7  lea     rax, aStringcchlengt_12; "StringCchLengthW (data enterprise id) f"...
0x18064bebe  mov     [rsp+138h+pszFormat], rax; pszFormat
0x18064bec3  mov     [rsp+138h+var_110], rsi; int
0x18064bec8  lea     rax, aOnecoreuapTerm; "onecoreuap\\termsrv\\rdpplatform\\commo"...
0x18064becf  mov     [rsp+138h+var_118], rax; int
0x18064bed4  lea     r9, aRdpedppolicyma; "RdpEdpPolicyManager::IsClipboardCopyAll"...
0x18064bedb  mov     edx, 200h; int
0x18064bee0  mov     ecx, 3; int
0x18064bee5  lea     r8d, [rdx+25h]; int
0x18064bee9  call    TRC_TraceBufferW
0x18064beee  nop
0x18064beef  lea     rcx, [rsp+138h+var_C8]
0x18064bef4  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bef9  nop
0x18064befa  lea     rcx, [rsp+138h+var_F8]
0x18064beff  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bf04  nop
0x18064bf05  lea     rcx, [rsp+138h+var_F0]
0x18064bf0a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18064bf0f  nop
0x18064bf10  lea     rcx, [rsp+138h+var_E8]
0x18064bf15  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bf1a  nop
0x18064bf1b  lea     rcx, [rsp+138h+var_D0]
0x18064bf20  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bf25  nop
0x18064bf26  lea     rcx, [rsp+138h+var_E0]
0x18064bf2b  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bf30  nop
0x18064bf31  lea     rcx, [rsp+138h+var_D8]
0x18064bf36  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x18064bf3b  nop
0x18064bf3c  jmp     loc_18064C914
0x18064bf41  mov     rdx, [rsp+138h+var_70]
0x18064bf49  test    rdx, rdx
0x18064bf4c  jnz     short loc_18064BF76
0x18064bf4e  test    r14, r14
0x18064bf51  jz      short loc_18064BF76
0x18064bf53  lea     rdx, [rsp+138h+var_C0]
0x18064bf58  lea     rcx, [rsp+138h+hstringHeader]
0x18064bf60  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18064bf65  mov     rcx, [rax+18h]
0x18064bf69  mov     [rsp+138h+string], rcx
0x18064bf71  jmp     loc_18064C026
0x18064bf76  inc     edx; length
0x18064bf78  lea     r8, [rsp+138h+string]; string
0x18064bf80  mov     rcx, [rsp+138h+sourceString]; sourceString
0x18064bf88  call    cs:__imp_WindowsCreateString
0x18064bf8e  mov     ebx, eax
0x18064bf90  test    eax, eax
0x18064bf92  jns     loc_18064C026
0x18064bf98  mov     dword ptr [rsp+138h+var_100], eax; char
0x18064bf9c  lea     rax, aWindowscreates_6; "WindowsCreateString (data enterprise id"...
0x18064bfa3  mov     [rsp+138h+pszFormat], rax; pszFormat
0x18064bfa8  mov     [rsp+138h+var_110], rsi; int
  ... truncated ...
```
