# CertHelper::FindIssuerCertificate(_CERT_CONTEXT const *,ushort const *,_CERT_CONTEXT const * *)

- ea: `0x1800952b0`
- end: `0x180095537`
- name: `?FindIssuerCertificate@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEBGPEAPEBU2@@Z`
- size: `647`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pSubjectContext, const struct _CERT_CONTEXT *, const unsigned __int16 *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b024`

## callees

- `0x180001aa0`
- `0x1800952b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800953e0`
- `CRYPT32!CertCloseStore` at `0x180095497`
- `CRYPT32!CertCloseStore` at `0x180095497`
- `CRYPT32!CertOpenStore` at `0x1800952ff`
- `CRYPT32!CertOpenStore` at `0x1800952ff`
- `CRYPT32!CertGetIssuerCertificateFromStore` at `0x1800953b2`
- `CRYPT32!CertGetIssuerCertificateFromStore` at `0x1800953b2`

## string_xrefs

- `0x1800952e1`: `AAD Token Issuer`
- `0x180095359`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095433`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x1800954d6`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095335`: `Opening issuer cert store failed`

## pseudocode

```c
__int64 __fastcall CertHelper::FindIssuerCertificate(
        PCCERT_CONTEXT pSubjectContext,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 *a3,
        const struct _CERT_CONTEXT **a4)
{
  HCERTSTORE v6; // rax
  void *v7; // rsi
  signed int LastError; // eax
  unsigned int v9; // ebx
  __int64 *v10; // rdx
  const char **v11; // rax
  PCCERT_CONTEXT IssuerCertificateFromStore; // r14
  DWORD v13; // eax
  signed int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  const char **v19; // [rsp+30h] [rbp-40h]
  const char **v20; // [rsp+40h] [rbp-30h]
  const char **v21; // [rsp+48h] [rbp-28h]
  const char *v22; // [rsp+50h] [rbp-20h] BYREF
  const char *v23; // [rsp+58h] [rbp-18h] BYREF
  const char *v24; // [rsp+60h] [rbp-10h] BYREF
  const char *v25; // [rsp+68h] [rbp-8h] BYREF
  unsigned int v26; // [rsp+A0h] [rbp+30h] BYREF
  const struct _CERT_CONTEXT *v27; // [rsp+A8h] [rbp+38h] BYREF
  DWORD pdwFlags; // [rsp+B8h] [rbp+48h] BYREF

  v27 = a2;
  pdwFlags = 0;
  if ( pSubjectContext && a3 )
  {
    v6 = CertOpenStore("System", 0, 0, 0x24000u, L"AAD Token Issuer");
    v7 = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v27) = 265;
        v22 = "Opening issuer cert store failed";
        v10 = (__int64 *)byte_1801B0475;
        v23 = "FindIssuerCertificate";
        v24 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
        v25 = "Error condition failed";
        v21 = &v22;
        v20 = &v23;
        v19 = &v24;
        v11 = &v25;
LABEL_21:
        v26 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)pSubjectContext,
          (_DWORD)v10,
          (_DWORD)a3,
          (_DWORD)a4,
          (__int64)v11,
          (__int64)&v26,
          (__int64)v19,
          (__int64)&v27,
          (__int64)v20,
          (__int64)v21);
        return v9;
      }
      return v9;
    }
    IssuerCertificateFromStore = CertGetIssuerCertificateFromStore(v6, pSubjectContext, 0, &pdwFlags);
    if ( !IssuerCertificateFromStore )
    {
      v13 = GetLastError();
      if ( v13 == -2146885628 || v13 == -2146885625 )
      {
        v9 = -2147024894;
LABEL_18:
        CertCloseStore(v7, 0);
        return v9;
      }
      v14 = GetLastError();
      v9 = v14;
      if ( v14 > 0 )
        v9 = (unsigned __int16)v14 | 0x80070000;
      if ( (v9 & 0x80000000) != 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v27) = 286;
          v25 = "CertGetIssuerCertificateFromStore failed";
          v26 = v9;
          v24 = "FindIssuerCertificate";
          v23 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
          v22 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v15,
            (unsigned int)word_1801B042A,
            v16,
            v17,
            (__int64)&v22,
            (__int64)&v26,
            (__int64)&v23,
            (__int64)&v27,
            (__int64)&v24,
            (__int64)&v25);
        }
        goto LABEL_18;
      }
    }
    *(_QWORD *)a3 = IssuerCertificateFromStore;
    v9 = 0;
    goto LABEL_18;
  }
  v9 = -2147024809;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v27) = 253;
    v25 = "argument check failed";
    v10 = qword_1801B04C0;
    v24 = "FindIssuerCertificate";
    v23 = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
    v22 = "Error condition failed";
    v21 = &v25;
    v20 = &v24;
    v19 = &v23;
    v11 = &v22;
    goto LABEL_21;
  }
  return v9;
}

```

