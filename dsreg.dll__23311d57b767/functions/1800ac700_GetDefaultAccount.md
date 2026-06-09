# GetDefaultAccount

- ea: `0x1800ac700`
- end: `0x1800acb4d`
- name: `GetDefaultAccount`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

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
- `0x1800abc0c`
- `0x1800abcac`
- `0x1800abcf4`
- `0x1800ac700`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac9dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acadc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acaea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac9dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acadc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800acaea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aca71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aca80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800acab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800acabf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aca71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aca80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800acab0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800acabf`

## string_xrefs

- `0x1800ac746`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x1800ac94a`: `ComPtr<IWebAccount>::As`
- `0x1800ac88b`: `BlockOnCompletionAndGetResults`
- `0x1800ac867`: `ITokenBrokerInternalStatics::GetDefaultSignInAccountAsync`
- `0x1800ac82a`: `ComPtr<ITokenBrokerInternalStatics>::As`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 GetDefaultAccount()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  int v2; // esi
  _BYTE **CurrentRef; // rax
  const wchar_t *v4; // r15
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  _BYTE **v33; // rax
  const wchar_t *v34; // r15
  __int64 v35; // rdx
  __int64 v36; // rcx
  _QWORD *v37; // rax
  __int64 v38; // rdx
  _QWORD *v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, HSTRING *); // rbx
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v47)(_QWORD, GUID *, __int64); // rbx
  __int64 v48; // rdx
  __int64 v49; // rcx
  _QWORD *v50; // rax
  __int64 v51; // rdx
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v53; // rbx
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // rax
  PCWSTR v57; // rbx
  PCWSTR v58; // rax
  HSTRING v60; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  __int64 v62; // [rsp+40h] [rbp-39h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-31h] BYREF
  __int64 v64; // [rsp+50h] [rbp-29h] BYREF
  __int64 v65; // [rsp+58h] [rbp-21h] BYREF
  __int64 v66; // [rsp+60h] [rbp-19h] BYREF
  __int64 (__fastcall ***v67)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  __int64 v69; // [rsp+88h] [rbp+Fh]

  v67 = 0;
  v65 = 0;
  v66 = 0;
  v64 = 0;
  v63 = 0;
  v69 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
         v69,
         (__int64)&v67);
  if ( v2 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v1, v0);
    v4 = L"GetActivationFactory";
    goto LABEL_3;
  }
  v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v67;
  v13 = **v67;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v65);
  v2 = v13(v12, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v65);
  if ( v2 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v15, v14);
    v4 = L"ComPtr<ITokenBrokerInternalStatics>::As";
    goto LABEL_3;
  }
  v16 = v65;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 232LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v64);
  v2 = v17(v16, &v64);
  if ( v2 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v19, v18);
    v4 = L"ITokenBrokerInternalStatics::GetDefaultSignInAccountAsync";
    goto LABEL_3;
  }
  v2 = BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(
         v64,
         (__int64)&v66);
  if ( v2 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v21, v20);
    v4 = L"BlockOnCompletionAndGetResults";
    goto LABEL_3;
  }
  v22 = v66;
  v23 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v66 + 48LL);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v63);
  v2 = v23(v22, &v63);
  if ( v2 < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v25, v24);
    v4 = L"IGetDefaultSignInAccountResult::get_DefaultWebAccount";
