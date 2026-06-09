# GetAadUserToken(ushort const * const,ushort const * const,ushort * *)

- ea: `0x1800ce928`
- end: `0x1800cf718`
- name: `?GetAadUserToken@@YAJQEBG0PEAPEAG@Z`
- size: `3568`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cdbe0`

## callees

- `0x18000b884`
- `0x1800124d8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x18006af54`
- `0x18006af9c`
- `0x18006db58`
- `0x1800cc904`
- `0x1800cc94c`
- `0x1800ce928`
- `0x1800cf7b0`
- `0x1800d07d0`
- `0x1800dddf0`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cf49c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cf49c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf48b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf5a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf48b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800cf5a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cf5af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800cf5af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cebb6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cec49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cee1a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cebb6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cec49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cee1a`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800ceb2e`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800ceb2e`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800cea1e`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800cea1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf3a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf54c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf3a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cf54c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cea57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cea57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cf344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ceb9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cec30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cee01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800ceb9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cec30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cee01`

## string_xrefs

- `0x1800ceb96`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x1800cec29`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GetAadUserToken(PCWSTR sourceString, PCWSTR a2, unsigned __int16 **a3)
{
  int v6; // ecx
  unsigned int v7; // esi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // rbx
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, __int64, HSTRING, HSTRING, _DWORD, __int64 *); // rsi
  HSTRING v18; // rdi
  int v19; // ecx
  int v20; // ecx
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, HSTRING, HSTRING, _BYTE *); // rdi
  HSTRING v23; // rbx
  int v24; // ecx
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, HSTRING, HSTRING, _BYTE *); // rdi
  HSTRING v27; // rbx
  int v28; // ecx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, __int64 *); // rbx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64 *); // rbx
  int v36; // ecx
  int v37; // ecx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, _QWORD, __int64 *); // rbx
  int v40; // ecx
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, HSTRING *); // rbx
  int v43; // ecx
  UINT32 v44; // ebx
  int v45; // ecx
  HANDLE ProcessHeap; // rax
  int v47; // ecx
  void *v48; // rbx
  UINT32 v49; // edi
  int v50; // ecx
  const unsigned __int16 *StringRawBuffer; // rax
  HANDLE v52; // rax
  __int64 v53; // rdi
  __int64 (__fastcall *v54)(__int64, __int64 *); // rbx
  int v55; // eax
  int v56; // ecx
  int v57; // eax
  char v58; // [rsp+20h] [rbp-E0h]
  char v59; // [rsp+20h] [rbp-E0h]
  _BYTE v60[4]; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 length; // [rsp+44h] [rbp-BCh] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+50h] [rbp-B0h] BYREF
  int v64; // [rsp+58h] [rbp-A8h] BYREF
  int v65; // [rsp+5Ch] [rbp-A4h] BYREF
  UINT32 dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  int dwBytes_4; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v68; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+70h] [rbp-90h] BYREF
  __int64 v70; // [rsp+78h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-80h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h] BYREF
  __int64 v73; // [rsp+90h] [rbp-70h] BYREF
  __int64 v74; // [rsp+98h] [rbp-68h] BYREF
  __int64 v75; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v76; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v77; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v78; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING v79; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING v81[4]; // [rsp+E0h] [rbp-20h] BYREF

  dwBytes_4 = 0;
  v78 = 0;
  v76 = 0;
  v77 = 0;
  v75 = 0;
  v74 = 0;
  v70 = 0;
  v73 = 0;
  v63 = 0;
  v69 = 0;
  v72 = 0;
  v71 = 0;
  v68 = 0;
  v64 = 0;
  string = 0;
  v65 = 0;
  v60[0] = 0;
  length = 0;
  fnEfsLogTrace1Strings(
    (_DWORD)sourceString,
    (unsigned int)EFS_TRACE_ENTER_EVENT,
    (unsigned int)&::sourceString,
    46,
    29);
  if ( a3 )
    *a3 = 0;
  if ( !sourceString )
  {
    v58 = 41;
LABEL_5:
    v7 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 46, v58);
    goto LABEL_6;
  }
  if ( !a2 )
  {
    v58 = 42;
    goto LABEL_5;
  }
  fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 44);
  v7 = CoIncrementMTAUsage(&v78);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&::sourceString,
              v7,
              46,
              44) >= 0 )
  {
    fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 48);
    if ( WindowsCreateStringReference(
           L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
           0x45u,
           &hstringHeader,
           &v79) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
           v79,
           &v76);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&::sourceString,
                v7,
                46,
                48) >= 0 )
    {
      fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 52);
      if ( WindowsCreateStringReference(
             L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
             0x38u,
             &hstringHeader,
             &v79) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(
             v79,
             &v77);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&::sourceString,
                  v7,
                  46,
                  52) >= 0 )
      {
        fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 55);
        v12 = v76;
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v76 + 88LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
        Windows::Internal::StringReference::_ConstructorHelper(&v79, WIP_AAD_PROVIDER_URL);
        v7 = v13(v12, v79, &v75);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&::sourceString,
                    v7,
                    46,
                    55) >= 0 )
        {
          fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 58);
          v7 = BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(
                 v75,
                 &v74);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&::sourceString,
                      v7,
                      46,
                      58) >= 0 )
          {
            if ( !v74 )
            {
              v7 = -2147023728;
              fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023728, 46, 59);
              goto LABEL_6;
            }
            fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 65);
            v16 = v77;
            v17 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, HSTRING, _DWORD, __int64 *))(*(_QWORD *)v77 + 56LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v70);
            Windows::Internal::StringReference::_ConstructorHelper(v81, WIP_AAD_DSR_CLIENT_ID);
            v18 = v81[0];
            if ( WindowsCreateStringReference(&::sourceString, 0, &hstringHeader, &v79) < 0 )
              RaiseException(0xC000000D, 1u, 0, 0);
            v7 = v17(v16, v74, v79, v18, 0, &v70);
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&::sourceString,
                        v7,
                        46,
                        65) >= 0 )
            {
              fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 67);
              v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 80LL))(v70, &v71);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&::sourceString,
                          v7,
                          46,
                          67) >= 0 )
              {
                fnEfsLogTrace1Strings(v20, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 71);
                v21 = v71;
                v22 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v71 + 80LL);
                Windows::Internal::StringReference::_ConstructorHelper(v81, sourceString);
                v23 = v81[0];
                Windows::Internal::StringReference::_ConstructorHelper(&v79, WIP_AAD_RESOURCE_KEY);
                v7 = v22(v21, v79, v23, v60);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&::sourceString,
                            v7,
                            46,
                            71) >= 0 )
                {
                  fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&::sourceString, 46, 75);
                  v25 = v71;
                  v26 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v71 + 80LL);
                  Windows::Internal::StringReference::_ConstructorHelper(v81, a2);
                  v27 = v81[0];
                  Windows::Internal::StringReference::_ConstructorHelper(&v79, WIP_AAD_AUTHORITY_KEY);
                  v7 = v26(v25, v79, v27, v60);
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&::sourceString,
                              v7,
                              46,
                              75) >= 0 )
                  {
                    fnEfsLogTrace1Strings(
                      v28,
                      (unsigned int)EFS_TRACE_START_EVENT,
                      (unsigned int)&::sourceString,
                      46,
                      77);
                    v29 = v76;
                    v30 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v76 + 48LL);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v73);
                    v7 = v30(v29, v70, &v73);
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&::sourceString,
                                v7,
                                46,
                                77) >= 0 )
                    {
                      fnEfsLogTrace1Strings(
                        v31,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&::sourceString,
                        46,
                        79);
                      v7 = BlockOnCompletionAndGetResults<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>(
                             v73,
                             &v63);
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&::sourceString,
                                  v7,
                                  46,
                                  79) >= 0 )
                      {
                        if ( !v63 )
                        {
                          v59 = 81;
LABEL_32:
                          v7 = -2147418113;
                          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 46, v59);
                          goto LABEL_6;
                        }
                        fnEfsLogTrace1Strings(
                          v32,
                          (unsigned int)EFS_TRACE_START_EVENT,
                          (unsigned int)&::sourceString,
                          46,
                          83);
                        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v63 + 56LL))(v63, &v64);
                        if ( (int)fnEfsLogTrace1String1Dword(
                                    g_hPublisher,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                    (unsigned int)&::sourceString,
                                    v7,
                                    46,
                                    83) >= 0 )
                        {
                          if ( v64 )
                          {
                            switch ( v64 )
                            {
                              case 3:
                                v7 = -2138701812;
                                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2138701812, 46, 121);
                                break;
                              case 1:
                                v7 = -2147023673;
                                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023673, 46, 125);
                                break;
                              case 5:
                                fnEfsLogTrace1Strings(
                                  v33,
                                  (unsigned int)EFS_TRACE_START_EVENT,
                                  (unsigned int)&::sourceString,
                                  46,
                                  129);
                                v53 = v63;
                                v54 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 64LL);
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v68);
                                v55 = v54(v53, &v68);
                                if ( (int)fnEfsLogTrace1String1Dword(
                                            g_hPublisher,
                                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                            (unsigned int)&::sourceString,
                                            v55,
                                            46,
                                            129) >= 0 )
                                {
                                  if ( !v68 )
                                  {
                                    v59 = -126;
                                    goto LABEL_32;
                                  }
                                  fnEfsLogTrace1Strings(
                                    v56,
                                    (unsigned int)EFS_TRACE_START_EVENT,
                                    (unsigned int)&::sourceString,
                                    46,
                                    132);
                                  v57 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v68 + 48LL))(
                                          v68,
                                          &dwBytes_4);
                                  if ( (int)fnEfsLogTrace1String1Dword(
                                              g_hPublisher,
                                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                              (unsigned int)&::sourceString,
                                              v57,
                                              46,
                                              132) >= 0 )
                                  {
                                    v7 = dwBytes_4;
                                    if ( dwBytes_4 > 0 )
                                      v7 = (unsigned __int16)dwBytes_4 | 0x80070000;
                                    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 46, 133);
                                  }
                                }
                                break;
                            }
                          }
                          else
                          {
                            fnEfsLogTrace1Strings(
                              v33,
                              (unsigned int)EFS_TRACE_START_EVENT,
                              (unsigned int)&::sourceString,
                              46,
                              87);
                            v34 = v63;
                            v35 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 48LL);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v69);
                            v7 = v35(v34, &v69);
                            if ( (int)fnEfsLogTrace1String1Dword(
                                        g_hPublisher,
                                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                        (unsigned int)&::sourceString,
                                        v7,
                                        46,
                                        87) >= 0 )
                            {
                              fnEfsLogTrace1Strings(
                                v36,
                                (unsigned int)EFS_TRACE_START_EVENT,
                                (unsigned int)&::sourceString,
                                46,
                                89);
                              v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v69 + 56LL))(v69, &v65);
                              if ( (int)fnEfsLogTrace1String1Dword(
                                          g_hPublisher,
                                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                          (unsigned int)&::sourceString,
                                          v7,
                                          46,
                                          89) >= 0 )
                              {
                                if ( !v65 )
                                {
                                  v59 = 92;
                                  goto LABEL_32;
                                }
                                fnEfsLogTrace1Strings(
                                  v37,
                                  (unsigned int)EFS_TRACE_START_EVENT,
                                  (unsigned int)&::sourceString,
                                  46,
                                  95);
                                v38 = v69;
                                v39 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v69 + 48LL);
                                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v72);
                                v7 = v39(v38, 0, &v72);
                                if ( (int)fnEfsLogTrace1String1Dword(
                                            g_hPublisher,
                                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                            (unsigned int)&::sourceString,
                                            v7,
                                            46,
                                            95) >= 0 )
                                {
                                  fnEfsLogTrace1Strings(
                                    v40,
                                    (unsigned int)EFS_TRACE_START_EVENT,
                                    (unsigned int)&::sourceString,
                                    46,
                                    97);
                                  v41 = v72;
                                  v42 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v72 + 48LL);
                                  WindowsDeleteString(string);
                                  string = 0;
                                  v7 = v42(v41, &string);
                                  if ( (int)fnEfsLogTrace1String1Dword(
                                              g_hPublisher,
                                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                              (unsigned int)&::sourceString,
                                              v7,
                                              46,
                                              97) >= 0 )
                                  {
                                    WindowsGetStringRawBuffer(string, &length);
                                    if ( !length )
                                    {
                                      v59 = 102;
                                      goto LABEL_32;
                                    }
                                    fnEfsLogTrace1Strings(
                                      v43,
                                      (unsigned int)EFS_TRACE_START_EVENT,
                                      (unsigned int)&::sourceString,
                                      46,
                                      105);
                                    v44 = length + 1;
                                    if ( length + 1 < length )
                                    {
                                      v7 = -2147024362;
                                      v44 = -1;
                                    }
                                    else
                                    {
                                      v7 = 0;
                                    }
                                    dwBytes = v44;
                                    if ( (int)fnEfsLogTrace1String1Dword(
                                                g_hPublisher,
                                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                                (unsigned int)&::sourceString,
                                                v7,
                                                46,
                                                105) >= 0 )
                                    {
                                      fnEfsLogTrace1Strings(
                                        v45,
                                        (unsigned int)EFS_TRACE_START_EVENT,
                                        (unsigned int)&::sourceString,
                                        46,
                                        107);
                                      v7 = ULongLongToULong(2LL * v44, &dwBytes);
                                      if ( (int)fnEfsLogTrace1String1Dword(
                                                  g_hPublisher,
                                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                                  (unsigned int)&::sourceString,
                                                  v7,
                                                  46,
                                                  107) >= 0 )
                                      {
                                        ProcessHeap = GetProcessHeap();
                                        v48 = HeapAlloc(ProcessHeap, 8u, dwBytes);
                                        if ( v48 )
                                        {
                                          fnEfsLogTrace1Strings(
                                            v47,
                                            (unsigned int)EFS_TRACE_START_EVENT,
                                            (unsigned int)&::sourceString,
                                            46,
                                            112);
                                          v49 = length + 1;
                                          if ( length + 1 < length )
                                          {
                                            v7 = -2147024362;
                                            v49 = -1;
                                          }
                                          else
                                          {
                                            v7 = 0;
                                          }
                                          if ( (int)fnEfsLogTrace1String1Dword(
                                                      g_hPublisher,
                                                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                                      (unsigned int)&::sourceString,
                                                      v7,
                                                      46,
                                                      112) < 0
                                            || (fnEfsLogTrace1Strings(
                                                  v50,
                                                  (unsigned int)EFS_TRACE_START_EVENT,
                                                  (unsigned int)&::sourceString,
                                                  46,
                                                  114),
                                                StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
                                                v7 = StringCchCopyW((unsigned __int16 *)v48, v49, StringRawBuffer),
                                                (int)fnEfsLogTrace1String1Dword(
                                                       g_hPublisher,
                                                       (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                                       (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                                       (unsigned int)&::sourceString,
                                                       v7,
                                                       46,
                                                       114) < 0) )
                                          {
                                            v52 = GetProcessHeap();
                                            HeapFree(v52, 0, v48);
                                          }
                                          else
                                          {
                                            *a3 = (unsigned __int16 *)v48;
                                          }
                                        }
                                        else
                                        {
                                          v7 = -2147024882;
                                          fnEfsLogTrace1(
                                            g_hPublisher,
                                            (unsigned int)EFS_TRACE_ERROR,
                                            -2147024882,
                                            46,
                                            110);
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_6:
  if ( v78 )
    CoDecrementMTAUsage();
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&::sourceString,
    v7,
    46,
    145);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v71);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v72);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v69);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v70);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v77);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  return v7;
}

```

