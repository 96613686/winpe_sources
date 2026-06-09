# CWAMTokenHandler::IsExcludedTokenObtained(ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *,ushort *,int *)

- ea: `0x1805e4948`
- end: `0x1805e50bf`
- name: `?IsExcludedTokenObtained@CWAMTokenHandler@@AEAAJPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@ABI@@PEAGPEAH@Z`
- size: `1911`
- prototype: `int(CWAMTokenHandler *__hidden this, struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1805e2bac`

## callees

- `0x1800054f4`
- `0x1800fdc84`
- `0x1805e4948`
- `0x1805e50c8`
- `0x18068c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1805e4f42`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1805e4f42`
- `OLEAUT32!__imp_SysFreeString` at `0x1805e5079`
- `OLEAUT32!__imp_SysFreeString` at `0x1805e5079`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805e4ea7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1805e4ea7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805e4df6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805e5084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805e4df6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1805e5084`

## string_xrefs

- `0x1805e4cc3`: `Web token response vector size is 0`
- `0x1805e4ecc`: `Token length is 0`
- `0x1805e49d9`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4a72`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4b04`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4baf`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4c4f`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4ce0`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4d91`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4e49`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4ee9`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4f85`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e501b`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.aadj.cpp`
- `0x1805e4a55`: `bstrExcludeToken is NULL.`
- `0x1805e49c7`: `IsExcludedTokenObtained`
- `0x1805e4a60`: `IsExcludedTokenObtained`
- `0x1805e4af2`: `IsExcludedTokenObtained`
- `0x1805e4b9d`: `IsExcludedTokenObtained`
- `0x1805e4c3d`: `IsExcludedTokenObtained`
- `0x1805e4cce`: `IsExcludedTokenObtained`
- `0x1805e4d7f`: `IsExcludedTokenObtained`
- `0x1805e4e37`: `IsExcludedTokenObtained`
- `0x1805e4ed7`: `IsExcludedTokenObtained`
- `0x1805e4f73`: `IsExcludedTokenObtained`
- `0x1805e5009`: `IsExcludedTokenObtained`
- `0x1805e4b92`: `pTokenRequestResult->get_ResponseData`
- `0x1805e4ae7`: `pbExcludedTokenObtained is NULL.`
- `0x1805e4d74`: `spWebTokenResponseVectorView->GetAt`
- `0x1805e4c32`: `spWebTokenResponseVectorView->get_Size`
- `0x1805e4ffe`: `IsSameToken`
- `0x1805e4e2c`: `spTokenResponse->get_Token`
- `0x1805e49bc`: ` pTokenRequestResult is NULL.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWAMTokenHandler::IsExcludedTokenObtained(
        CWAMTokenHandler *this,
        struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *a2,
        unsigned __int16 *a3,
        int *a4)
{
  CWAMTokenHandler *v7; // rcx
  int IsSameToken; // ebx
  const char **v9; // rax
  char *v10; // rdx
  __int64 (__fastcall *v11)(struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *); // rbx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD *); // rbx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  const OLECHAR *StringRawBuffer; // rax
  unsigned __int16 *v17; // rax
  OLECHAR *v18; // rdi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int *v23; // [rsp+30h] [rbp-31h]
  const char **v24; // [rsp+38h] [rbp-29h]
  int *v25; // [rsp+40h] [rbp-21h]
  const char **v26; // [rsp+48h] [rbp-19h]
  const char **v27; // [rsp+50h] [rbp-11h]
  int v28; // [rsp+58h] [rbp-9h] BYREF
  int v29; // [rsp+5Ch] [rbp-5h] BYREF
  const char *v30; // [rsp+60h] [rbp-1h] BYREF
  const char *v31; // [rsp+68h] [rbp+7h] BYREF
  const char *v32; // [rsp+70h] [rbp+Fh] BYREF
  const char *v33; // [rsp+78h] [rbp+17h] BYREF
  HSTRING string; // [rsp+80h] [rbp+1Fh] BYREF
  __int64 v35; // [rsp+88h] [rbp+27h] BYREF
  _QWORD v36[3]; // [rsp+90h] [rbp+2Fh] BYREF
  int v37; // [rsp+C8h] [rbp+67h] BYREF
  int v38; // [rsp+CCh] [rbp+6Bh]
  UINT32 length; // [rsp+D0h] [rbp+6Fh] BYREF

  v38 = HIDWORD(this);
  v36[1] = -2;
  v35 = 0;
  v36[0] = 0;
  v37 = 0;
  string = 0;
  length = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      LODWORD(v7) = -2147467261;
      IsSameToken = -2147467261;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "bstrExcludeToken is NULL.";
      v32 = "IsExcludedTokenObtained";
      v29 = 919;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = -2147467261;
      v30 = "Error condition failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = (char *)word_18088D36A;
      goto LABEL_4;
    }
    if ( !a4 )
    {
      LODWORD(v7) = -2147467261;
      IsSameToken = -2147467261;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "pbExcludedTokenObtained is NULL.";
      v32 = "IsExcludedTokenObtained";
      v29 = 920;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = -2147467261;
      v30 = "Error condition failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = byte_18088D283;
      goto LABEL_4;
    }
    v11 = *(__int64 (__fastcall **)(struct ABI::Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v35);
    IsSameToken = v11(a2, &v35);
    if ( IsSameToken < 0 )
    {
      LODWORD(v7) = dword_1808B5850;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "pTokenRequestResult->get_ResponseData";
      v32 = "IsExcludedTokenObtained";
      v29 = 923;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = IsSameToken;
      v30 = "Error HResult failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = (char *)qword_18088D2D0;
      goto LABEL_4;
    }
    IsSameToken = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 56LL))(v35, &v37);
    if ( IsSameToken < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "spWebTokenResponseVectorView->get_Size";
      v32 = "IsExcludedTokenObtained";
      v29 = 926;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = IsSameToken;
      v30 = "Error HResult failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = &byte_18088CEEF;
      goto LABEL_4;
    }
    if ( !v37 )
    {
      IsSameToken = -1056919550;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "Web token response vector size is 0";
      v32 = "IsExcludedTokenObtained";
      v29 = 927;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = -1056919550;
      v30 = "Error condition failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = (char *)&dword_18088CF3C;
      goto LABEL_4;
    }
    v12 = v35;
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v35 + 48LL);
    Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(v36);
    IsSameToken = v13(v12, 0, v36);
    if ( IsSameToken < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "spWebTokenResponseVectorView->GetAt";
      v32 = "IsExcludedTokenObtained";
      v29 = 930;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = IsSameToken;
      v30 = "Error HResult failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = byte_18088CE55;
      goto LABEL_4;
    }
    v14 = v36[0];
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36[0] + 48LL);
    WindowsDeleteString(string);
    string = 0;
    IsSameToken = v15(v14, &string);
    if ( IsSameToken < 0 )
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "spTokenResponse->get_Token";
      v32 = "IsExcludedTokenObtained";
      v29 = 933;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = IsSameToken;
      v30 = "Error HResult failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = (char *)word_18088CEA2;
      goto LABEL_4;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( !length )
    {
      IsSameToken = -1056919549;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "Token length is 0";
      v32 = "IsExcludedTokenObtained";
      v29 = 936;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = -1056919549;
      v30 = "Error condition failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = byte_18088CDBB;
      goto LABEL_4;
    }
    v17 = SysAllocStringLen(StringRawBuffer, length);
    v18 = v17;
    if ( !v17 )
    {
      IsSameToken = -1056919545;
      if ( (unsigned int)dword_1808B5850 <= 2 )
        goto LABEL_36;
      v33 = "SysAllocString returned NULL";
      v32 = "IsExcludedTokenObtained";
      v29 = 939;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = -1056919545;
      v30 = "Error condition failed";
      v27 = &v33;
      v26 = &v32;
      v25 = &v29;
      v24 = &v31;
      v23 = &v28;
      v9 = &v30;
      v10 = (char *)qword_18088CE08;
      goto LABEL_4;
    }
    IsSameToken = CWAMTokenHandler::IsSameToken(v7, v17, a3, a4);
    if ( IsSameToken < 0 && (unsigned int)dword_1808B5850 > 2 )
    {
      v33 = "IsSameToken";
      v32 = "IsExcludedTokenObtained";
      v29 = 942;
      v31 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v28 = IsSameToken;
      v30 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)byte_18088CD21,
        v20,
        v21,
        (__int64)&v30,
        (__int64)&v28,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v32,
        (__int64)&v33);
    }
    SysFreeString(v18);
  }
  else
  {
    LODWORD(v7) = -2147467261;
    IsSameToken = -2147467261;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v30 = " pTokenRequestResult is NULL.";
      v31 = "IsExcludedTokenObtained";
      v28 = 918;
      v32 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.aadj.cpp";
      v29 = -2147467261;
      v33 = "Error condition failed";
      v27 = &v30;
      v26 = &v31;
      v25 = &v28;
      v24 = &v32;
      v23 = &v29;
      v9 = &v33;
      v10 = byte_18088D31D;
LABEL_4:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (_DWORD)v10,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)v9,
        (__int64)v23,
        (__int64)v24,
        (__int64)v25,
        (__int64)v26,
        (__int64)v27);
    }
  }