LABEL_3:
    if ( **CurrentRef )
    {
      wprintf(L"%s: %s failed with error code: 0x%08x.\n", L"GetDefaultAccount", v4, (unsigned int)v2);
      v7 = (_QWORD *)CmdOptions::GetCurrentRef(v6, v5);
      if ( *(_BYTE *)(*v7 + 12LL) )
      {
        v9 = (_QWORD *)CmdOptions::GetCurrentRef(*v7, v8);
        if ( *(_QWORD *)(*v9 + 184LL) )
        {
          v11 = CmdOptions::GetCurrentRef(*v9, v10);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v11 + 184LL),
            L"%s: %s failed with error code: 0x%08x.\n",
            L"GetDefaultAccount",
            v4,
            v2);
        }
      }
    }
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.\n", L"GetDefaultAccount", v4, (unsigned int)v2);
    goto LABEL_37;
  }
  if ( v63 )
  {
    v62 = 0;
    string = 0;
    v60 = 0;
    v2 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
           &v63,
           (__int64)&v62);
    if ( v2 >= 0 )
    {
      v42 = v62;
      v43 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v62 + 48LL);
      WindowsDeleteString(string);
      string = 0;
      v2 = v43(v42, &string);
      if ( v2 >= 0 )
      {
        v46 = v63;
        v47 = (*v63)[7];
        WindowsDeleteString(v60);
        v60 = 0;
        v2 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64), HSTRING *))v47)(v46, &v60);
        if ( v2 >= 0 )
        {
          v50 = (_QWORD *)CmdOptions::GetCurrentRef(v49, v48);
          if ( *(_BYTE *)(*v50 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v50, v51) + 184LL) )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(v60, 0);
            v53 = WindowsGetStringRawBuffer(string, 0);
            v56 = CmdOptions::GetCurrentRef(v55, v54);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v56 + 184LL),
              L"Default account: %s, user: %s.\n",
              v53,
              StringRawBuffer);
          }
          v57 = WindowsGetStringRawBuffer(v60, 0);
          v58 = WindowsGetStringRawBuffer(string, 0);
          wprintf(L"Default account: %s, user: %s.\n", v58, v57);
          goto LABEL_36;
        }
        v33 = (_BYTE **)CmdOptions::GetCurrentRef(v49, v48);
        v34 = L"IWebAccount::get_UserName";
      }
      else
      {
        v33 = (_BYTE **)CmdOptions::GetCurrentRef(v45, v44);
        v34 = L"IWebAccount2::get_Id";
      }
    }
    else
    {
      v33 = (_BYTE **)CmdOptions::GetCurrentRef(v32, v31);
      v34 = L"ComPtr<IWebAccount>::As";
    }
    if ( **v33 )
    {
      wprintf(L"%s: %s failed with error code: 0x%08x.\n", L"GetDefaultAccount", v34, (unsigned int)v2);
      v37 = (_QWORD *)CmdOptions::GetCurrentRef(v36, v35);
      if ( *(_BYTE *)(*v37 + 12LL) )
      {
        v39 = (_QWORD *)CmdOptions::GetCurrentRef(*v37, v38);
        if ( *(_QWORD *)(*v39 + 184LL) )
        {
          v41 = CmdOptions::GetCurrentRef(*v39, v40);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v41 + 184LL),
            L"%s: %s failed with error code: 0x%08x.\n",
            L"GetDefaultAccount",
            v34,
            v2);
        }
      }
    }
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.\n", L"GetDefaultAccount", v34, (unsigned int)v2);
LABEL_36:
    WindowsDeleteString(v60);
    v60 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v62);
    goto LABEL_37;
  }
  v26 = (_QWORD *)CmdOptions::GetCurrentRef(v25, v24);
  if ( *(_BYTE *)(*v26 + 12LL) )
  {
    v28 = (_QWORD *)CmdOptions::GetCurrentRef(*v26, v27);
    if ( *(_QWORD *)(*v28 + 184LL) )
    {
      v30 = CmdOptions::GetCurrentRef(v29, *v28);
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v30 + 184LL), L"Default account is not set.\n");
    }
  }
  wprintf(L"Default account is not set.\n");