## disassembly

```asm
0x1800ce928  mov     [rsp-8+arg_18], rbx
0x1800ce92d  push    rbp
0x1800ce92e  push    rsi
0x1800ce92f  push    rdi
0x1800ce930  push    r12
0x1800ce932  push    r13
0x1800ce934  push    r14
0x1800ce936  push    r15
0x1800ce938  lea     rbp, [rsp-10h]
0x1800ce93d  sub     rsp, 110h
0x1800ce944  mov     rax, cs:__security_cookie
0x1800ce94b  xor     rax, rsp
0x1800ce94e  mov     [rbp+40h+var_40], rax
0x1800ce952  mov     r15, r8
0x1800ce955  mov     r12, rdx
0x1800ce958  mov     r14, rcx
0x1800ce95b  xor     r13d, r13d
0x1800ce95e  mov     dword ptr [rsp+140h+dwBytes+4], r13d
0x1800ce963  mov     [rbp+40h+var_88], r13
0x1800ce967  mov     [rbp+40h+var_98], r13
0x1800ce96b  mov     [rbp+40h+var_90], r13
0x1800ce96f  mov     [rbp+40h+var_A0], r13
0x1800ce973  mov     [rbp+40h+var_A8], r13
0x1800ce977  mov     [rsp+140h+var_C8], r13
0x1800ce97c  mov     [rbp+40h+var_B0], r13
0x1800ce980  mov     [rsp+140h+var_F0], r13
0x1800ce985  mov     [rsp+140h+var_D0], r13
0x1800ce98a  mov     [rbp+40h+var_B8], r13
0x1800ce98e  mov     [rbp+40h+var_C0], r13
0x1800ce992  mov     [rsp+140h+var_D8], r13
0x1800ce997  mov     [rsp+140h+var_E8], r13d
0x1800ce99c  mov     [rsp+140h+string], r13
0x1800ce9a1  mov     [rsp+140h+var_E4], r13d
0x1800ce9a6  mov     [rsp+140h+var_100], r13b
0x1800ce9ab  mov     [rsp+140h+length], r13d
0x1800ce9b0  mov     dword ptr [rsp+140h+var_120], 21Dh
0x1800ce9b8  lea     edi, [r13+2Eh]
0x1800ce9bc  mov     r9d, edi
0x1800ce9bf  lea     r8, sourceString
0x1800ce9c6  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800ce9cd  call    fnEfsLogTrace1Strings
0x1800ce9d2  test    r15, r15
0x1800ce9d5  jz      short loc_1800CE9DC
0x1800ce9d7  xor     eax, eax
0x1800ce9d9  mov     [r15], rax
0x1800ce9dc  mov     r9d, edi
0x1800ce9df  test    r14, r14
0x1800ce9e2  jnz     loc_1800CEAFC
0x1800ce9e8  mov     dword ptr [rsp+140h+var_120], 229h
0x1800ce9f0  mov     esi, 80070057h
0x1800ce9f5  mov     r8d, 80070057h
0x1800ce9fb  lea     rdx, EFS_TRACE_ERROR
0x1800cea02  mov     rcx, cs:g_hPublisher
0x1800cea09  call    fnEfsLogTrace1
0x1800cea0e  lea     r12, sourceString
0x1800cea15  mov     rcx, [rbp+40h+var_88]
0x1800cea19  test    rcx, rcx
0x1800cea1c  jz      short loc_1800CEA24
0x1800cea1e  call    cs:__imp_CoDecrementMTAUsage
0x1800cea24  mov     [rsp+140h+var_110], 291h
0x1800cea2c  mov     dword ptr [rsp+140h+var_118], edi
0x1800cea30  mov     dword ptr [rsp+140h+var_120], esi
0x1800cea34  mov     r9, r12
0x1800cea37  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800cea3e  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800cea45  mov     rcx, cs:g_hPublisher
0x1800cea4c  call    fnEfsLogTrace1String1Dword
0x1800cea51  nop
0x1800cea52  mov     rcx, [rsp+140h+string]; string
0x1800cea57  call    cs:__imp_WindowsDeleteString
0x1800cea5d  mov     [rsp+140h+string], r13
0x1800cea62  lea     rcx, [rsp+140h+var_D8]
0x1800cea67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800cea6c  nop
0x1800cea6d  lea     rcx, [rbp+40h+var_C0]
0x1800cea71  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800cea76  nop
0x1800cea77  lea     rcx, [rbp+40h+var_B8]
0x1800cea7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800cea80  nop
0x1800cea81  lea     rcx, [rsp+140h+var_D0]
0x1800cea86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800cea8b  nop
0x1800cea8c  lea     rcx, [rsp+140h+var_F0]
0x1800cea91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800cea96  nop
0x1800cea97  lea     rcx, [rbp+40h+var_B0]
0x1800cea9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800ceaa0  nop
0x1800ceaa1  lea     rcx, [rsp+140h+var_C8]
0x1800ceaa6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800ceaab  nop
0x1800ceaac  lea     rcx, [rbp+40h+var_A8]
0x1800ceab0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ceab5  nop
0x1800ceab6  lea     rcx, [rbp+40h+var_A0]
0x1800ceaba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ceabf  nop
0x1800ceac0  lea     rcx, [rbp+40h+var_90]
0x1800ceac4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800ceac9  nop
0x1800ceaca  lea     rcx, [rbp+40h+var_98]
0x1800ceace  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cead3  mov     eax, esi
0x1800cead5  mov     rcx, [rbp+40h+var_40]
0x1800cead9  xor     rcx, rsp; StackCookie
0x1800ceadc  call    __security_check_cookie
0x1800ceae1  mov     rbx, [rsp+140h+arg_18]
0x1800ceae9  add     rsp, 110h
0x1800ceaf0  pop     r15
0x1800ceaf2  pop     r14
0x1800ceaf4  pop     r13
0x1800ceaf6  pop     r12
0x1800ceaf8  pop     rdi
0x1800ceaf9  pop     rsi
0x1800ceafa  pop     rbp
0x1800ceafb  retn
0x1800ceafc  test    r12, r12
0x1800ceaff  jnz     short loc_1800CEB0E
0x1800ceb01  mov     dword ptr [rsp+140h+var_120], 22Ah
0x1800ceb09  jmp     loc_1800CE9F0
0x1800ceb0e  mov     ebx, 22Ch
0x1800ceb13  mov     dword ptr [rsp+140h+var_120], ebx
0x1800ceb17  lea     r8, sourceString
0x1800ceb1e  lea     rdx, EFS_TRACE_START_EVENT
0x1800ceb25  call    fnEfsLogTrace1Strings
0x1800ceb2a  lea     rcx, [rbp+40h+var_88]
0x1800ceb2e  call    cs:__imp_CoIncrementMTAUsage
0x1800ceb34  mov     esi, eax
0x1800ceb36  mov     [rsp+140h+var_110], ebx
0x1800ceb3a  mov     dword ptr [rsp+140h+var_118], edi
0x1800ceb3e  mov     dword ptr [rsp+140h+var_120], eax
0x1800ceb42  lea     rbx, sourceString
0x1800ceb49  mov     r9, rbx
0x1800ceb4c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ceb53  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ceb5a  mov     rcx, cs:g_hPublisher
0x1800ceb61  call    fnEfsLogTrace1String1Dword
0x1800ceb66  test    eax, eax
0x1800ceb68  js      loc_1800CEA0E
0x1800ceb6e  mov     dword ptr [rsp+140h+var_120], 230h
0x1800ceb76  mov     r9d, edi
0x1800ceb79  mov     r8, rbx
0x1800ceb7c  lea     rdx, EFS_TRACE_START_EVENT
0x1800ceb83  call    fnEfsLogTrace1Strings
0x1800ceb88  nop
0x1800ceb89  lea     r9, [rbp+40h+var_80]; string
0x1800ceb8d  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x1800ceb91  mov     edx, 45h ; 'E'; length
0x1800ceb96  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800ceb9d  call    cs:__imp_WindowsCreateStringReference
0x1800ceba3  test    eax, eax
0x1800ceba5  jns     short loc_1800CEBBD
0x1800ceba7  xor     r9d, r9d; lpArguments
0x1800cebaa  xor     r8d, r8d; nNumberOfArguments
0x1800cebad  lea     edx, [r9+1]; dwExceptionFlags
0x1800cebb1  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cebb6  call    cs:__imp_RaiseException
0x1800cebbc  nop
0x1800cebbd  lea     rdx, [rbp+40h+var_98]
0x1800cebc1  mov     rcx, [rbp+40h+var_80]
0x1800cebc5  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x1800cebca  mov     esi, eax
0x1800cebcc  mov     [rsp+140h+var_110], 230h
0x1800cebd4  mov     dword ptr [rsp+140h+var_118], edi
0x1800cebd8  mov     dword ptr [rsp+140h+var_120], eax
0x1800cebdc  mov     r9, rbx
0x1800cebdf  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cebe6  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cebed  mov     rcx, cs:g_hPublisher
0x1800cebf4  call    fnEfsLogTrace1String1Dword
0x1800cebf9  test    eax, eax
0x1800cebfb  js      loc_1800CEA0E
0x1800cec01  mov     dword ptr [rsp+140h+var_120], 234h
0x1800cec09  mov     r9d, edi
0x1800cec0c  mov     r8, rbx
0x1800cec0f  lea     rdx, EFS_TRACE_START_EVENT
0x1800cec16  call    fnEfsLogTrace1Strings
0x1800cec1b  nop
0x1800cec1c  lea     r9, [rbp+40h+var_80]; string
0x1800cec20  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x1800cec24  mov     edx, 38h ; '8'; length
0x1800cec29  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800cec30  call    cs:__imp_WindowsCreateStringReference
0x1800cec36  test    eax, eax
0x1800cec38  jns     short loc_1800CEC50
0x1800cec3a  xor     r9d, r9d; lpArguments
0x1800cec3d  xor     r8d, r8d; nNumberOfArguments
0x1800cec40  lea     edx, [r9+1]; dwExceptionFlags
0x1800cec44  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cec49  call    cs:__imp_RaiseException
0x1800cec4f  nop
0x1800cec50  lea     rdx, [rbp+40h+var_90]
0x1800cec54  mov     rcx, [rbp+40h+var_80]
0x1800cec58  call    ??$GetActivationFactory@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>>)
0x1800cec5d  mov     esi, eax
0x1800cec5f  mov     [rsp+140h+var_110], 234h
0x1800cec67  mov     dword ptr [rsp+140h+var_118], edi
0x1800cec6b  mov     dword ptr [rsp+140h+var_120], eax
0x1800cec6f  mov     r9, rbx
0x1800cec72  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800cec79  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800cec80  mov     rcx, cs:g_hPublisher
0x1800cec87  call    fnEfsLogTrace1String1Dword
0x1800cec8c  test    eax, eax
0x1800cec8e  js      loc_1800CEA0E
0x1800cec94  mov     r13d, 237h
0x1800cec9a  mov     dword ptr [rsp+140h+var_120], r13d
0x1800cec9f  mov     r9d, edi
0x1800ceca2  mov     r8, rbx
0x1800ceca5  lea     rdx, EFS_TRACE_START_EVENT
0x1800cecac  call    fnEfsLogTrace1Strings
0x1800cecb1  mov     rdi, [rbp+40h+var_98]
0x1800cecb5  mov     rax, [rdi]
0x1800cecb8  mov     rbx, [rax+58h]
0x1800cecbc  lea     rcx, [rbp+40h+var_A0]
0x1800cecc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cecc5  mov     rdx, cs:?WIP_AAD_PROVIDER_URL@@3QEAGEA; sourceString
0x1800ceccc  lea     rcx, [rbp+40h+var_80]; string
0x1800cecd0  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800cecd5  lea     r8, [rbp+40h+var_A0]
0x1800cecd9  mov     rdx, [rbp+40h+var_80]
0x1800cecdd  mov     rcx, rdi
0x1800cece0  mov     rax, rbx
0x1800cece3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cece8  mov     esi, eax
0x1800cecea  mov     [rsp+140h+var_110], r13d
0x1800cecef  mov     edi, 2Eh ; '.'
0x1800cecf4  mov     dword ptr [rsp+140h+var_118], edi
0x1800cecf8  mov     dword ptr [rsp+140h+var_120], eax
0x1800cecfc  lea     r9, sourceString
0x1800ced03  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ced0a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ced11  mov     rcx, cs:g_hPublisher
0x1800ced18  call    fnEfsLogTrace1String1Dword
0x1800ced1d  xor     r13d, r13d
0x1800ced20  test    eax, eax
0x1800ced22  js      loc_1800CEA0E
0x1800ced28  mov     ebx, 23Ah
0x1800ced2d  mov     dword ptr [rsp+140h+var_120], ebx
0x1800ced31  mov     r9d, edi
0x1800ced34  lea     r8, sourceString
0x1800ced3b  lea     rdx, EFS_TRACE_START_EVENT
0x1800ced42  call    fnEfsLogTrace1Strings
0x1800ced47  lea     rdx, [rbp+40h+var_A8]
0x1800ced4b  mov     rcx, [rbp+40h+var_A0]
0x1800ced4f  call    ??$BlockOnCompletionAndGetResults@PEAVWebAccountProvider@Credentials@Security@Windows@@UIWebAccountProvider@234@@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Security::Credentials::WebAccountProvider *,Windows::Security::Credentials::IWebAccountProvider>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>>,tagCOWAIT_FLAGS,void *)
0x1800ced54  mov     esi, eax
0x1800ced56  mov     [rsp+140h+var_110], ebx
0x1800ced5a  mov     dword ptr [rsp+140h+var_118], edi
0x1800ced5e  mov     dword ptr [rsp+140h+var_120], eax
0x1800ced62  lea     r9, sourceString
0x1800ced69  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800ced70  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800ced77  mov     rcx, cs:g_hPublisher
0x1800ced7e  call    fnEfsLogTrace1String1Dword
0x1800ced83  test    eax, eax
0x1800ced85  js      loc_1800CEA0E
0x1800ced8b  mov     r9d, edi
0x1800ced8e  cmp     [rbp+40h+var_A8], r13
0x1800ced92  jnz     short loc_1800CEDAC
0x1800ced94  mov     esi, 80070490h
0x1800ced99  mov     dword ptr [rsp+140h+var_120], 23Bh
0x1800ceda1  mov     r8d, 80070490h
0x1800ceda7  jmp     loc_1800CE9FB
0x1800cedac  mov     dword ptr [rsp+140h+var_120], 241h
0x1800cedb4  lea     r8, sourceString
0x1800cedbb  lea     rdx, EFS_TRACE_START_EVENT
0x1800cedc2  call    fnEfsLogTrace1Strings
0x1800cedc7  mov     rbx, [rbp+40h+var_90]
0x1800cedcb  mov     rax, [rbx]
0x1800cedce  mov     rsi, [rax+38h]
0x1800cedd2  lea     rcx, [rsp+140h+var_C8]
0x1800cedd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800ceddc  mov     rdx, cs:?WIP_AAD_DSR_CLIENT_ID@@3QEAGEA; sourceString
0x1800cede3  lea     rcx, [rbp+40h+var_60]; string
0x1800cede7  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800cedec  mov     rdi, [rbp+40h+var_60]
0x1800cedf0  lea     r9, [rbp+40h+var_80]; string
0x1800cedf4  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x1800cedf8  xor     edx, edx; length
0x1800cedfa  lea     rcx, sourceString; sourceString
0x1800cee01  call    cs:__imp_WindowsCreateStringReference
0x1800cee07  test    eax, eax
0x1800cee09  jns     short loc_1800CEE21
0x1800cee0b  xor     r9d, r9d; lpArguments
0x1800cee0e  xor     r8d, r8d; nNumberOfArguments
0x1800cee11  lea     edx, [r9+1]; dwExceptionFlags
0x1800cee15  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cee1a  call    cs:__imp_RaiseException
0x1800cee20  nop
0x1800cee21  lea     rax, [rsp+140h+var_C8]
0x1800cee26  mov     [rsp+140h+var_118], rax
0x1800cee2b  mov     dword ptr [rsp+140h+var_120], r13d
0x1800cee30  mov     r9, rdi
0x1800cee33  mov     r8, [rbp+40h+var_80]
0x1800cee37  mov     rdx, [rbp+40h+var_A8]
0x1800cee3b  mov     rcx, rbx
0x1800cee3e  mov     rax, rsi
0x1800cee41  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
