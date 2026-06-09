# CWAMTokenHandler::GetTokenFromAccount(int,Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>,Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccountProvider>,Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory>,CWAMTokenHandler::ClaimsHint,int,Microsoft::WRL::ComPtr<ABI::Windows::Security::Credentials::IWebAccount>,ushort *,ushort *,Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort *)

- ea: `0x1805dc8d8`
- end: `0x1805dd1b3`
- name: `?GetTokenFromAccount@CWAMTokenHandler@@AEAAJHV?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@V?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@ABI@@@34@V?$ComPtr@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@ABI@@@34@UClaimsHint@1@HV?$ComPtr@UIWebAccount@Credentials@Security@Windows@ABI@@@34@PEAG5AEAV?$ComPtr@UIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@@34@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@5@Z`
- size: `2267`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, int, __int64, BSTR pbstr, int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1805dfd78`
- `0x1805e0540`
- `0x1805e0af0`

## callees

- `0x180002058`
- `0x1800054f4`
- `0x18000e490`
- `0x180082ad8`
- `0x1800fdc84`
- `0x180129c2c`
- `0x1805d9a04`
- `0x1805d9ba8`
- `0x1805d9c04`
- `0x1805dbaac`
- `0x1805dbd3c`
- `0x1805dc8ac`
- `0x1805dc8d8`
- `0x1805dd824`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1805dcef7`
- `OLEAUT32!__imp_SysStringLen` at `0x1805dcef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805dd0ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805dd0ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805dcaa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805dcabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805dd09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805dcaa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805dcabe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805dd09a`

## string_xrefs