LABEL_36:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(v36);
  Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(&v35);
  return (unsigned int)IsSameToken;
}

```

## disassembly

```asm
0x1805e4948  mov     r11, rsp
0x1805e494b  mov     [r11+8], rcx
0x1805e494f  push    rbp
0x1805e4950  push    rdi
0x1805e4951  push    r14
0x1805e4953  lea     rbp, [r11-5Fh]
0x1805e4957  sub     rsp, 0A0h
0x1805e495e  mov     [rbp+57h+var_20], 0FFFFFFFFFFFFFFFEh
0x1805e4966  mov     [r11+18h], rbx
0x1805e496a  mov     [r11+20h], rsi
0x1805e496e  mov     rsi, r9
0x1805e4971  mov     r14, r8
0x1805e4974  mov     rdi, rdx
0x1805e4977  mov     [rbp+57h+var_30], 0
0x1805e497f  mov     [rbp+57h+var_28], 0
0x1805e4987  mov     [rbp+57h+arg_0], 0
0x1805e498e  mov     [rbp+57h+string], 0
0x1805e4996  mov     [rbp+57h+length], 0
0x1805e499d  test    rdx, rdx
0x1805e49a0  jnz     loc_1805E4A36
0x1805e49a6  mov     ecx, 80004003h
0x1805e49ab  mov     ebx, ecx
0x1805e49ad  mov     eax, cs:dword_1808B5850
0x1805e49b3  cmp     eax, 2
0x1805e49b6  jbe     loc_1805E5080
0x1805e49bc  lea     rax, aPtokenrequestr; " pTokenRequestResult is NULL."
0x1805e49c3  mov     [rbp+57h+var_58], rax
0x1805e49c7  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e49ce  mov     [rbp+57h+var_50], rax
0x1805e49d2  mov     [rbp+57h+var_60], 396h
0x1805e49d9  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e49e0  mov     [rbp+57h+var_48], rax
0x1805e49e4  mov     [rbp+57h+var_5C], ecx
0x1805e49e7  lea     rax, aErrorCondition; "Error condition failed"
0x1805e49ee  mov     [rbp+57h+var_40], rax
0x1805e49f2  lea     rax, [rbp+57h+var_58]
0x1805e49f6  mov     [r11-70h], rax
0x1805e49fa  lea     rax, [rbp+57h+var_50]
0x1805e49fe  mov     [r11-78h], rax
0x1805e4a02  lea     rax, [rbp+57h+var_60]
0x1805e4a06  mov     [r11-80h], rax
0x1805e4a0a  lea     rax, [rbp+57h+var_48]
0x1805e4a0e  mov     [rsp+0B0h+var_80], rax
0x1805e4a13  lea     rax, [rbp+57h+var_5C]
0x1805e4a17  mov     [rsp+0B0h+var_88], rax
0x1805e4a1c  lea     rax, [rbp+57h+var_40]
0x1805e4a20  lea     rdx, byte_18088D31D
0x1805e4a27  mov     [rsp+0B0h+var_90], rax
0x1805e4a2c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1805e4a31  jmp     loc_1805E5080
0x1805e4a36  test    r14, r14
0x1805e4a39  jnz     loc_1805E4AC8
0x1805e4a3f  mov     ecx, 80004003h
0x1805e4a44  mov     ebx, ecx
0x1805e4a46  mov     eax, cs:dword_1808B5850
0x1805e4a4c  cmp     eax, 2
0x1805e4a4f  jbe     loc_1805E5080
0x1805e4a55  lea     rax, aBstrexcludetok; "bstrExcludeToken is NULL."
0x1805e4a5c  mov     [rbp+57h+var_40], rax
0x1805e4a60  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e4a67  mov     [rbp+57h+var_48], rax
0x1805e4a6b  mov     [rbp+57h+var_5C], 397h
0x1805e4a72  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e4a79  mov     [rbp+57h+var_50], rax
0x1805e4a7d  mov     [rbp+57h+var_60], ecx
0x1805e4a80  lea     rax, aErrorCondition; "Error condition failed"
0x1805e4a87  mov     [rbp+57h+var_58], rax
0x1805e4a8b  lea     rax, [rbp+57h+var_40]
0x1805e4a8f  mov     [rsp+0B0h+var_68], rax
0x1805e4a94  lea     rax, [rbp+57h+var_48]
0x1805e4a98  mov     [rsp+0B0h+var_70], rax
0x1805e4a9d  lea     rax, [rbp+57h+var_5C]
0x1805e4aa1  mov     [rsp+0B0h+var_78], rax
0x1805e4aa6  lea     rax, [rbp+57h+var_50]
0x1805e4aaa  mov     [rsp+0B0h+var_80], rax
0x1805e4aaf  lea     rax, [rbp+57h+var_60]
0x1805e4ab3  mov     [rsp+0B0h+var_88], rax
0x1805e4ab8  lea     rax, [rbp+57h+var_58]
0x1805e4abc  lea     rdx, word_18088D36A
0x1805e4ac3  jmp     loc_1805E4A27
0x1805e4ac8  test    rsi, rsi
0x1805e4acb  jnz     loc_1805E4B5A
0x1805e4ad1  mov     ecx, 80004003h
0x1805e4ad6  mov     ebx, ecx
0x1805e4ad8  mov     eax, cs:dword_1808B5850
0x1805e4ade  cmp     eax, 2
0x1805e4ae1  jbe     loc_1805E5080
0x1805e4ae7  lea     rax, aPbexcludedtoke; "pbExcludedTokenObtained is NULL."
0x1805e4aee  mov     [rbp+57h+var_40], rax
0x1805e4af2  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e4af9  mov     [rbp+57h+var_48], rax
0x1805e4afd  mov     [rbp+57h+var_5C], 398h
0x1805e4b04  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e4b0b  mov     [rbp+57h+var_50], rax
0x1805e4b0f  mov     [rbp+57h+var_60], ecx
0x1805e4b12  lea     rax, aErrorCondition; "Error condition failed"
0x1805e4b19  mov     [rbp+57h+var_58], rax
0x1805e4b1d  lea     rax, [rbp+57h+var_40]
0x1805e4b21  mov     [rsp+0B0h+var_68], rax
0x1805e4b26  lea     rax, [rbp+57h+var_48]
0x1805e4b2a  mov     [rsp+0B0h+var_70], rax
0x1805e4b2f  lea     rax, [rbp+57h+var_5C]
0x1805e4b33  mov     [rsp+0B0h+var_78], rax
0x1805e4b38  lea     rax, [rbp+57h+var_50]
0x1805e4b3c  mov     [rsp+0B0h+var_80], rax
0x1805e4b41  lea     rax, [rbp+57h+var_60]
0x1805e4b45  mov     [rsp+0B0h+var_88], rax
0x1805e4b4a  lea     rax, [rbp+57h+var_58]
0x1805e4b4e  lea     rdx, byte_18088D283
0x1805e4b55  jmp     loc_1805E4A27
0x1805e4b5a  mov     rax, [rdx]
0x1805e4b5d  mov     rbx, [rax+30h]
0x1805e4b61  lea     rcx, [rbp+57h+var_30]
0x1805e4b65  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805e4b6a  lea     rdx, [rbp+57h+var_30]
0x1805e4b6e  mov     rcx, rdi
0x1805e4b71  mov     rax, rbx
0x1805e4b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e4b79  mov     ebx, eax
0x1805e4b7b  test    eax, eax
0x1805e4b7d  jns     loc_1805E4C05
0x1805e4b83  mov     ecx, cs:dword_1808B5850
0x1805e4b89  cmp     ecx, 2
0x1805e4b8c  jbe     loc_1805E5080
0x1805e4b92  lea     rax, aPtokenrequestr_0; "pTokenRequestResult->get_ResponseData"
0x1805e4b99  mov     [rbp+57h+var_40], rax
0x1805e4b9d  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e4ba4  mov     [rbp+57h+var_48], rax
0x1805e4ba8  mov     [rbp+57h+var_5C], 39Bh
0x1805e4baf  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e4bb6  mov     [rbp+57h+var_50], rax
0x1805e4bba  mov     [rbp+57h+var_60], ebx
0x1805e4bbd  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1805e4bc4  mov     [rbp+57h+var_58], rax
0x1805e4bc8  lea     rax, [rbp+57h+var_40]
0x1805e4bcc  mov     [rsp+0B0h+var_68], rax
0x1805e4bd1  lea     rax, [rbp+57h+var_48]
0x1805e4bd5  mov     [rsp+0B0h+var_70], rax
0x1805e4bda  lea     rax, [rbp+57h+var_5C]
0x1805e4bde  mov     [rsp+0B0h+var_78], rax
0x1805e4be3  lea     rax, [rbp+57h+var_50]
0x1805e4be7  mov     [rsp+0B0h+var_80], rax
0x1805e4bec  lea     rax, [rbp+57h+var_60]
0x1805e4bf0  mov     [rsp+0B0h+var_88], rax
0x1805e4bf5  lea     rax, [rbp+57h+var_58]
0x1805e4bf9  lea     rdx, qword_18088D2D0
0x1805e4c00  jmp     loc_1805E4A27
0x1805e4c05  mov     rcx, [rbp+57h+var_30]
0x1805e4c09  mov     rax, [rcx]
0x1805e4c0c  lea     rdx, [rbp+57h+arg_0]
0x1805e4c10  mov     rax, [rax+38h]
0x1805e4c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e4c19  mov     ebx, eax
0x1805e4c1b  test    eax, eax
0x1805e4c1d  jns     loc_1805E4CA5
0x1805e4c23  mov     eax, cs:dword_1808B5850
0x1805e4c29  cmp     eax, 2
0x1805e4c2c  jbe     loc_1805E5080
0x1805e4c32  lea     rax, aSpwebtokenresp; "spWebTokenResponseVectorView->get_Size"
0x1805e4c39  mov     [rbp+57h+var_40], rax
0x1805e4c3d  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e4c44  mov     [rbp+57h+var_48], rax
0x1805e4c48  mov     [rbp+57h+var_5C], 39Eh
0x1805e4c4f  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e4c56  mov     [rbp+57h+var_50], rax
0x1805e4c5a  mov     [rbp+57h+var_60], ebx
0x1805e4c5d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1805e4c64  mov     [rbp+57h+var_58], rax
0x1805e4c68  lea     rax, [rbp+57h+var_40]
0x1805e4c6c  mov     [rsp+0B0h+var_68], rax
0x1805e4c71  lea     rax, [rbp+57h+var_48]
0x1805e4c75  mov     [rsp+0B0h+var_70], rax
0x1805e4c7a  lea     rax, [rbp+57h+var_5C]
0x1805e4c7e  mov     [rsp+0B0h+var_78], rax
0x1805e4c83  lea     rax, [rbp+57h+var_50]
0x1805e4c87  mov     [rsp+0B0h+var_80], rax
0x1805e4c8c  lea     rax, [rbp+57h+var_60]
0x1805e4c90  mov     [rsp+0B0h+var_88], rax
0x1805e4c95  lea     rax, [rbp+57h+var_58]
0x1805e4c99  lea     rdx, byte_18088CEEF
0x1805e4ca0  jmp     loc_1805E4A27
0x1805e4ca5  cmp     [rbp+57h+arg_0], 0
0x1805e4ca9  jnz     loc_1805E4D36
0x1805e4caf  mov     ebx, 0C100B002h
0x1805e4cb4  mov     eax, cs:dword_1808B5850
0x1805e4cba  cmp     eax, 2
0x1805e4cbd  jbe     loc_1805E5080
0x1805e4cc3  lea     rax, aWebTokenRespon; "Web token response vector size is 0"
0x1805e4cca  mov     [rbp+57h+var_40], rax
0x1805e4cce  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e4cd5  mov     [rbp+57h+var_48], rax
0x1805e4cd9  mov     [rbp+57h+var_5C], 39Fh
0x1805e4ce0  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e4ce7  mov     [rbp+57h+var_50], rax
0x1805e4ceb  mov     [rbp+57h+var_60], ebx
0x1805e4cee  lea     rax, aErrorCondition; "Error condition failed"
0x1805e4cf5  mov     [rbp+57h+var_58], rax
0x1805e4cf9  lea     rax, [rbp+57h+var_40]
0x1805e4cfd  mov     [rsp+0B0h+var_68], rax
0x1805e4d02  lea     rax, [rbp+57h+var_48]
0x1805e4d06  mov     [rsp+0B0h+var_70], rax
0x1805e4d0b  lea     rax, [rbp+57h+var_5C]
0x1805e4d0f  mov     [rsp+0B0h+var_78], rax
0x1805e4d14  lea     rax, [rbp+57h+var_50]
0x1805e4d18  mov     [rsp+0B0h+var_80], rax
0x1805e4d1d  lea     rax, [rbp+57h+var_60]
0x1805e4d21  mov     [rsp+0B0h+var_88], rax
0x1805e4d26  lea     rax, [rbp+57h+var_58]
0x1805e4d2a  lea     rdx, dword_18088CF3C
0x1805e4d31  jmp     loc_1805E4A27
0x1805e4d36  mov     rdi, [rbp+57h+var_30]
0x1805e4d3a  mov     rax, [rdi]
0x1805e4d3d  mov     rbx, [rax+30h]
0x1805e4d41  lea     rcx, [rbp+57h+var_28]
0x1805e4d45  call    ?InternalRelease@?$ComPtr@UIWebTokenResponse@Core@Web@Authentication@Security@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::Security::Authentication::Web::Core::IWebTokenResponse>::InternalRelease(void)
0x1805e4d4a  lea     r8, [rbp+57h+var_28]
0x1805e4d4e  xor     edx, edx
0x1805e4d50  mov     rcx, rdi
0x1805e4d53  mov     rax, rbx
0x1805e4d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e4d5b  mov     ebx, eax
0x1805e4d5d  test    eax, eax
0x1805e4d5f  jns     loc_1805E4DE7
0x1805e4d65  mov     eax, cs:dword_1808B5850
0x1805e4d6b  cmp     eax, 2
0x1805e4d6e  jbe     loc_1805E5080
0x1805e4d74  lea     rax, aSpwebtokenresp_0; "spWebTokenResponseVectorView->GetAt"
0x1805e4d7b  mov     [rbp+57h+var_40], rax
0x1805e4d7f  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e4d86  mov     [rbp+57h+var_48], rax
0x1805e4d8a  mov     [rbp+57h+var_5C], 3A2h
0x1805e4d91  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e4d98  mov     [rbp+57h+var_50], rax
0x1805e4d9c  mov     [rbp+57h+var_60], ebx
0x1805e4d9f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1805e4da6  mov     [rbp+57h+var_58], rax
0x1805e4daa  lea     rax, [rbp+57h+var_40]
0x1805e4dae  mov     [rsp+0B0h+var_68], rax
0x1805e4db3  lea     rax, [rbp+57h+var_48]
0x1805e4db7  mov     [rsp+0B0h+var_70], rax
0x1805e4dbc  lea     rax, [rbp+57h+var_5C]
0x1805e4dc0  mov     [rsp+0B0h+var_78], rax
0x1805e4dc5  lea     rax, [rbp+57h+var_50]
0x1805e4dc9  mov     [rsp+0B0h+var_80], rax
0x1805e4dce  lea     rax, [rbp+57h+var_60]
0x1805e4dd2  mov     [rsp+0B0h+var_88], rax
0x1805e4dd7  lea     rax, [rbp+57h+var_58]
0x1805e4ddb  lea     rdx, byte_18088CE55
0x1805e4de2  jmp     loc_1805E4A27
0x1805e4de7  mov     rdi, [rbp+57h+var_28]
0x1805e4deb  mov     rax, [rdi]
0x1805e4dee  mov     rbx, [rax+30h]
0x1805e4df2  mov     rcx, [rbp+57h+string]; string
0x1805e4df6  call    cs:__imp_WindowsDeleteString
0x1805e4dfc  mov     [rbp+57h+string], 0
0x1805e4e04  lea     rdx, [rbp+57h+string]
0x1805e4e08  mov     rcx, rdi
0x1805e4e0b  mov     rax, rbx
0x1805e4e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805e4e13  mov     ebx, eax
0x1805e4e15  test    eax, eax
0x1805e4e17  jns     loc_1805E4E9F
0x1805e4e1d  mov     eax, cs:dword_1808B5850
0x1805e4e23  cmp     eax, 2
0x1805e4e26  jbe     loc_1805E5080
0x1805e4e2c  lea     rax, aSptokenrespons; "spTokenResponse->get_Token"
0x1805e4e33  mov     [rbp+57h+var_40], rax
0x1805e4e37  lea     rax, aIsexcludedtoke; "IsExcludedTokenObtained"
0x1805e4e3e  mov     [rbp+57h+var_48], rax
0x1805e4e42  mov     [rbp+57h+var_5C], 3A5h
0x1805e4e49  lea     rax, aClientcoreTerm_14; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805e4e50  mov     [rbp+57h+var_50], rax
0x1805e4e54  mov     [rbp+57h+var_60], ebx
0x1805e4e57  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1805e4e5e  mov     [rbp+57h+var_58], rax
0x1805e4e62  lea     rax, [rbp+57h+var_40]
0x1805e4e66  mov     [rsp+0B0h+var_68], rax
0x1805e4e6b  lea     rax, [rbp+57h+var_48]
0x1805e4e6f  mov     [rsp+0B0h+var_70], rax
0x1805e4e74  lea     rax, [rbp+57h+var_5C]
0x1805e4e78  mov     [rsp+0B0h+var_78], rax
0x1805e4e7d  lea     rax, [rbp+57h+var_50]
0x1805e4e81  mov     [rsp+0B0h+var_80], rax
0x1805e4e86  lea     rax, [rbp+57h+var_60]
0x1805e4e8a  mov     [rsp+0B0h+var_88], rax
0x1805e4e8f  lea     rax, [rbp+57h+var_58]
0x1805e4e93  lea     rdx, word_18088CEA2
0x1805e4e9a  jmp     loc_1805E4A27
0x1805e4e9f  lea     rdx, [rbp+57h+length]; length
0x1805e4ea3  mov     rcx, [rbp+57h+string]; string
0x1805e4ea7  call    cs:__imp_WindowsGetStringRawBuffer
0x1805e4ead  mov     edx, [rbp+57h+length]; ui
0x1805e4eb0  test    edx, edx
0x1805e4eb2  jnz     loc_1805E4F3F
0x1805e4eb8  mov     ebx, 0C100B003h
0x1805e4ebd  mov     eax, cs:dword_1808B5850
0x1805e4ec3  cmp     eax, 2
0x1805e4ec6  jbe     loc_1805E5080
0x1805e4ecc  lea     rax, aTokenLengthIs0; "Token length is 0"
0x1805e4ed3  mov     [rbp+57h+var_40], rax
  ... truncated ...
```
