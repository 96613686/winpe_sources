# DomainNameFromSid(void *,ushort * *)

- ea: `0x18008a760`
- end: `0x18008ab39`
- name: `?DomainNameFromSid@@YAJPEAXPEAPEAG@Z`
- size: `985`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18008ab40`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x1800787d4`
- `0x180078820`
- `0x18008a760`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008aa9f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a7aa`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008aa8b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a7aa`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008aa8b`

## string_xrefs

- `0x18008a821`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008a8ac`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008a969`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008aa15`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008ab22`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008a885`: `LookupAccountSidW failed`
- `0x18008aafb`: `LookupAccountSidW failed`
- `0x18008a808`: `DomainNameFromSid`
- `0x18008a89e`: `DomainNameFromSid`
- `0x18008a95b`: `DomainNameFromSid`
- `0x18008aa07`: `DomainNameFromSid`
- `0x18008ab14`: `DomainNameFromSid`
- `0x18008a82f`: `Unexpected: No domain SID in the user SID?`

## pseudocode

```c
__int64 __fastcall DomainNameFromSid(PSID Sid, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  signed int LastError; // eax
  WCHAR *v9; // rsi
  int v10; // r8d
  int v11; // r9d
  WCHAR *ReferencedDomainName; // rdi
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  __int16 *v16; // rdx
  const char *v17; // rax
  signed int v18; // eax
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-30h] BYREF
  int v21; // [rsp+54h] [rbp-2Ch] BYREF
  int v22; // [rsp+58h] [rbp-28h] BYREF
  const char *v23; // [rsp+60h] [rbp-20h] BYREF
  const char *v24; // [rsp+68h] [rbp-18h] BYREF
  const char *v25; // [rsp+70h] [rbp-10h] BYREF
  const char *v26; // [rsp+78h] [rbp-8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+C8h] [rbp+48h] BYREF

  v2 = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() == 122 )
    goto LABEL_7;
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) == 0 )
    {
LABEL_7:
      if ( !cchReferencedDomainName )
      {
        v2 = -2147467259;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v22 = 1107;
          v26 = "DomainNameFromSid";
          v21 = -2147467259;
          v25 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v24 = "Unexpected: No domain SID in the user SID?";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v5,
            (unsigned int)qword_1801ACFE8,
            v6,
            v7,
            (__int64)&v24,
            (__int64)&v21,
            (__int64)&v25,
            (__int64)&v22,
            (__int64)&v26);
        }
        return v2;
      }
      v9 = (WCHAR *)operator new(saturated_mul(cchName, 2u));
      if ( !v9 )
      {
        v2 = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v22 = 1112;
          v26 = "pwszUserName allocation failed";
          v21 = -2147024882;
          v25 = "DomainNameFromSid";
          v24 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v23 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)&byte_1801ACF97,
            v10,
            v11,
            (__int64)&v23,
            (__int64)&v21,
            (__int64)&v24,
            (__int64)&v22,
            (__int64)&v25,
            (__int64)&v26);
        }
        return v2;
      }
      ReferencedDomainName = (WCHAR *)operator new(saturated_mul(cchReferencedDomainName, 2u));
      if ( !ReferencedDomainName )
      {
        v15 = -2147024882;
        v2 = -2147024882;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_26;
        v22 = 1115;
        v26 = "pwszDomainName allocation failed";
        v16 = &word_1801ACF46;
        v21 = -2147024882;
        v25 = "DomainNameFromSid";
        v24 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
        v17 = "Error condition failed";
        goto LABEL_19;
      }
      if ( LookupAccountSidW(0, Sid, v9, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        goto LABEL_25;
      if ( GetLastError() )
      {
        v18 = GetLastError();
        v2 = v18;
        if ( v18 > 0 )
          v2 = (unsigned __int16)v18 | 0x80070000;
        if ( (v2 & 0x80000000) == 0 )
        {
LABEL_25:
          *a2 = ReferencedDomainName;
          ReferencedDomainName = 0;
          goto LABEL_26;
        }
      }
      else
      {
        v2 = -2147467259;
      }
      if ( (unsigned int)CallbackContext > 2 )
      {
        v22 = 1120;
        v26 = "LookupAccountSidW failed";
        v16 = (__int16 *)byte_1801ACEF5;
        v21 = v2;
        v25 = "DomainNameFromSid";
        v24 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
        v17 = "Error HResult failed";
LABEL_19:
        v23 = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v15,
          (_DWORD)v16,
          v13,
          v14,
          (__int64)&v23,
          (__int64)&v21,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v25,
          (__int64)&v26);
      }
LABEL_26:
      operator delete(v9);
      if ( ReferencedDomainName )
        operator delete(ReferencedDomainName);
      return v2;
    }
  }
  else
  {
    v2 = -2147467259;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v21 = 1100;
    v23 = "LookupAccountSidW failed";
    v22 = v2;
    v24 = "DomainNameFromSid";
    v25 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
    v26 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)byte_1801AD031,
      v6,
      v7,
      (__int64)&v26,
      (__int64)&v22,
      (__int64)&v25,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v23);
  }
  return v2;
}

```