- `0x1805dca38`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dccbb`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dcdb3`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dcfc7`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dd13d`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805dced1`: `AwaitGetTokenOperation failed!`
- `0x1805dcfb4`: `Web token response vector size is 0`
- `0x1805dd01f`: `Get spTokenResponse`
- `0x1805dd127`: `User hint doesnt match username for token.`
- `0x1805dca25`: `GetTokenFromAccount`
- `0x1805dcb63`: `GetTokenFromAccount`
- `0x1805dca1a`: `WebTokenRequest creation failed`
- `0x1805dcca4`: `InsertTokenRequestProperties failed`
- `0x1805dcbc6`: `spWebTokenRequest3->put_CorrelationId`
- `0x1805dcd99`: `GetTokenSilentlyWithWebAccountAsync failed!`
- `0x1805dcd27`: `Web account found for token retrieval.`
- `0x1805dce83`: `GetTokenSilentlyAsync failed!`
- `0x1805dce18`: `No web account found for token retrieval. Use default.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CWAMTokenHandler::GetTokenFromAccount(
        __int64 a1,
        __int64 a2,
        const char *a3,
        _QWORD *a4,
        __int64 *a5,
        CWAMTokenHandler::ClaimsHint *a6,
        int a7,
        const char *a8,
        BSTR pbstr,
        int a10,
        const char *a11,
        const char *a12,
        const char *a13)
{
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, HSTRING, __int64, struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest **); // rbx
  __int64 v16; // r9
  int inserted; // ebx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  const char **v21; // rax
  int *v22; // rdx
  const char *v23; // r14
  const char *v24; // rsi
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64); // rbx
  __int64 v28; // rdx
  int v29; // eax
  int v30; // r8d
  int v31; // r9d
  CWAMTokenHandler::ClaimsHint *v32; // rdi
  const unsigned __int16 *v33; // r14
  const unsigned __int16 *v34; // rsi
  const unsigned __int16 *v35; // rbx
  const unsigned __int16 *v36; // rdi
  const unsigned __int16 *v37; // rax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest *, _QWORD, __int64 *); // rbx
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  const char *v43; // rax
  __int16 *v44; // rdx
  const char *v45; // rax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest *, __int64 *); // rbx
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64 *); // rbx
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, _QWORD, __int64 *); // rbx
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, __int64 *); // rbx
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rdi
  int v57; // r8d
  int v58; // r9d
  unsigned __int16 *p_Buffer; // [rsp+28h] [rbp-D8h]
  const char **v60; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v61; // [rsp+38h] [rbp-C8h]
  const char **v62; // [rsp+40h] [rbp-C0h]
  const char **v63; // [rsp+48h] [rbp-B8h]
  int v64; // [rsp+70h] [rbp-90h] BYREF
  const char *v65; // [rsp+78h] [rbp-88h] BYREF
  __int64 Buffer; // [rsp+80h] [rbp-80h] BYREF
  const char *v67; // [rsp+88h] [rbp-78h] BYREF
  const char *v68; // [rsp+90h] [rbp-70h] BYREF
  const char *v69; // [rsp+98h] [rbp-68h] BYREF
  const char *v70; // [rsp+A0h] [rbp-60h] BYREF
  struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest *v71; // [rsp+A8h] [rbp-58h] BYREF
  const char *v72; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING v73; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v74; // [rsp+C0h] [rbp-40h] BYREF
  int v75; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v76; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v78; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v79; // [rsp+E8h] [rbp-18h] BYREF
  CWAMTokenHandler::ClaimsHint *v80; // [rsp+F0h] [rbp-10h]
  UINT32 length; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v82; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v83; // [rsp+108h] [rbp+8h]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const char *v86; // [rsp+120h] [rbp+20h]
  _QWORD *v87; // [rsp+128h] [rbp+28h]
  __int64 v88; // [rsp+130h] [rbp+30h]
  CWAMTokenHandler::ClaimsHint *v89; // [rsp+138h] [rbp+38h]
  __int64 v90; // [rsp+140h] [rbp+40h]
  _BYTE v91[32]; // [rsp+148h] [rbp+48h] BYREF

  v85 = -2;
  v83 = a4;
  v70 = a3;
  v86 = a3;
  v87 = a4;
  v84 = (__int64)a5;
  v88 = (__int64)a5;
  v80 = a6;
  v89 = a6;
  v72 = a8;
  v90 = (__int64)a8;
  v67 = a12;
  v65 = a13;
  v71 = 0;
  v74 = 0;
  v76 = 0;
  v75 = 0;
  v79 = 0;
  v78 = 0;
  v73 = 0;
  length = 0;
  v82 = 0;
  string = 0;
  if ( *(_DWORD *)(*((_QWORD *)a6 + 4) - 16LL) )
    Microsoft::WRL::Wrappers::HString::Set<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&string);
  v14 = *a5;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64, struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest **))(*(_QWORD *)*a5 + 48LL);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v71);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer((char *)v80 + 8);
  v16 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v91, &Buffer) + 24);
  inserted = v15(v14, *a4, string, v16, &v71);
  if ( inserted < 0 )
  {
    v20 = dword_1808B5850;
    if ( (unsigned int)dword_1808B5850 <= 2 )
    {
LABEL_7:
      v23 = v72;
      v24 = v70;
      goto LABEL_8;
    }
    v67 = "WebTokenRequest creation failed";
    v68 = "GetTokenFromAccount";
    v64 = 441;
    v69 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
    LODWORD(Buffer) = inserted;
    v65 = "Error HResult failed";
    v63 = &v67;
    v62 = &v68;
    v61 = (unsigned __int16 *)&v64;
    v60 = &v69;
    p_Buffer = (unsigned __int16 *)&Buffer;
    v21 = &v65;
    v22 = (int *)byte_18088C735;
LABEL_6:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v20,
      (_DWORD)v22,
      v18,
      v19,
      (__int64)v21,
      (__int64)p_Buffer,
      (__int64)v60,
      (__int64)v61,
      (__int64)v62,
      (__int64)v63);
    goto LABEL_7;
  }
  if ( (int)Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::As<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest3>(
              &v71,
              &v82) >= 0 )
  {
    if ( a13 )
    {
      if ( *(_WORD *)a13 )
      {
        v26 = v82;
        v27 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 56LL);
        v28 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v91, &v65) + 24);
        v29 = v27(v26, v28);
        if ( v29 < 0 && (unsigned int)dword_1808B5850 > 3 )
        {
          v65 = "GetTokenFromAccount";
          LODWORD(Buffer) = v29;
          v69 = "spWebTokenRequest3->put_CorrelationId";
          v68 = "HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            dword_1808B5850,
            (unsigned int)word_18088C6FA,
            v30,
            v31,
            (__int64)&v68,
            (__int64)&v69,
            (__int64)&Buffer,
            (__int64)&v65);
        }
      }
    }
  }
  v32 = v80;
  v33 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer((char *)v80 + 56);
  v34 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer((char *)v32 + 48);
  v35 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer((char *)v32 + 40);
  v36 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer((char *)v32 + 24);
  v37 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v80);
  inserted = CWAMTokenHandler::InsertTokenRequestProperties(
               (CWAMTokenHandler *)&g_WAMHandler,
               v71,
               v37,
               v36,
               pbstr,
               0,
               v35,
               v34,
               v33,
               0,
               0,
               1,
               0);
  if ( inserted < 0 )
  {
    if ( (unsigned int)dword_1808B5850 <= 2 )
      goto LABEL_7;
    v65 = "InsertTokenRequestProperties failed";
    v69 = "GetTokenFromAccount";
    LODWORD(Buffer) = 464;
    v68 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
    v64 = inserted;
    v67 = "Error HResult failed";
    v63 = &v65;
    v62 = &v69;
    v61 = (unsigned __int16 *)&Buffer;
    v60 = &v68;
    p_Buffer = (unsigned __int16 *)&v64;
    v21 = &v67;
    v22 = &dword_18088C68C;
    goto LABEL_6;
  }
  v23 = v72;
  if ( *(_QWORD *)v72 )
  {
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v65 = "Web account found for token retrieval.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)byte_18088C6D9,
        0,
        v19,
        (__int64)&v65);
    }
    v24 = v70;
    v38 = *(_QWORD *)v70;
    v39 = *(__int64 (__fastcall **)(__int64, struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest *, _QWORD, __int64 *))(**(_QWORD **)v70 + 56LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v74);
    inserted = v39(v38, v71, *(_QWORD *)v23, &v74);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v43 = "GetTokenSilentlyWithWebAccountAsync failed!";
      LODWORD(Buffer) = 475;
      v44 = &word_18088C61E;
      goto LABEL_24;
    }
  }
  else
  {
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v65 = "No web account found for token retrieval. Use default.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)byte_18088C66B,
        0,
        v19,
        (__int64)&v65);
    }
    v24 = v70;
    v46 = *(_QWORD *)v70;
    v47 = *(__int64 (__fastcall **)(__int64, struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest *, __int64 *))(**(_QWORD **)v70 + 48LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v74);
    inserted = v47(v46, v71, &v74);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v43 = "GetTokenSilentlyAsync failed!";
      LODWORD(Buffer) = 485;
      v44 = (__int16 *)byte_18088C903;
      goto LABEL_24;
    }
  }
  v65 = a11;
  LOBYTE(v41) = 1;
  inserted = CWAMTokenHandler::AwaitGetTokenOperation<Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult>>>(
               v40,
               v74,
               v41,
               (unsigned int)&v65,
               (__int64)v67);
  if ( inserted < 0 )
  {
    if ( (unsigned int)dword_1808B5850 <= 2 )
      goto LABEL_8;
    v43 = "AwaitGetTokenOperation failed!";
    LODWORD(Buffer) = 490;
    v44 = (__int16 *)byte_18088C869;
    goto LABEL_24;
  }
  if ( pbstr && SysStringLen(pbstr) )
  {
    v48 = *(_QWORD *)a11;
    v49 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)a11 + 48LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v76);
    inserted = v49(v48, &v76);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v43 = "get_ResponseData";
      LODWORD(Buffer) = 496;
      v44 = &word_18088C8B6;
      goto LABEL_24;
    }
    inserted = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v76 + 56LL))(v76, &v75);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v43 = "get_Size";
      LODWORD(Buffer) = 499;
      v44 = (__int16 *)&dword_18088C81C;
      goto LABEL_24;
    }
    if ( !v75 )
    {
      inserted = -1056919550;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v65 = "Web token response vector size is 0";
      LODWORD(Buffer) = 506;
      v68 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
      v45 = "Error condition failed";
      v44 = word_18088C782;
      goto LABEL_25;
    }
    v50 = v76;
    v51 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v76 + 48LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v79);
    inserted = v51(v50, 0, &v79);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v43 = "Get spTokenResponse";
      LODWORD(Buffer) = 509;
      v44 = (__int16 *)&byte_18088C7CF;
      goto LABEL_24;
    }
    v52 = v79;
    v53 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 64LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v78);
    inserted = v53(v52, &v78);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v43 = "get_WebAccount";
      LODWORD(Buffer) = 513;
      v44 = &word_18088C40E;
      goto LABEL_24;
    }
    v54 = v78;
    v55 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v78 + 56LL);
    WindowsDeleteString(v73);
    v73 = 0;
    inserted = v55(v54, &v73);
    if ( inserted < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_8;
      v43 = "get_UserName";
      LODWORD(Buffer) = 516;
      v44 = word_18088C35A;
LABEL_24:
      v65 = v43;
      v68 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
      v45 = "Error HResult failed";
LABEL_25:
      v67 = v45;
      v69 = "GetTokenFromAccount";
      v64 = inserted;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v40,
        (_DWORD)v44,
        v41,
        v42,
        (__int64)&v67,
        (__int64)&v64,
        (__int64)&v68,
        (__int64)&Buffer,
        (__int64)&v69,
        (__int64)&v65);
      goto LABEL_8;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v73, &length);
    if ( wcsicmp_0(pbstr, StringRawBuffer) )
    {
      inserted = -2147467259;
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v65 = (const char *)StringRawBuffer;
        v69 = (const char *)pbstr;
        v68 = "User hint doesnt match username for token.";
        v67 = "GetTokenFromAccount";
        LODWORD(Buffer) = 526;
        v72 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
        v64 = -2147467259;
        v70 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          dword_1808B5850,
          (unsigned int)&byte_18088C3A7,
          v57,
          v58,
          (__int64)&v70,
          (__int64)&v64,
          (__int64)&v72,
          (__int64)&Buffer,
          (__int64)&v67,
          (__int64)&v68,
          (__int64)&v69,
          (__int64)&v65);
      }
    }
  }
