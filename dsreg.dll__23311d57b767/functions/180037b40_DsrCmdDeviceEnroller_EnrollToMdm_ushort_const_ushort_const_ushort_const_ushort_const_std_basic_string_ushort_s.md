# DsrCmdDeviceEnroller::EnrollToMdm(ushort const *,ushort const *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180037b40`
- end: `0x18003827d`
- name: `?EnrollToMdm@DsrCmdDeviceEnroller@@QEAAJPEBG000AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1853`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099424`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x18000bac0`
- `0x18002dd24`
- `0x1800307c4`
- `0x1800318e8`
- `0x180037b40`
- `0x18003e2c0`
- `0x180044300`
- `0x180044d30`
- `0x18004c840`
- `0x180067c6c`
- `0x18009fe40`
- `0x18009fe80`
- `0x1800a0840`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038197`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800381f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038202`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038170`

## string_xrefs

- `0x180037fde`: `WaitForCompletionOrTimeoutNoThrow`
- `0x180037cf2`: `accessToken`
- `0x180037d0c`: `accessToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DsrCmdDeviceEnroller::EnrollToMdm(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        _QWORD *Src)
{
  _WORD *v10; // rcx
  unsigned int v11; // ebx
  const unsigned __int16 *v12; // rdx
  const WCHAR *v13; // rbx
  __int64 v14; // rcx
  int v15; // eax
  const wchar_t *v16; // r8
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, __int64, __int128 *, __int64 *, __int64 *); // rdi
  __int64 v19; // rcx
  __int128 v20; // xmm6
  __int128 v21; // xmm7
  __int128 v22; // xmm8
  __int128 v23; // xmm9
  __int128 v24; // xmm10
  __int64 v25; // xmm11_8
  const wchar_t *v26; // rbx
  __int64 v27; // rsi
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, __int128 *, _QWORD); // rdi
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // rcx
  DWORD v31; // edx
  int v32; // r8d
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v35; // rcx
  __int64 v36; // rsi
  __int64 v37; // r8
  __int64 v38; // rdi
  int (__fastcall *v39)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  char v42; // [rsp+48h] [rbp-C0h] BYREF
  int v43; // [rsp+4Ch] [rbp-BCh] BYREF
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+58h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+70h] [rbp-98h] BYREF
  HSTRING v49; // [rsp+78h] [rbp-90h] BYREF
  HSTRING v50; // [rsp+80h] [rbp-88h] BYREF
  HSTRING v51; // [rsp+88h] [rbp-80h] BYREF
  HSTRING v52; // [rsp+90h] [rbp-78h] BYREF
  HSTRING v53; // [rsp+98h] [rbp-70h] BYREF
  HSTRING v54; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v55; // [rsp+A8h] [rbp-60h] BYREF
  const unsigned __int16 *v56; // [rsp+B0h] [rbp-58h] BYREF
  const unsigned __int16 *v57; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v58; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v59; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v60; // [rsp+D8h] [rbp-30h]
  __int128 v61; // [rsp+E8h] [rbp-20h]
  __int128 v62; // [rsp+F8h] [rbp-10h]
  __int128 v63; // [rsp+108h] [rbp+0h]
  __int64 v64; // [rsp+118h] [rbp+10h]
  __int128 v65; // [rsp+128h] [rbp+20h] BYREF
  __int128 v66; // [rsp+138h] [rbp+30h]
  __int128 v67; // [rsp+148h] [rbp+40h]
  __int128 v68; // [rsp+158h] [rbp+50h]
  __int128 v69; // [rsp+168h] [rbp+60h]
  __int64 v70; // [rsp+178h] [rbp+70h]
  __int128 hstringHeader; // [rsp+188h] [rbp+80h] BYREF
  __int128 hstringHeader_16; // [rsp+198h] [rbp+90h]

  v56 = a2;
  string = (HSTRING)a3;
  v57 = a4;
  v58 = a5;
  v43 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v55 = 0;
  memset_0(&v59, 0, 0x58u);
  v42 = 0;
  LODWORD(v48) = 0;
  v54 = 0;
  v53 = 0;
  v52 = 0;
  v51 = 0;
  v50 = 0;
  v49 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"DsrCmdDeviceEnroller::EnrollToMdm");
  Src[2] = 0;
  if ( Src[3] <= 7u )
    v10 = Src;
  else
    v10 = (_WORD *)*Src;
  *v10 = 0;
  if ( (unsigned int)IsEmptyString(a2) )
  {
    v11 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null or empty.", L"DsrCmdDeviceEnroller::EnrollToMdm", L"tenantId");
    v12 = L"tenantId";
LABEL_6:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DsrCmdDeviceEnroller::EnrollToMdm", v12);
    goto LABEL_56;
  }
  if ( (unsigned int)IsEmptyString(a3) )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"DsrCmdDeviceEnroller::EnrollToMdm",
      L"mdmEnrollmentUrl");
    v12 = L"mdmEnrollmentUrl";
    goto LABEL_6;
  }
  if ( (unsigned int)IsEmptyString(a4) )
  {
    v11 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null or empty.",
      L"DsrCmdDeviceEnroller::EnrollToMdm",
      L"mdmResourceId");
    v12 = L"mdmResourceId";
    goto LABEL_6;
  }
  if ( (unsigned int)IsEmptyString(a5) )
  {
    v11 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null or empty.", L"DsrCmdDeviceEnroller::EnrollToMdm", L"accessToken");
    v12 = L"accessToken";
    goto LABEL_6;
  }
  v13 = &cchOriginalDestLength;
  Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v54, &cchOriginalDestLength, 0);
  Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v53, &string);
  Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v52, &v57);
  Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v51, &v58);
  Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v50, &v56);
  if ( *(_QWORD *)(a1 + 24) )
    v13 = *(const WCHAR **)(a1 + 24);
  v56 = v13;
  Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v49, &v56);
  *(_QWORD *)&v59 = v54;
  *((_QWORD *)&v59 + 1) = v53;
  *(_QWORD *)&v62 = v52;
  *(_QWORD *)&v60 = v51;
  *(_QWORD *)&v63 = v50;
  LODWORD(v61) = 12;
  *((_QWORD *)&v63 + 1) = v49;
  v14 = v47;
  v47 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&hstringHeader,
    L"Windows.Internal.Management.Enrollment.Enroller",
    0x30u,
    0x2Fu);
  v15 = Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(
          *((_QWORD *)&hstringHeader_16 + 1),
          &v47);
  v11 = v15;
  if ( v15 < 0 )
  {
    v16 = L"ActivateInstance";
LABEL_19:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrCmdDeviceEnroller::EnrollToMdm",
      v16,
      (unsigned int)v15);
    goto LABEL_56;
  }
  v17 = v47;
  v18 = *(__int64 (__fastcall **)(__int64, __int64, __int128 *, __int64 *, __int64 *))(*(_QWORD *)v47 + 112LL);
  v19 = v55;
  v55 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = v59;
  v65 = v59;
  v21 = v60;
  v66 = v60;
  v22 = v61;
  v67 = v61;
  v23 = v62;
  v68 = v62;
  v24 = v63;
  v69 = v63;
  v25 = v64;
  v70 = v64;
  v15 = v18(v17, 6, &v65, &v48, &v55);
  v11 = v15;
  if ( v15 < 0 )
  {
    v16 = L"Enrollment::CanEnroll";
    goto LABEL_19;
  }
  if ( (_DWORD)v48 == 1 )
  {
    v28 = v47;
    v29 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v47 + 72LL);
    v30 = v46;
    v46 = 0;
    if ( v30 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v30)[2])(v30);
    v65 = v20;
    v66 = v21;
    v67 = v22;
    v68 = v23;
    v69 = v24;
    v70 = v25;
    v15 = v29(v28, &v65, &v46);
    v11 = v15;
    if ( v15 < 0 )
    {
      v16 = L"Enrollment::AADEnrollAsync";
      goto LABEL_19;
    }
    v15 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(
            v46,
            v31,
            v32,
            &v42);
    v11 = v15;
    if ( v15 < 0 )
    {
      v16 = L"WaitForCompletionOrTimeoutNoThrow";
      goto LABEL_19;
    }
    if ( v42 )
    {
      v11 = -2147024638;
      Logger::TraceError(
        L"%s: AADEnrollAsync failed with timeout (error code: 0x%08x).",
        L"DsrCmdDeviceEnroller::EnrollToMdm",
        2147942658LL);
      goto LABEL_56;
    }
    v33 = v46;
    v34 = (*v46)[8];
    v35 = v45;
    v45 = 0;
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v34)(v33, &v45);
    v11 = v15;
    if ( v15 < 0 )
    {
      v16 = L"AsyncOperation<EnrollmentResult*>::GetResults";
      goto LABEL_19;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 64LL))(v45, &v43);
    v11 = v15;
    if ( v15 < 0 )
    {
      v16 = L"EnrollmentResult::get_EnrollmentErrorCode";
      goto LABEL_19;
    }
    if ( v43 < 0 )
    {
      hstringHeader = 0;
      hstringHeader_16 = 0;
      string = 0;
      Logger::TraceError(L"%s: MDM enrollment failed with error code 0x%08x.", L"DsrCmdDeviceEnroller::EnrollToMdm");
      v36 = -1;
      if ( (int)StringCchPrintfExW((wchar_t *)&hstringHeader, 0xFu, 0, 0, 0, L"0x%08x", 0) >= 0 )
      {
        std::wstring::_Append<unsigned short>(Src);
        v37 = -1;
        do
          ++v37;
        while ( *((_WORD *)&hstringHeader + v37) );
        std::wstring::_Append<unsigned short>(Src);
      }
      v38 = v45;
      v39 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 72LL);
      WindowsDeleteString(string);
      string = 0;
      if ( v39(v38, &string) >= 0 )
      {
        std::wstring::_Append<unsigned short>(Src);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        do
          ++v36;
        while ( StringRawBuffer[v36] );
        std::wstring::_Append<unsigned short>(Src);
      }
      v11 = v43;
      WindowsDeleteString(string);
    }
  }
  else
  {
    if ( (_DWORD)v48 )
    {
      v26 = L"CanEnrollWithEviction";
      if ( (_DWORD)v48 != 2 )
        v26 = L"<unknown>";
    }
    else
    {
      v26 = L"CannotEnroll";
    }
    Logger::TraceError(
      L"%s: MDM enrollment cannot be performed. MDM CanEnroll call returned %s value.",
      L"DsrCmdDeviceEnroller::EnrollToMdm",
      v26);
    std::wstring::_Append<unsigned short>(Src);
    v27 = -1;
    do
      ++v27;
    while ( v26[v27] );
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
    v11 = -2145648525;
  }