## disassembly

```asm
0x1800952b0  mov     [rsp-28h+arg_8], rdx
0x1800952b5  push    rbp
0x1800952b6  push    rbx
0x1800952b7  push    rsi
0x1800952b8  push    rdi
0x1800952b9  push    r14
0x1800952bb  mov     rbp, rsp
0x1800952be  sub     rsp, 70h
0x1800952c2  mov     [rbp+pdwFlags], 0
0x1800952c9  mov     rdi, r8
0x1800952cc  mov     rbx, rcx
0x1800952cf  test    rcx, rcx
0x1800952d2  jz      loc_1800954A2
0x1800952d8  test    r8, r8
0x1800952db  jz      loc_1800954A2
0x1800952e1  lea     rax, aAadTokenIssuer; "AAD Token Issuer"
0x1800952e8  mov     r9d, 24000h; dwFlags
0x1800952ee  xor     r8d, r8d; hCryptProv
0x1800952f1  mov     [rsp+70h+pvPara], rax; pvPara
0x1800952f6  xor     edx, edx; dwEncodingType
0x1800952f8  lea     rcx, szStoreProvider; "System"
0x1800952ff  call    cs:__imp_CertOpenStore
0x180095305  mov     rsi, rax
0x180095308  test    rax, rax
0x18009530b  jnz     loc_1800953A5
0x180095311  call    cs:__imp_GetLastError
0x180095317  mov     ebx, eax
0x180095319  test    eax, eax
0x18009531b  jle     short loc_180095326
0x18009531d  movzx   ebx, ax
0x180095320  or      ebx, 80070000h
0x180095326  mov     eax, cs:CallbackContext
0x18009532c  cmp     eax, 2
0x18009532f  jbe     loc_18009552A
0x180095335  lea     rax, aOpeningIssuerC; "Opening issuer cert store failed"
0x18009533c  mov     dword ptr [rbp+arg_8], 109h
0x180095343  mov     [rbp+var_20], rax
0x180095347  lea     rdx, byte_1801B0475
0x18009534e  lea     rax, aFindissuercert_0; "FindIssuerCertificate"
0x180095355  mov     [rbp+var_18], rax
0x180095359  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180095360  mov     [rbp+var_10], rax
0x180095364  lea     rax, aErrorCondition; "Error condition failed"
0x18009536b  mov     [rbp+var_8], rax
0x18009536f  lea     rax, [rbp+var_20]
0x180095373  mov     [rsp+70h+var_28], rax
0x180095378  lea     rax, [rbp+var_18]
0x18009537c  mov     [rsp+70h+var_30], rax
0x180095381  lea     rax, [rbp+arg_8]
0x180095385  mov     [rsp+70h+var_38], rax
0x18009538a  lea     rax, [rbp+var_10]
0x18009538e  mov     [rsp+70h+var_40], rax
0x180095393  lea     rax, [rbp+arg_0]
0x180095397  mov     [rsp+70h+var_48], rax
0x18009539c  lea     rax, [rbp+var_8]
0x1800953a0  jmp     loc_18009551D
0x1800953a5  lea     r9, [rbp+pdwFlags]; pdwFlags
0x1800953a9  xor     r8d, r8d; pPrevIssuerContext
0x1800953ac  mov     rdx, rbx; pSubjectContext
0x1800953af  mov     rcx, rsi; hCertStore
0x1800953b2  call    cs:__imp_CertGetIssuerCertificateFromStore
0x1800953b8  mov     r14, rax
0x1800953bb  test    rax, rax
0x1800953be  jnz     loc_18009548D
0x1800953c4  call    cs:__imp_GetLastError
0x1800953ca  cmp     eax, 80092004h
0x1800953cf  jz      loc_180095486
0x1800953d5  cmp     eax, 80092007h
0x1800953da  jz      loc_180095486
0x1800953e0  call    cs:__imp_GetLastError
0x1800953e6  mov     ebx, eax
0x1800953e8  test    eax, eax
0x1800953ea  jle     short loc_1800953F5
0x1800953ec  movzx   ebx, ax
0x1800953ef  or      ebx, 80070000h
0x1800953f5  test    ebx, ebx
0x1800953f7  jns     loc_18009548D
0x1800953fd  mov     eax, cs:CallbackContext
0x180095403  cmp     eax, 2
0x180095406  jbe     loc_180095492
0x18009540c  lea     rax, aCertgetissuerc_0; "CertGetIssuerCertificateFromStore faile"...
0x180095413  mov     dword ptr [rbp+arg_8], 11Eh
0x18009541a  mov     [rbp+var_8], rax
0x18009541e  lea     rdx, word_1801B042A
0x180095425  lea     rax, aFindissuercert_0; "FindIssuerCertificate"
0x18009542c  mov     [rbp+arg_0], ebx
0x18009542f  mov     [rbp+var_10], rax
0x180095433  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18009543a  mov     [rbp+var_18], rax
0x18009543e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180095445  mov     [rbp+var_20], rax
0x180095449  lea     rax, [rbp+var_8]
0x18009544d  mov     [rsp+70h+var_28], rax
0x180095452  lea     rax, [rbp+var_10]
0x180095456  mov     [rsp+70h+var_30], rax
0x18009545b  lea     rax, [rbp+arg_8]
0x18009545f  mov     [rsp+70h+var_38], rax
0x180095464  lea     rax, [rbp+var_18]
0x180095468  mov     [rsp+70h+var_40], rax
0x18009546d  lea     rax, [rbp+arg_0]
0x180095471  mov     [rsp+70h+var_48], rax
0x180095476  lea     rax, [rbp+var_20]
0x18009547a  mov     [rsp+70h+pvPara], rax
0x18009547f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180095484  jmp     short loc_180095492
0x180095486  mov     ebx, 80070002h
0x18009548b  jmp     short loc_180095492
0x18009548d  mov     [rdi], r14
0x180095490  xor     ebx, ebx
0x180095492  xor     edx, edx; dwFlags
0x180095494  mov     rcx, rsi; hCertStore
0x180095497  call    cs:__imp_CertCloseStore
0x18009549d  jmp     loc_18009552A
0x1800954a2  mov     eax, cs:CallbackContext
0x1800954a8  mov     ebx, 80070057h
0x1800954ad  cmp     eax, 2
0x1800954b0  jbe     short loc_18009552A
0x1800954b2  lea     rax, aArgumentCheckF; "argument check failed"
0x1800954b9  mov     dword ptr [rbp+arg_8], 0FDh
0x1800954c0  mov     [rbp+var_8], rax
0x1800954c4  lea     rdx, qword_1801B04C0
0x1800954cb  lea     rax, aFindissuercert_0; "FindIssuerCertificate"
0x1800954d2  mov     [rbp+var_10], rax
0x1800954d6  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800954dd  mov     [rbp+var_18], rax
0x1800954e1  lea     rax, aErrorCondition; "Error condition failed"
0x1800954e8  mov     [rbp+var_20], rax
0x1800954ec  lea     rax, [rbp+var_8]
0x1800954f0  mov     [rsp+70h+var_28], rax
0x1800954f5  lea     rax, [rbp+var_10]
0x1800954f9  mov     [rsp+70h+var_30], rax
0x1800954fe  lea     rax, [rbp+arg_8]
0x180095502  mov     [rsp+70h+var_38], rax
0x180095507  lea     rax, [rbp+var_18]
0x18009550b  mov     [rsp+70h+var_40], rax
0x180095510  lea     rax, [rbp+arg_0]
0x180095514  mov     [rsp+70h+var_48], rax
0x180095519  lea     rax, [rbp+var_20]
0x18009551d  mov     [rsp+70h+pvPara], rax
0x180095522  mov     [rbp+arg_0], ebx
0x180095525  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009552a  mov     eax, ebx
0x18009552c  add     rsp, 70h
0x180095530  pop     r14
0x180095532  pop     rdi
0x180095533  pop     rsi
0x180095534  pop     rbx
0x180095535  pop     rbp
0x180095536  retn
```