LABEL_8:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v82);
  WindowsDeleteString(v73);
  v73 = 0;
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v79);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v76);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v74);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v71);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(v24);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(v83);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(v84);
  CWAMTokenHandler::ClaimsHint::~ClaimsHint(v80);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(v23);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1805dc8d8  mov     rax, rsp
0x1805dc8db  push    rbp
0x1805dc8dc  push    rsi
0x1805dc8dd  push    rdi
0x1805dc8de  push    r12
0x1805dc8e0  push    r13
0x1805dc8e2  push    r14
0x1805dc8e4  push    r15
0x1805dc8e6  lea     rbp, [rsp-70h]
0x1805dc8eb  sub     rsp, 170h
0x1805dc8f2  mov     [rbp+0A0h+var_88], 0FFFFFFFFFFFFFFFEh
0x1805dc8fa  mov     [rax+8], rbx
0x1805dc8fe  mov     rax, cs:__security_cookie
0x1805dc905  xor     rax, rsp
0x1805dc908  mov     [rbp+0A0h+var_38], rax
0x1805dc90c  mov     r14, r9
0x1805dc90f  mov     [rbp+0A0h+var_98], r9
0x1805dc913  mov     rax, r8
0x1805dc916  mov     [rbp+0A0h+var_100], rax
0x1805dc91a  mov     rsi, [rbp+0A0h+arg_60]
0x1805dc921  mov     [rbp+0A0h+var_80], rax
0x1805dc925  mov     [rbp+0A0h+var_78], r9
0x1805dc929  mov     rbx, [rbp+0A0h+arg_20]
0x1805dc930  mov     [rbp+0A0h+var_90], rbx
0x1805dc934  mov     [rbp+0A0h+var_70], rbx
0x1805dc938  mov     rax, [rbp+0A0h+arg_28]
0x1805dc93f  mov     [rbp+0A0h+var_B0], rax
0x1805dc943  mov     [rbp+0A0h+var_68], rax
0x1805dc947  mov     rcx, [rbp+0A0h+arg_38]
0x1805dc94e  mov     [rbp+0A0h+var_F0], rcx
0x1805dc952  mov     [rbp+0A0h+var_60], rcx
0x1805dc956  mov     r12, [rbp+0A0h+pbstr]
0x1805dc95d  mov     r13, [rbp+0A0h+arg_50]
0x1805dc964  mov     rcx, [rbp+0A0h+arg_58]
0x1805dc96b  mov     [rbp+0A0h+var_118], rcx
0x1805dc96f  mov     [rsp+1A0h+var_128], rsi
0x1805dc974  xor     ecx, ecx
0x1805dc976  mov     [rbp+0A0h+var_F8], rcx
0x1805dc97a  mov     [rbp+0A0h+var_E0], rcx
0x1805dc97e  mov     [rbp+0A0h+var_D0], rcx
0x1805dc982  mov     [rbp+0A0h+var_D8], ecx
0x1805dc985  mov     [rbp+0A0h+var_B8], rcx
0x1805dc989  mov     [rbp+0A0h+var_C0], rcx
0x1805dc98d  mov     [rbp+0A0h+var_E8], rcx
0x1805dc991  mov     [rbp+0A0h+length], ecx
0x1805dc994  mov     [rbp+0A0h+var_A0], rcx
0x1805dc998  mov     [rbp+0A0h+string], rcx
0x1805dc99c  lea     rdx, [rax+20h]
0x1805dc9a0  mov     rax, [rdx]
0x1805dc9a3  cmp     [rax-10h], ecx
0x1805dc9a6  jz      short loc_1805DC9B1
0x1805dc9a8  lea     rcx, [rbp+0A0h+string]; string
0x1805dc9ac  call    ??$Set@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@HString@Wrappers@WRL@Microsoft@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,Microsoft::WRL::Details::Dummy)
0x1805dc9b1  mov     rdi, [rbx]
0x1805dc9b4  mov     rax, [rdi]
0x1805dc9b7  mov     rbx, [rax+30h]
0x1805dc9bb  lea     rcx, [rbp+0A0h+var_F8]
0x1805dc9bf  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dc9c4  mov     rcx, [rbp+0A0h+var_B0]
0x1805dc9c8  add     rcx, 8
0x1805dc9cc  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1805dc9d1  mov     [rbp+0A0h+var_120], rax
0x1805dc9d5  lea     rdx, [rbp+0A0h+var_120]
0x1805dc9d9  lea     rcx, [rbp+0A0h+var_58]
0x1805dc9dd  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1805dc9e2  nop
0x1805dc9e3  lea     rcx, [rbp+0A0h+var_F8]
0x1805dc9e7  mov     [rsp+1A0h+var_180], rcx
0x1805dc9ec  mov     r9, [rax+18h]
0x1805dc9f0  mov     r8, [rbp+0A0h+string]
0x1805dc9f4  mov     rdx, [r14]
0x1805dc9f7  mov     rcx, rdi
0x1805dc9fa  mov     rax, rbx
0x1805dc9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805dca02  mov     ebx, eax
0x1805dca04  xor     r14d, r14d
0x1805dca07  test    eax, eax
0x1805dca09  jns     loc_1805DCB56
0x1805dca0f  mov     ecx, cs:dword_1808B5850
0x1805dca15  cmp     ecx, 2
0x1805dca18  jbe     short loc_1805DCA96
0x1805dca1a  lea     rax, aWebtokenreques_0; "WebTokenRequest creation failed"
0x1805dca21  mov     [rbp+0A0h+var_118], rax
0x1805dca25  lea     r15, aGettokenfromac_0; "GetTokenFromAccount"
0x1805dca2c  mov     [rbp+0A0h+var_110], r15
0x1805dca30  mov     [rsp+1A0h+var_130], 1B9h
0x1805dca38  lea     rax, aClientcoreTerm_42; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805dca3f  mov     [rbp+0A0h+var_108], rax
0x1805dca43  mov     dword ptr [rbp+0A0h+var_120], ebx
0x1805dca46  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1805dca4d  mov     [rsp+1A0h+var_128], rax
0x1805dca52  lea     rax, [rbp+0A0h+var_118]
0x1805dca56  mov     qword ptr [rsp+1A0h+var_158], rax
0x1805dca5b  lea     rax, [rbp+0A0h+var_110]
0x1805dca5f  mov     [rsp+1A0h+var_160], rax
0x1805dca64  lea     rax, [rsp+1A0h+var_130]
0x1805dca69  mov     [rsp+1A0h+var_168], rax
0x1805dca6e  lea     rax, [rbp+0A0h+var_108]
0x1805dca72  mov     [rsp+1A0h+var_170], rax
0x1805dca77  lea     rax, [rbp+0A0h+var_120]
0x1805dca7b  mov     [rsp+1A0h+var_178], rax
0x1805dca80  lea     rax, [rsp+1A0h+var_128]
0x1805dca85  lea     rdx, byte_18088C735
0x1805dca8c  mov     [rsp+1A0h+var_180], rax
0x1805dca91  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1805dca96  mov     r14, [rbp+0A0h+var_F0]
0x1805dca9a  mov     rsi, [rbp+0A0h+var_100]
0x1805dca9e  mov     rcx, [rbp+0A0h+string]; string
0x1805dcaa2  call    cs:__imp_WindowsDeleteString
0x1805dcaa8  mov     [rbp+0A0h+string], 0
0x1805dcab0  lea     rcx, [rbp+0A0h+var_A0]
0x1805dcab4  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcab9  nop
0x1805dcaba  mov     rcx, [rbp+0A0h+var_E8]; string
0x1805dcabe  call    cs:__imp_WindowsDeleteString
0x1805dcac4  mov     [rbp+0A0h+var_E8], 0
0x1805dcacc  lea     rcx, [rbp+0A0h+var_C0]
0x1805dcad0  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcad5  nop
0x1805dcad6  lea     rcx, [rbp+0A0h+var_B8]
0x1805dcada  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcadf  nop
0x1805dcae0  lea     rcx, [rbp+0A0h+var_D0]
0x1805dcae4  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcae9  nop
0x1805dcaea  lea     rcx, [rbp+0A0h+var_E0]
0x1805dcaee  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcaf3  nop
0x1805dcaf4  lea     rcx, [rbp+0A0h+var_F8]
0x1805dcaf8  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcafd  nop
0x1805dcafe  mov     rcx, rsi
0x1805dcb01  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcb06  nop
0x1805dcb07  mov     rcx, [rbp+0A0h+var_98]
0x1805dcb0b  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcb10  nop
0x1805dcb11  mov     rcx, [rbp+0A0h+var_90]
0x1805dcb15  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcb1a  nop
0x1805dcb1b  mov     rcx, [rbp+0A0h+var_B0]; this
0x1805dcb1f  call    ??1ClaimsHint@CWAMTokenHandler@@QEAA@XZ; CWAMTokenHandler::ClaimsHint::~ClaimsHint(void)
0x1805dcb24  nop
0x1805dcb25  mov     rcx, r14
0x1805dcb28  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcb2d  mov     eax, ebx
0x1805dcb2f  mov     rcx, [rbp+0A0h+var_38]
0x1805dcb33  xor     rcx, rsp; StackCookie
0x1805dcb36  call    __security_check_cookie
0x1805dcb3b  mov     rbx, [rsp+1A0h+arg_0]
0x1805dcb43  add     rsp, 170h
0x1805dcb4a  pop     r15
0x1805dcb4c  pop     r14
0x1805dcb4e  pop     r13
0x1805dcb50  pop     r12
0x1805dcb52  pop     rdi
0x1805dcb53  pop     rsi
0x1805dcb54  pop     rbp
0x1805dcb55  retn
0x1805dcb56  lea     rdx, [rbp+0A0h+var_A0]
0x1805dcb5a  lea     rcx, [rbp+0A0h+var_F8]
0x1805dcb5e  call    ??$As@UIWebTokenRequest3@Core@Web@Authentication@Security@Windows@ABI@@@?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebTokenRequest3@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest>::As<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest3>>)
0x1805dcb63  lea     r15, aGettokenfromac_0; "GetTokenFromAccount"
0x1805dcb6a  test    eax, eax
0x1805dcb6c  js      loc_1805DCC0D
0x1805dcb72  test    rsi, rsi
0x1805dcb75  jz      loc_1805DCC0D
0x1805dcb7b  cmp     [rsi], r14w
0x1805dcb7f  jz      loc_1805DCC0D
0x1805dcb85  mov     rdi, [rbp+0A0h+var_A0]
0x1805dcb89  mov     rax, [rdi]
0x1805dcb8c  mov     rbx, [rax+38h]
0x1805dcb90  lea     rdx, [rsp+1A0h+var_128]
0x1805dcb95  lea     rcx, [rbp+0A0h+var_58]
0x1805dcb99  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1805dcb9e  nop
0x1805dcb9f  mov     rdx, [rax+18h]
0x1805dcba3  mov     rcx, rdi
0x1805dcba6  mov     rax, rbx
0x1805dcba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805dcbae  nop
0x1805dcbaf  test    eax, eax
0x1805dcbb1  jns     short loc_1805DCC0D
0x1805dcbb3  mov     ecx, cs:dword_1808B5850
0x1805dcbb9  cmp     ecx, 3
0x1805dcbbc  jbe     short loc_1805DCC0D
0x1805dcbbe  mov     [rsp+1A0h+var_128], r15
0x1805dcbc3  mov     dword ptr [rbp+0A0h+var_120], eax
0x1805dcbc6  lea     rax, aSpwebtokenrequ; "spWebTokenRequest3->put_CorrelationId"
0x1805dcbcd  mov     [rbp+0A0h+var_108], rax
0x1805dcbd1  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1805dcbd8  mov     [rbp+0A0h+var_110], rax
0x1805dcbdc  lea     rax, [rsp+1A0h+var_128]
0x1805dcbe1  mov     [rsp+1A0h+var_168], rax
0x1805dcbe6  lea     rax, [rbp+0A0h+var_120]
0x1805dcbea  mov     [rsp+1A0h+var_170], rax
0x1805dcbef  lea     rax, [rbp+0A0h+var_108]
0x1805dcbf3  mov     [rsp+1A0h+var_178], rax
0x1805dcbf8  lea     rax, [rbp+0A0h+var_110]
0x1805dcbfc  mov     [rsp+1A0h+var_180], rax
0x1805dcc01  lea     rdx, word_18088C6FA
0x1805dcc08  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1805dcc0d  mov     rdi, [rbp+0A0h+var_B0]
0x1805dcc11  lea     rcx, [rdi+38h]
0x1805dcc15  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1805dcc1a  mov     r14, rax
0x1805dcc1d  lea     rcx, [rdi+30h]
0x1805dcc21  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1805dcc26  mov     rsi, rax
0x1805dcc29  lea     rcx, [rdi+28h]
0x1805dcc2d  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1805dcc32  mov     rbx, rax
0x1805dcc35  lea     rcx, [rdi+18h]
0x1805dcc39  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1805dcc3e  mov     rdi, rax
0x1805dcc41  mov     rcx, [rbp+0A0h+var_B0]
0x1805dcc45  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1805dcc4a  xor     ecx, ecx
0x1805dcc4c  mov     [rsp+1A0h+var_140], ecx; int
0x1805dcc50  mov     [rsp+1A0h+var_148], 1; int
0x1805dcc58  mov     [rsp+1A0h+var_150], ecx; int
0x1805dcc5c  mov     [rsp+1A0h+var_158], ecx; int
0x1805dcc60  mov     [rsp+1A0h+var_160], r14; unsigned __int16 *
0x1805dcc65  mov     [rsp+1A0h+var_168], rsi; unsigned __int16 *
0x1805dcc6a  mov     [rsp+1A0h+var_170], rbx; unsigned __int16 *
0x1805dcc6f  mov     [rsp+1A0h+var_178], rcx; unsigned __int16 *
0x1805dcc74  mov     [rsp+1A0h+var_180], r12; unsigned __int16 *
0x1805dcc79  mov     r9, rdi; unsigned __int16 *
0x1805dcc7c  mov     r8, rax; unsigned __int16 *
0x1805dcc7f  mov     rdx, [rbp+0A0h+var_F8]; struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest *
0x1805dcc83  lea     rcx, ?g_WAMHandler@@3VCWAMTokenHandler@@A; this
0x1805dcc8a  call    ?InsertTokenRequestProperties@CWAMTokenHandler@@AEAAJPEAUIWebTokenRequest@Core@Web@Authentication@Security@Windows@ABI@@PEBG111111HHHH@Z; CWAMTokenHandler::InsertTokenRequestProperties(ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequest *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,int,int,int)
0x1805dcc8f  mov     ebx, eax
0x1805dcc91  test    eax, eax
0x1805dcc93  mov     eax, cs:dword_1808B5850
0x1805dcc99  jns     short loc_1805DCD14
0x1805dcc9b  cmp     eax, 2
0x1805dcc9e  jbe     loc_1805DCA96
0x1805dcca4  lea     rax, aInserttokenreq_0; "InsertTokenRequestProperties failed"
0x1805dccab  mov     [rsp+1A0h+var_128], rax
0x1805dccb0  mov     [rbp+0A0h+var_108], r15
0x1805dccb4  mov     dword ptr [rbp+0A0h+var_120], 1D0h
0x1805dccbb  lea     rax, aClientcoreTerm_42; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805dccc2  mov     [rbp+0A0h+var_110], rax
0x1805dccc6  mov     [rsp+1A0h+var_130], ebx
0x1805dccca  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1805dccd1  mov     [rbp+0A0h+var_118], rax
0x1805dccd5  lea     rax, [rsp+1A0h+var_128]
0x1805dccda  mov     qword ptr [rsp+1A0h+var_158], rax
0x1805dccdf  lea     rax, [rbp+0A0h+var_108]
0x1805dcce3  mov     [rsp+1A0h+var_160], rax
0x1805dcce8  lea     rax, [rbp+0A0h+var_120]
0x1805dccec  mov     [rsp+1A0h+var_168], rax
0x1805dccf1  lea     rax, [rbp+0A0h+var_110]
0x1805dccf5  mov     [rsp+1A0h+var_170], rax
0x1805dccfa  lea     rax, [rsp+1A0h+var_130]
0x1805dccff  mov     [rsp+1A0h+var_178], rax
0x1805dcd04  lea     rax, [rbp+0A0h+var_118]
0x1805dcd08  lea     rdx, dword_18088C68C
0x1805dcd0f  jmp     loc_1805DCA8C
0x1805dcd14  mov     r14, [rbp+0A0h+var_F0]
0x1805dcd18  cmp     qword ptr [r14], 0
0x1805dcd1c  jz      loc_1805DCE13
0x1805dcd22  cmp     eax, 4
0x1805dcd25  jbe     short loc_1805DCD53
0x1805dcd27  lea     rax, aWebAccountFoun; "Web account found for token retrieval."
0x1805dcd2e  mov     [rsp+1A0h+var_128], rax
0x1805dcd33  lea     rax, [rsp+1A0h+var_128]
0x1805dcd38  mov     [rsp+1A0h+var_180], rax
0x1805dcd3d  xor     r8d, r8d
0x1805dcd40  lea     rdx, byte_18088C6D9
0x1805dcd47  lea     rcx, dword_1808B5850
0x1805dcd4e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1805dcd53  mov     rsi, [rbp+0A0h+var_100]
0x1805dcd57  mov     rdi, [rsi]
0x1805dcd5a  mov     rax, [rdi]
0x1805dcd5d  mov     rbx, [rax+38h]
0x1805dcd61  lea     rcx, [rbp+0A0h+var_E0]
0x1805dcd65  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805dcd6a  lea     r9, [rbp+0A0h+var_E0]
0x1805dcd6e  mov     r8, [r14]
0x1805dcd71  mov     rdx, [rbp+0A0h+var_F8]
0x1805dcd75  mov     rcx, rdi
0x1805dcd78  mov     rax, rbx
0x1805dcd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805dcd80  mov     ebx, eax
0x1805dcd82  test    eax, eax
0x1805dcd84  jns     loc_1805DCE9D
0x1805dcd8a  mov     eax, cs:dword_1808B5850
0x1805dcd90  cmp     eax, 2
0x1805dcd93  jbe     loc_1805DCA9E
0x1805dcd99  lea     rax, aGettokensilent; "GetTokenSilentlyWithWebAccountAsync fai"...
0x1805dcda0  mov     dword ptr [rbp+0A0h+var_120], 1DBh
0x1805dcda7  lea     rdx, word_18088C61E
0x1805dcdae  mov     [rsp+1A0h+var_128], rax
0x1805dcdb3  lea     rax, aClientcoreTerm_42; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805dcdba  mov     [rbp+0A0h+var_110], rax
0x1805dcdbe  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1805dcdc5  mov     [rbp+0A0h+var_118], rax
0x1805dcdc9  lea     rax, [rsp+1A0h+var_128]
  ... truncated ...
```