## disassembly

```asm
0x18008a760  mov     [rsp-28h+arg_0], rbx
0x18008a765  push    rbp
0x18008a766  push    rsi
0x18008a767  push    rdi
0x18008a768  push    r14
0x18008a76a  push    r15
0x18008a76c  mov     rbp, rsp
0x18008a76f  sub     rsp, 80h
0x18008a776  xor     ebx, ebx
0x18008a778  lea     rax, [rbp+var_30]
0x18008a77c  mov     [rsp+80h+peUse], rax; peUse
0x18008a781  lea     r9, [rbp+cchName]; cchName
0x18008a785  lea     rax, [rbp+arg_10]
0x18008a789  mov     [rbp+cchName], ebx
0x18008a78c  mov     r15, rdx
0x18008a78f  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18008a794  mov     r14, rcx
0x18008a797  mov     [rsp+80h+ReferencedDomainName], rbx; ReferencedDomainName
0x18008a79c  mov     rdx, rcx; Sid
0x18008a79f  mov     [rbp+arg_10], ebx
0x18008a7a2  xor     r8d, r8d; Name
0x18008a7a5  mov     [rbp+var_30], ebx
0x18008a7a8  xor     ecx, ecx; lpSystemName
0x18008a7aa  call    cs:__imp_LookupAccountSidW
0x18008a7b0  test    eax, eax
0x18008a7b2  jnz     short loc_18008A7EA
0x18008a7b4  call    cs:__imp_GetLastError
0x18008a7ba  cmp     eax, 7Ah ; 'z'
0x18008a7bd  jz      short loc_18008A7EA
0x18008a7bf  call    cs:__imp_GetLastError
0x18008a7c5  test    eax, eax
0x18008a7c7  jz      loc_18008A871
0x18008a7cd  call    cs:__imp_GetLastError
0x18008a7d3  mov     ebx, eax
0x18008a7d5  test    eax, eax
0x18008a7d7  jle     short loc_18008A7E2
0x18008a7d9  movzx   ebx, ax
0x18008a7dc  or      ebx, 80070000h
0x18008a7e2  test    ebx, ebx
0x18008a7e4  js      loc_18008A876
0x18008a7ea  cmp     [rbp+arg_10], 0
0x18008a7ee  jnz     loc_18008A902
0x18008a7f4  mov     eax, cs:CallbackContext
0x18008a7fa  mov     ebx, 80004005h
0x18008a7ff  cmp     eax, 2
0x18008a802  jbe     loc_18008AAD2
0x18008a808  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18008a80f  mov     [rbp+var_28], 453h
0x18008a816  mov     [rbp+var_8], rax
0x18008a81a  lea     rdx, qword_1801ACFE8
0x18008a821  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008a828  mov     [rbp+var_2C], ebx
0x18008a82b  mov     [rbp+var_10], rax
0x18008a82f  lea     rax, aUnexpectedNoDo; "Unexpected: No domain SID in the user S"...
0x18008a836  mov     [rbp+var_18], rax
0x18008a83a  lea     rax, [rbp+var_8]
0x18008a83e  mov     [rsp+80h+var_40], rax
0x18008a843  lea     rax, [rbp+var_28]
0x18008a847  mov     [rsp+80h+var_48], rax
0x18008a84c  lea     rax, [rbp+var_10]
0x18008a850  mov     [rsp+80h+peUse], rax
0x18008a855  lea     rax, [rbp+var_2C]
0x18008a859  mov     [rsp+80h+cchReferencedDomainName], rax
0x18008a85e  lea     rax, [rbp+var_18]
0x18008a862  mov     [rsp+80h+ReferencedDomainName], rax
0x18008a867  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008a86c  jmp     loc_18008AAD2
0x18008a871  mov     ebx, 80004005h
0x18008a876  mov     eax, cs:CallbackContext
0x18008a87c  cmp     eax, 2
0x18008a87f  jbe     loc_18008AAD2
0x18008a885  lea     rax, aLookupaccounts_0; "LookupAccountSidW failed"
0x18008a88c  mov     [rbp+var_2C], 44Ch
0x18008a893  mov     [rbp+var_20], rax
0x18008a897  lea     rdx, byte_1801AD031
0x18008a89e  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18008a8a5  mov     [rbp+var_28], ebx
0x18008a8a8  mov     [rbp+var_18], rax
0x18008a8ac  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008a8b3  mov     [rbp+var_10], rax
0x18008a8b7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008a8be  mov     [rbp+var_8], rax
0x18008a8c2  lea     rax, [rbp+var_20]
0x18008a8c6  mov     [rsp+80h+var_38], rax
0x18008a8cb  lea     rax, [rbp+var_18]
0x18008a8cf  mov     [rsp+80h+var_40], rax
0x18008a8d4  lea     rax, [rbp+var_2C]
0x18008a8d8  mov     [rsp+80h+var_48], rax
0x18008a8dd  lea     rax, [rbp+var_10]
0x18008a8e1  mov     [rsp+80h+peUse], rax
0x18008a8e6  lea     rax, [rbp+var_28]
0x18008a8ea  mov     [rsp+80h+cchReferencedDomainName], rax
0x18008a8ef  lea     rax, [rbp+var_8]
0x18008a8f3  mov     [rsp+80h+ReferencedDomainName], rax
0x18008a8f8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008a8fd  jmp     loc_18008AAD2
0x18008a902  mov     ecx, [rbp+cchName]
0x18008a905  mov     eax, 2
0x18008a90a  mul     rcx
0x18008a90d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18008a914  cmovb   rax, rdi
0x18008a918  mov     rcx, rax; Size
0x18008a91b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008a920  mov     rsi, rax
0x18008a923  test    rax, rax
0x18008a926  jnz     loc_18008A9B5
0x18008a92c  mov     eax, cs:CallbackContext
0x18008a932  mov     ecx, 8007000Eh
0x18008a937  mov     ebx, ecx
0x18008a939  cmp     eax, 2
0x18008a93c  jbe     loc_18008AAD2
0x18008a942  lea     rax, aPwszusernameAl; "pwszUserName allocation failed"
0x18008a949  mov     [rbp+var_28], 458h
0x18008a950  mov     [rbp+var_8], rax
0x18008a954  lea     rdx, byte_1801ACF97
0x18008a95b  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18008a962  mov     [rbp+var_2C], ecx
0x18008a965  mov     [rbp+var_10], rax
0x18008a969  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008a970  mov     [rbp+var_18], rax
0x18008a974  lea     rax, aErrorCondition; "Error condition failed"
0x18008a97b  mov     [rbp+var_20], rax
0x18008a97f  lea     rax, [rbp+var_8]
0x18008a983  mov     [rsp+80h+var_38], rax
0x18008a988  lea     rax, [rbp+var_10]
0x18008a98c  mov     [rsp+80h+var_40], rax
0x18008a991  lea     rax, [rbp+var_28]
0x18008a995  mov     [rsp+80h+var_48], rax
0x18008a99a  lea     rax, [rbp+var_18]
0x18008a99e  mov     [rsp+80h+peUse], rax
0x18008a9a3  lea     rax, [rbp+var_2C]
0x18008a9a7  mov     [rsp+80h+cchReferencedDomainName], rax
0x18008a9ac  lea     rax, [rbp+var_20]
0x18008a9b0  jmp     loc_18008A8F3
0x18008a9b5  mov     ecx, [rbp+arg_10]
0x18008a9b8  mov     eax, 2
0x18008a9bd  mul     rcx
0x18008a9c0  cmovb   rax, rdi
0x18008a9c4  mov     rcx, rax; Size
0x18008a9c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008a9cc  mov     rdi, rax
0x18008a9cf  test    rax, rax
0x18008a9d2  jnz     loc_18008AA68
0x18008a9d8  mov     eax, cs:CallbackContext
0x18008a9de  mov     ecx, 8007000Eh
0x18008a9e3  mov     ebx, ecx
0x18008a9e5  cmp     eax, 2
0x18008a9e8  jbe     loc_18008AABD
0x18008a9ee  lea     rax, aPwszdomainname; "pwszDomainName allocation failed"
0x18008a9f5  mov     [rbp+var_28], 45Bh
0x18008a9fc  mov     [rbp+var_8], rax
0x18008aa00  lea     rdx, word_1801ACF46
0x18008aa07  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18008aa0e  mov     [rbp+var_2C], ecx
0x18008aa11  mov     [rbp+var_10], rax
0x18008aa15  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008aa1c  mov     [rbp+var_18], rax
0x18008aa20  lea     rax, aErrorCondition; "Error condition failed"
0x18008aa27  mov     [rbp+var_20], rax
0x18008aa2b  lea     rax, [rbp+var_8]
0x18008aa2f  mov     [rsp+80h+var_38], rax
0x18008aa34  lea     rax, [rbp+var_10]
0x18008aa38  mov     [rsp+80h+var_40], rax
0x18008aa3d  lea     rax, [rbp+var_28]
0x18008aa41  mov     [rsp+80h+var_48], rax
0x18008aa46  lea     rax, [rbp+var_18]
0x18008aa4a  mov     [rsp+80h+peUse], rax
0x18008aa4f  lea     rax, [rbp+var_2C]
0x18008aa53  mov     [rsp+80h+cchReferencedDomainName], rax
0x18008aa58  lea     rax, [rbp+var_20]
0x18008aa5c  mov     [rsp+80h+ReferencedDomainName], rax
0x18008aa61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008aa66  jmp     short loc_18008AABD
0x18008aa68  lea     rax, [rbp+var_30]
0x18008aa6c  mov     r8, rsi; Name
0x18008aa6f  mov     [rsp+80h+peUse], rax; peUse
0x18008aa74  lea     r9, [rbp+cchName]; cchName
0x18008aa78  lea     rax, [rbp+arg_10]
0x18008aa7c  mov     rdx, r14; Sid
0x18008aa7f  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18008aa84  xor     ecx, ecx; lpSystemName
0x18008aa86  mov     [rsp+80h+ReferencedDomainName], rdi; ReferencedDomainName
0x18008aa8b  call    cs:__imp_LookupAccountSidW
0x18008aa91  test    eax, eax
0x18008aa93  jnz     short loc_18008AAB8
0x18008aa95  call    cs:__imp_GetLastError
0x18008aa9b  test    eax, eax
0x18008aa9d  jz      short loc_18008AAEB
0x18008aa9f  call    cs:__imp_GetLastError
0x18008aaa5  mov     ebx, eax
0x18008aaa7  test    eax, eax
0x18008aaa9  jle     short loc_18008AAB4
0x18008aaab  movzx   ebx, ax
0x18008aaae  or      ebx, 80070000h
0x18008aab4  test    ebx, ebx
0x18008aab6  js      short loc_18008AAF0
0x18008aab8  mov     [r15], rdi
0x18008aabb  xor     edi, edi
0x18008aabd  mov     rcx, rsi; Block
0x18008aac0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008aac5  test    rdi, rdi
0x18008aac8  jz      short loc_18008AAD2
0x18008aaca  mov     rcx, rdi; Block
0x18008aacd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008aad2  mov     eax, ebx
0x18008aad4  mov     rbx, [rsp+80h+arg_0]
0x18008aadc  add     rsp, 80h
0x18008aae3  pop     r15
0x18008aae5  pop     r14
0x18008aae7  pop     rdi
0x18008aae8  pop     rsi
0x18008aae9  pop     rbp
0x18008aaea  retn
0x18008aaeb  mov     ebx, 80004005h
0x18008aaf0  mov     eax, cs:CallbackContext
0x18008aaf6  cmp     eax, 2
0x18008aaf9  jbe     short loc_18008AABD
0x18008aafb  lea     rax, aLookupaccounts_0; "LookupAccountSidW failed"
0x18008ab02  mov     [rbp+var_28], 460h
0x18008ab09  mov     [rbp+var_8], rax
0x18008ab0d  lea     rdx, byte_1801ACEF5
0x18008ab14  lea     rax, aDomainnamefrom_2; "DomainNameFromSid"
0x18008ab1b  mov     [rbp+var_2C], ebx
0x18008ab1e  mov     [rbp+var_10], rax
0x18008ab22  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008ab29  mov     [rbp+var_18], rax
0x18008ab2d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008ab34  jmp     loc_18008AA27
```