LABEL_37:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v63);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v64);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v66);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v65);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v67);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800ac700  push    rbp
0x1800ac702  push    rbx
0x1800ac703  push    rsi
0x1800ac704  push    rdi
0x1800ac705  push    r14
0x1800ac707  push    r15
0x1800ac709  lea     rbp, [rsp-2Fh]
0x1800ac70e  sub     rsp, 0A8h
0x1800ac715  mov     rax, cs:__security_cookie
0x1800ac71c  xor     rax, rsp
0x1800ac71f  mov     [rbp+57h+var_40], rax
0x1800ac723  xor     r14d, r14d
0x1800ac726  mov     [rbp+57h+var_68], r14
0x1800ac72a  mov     [rbp+57h+var_78], r14
0x1800ac72e  mov     [rbp+57h+var_70], r14
0x1800ac732  mov     [rbp+57h+var_80], r14
0x1800ac736  mov     [rbp+57h+var_88], r14
0x1800ac73a  mov     [rbp+57h+var_48], r14
0x1800ac73e  lea     r9d, [r14+40h]; unsigned int
0x1800ac742  lea     r8d, [r14+41h]; unsigned int
0x1800ac746  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x1800ac74d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800ac751  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800ac756  lea     rdx, [rbp+57h+var_68]
0x1800ac75a  mov     rcx, [rbp+57h+var_48]
0x1800ac75e  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x1800ac763  mov     esi, eax
0x1800ac765  test    eax, eax
0x1800ac767  jns     loc_1800AC7F6
0x1800ac76d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac772  lea     r15, aGetactivationf; "GetActivationFactory"
0x1800ac779  lea     rbx, aGetdefaultacco; "GetDefaultAccount"
0x1800ac780  lea     rdi, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."...
0x1800ac787  mov     rcx, [rax]
0x1800ac78a  cmp     [rcx], r14b
0x1800ac78d  jz      short loc_1800AC7E0
0x1800ac78f  mov     r9d, esi
0x1800ac792  mov     r8, r15
0x1800ac795  mov     rdx, rbx
0x1800ac798  mov     rcx, rdi; Format
0x1800ac79b  call    wprintf
0x1800ac7a0  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac7a5  mov     rcx, [rax]
0x1800ac7a8  cmp     [rcx+0Ch], r14b
0x1800ac7ac  jz      short loc_1800AC7E0
0x1800ac7ae  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac7b3  mov     rcx, [rax]
0x1800ac7b6  cmp     [rcx+0B8h], r14
0x1800ac7bd  jz      short loc_1800AC7E0
0x1800ac7bf  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac7c4  mov     rcx, [rax]
0x1800ac7c7  mov     [rsp+0D0h+var_B0], esi
0x1800ac7cb  mov     r9, r15
0x1800ac7ce  mov     r8, rbx
0x1800ac7d1  mov     rdx, rdi; Format
0x1800ac7d4  mov     rcx, [rcx+0B8h]; Stream
0x1800ac7db  call    fwprintf_s
0x1800ac7e0  mov     r9d, esi
0x1800ac7e3  mov     r8, r15
0x1800ac7e6  mov     rdx, rbx
0x1800ac7e9  mov     rcx, rdi; unsigned __int16 *
0x1800ac7ec  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ac7f1  jmp     loc_1800ACAFE
0x1800ac7f6  mov     rbx, [rbp+57h+var_68]
0x1800ac7fa  mov     rax, [rbx]
0x1800ac7fd  mov     rdi, [rax]
0x1800ac800  lea     rcx, [rbp+57h+var_78]
0x1800ac804  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ac809  lea     r8, [rbp+57h+var_78]
0x1800ac80d  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x1800ac814  mov     rcx, rbx
0x1800ac817  mov     rax, rdi
0x1800ac81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac81f  mov     esi, eax
0x1800ac821  test    eax, eax
0x1800ac823  jns     short loc_1800AC836
0x1800ac825  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac82a  lea     r15, aComptrItokenbr; "ComPtr<ITokenBrokerInternalStatics>::As"
0x1800ac831  jmp     loc_1800AC779
0x1800ac836  mov     rdi, [rbp+57h+var_78]
0x1800ac83a  mov     rax, [rdi]
0x1800ac83d  mov     rbx, [rax+0E8h]
0x1800ac844  lea     rcx, [rbp+57h+var_80]
0x1800ac848  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ac84d  lea     rdx, [rbp+57h+var_80]
0x1800ac851  mov     rcx, rdi
0x1800ac854  mov     rax, rbx
0x1800ac857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac85c  mov     esi, eax
0x1800ac85e  test    eax, eax
0x1800ac860  jns     short loc_1800AC873
0x1800ac862  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac867  lea     r15, aItokenbrokerin; "ITokenBrokerInternalStatics::GetDefault"...
0x1800ac86e  jmp     loc_1800AC779
0x1800ac873  lea     rdx, [rbp+57h+var_70]
0x1800ac877  mov     rcx, [rbp+57h+var_80]
0x1800ac87b  call    ??$BlockOnCompletionAndGetResults@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@UIGetDefaultSignInAccountResult@23456@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *,Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::IGetDefaultSignInAccountResult>>,tagCOWAIT_FLAGS,void *)
0x1800ac880  mov     esi, eax
0x1800ac882  test    eax, eax
0x1800ac884  jns     short loc_1800AC897
0x1800ac886  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac88b  lea     r15, aBlockoncomplet; "BlockOnCompletionAndGetResults"
0x1800ac892  jmp     loc_1800AC779
0x1800ac897  mov     rdi, [rbp+57h+var_70]
0x1800ac89b  mov     rax, [rdi]
0x1800ac89e  mov     rbx, [rax+30h]
0x1800ac8a2  lea     rcx, [rbp+57h+var_88]
0x1800ac8a6  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800ac8ab  lea     rdx, [rbp+57h+var_88]
0x1800ac8af  mov     rcx, rdi
0x1800ac8b2  mov     rax, rbx
0x1800ac8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8ba  mov     esi, eax
0x1800ac8bc  test    eax, eax
0x1800ac8be  jns     short loc_1800AC8D1
0x1800ac8c0  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac8c5  lea     r15, aIgetdefaultsig; "IGetDefaultSignInAccountResult::get_Def"...
0x1800ac8cc  jmp     loc_1800AC779
0x1800ac8d1  cmp     [rbp+57h+var_88], r14
0x1800ac8d5  jnz     short loc_1800AC922
0x1800ac8d7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac8dc  mov     rcx, [rax]
0x1800ac8df  cmp     [rcx+0Ch], r14b
0x1800ac8e3  jz      short loc_1800AC911
0x1800ac8e5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac8ea  mov     rdx, [rax]
0x1800ac8ed  cmp     [rdx+0B8h], r14
0x1800ac8f4  jz      short loc_1800AC911
0x1800ac8f6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac8fb  mov     rcx, [rax]
0x1800ac8fe  lea     rdx, aDefaultAccount; "Default account is not set.\n"
0x1800ac905  mov     rcx, [rcx+0B8h]; Stream
0x1800ac90c  call    fwprintf_s
0x1800ac911  lea     rcx, aDefaultAccount; "Default account is not set.\n"
0x1800ac918  call    wprintf
0x1800ac91d  jmp     loc_1800ACAFE
0x1800ac922  mov     [rbp+57h+var_90], r14
0x1800ac926  mov     [rbp+57h+string], r14
0x1800ac92a  mov     [rbp+57h+var_A0], r14
0x1800ac92e  lea     rdx, [rbp+57h+var_90]
0x1800ac932  lea     rcx, [rbp+57h+var_88]
0x1800ac936  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x1800ac93b  mov     esi, eax
0x1800ac93d  test    eax, eax
0x1800ac93f  jns     loc_1800AC9CE
0x1800ac945  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac94a  lea     r15, aComptrIwebacco_0; "ComPtr<IWebAccount>::As"
0x1800ac951  lea     rdi, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."...
0x1800ac958  mov     rcx, [rax]
0x1800ac95b  lea     rbx, aGetdefaultacco; "GetDefaultAccount"
0x1800ac962  cmp     [rcx], r14b
0x1800ac965  jz      short loc_1800AC9B8
0x1800ac967  mov     r9d, esi
0x1800ac96a  mov     r8, r15
0x1800ac96d  mov     rdx, rbx
0x1800ac970  mov     rcx, rdi; Format
0x1800ac973  call    wprintf
0x1800ac978  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac97d  mov     rcx, [rax]
0x1800ac980  cmp     [rcx+0Ch], r14b
0x1800ac984  jz      short loc_1800AC9B8
0x1800ac986  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac98b  mov     rcx, [rax]
0x1800ac98e  cmp     [rcx+0B8h], r14
0x1800ac995  jz      short loc_1800AC9B8
0x1800ac997  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ac99c  mov     rcx, [rax]
0x1800ac99f  mov     [rsp+0D0h+var_B0], esi
0x1800ac9a3  mov     r9, r15
0x1800ac9a6  mov     r8, rbx
0x1800ac9a9  mov     rdx, rdi; Format
0x1800ac9ac  mov     rcx, [rcx+0B8h]; Stream
0x1800ac9b3  call    fwprintf_s
0x1800ac9b8  mov     r9d, esi
0x1800ac9bb  mov     r8, r15
0x1800ac9be  mov     rdx, rbx
0x1800ac9c1  mov     rcx, rdi; unsigned __int16 *
0x1800ac9c4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ac9c9  jmp     loc_1800ACAD8
0x1800ac9ce  mov     rdi, [rbp+57h+var_90]
0x1800ac9d2  mov     rax, [rdi]
0x1800ac9d5  mov     rbx, [rax+30h]
0x1800ac9d9  mov     rcx, [rbp+57h+string]; string
0x1800ac9dd  call    cs:__imp_WindowsDeleteString
0x1800ac9e3  mov     [rbp+57h+string], r14
0x1800ac9e7  lea     rdx, [rbp+57h+string]
0x1800ac9eb  mov     rcx, rdi
0x1800ac9ee  mov     rax, rbx
0x1800ac9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac9f6  mov     esi, eax
0x1800ac9f8  test    eax, eax
0x1800ac9fa  jns     short loc_1800ACA0D
0x1800ac9fc  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aca01  lea     r15, aIwebaccount2Ge; "IWebAccount2::get_Id"
0x1800aca08  jmp     loc_1800AC951
0x1800aca0d  mov     rdi, [rbp+57h+var_88]
0x1800aca11  mov     rax, [rdi]
0x1800aca14  mov     rbx, [rax+38h]
0x1800aca18  mov     rcx, [rbp+57h+var_A0]; string
0x1800aca1c  call    cs:__imp_WindowsDeleteString
0x1800aca22  mov     [rbp+57h+var_A0], r14
0x1800aca26  lea     rdx, [rbp+57h+var_A0]
0x1800aca2a  mov     rcx, rdi
0x1800aca2d  mov     rax, rbx
0x1800aca30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aca35  mov     esi, eax
0x1800aca37  test    eax, eax
0x1800aca39  jns     short loc_1800ACA4C
0x1800aca3b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aca40  lea     r15, aIwebaccountGet; "IWebAccount::get_UserName"
0x1800aca47  jmp     loc_1800AC951
0x1800aca4c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aca51  mov     rcx, [rax]
0x1800aca54  cmp     [rcx+0Ch], r14b
0x1800aca58  jz      short loc_1800ACAAA
0x1800aca5a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aca5f  mov     rcx, [rax]
0x1800aca62  cmp     [rcx+0B8h], r14
0x1800aca69  jz      short loc_1800ACAAA
0x1800aca6b  xor     edx, edx; length
0x1800aca6d  mov     rcx, [rbp+57h+var_A0]; string
0x1800aca71  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aca77  mov     rdi, rax
0x1800aca7a  xor     edx, edx; length
0x1800aca7c  mov     rcx, [rbp+57h+string]; string
0x1800aca80  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aca86  mov     rbx, rax
0x1800aca89  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aca8e  mov     rcx, [rax]
0x1800aca91  mov     r9, rdi
0x1800aca94  mov     r8, rbx
0x1800aca97  lea     rdx, aDefaultAccount_0; "Default account: %s, user: %s.\n"
0x1800aca9e  mov     rcx, [rcx+0B8h]; Stream
0x1800acaa5  call    fwprintf_s
0x1800acaaa  xor     edx, edx; length
0x1800acaac  mov     rcx, [rbp+57h+var_A0]; string
0x1800acab0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800acab6  mov     rbx, rax
0x1800acab9  xor     edx, edx; length
0x1800acabb  mov     rcx, [rbp+57h+string]; string
0x1800acabf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800acac5  mov     r8, rbx
0x1800acac8  mov     rdx, rax
0x1800acacb  lea     rcx, aDefaultAccount_0; "Default account: %s, user: %s.\n"
0x1800acad2  call    wprintf
0x1800acad7  nop
0x1800acad8  mov     rcx, [rbp+57h+var_A0]; string
0x1800acadc  call    cs:__imp_WindowsDeleteString
0x1800acae2  mov     [rbp+57h+var_A0], r14
0x1800acae6  mov     rcx, [rbp+57h+string]; string
0x1800acaea  call    cs:__imp_WindowsDeleteString
0x1800acaf0  mov     [rbp+57h+string], r14
0x1800acaf4  lea     rcx, [rbp+57h+var_90]
0x1800acaf8  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800acafd  nop
0x1800acafe  lea     rcx, [rbp+57h+var_88]
0x1800acb02  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800acb07  nop
0x1800acb08  lea     rcx, [rbp+57h+var_80]
0x1800acb0c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800acb11  nop
0x1800acb12  lea     rcx, [rbp+57h+var_70]
0x1800acb16  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800acb1b  nop
0x1800acb1c  lea     rcx, [rbp+57h+var_78]
0x1800acb20  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800acb25  nop
0x1800acb26  lea     rcx, [rbp+57h+var_68]
0x1800acb2a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800acb2f  mov     eax, esi
0x1800acb31  mov     rcx, [rbp+57h+var_40]
0x1800acb35  xor     rcx, rsp; StackCookie
0x1800acb38  call    __security_check_cookie
0x1800acb3d  add     rsp, 0A8h
0x1800acb44  pop     r15
0x1800acb46  pop     r14
0x1800acb48  pop     rdi
0x1800acb49  pop     rsi
0x1800acb4a  pop     rbx
0x1800acb4b  pop     rbp
0x1800acb4c  retn
```