LABEL_56:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DsrCmdDeviceEnroller::EnrollToMdm", v11);
  WindowsDeleteString(v49);
  v49 = 0;
  WindowsDeleteString(v50);
  v50 = 0;
  WindowsDeleteString(v51);
  v51 = 0;
  WindowsDeleteString(v52);
  v52 = 0;
  WindowsDeleteString(v53);
  v53 = 0;
  WindowsDeleteString(v54);
  v54 = 0;
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v55);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v45);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>((__int64 *)&v46);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebProviderError,wil::err_returncode_policy>(&v47);
  return v11;
}

```

## disassembly

```asm
0x180037b40  mov     rax, rsp
0x180037b43  push    rbp
0x180037b44  push    rbx
0x180037b45  push    rsi
0x180037b46  push    rdi
0x180037b47  push    r12
0x180037b49  push    r13
0x180037b4b  push    r14
0x180037b4d  push    r15
0x180037b4f  lea     rbp, [rax-158h]
0x180037b56  sub     rsp, 218h
0x180037b5d  movaps  xmmword ptr [rax-58h], xmm6
0x180037b61  movaps  xmmword ptr [rax-68h], xmm7
0x180037b65  movaps  xmmword ptr [rax-78h], xmm8
0x180037b6a  movaps  xmmword ptr [rax-88h], xmm9
0x180037b72  movaps  xmmword ptr [rax-98h], xmm10
0x180037b7a  movaps  xmmword ptr [rax-0A8h], xmm11
0x180037b82  mov     rax, cs:__security_cookie
0x180037b89  xor     rax, rsp
0x180037b8c  mov     [rbp+150h+var_B0], rax
0x180037b93  mov     rdi, r9
0x180037b96  mov     rbx, r8
0x180037b99  mov     r15, rdx
0x180037b9c  mov     r12, rcx
0x180037b9f  mov     r14, [rbp+150h+Src]
0x180037ba6  mov     [rbp+150h+var_1A8], rdx
0x180037baa  mov     [rsp+250h+string], rbx
0x180037baf  mov     [rbp+150h+var_1A0], r9
0x180037bb3  mov     rsi, [rbp+150h+arg_20]
0x180037bba  mov     [rbp+150h+var_198], rsi
0x180037bbe  xor     r13d, r13d
0x180037bc1  mov     dword ptr [rsp+250h+var_210+4], r13d
0x180037bc6  mov     [rsp+250h+var_1F0], r13
0x180037bcb  mov     [rsp+250h+var_1F8], r13
0x180037bd0  mov     [rsp+250h+var_200], r13
0x180037bd5  mov     [rbp+150h+var_1B0], r13
0x180037bd9  xor     edx, edx; Val
0x180037bdb  lea     r8d, [r13+58h]; Size
0x180037bdf  lea     rcx, [rbp+150h+var_190]; void *
0x180037be3  call    memset_0
0x180037be8  mov     byte ptr [rsp+250h+var_210], r13b
0x180037bed  mov     dword ptr [rsp+250h+var_1E8], r13d
0x180037bf2  mov     [rbp+150h+var_1B8], r13
0x180037bf6  mov     [rbp+150h+var_1C0], r13
0x180037bfa  mov     [rbp+150h+var_1C8], r13
0x180037bfe  mov     [rbp+150h+var_1D0], r13
0x180037c02  mov     [rsp+250h+var_1D8], r13
0x180037c07  mov     [rsp+250h+var_1E0], r13
0x180037c0c  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037c13  lea     rcx, aSStarted; "%s started"
0x180037c1a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180037c1f  mov     [r14+10h], r13
0x180037c23  cmp     qword ptr [r14+18h], 7
0x180037c28  jbe     short loc_180037C2F
0x180037c2a  mov     rcx, [r14]
0x180037c2d  jmp     short loc_180037C32
0x180037c2f  mov     rcx, r14
0x180037c32  mov     [rcx], r13w
0x180037c36  mov     rcx, r15; unsigned __int16 *
0x180037c39  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180037c3e  test    eax, eax
0x180037c40  jz      short loc_180037C79
0x180037c42  mov     ebx, 80070057h
0x180037c47  lea     r8, aTenantid_1; "tenantId"
0x180037c4e  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037c55  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180037c5c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180037c61  lea     rdx, aTenantid_1; "tenantId"
0x180037c68  lea     rcx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037c6f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180037c74  jmp     loc_18003819D
0x180037c79  mov     rcx, rbx; unsigned __int16 *
0x180037c7c  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180037c81  test    eax, eax
0x180037c83  jz      short loc_180037CAD
0x180037c85  mov     ebx, 80070057h
0x180037c8a  lea     r8, aMdmenrollmentu; "mdmEnrollmentUrl"
0x180037c91  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037c98  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180037c9f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180037ca4  lea     rdx, aMdmenrollmentu; "mdmEnrollmentUrl"
0x180037cab  jmp     short loc_180037C68
0x180037cad  mov     rcx, rdi; unsigned __int16 *
0x180037cb0  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180037cb5  test    eax, eax
0x180037cb7  jz      short loc_180037CE1
0x180037cb9  mov     ebx, 80070057h
0x180037cbe  lea     r8, aMdmresourceid; "mdmResourceId"
0x180037cc5  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037ccc  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180037cd3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180037cd8  lea     rdx, aMdmresourceid; "mdmResourceId"
0x180037cdf  jmp     short loc_180037C68
0x180037ce1  mov     rcx, rsi; unsigned __int16 *
0x180037ce4  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180037ce9  test    eax, eax
0x180037ceb  jz      short loc_180037D18
0x180037ced  mov     ebx, 80070057h
0x180037cf2  lea     r8, aAccesstoken; "accessToken"
0x180037cf9  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037d00  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null or empty."
0x180037d07  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180037d0c  lea     rdx, aAccesstoken; "accessToken"
0x180037d13  jmp     loc_180037C68
0x180037d18  xor     r8d, r8d; unsigned int
0x180037d1b  lea     rbx, cchOriginalDestLength
0x180037d22  mov     rdx, rbx; unsigned __int16 *
0x180037d25  lea     rcx, [rbp+150h+var_1B8]; this
0x180037d29  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180037d2e  lea     rdx, [rsp+250h+string]
0x180037d33  lea     rcx, [rbp+150h+var_1C0]
0x180037d37  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037d3c  lea     rdx, [rbp+150h+var_1A0]
0x180037d40  lea     rcx, [rbp+150h+var_1C8]
0x180037d44  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037d49  lea     rdx, [rbp+150h+var_198]
0x180037d4d  lea     rcx, [rbp+150h+var_1D0]
0x180037d51  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037d56  lea     rdx, [rbp+150h+var_1A8]
0x180037d5a  lea     rcx, [rsp+250h+var_1D8]
0x180037d5f  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037d64  cmp     [r12+18h], r13
0x180037d69  cmovnz  rbx, [r12+18h]
0x180037d6f  mov     [rbp+150h+var_1A8], rbx
0x180037d73  lea     rdx, [rbp+150h+var_1A8]
0x180037d77  lea     rcx, [rsp+250h+var_1E0]
0x180037d7c  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180037d81  mov     rax, [rbp+150h+var_1B8]
0x180037d85  mov     qword ptr [rbp+150h+var_190], rax
0x180037d89  mov     rax, [rbp+150h+var_1C0]
0x180037d8d  mov     qword ptr [rbp+150h+var_190+8], rax
0x180037d91  mov     rax, [rbp+150h+var_1C8]
0x180037d95  mov     qword ptr [rbp+150h+var_160], rax
0x180037d99  mov     rax, [rbp+150h+var_1D0]
0x180037d9d  mov     qword ptr [rbp+150h+var_180], rax
0x180037da1  mov     rax, [rsp+250h+var_1D8]
0x180037da6  mov     qword ptr [rbp+150h+var_150], rax
0x180037daa  mov     dword ptr [rbp+150h+var_170], 0Ch
0x180037db1  mov     rax, [rsp+250h+var_1E0]
0x180037db6  mov     qword ptr [rbp+150h+var_150+8], rax
0x180037dba  mov     rcx, [rsp+250h+var_1F0]
0x180037dbf  mov     [rsp+250h+var_1F0], r13
0x180037dc4  test    rcx, rcx
0x180037dc7  jz      short loc_180037DD6
0x180037dc9  mov     rax, [rcx]
0x180037dcc  mov     rax, [rax+10h]
0x180037dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037dd5  nop
0x180037dd6  mov     [rbp+150h+var_B8], r13
0x180037ddd  mov     r9d, 2Fh ; '/'; unsigned int
0x180037de3  lea     r8d, [r9+1]; unsigned int
0x180037de7  lea     rdx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x180037dee  lea     rcx, [rbp+150h+hstringHeader]; hstringHeader
0x180037df5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180037dfa  nop
0x180037dfb  lea     rdx, [rsp+250h+var_1F0]
0x180037e00  mov     rcx, [rbp+150h+var_B8]
0x180037e07  call    ??$ActivateInstance@UIEnrollment@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIEnrollment@Enrollment@Management@Internal@1@@Z; Windows::Foundation::ActivateInstance<Windows::Internal::Management::Enrollment::IEnrollment>(HSTRING__ *,Windows::Internal::Management::Enrollment::IEnrollment * *)
0x180037e0c  mov     ebx, eax
0x180037e0e  test    eax, eax
0x180037e10  jns     short loc_180037E34
0x180037e12  lea     r8, aActivateinstan; "ActivateInstance"
0x180037e19  mov     r9d, eax
0x180037e1c  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037e23  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180037e2a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180037e2f  jmp     loc_18003819D
0x180037e34  mov     rbx, [rsp+250h+var_1F0]
0x180037e39  mov     rax, [rbx]
0x180037e3c  mov     rdi, [rax+70h]
0x180037e40  mov     rcx, [rbp+150h+var_1B0]
0x180037e44  mov     [rbp+150h+var_1B0], r13
0x180037e48  test    rcx, rcx
0x180037e4b  jz      short loc_180037E5A
0x180037e4d  mov     rax, [rcx]
0x180037e50  mov     rax, [rax+10h]
0x180037e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e59  nop
0x180037e5a  movaps  xmm6, [rbp+150h+var_190]
0x180037e5e  movaps  [rbp+150h+var_130], xmm6
0x180037e62  movaps  xmm7, [rbp+150h+var_180]
0x180037e66  movaps  [rbp+150h+var_120], xmm7
0x180037e6a  movaps  xmm8, [rbp+150h+var_170]
0x180037e6f  movaps  [rbp+150h+var_110], xmm8
0x180037e74  movaps  xmm9, [rbp+150h+var_160]
0x180037e79  movaps  [rbp+150h+var_100], xmm9
0x180037e7e  movaps  xmm10, [rbp+150h+var_150]
0x180037e83  movaps  [rbp+150h+var_F0], xmm10
0x180037e88  movsd   xmm11, [rbp+150h+var_140]
0x180037e8e  movsd   [rbp+150h+var_E0], xmm11
0x180037e94  lea     rax, [rbp+150h+var_1B0]
0x180037e98  mov     qword ptr [rsp+250h+var_230], rax
0x180037e9d  lea     r9, [rsp+250h+var_1E8]
0x180037ea2  lea     r8, [rbp+150h+var_130]
0x180037ea6  mov     r15d, 6
0x180037eac  mov     edx, r15d
0x180037eaf  mov     rcx, rbx
0x180037eb2  mov     rax, rdi
0x180037eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037eba  mov     ebx, eax
0x180037ebc  test    eax, eax
0x180037ebe  jns     short loc_180037ECC
0x180037ec0  lea     r8, aEnrollmentCane; "Enrollment::CanEnroll"
0x180037ec7  jmp     loc_180037E19
0x180037ecc  mov     eax, dword ptr [rsp+250h+var_1E8]
0x180037ed0  cmp     eax, 1
0x180037ed3  jz      loc_180037F5E
0x180037ed9  test    eax, eax
0x180037edb  jnz     short loc_180037EE6
0x180037edd  lea     rbx, aCannotenroll; "CannotEnroll"
0x180037ee4  jmp     short loc_180037EFB
0x180037ee6  lea     rbx, aCanenrollwithe; "CanEnrollWithEviction"
0x180037eed  lea     rcx, aUnknown_0; "<unknown>"
0x180037ef4  cmp     eax, 2
0x180037ef7  cmovnz  rbx, rcx
0x180037efb  mov     r8, rbx
0x180037efe  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180037f05  lea     rcx, aSMdmEnrollment_1; "%s: MDM enrollment cannot be performed."...
0x180037f0c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180037f11  mov     r8d, 1Ch
0x180037f17  lea     rdx, aMdmCanenrollCa; "MDM CanEnroll call returned "
0x180037f1e  mov     rcx, r14; Src
0x180037f21  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180037f26  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180037f2a  inc     rsi
0x180037f2d  cmp     [rbx+rsi*2], r13w
0x180037f32  jnz     short loc_180037F2A
0x180037f34  mov     r8, rsi
0x180037f37  mov     rdx, rbx
0x180037f3a  mov     rcx, r14; Src
0x180037f3d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180037f42  mov     r8, r15
0x180037f45  lea     rdx, aValue; " value"
0x180037f4c  mov     rcx, r14; Src
0x180037f4f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180037f54  mov     ebx, 801C0073h
0x180037f59  jmp     loc_18003819D
0x180037f5e  mov     rbx, [rsp+250h+var_1F0]
0x180037f63  mov     rax, [rbx]
0x180037f66  mov     rdi, [rax+48h]
0x180037f6a  mov     rcx, [rsp+250h+var_1F8]
0x180037f6f  mov     [rsp+250h+var_1F8], r13
0x180037f74  test    rcx, rcx
0x180037f77  jz      short loc_180037F86
0x180037f79  mov     rax, [rcx]
0x180037f7c  mov     rax, [rax+10h]
0x180037f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f85  nop
0x180037f86  movaps  [rbp+150h+var_130], xmm6
0x180037f8a  movaps  [rbp+150h+var_120], xmm7
0x180037f8e  movaps  [rbp+150h+var_110], xmm8
0x180037f93  movaps  [rbp+150h+var_100], xmm9
0x180037f98  movaps  [rbp+150h+var_F0], xmm10
0x180037f9d  movsd   [rbp+150h+var_E0], xmm11
0x180037fa3  lea     r8, [rsp+250h+var_1F8]
0x180037fa8  lea     rdx, [rbp+150h+var_130]
0x180037fac  mov     rcx, rbx
0x180037faf  mov     rax, rdi
0x180037fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fb7  mov     ebx, eax
0x180037fb9  test    eax, eax
0x180037fbb  jns     short loc_180037FC9
0x180037fbd  lea     r8, aEnrollmentAade; "Enrollment::AADEnrollAsync"
0x180037fc4  jmp     loc_180037E19
0x180037fc9  lea     r9, [rsp+250h+var_210]
0x180037fce  mov     rcx, [rsp+250h+var_1F8]
0x180037fd3  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::Management::Enrollment::EnrollmentResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180037fd8  mov     ebx, eax
0x180037fda  test    eax, eax
0x180037fdc  jns     short loc_180037FEA
0x180037fde  lea     r8, aWaitforcomplet_1; "WaitForCompletionOrTimeoutNoThrow"
0x180037fe5  jmp     loc_180037E19
0x180037fea  cmp     byte ptr [rsp+250h+var_210], r13b
0x180037fef  jz      short loc_180038011
0x180037ff1  mov     ebx, 80070102h
0x180037ff6  mov     r8d, ebx
0x180037ff9  lea     rdx, aDsrcmddeviceen_4; "DsrCmdDeviceEnroller::EnrollToMdm"
0x180038000  lea     rcx, aSAadenrollasyn; "%s: AADEnrollAsync failed with timeout "...
0x180038007  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003800c  jmp     loc_18003819D
0x180038011  mov     rbx, [rsp+250h+var_1F8]
0x180038016  mov     rax, [rbx]
0x180038019  mov     rdi, [rax+40h]
0x18003801d  mov     rcx, [rsp+250h+var_200]
0x180038022  mov     [rsp+250h+var_200], r13
0x180038027  test    rcx, rcx
0x18003802a  jz      short loc_180038039
0x18003802c  mov     rdx, [rcx]
0x18003802f  mov     rax, [rdx+10h]
0x180038033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038038  nop
0x180038039  lea     rdx, [rsp+250h+var_200]
0x18003803e  mov     rcx, rbx
0x180038041  mov     rax, rdi
0x180038044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038049  mov     ebx, eax
0x18003804b  test    eax, eax
0x18003804d  jns     short loc_18003805B
0x18003804f  lea     r8, aAsyncoperation; "AsyncOperation<EnrollmentResult*>::GetR"...
0x180038056  jmp     loc_180037E19
  ... truncated ...
```
