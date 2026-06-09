# CRDPENCCONSecurityFilterStream::GetCertificate(_CERT_CONTEXT const * *)

- ea: `0x1800edd4c`
- end: `0x1800edf53`
- name: `?GetCertificate@CRDPENCCONSecurityFilterStream@@AEAAJPEAPEBU_CERT_CONTEXT@@@Z`
- size: `519`
- prototype: `__int64 __fastcall(CRDPENCCONSecurityFilterStream *__hidden this, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ecc38`

## callees

- `0x180001aa0`
- `0x1800edd4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edd9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ede8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800edd9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ede8f`
- `CRYPT32!CertCloseStore` at `0x1800edf40`
- `CRYPT32!CertCloseStore` at `0x1800edf40`
- `CRYPT32!CertOpenStore` at `0x1800edd8c`
- `CRYPT32!CertOpenStore` at `0x1800edd8c`
- `CRYPT32!CertFindCertificateInStore` at `0x1800ede7d`
- `CRYPT32!CertFindCertificateInStore` at `0x1800ede7d`

## string_xrefs

- `0x1800eddca`: `CertOpenStore failed`

## pseudocode

```c
__int64 __fastcall CRDPENCCONSecurityFilterStream::GetCertificate(
        CRDPENCCONSecurityFilterStream *this,
        const struct _CERT_CONTEXT **a2)
{
  const void *pvPara; // rax
  HCERTSTORE v5; // rdi
  signed int LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  signed int v10; // ebx
  const struct _CERT_CONTEXT *CertificateInStore; // rsi
  signed int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v17; // [rsp+50h] [rbp-20h] BYREF
  const char *v18; // [rsp+58h] [rbp-18h] BYREF
  __int128 pvFindPara; // [rsp+60h] [rbp-10h] BYREF
  int v20; // [rsp+A0h] [rbp+30h] BYREF
  signed int v21; // [rsp+A8h] [rbp+38h] BYREF
  const char *v22; // [rsp+B0h] [rbp+40h] BYREF
  const char *v23; // [rsp+B8h] [rbp+48h] BYREF

  pvPara = (const void *)*((_QWORD *)this + 40);
  *a2 = 0;
  pvFindPara = 0;
  v5 = CertOpenStore("System", 0, 0, 0x2C000u, pvPara);
  if ( v5 )
    goto LABEL_7;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_7:
    *((_QWORD *)&pvFindPara + 1) = *((_QWORD *)this + 38);
    LODWORD(pvFindPara) = *((_DWORD *)this + 78);
    CertificateInStore = CertFindCertificateInStore(v5, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    if ( CertificateInStore )
      goto LABEL_13;
    v12 = GetLastError();
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    if ( v10 >= 0 )
    {
LABEL_13:
      *a2 = CertificateInStore;
      v10 = 0;
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v20 = 4123;
      v22 = "CertFindCertificateInStore failed";
      v21 = v10;
      v23 = "GetCertificate";
      v18 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
      v17 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)byte_1801BFCBD,
        v14,
        v15,
        (__int64)&v17,
        (__int64)&v21,
        (__int64)&v18,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v22);
    }
    if ( v5 )
      CertCloseStore(v5, 0);
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    v20 = 4104;
    v22 = "CertOpenStore failed";
    v21 = v10;
    v23 = "GetCertificate";
    v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencsecfilter.cpp";
    v18 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v7,
      (unsigned int)&word_1801BFDBE,
      v8,
      v9,
      (__int64)&v18,
      (__int64)&v21,
      (__int64)&v17,
      (__int64)&v20,
      (__int64)&v23,
      (__int64)&v22);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800edd4c  push    rbp
0x1800edd4e  push    rbx
0x1800edd4f  push    rsi
0x1800edd50  push    rdi
0x1800edd51  push    r14
0x1800edd53  mov     rbp, rsp
0x1800edd56  sub     rsp, 70h
0x1800edd5a  mov     rax, [rcx+140h]
0x1800edd61  mov     r14, rdx
0x1800edd64  mov     rsi, rcx
0x1800edd67  mov     qword ptr [rdx], 0
0x1800edd6e  xorps   xmm0, xmm0
0x1800edd71  mov     [rsp+70h+pvPara], rax; pvPara
0x1800edd76  xor     edx, edx; dwEncodingType
0x1800edd78  lea     rcx, szStoreProvider; "System"
0x1800edd7f  mov     r9d, 2C000h; dwFlags
0x1800edd85  xor     r8d, r8d; hCryptProv
0x1800edd88  movups  [rbp+pvFindPara], xmm0
0x1800edd8c  call    cs:__imp_CertOpenStore
0x1800edd92  mov     rdi, rax
0x1800edd95  test    rax, rax
0x1800edd98  jnz     loc_1800EDE47
0x1800edd9e  call    cs:__imp_GetLastError
0x1800edda4  mov     ebx, eax
0x1800edda6  test    eax, eax
0x1800edda8  jle     short loc_1800EDDB3
0x1800eddaa  movzx   ebx, ax
0x1800eddad  or      ebx, 80070000h
0x1800eddb3  test    ebx, ebx
0x1800eddb5  jns     loc_1800EDE47
0x1800eddbb  mov     eax, cs:CallbackContext
0x1800eddc1  cmp     eax, 2
0x1800eddc4  jbe     loc_1800EDF46
0x1800eddca  lea     rax, aCertopenstoreF; "CertOpenStore failed"
0x1800eddd1  mov     [rbp+arg_0], 1008h
0x1800eddd8  mov     [rbp+arg_10], rax
0x1800edddc  lea     rdx, word_1801BFDBE
0x1800edde3  lea     rax, aGetcertificate_2; "GetCertificate"
0x1800eddea  mov     [rbp+arg_8], ebx
0x1800edded  mov     [rbp+arg_18], rax
0x1800eddf1  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800eddf8  mov     [rbp+var_20], rax
0x1800eddfc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800ede03  mov     [rbp+var_18], rax
0x1800ede07  lea     rax, [rbp+arg_10]
0x1800ede0b  mov     [rsp+70h+var_28], rax
0x1800ede10  lea     rax, [rbp+arg_18]
0x1800ede14  mov     [rsp+70h+var_30], rax
0x1800ede19  lea     rax, [rbp+arg_0]
0x1800ede1d  mov     [rsp+70h+var_38], rax
0x1800ede22  lea     rax, [rbp+var_20]
0x1800ede26  mov     [rsp+70h+var_40], rax
0x1800ede2b  lea     rax, [rbp+arg_8]
0x1800ede2f  mov     [rsp+70h+pPrevCertContext], rax
0x1800ede34  lea     rax, [rbp+var_18]
0x1800ede38  mov     [rsp+70h+pvPara], rax
0x1800ede3d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800ede42  jmp     loc_1800EDF46
0x1800ede47  mov     rax, [rsi+130h]
0x1800ede4e  mov     r9d, 10000h; dwFindType
0x1800ede54  mov     qword ptr [rbp+pvFindPara+8], rax
0x1800ede58  xor     r8d, r8d; dwFindFlags
0x1800ede5b  mov     eax, [rsi+138h]
0x1800ede61  mov     rcx, rdi; hCertStore
0x1800ede64  mov     dword ptr [rbp+pvFindPara], eax
0x1800ede67  lea     rax, [rbp+pvFindPara]
0x1800ede6b  mov     [rsp+70h+pPrevCertContext], 0; pPrevCertContext
0x1800ede74  lea     edx, [r9+1]; dwCertEncodingType
0x1800ede78  mov     [rsp+70h+pvPara], rax; pvFindPara
0x1800ede7d  call    cs:__imp_CertFindCertificateInStore
0x1800ede83  mov     rsi, rax
0x1800ede86  test    rax, rax
0x1800ede89  jnz     loc_1800EDF31
0x1800ede8f  call    cs:__imp_GetLastError
0x1800ede95  mov     ebx, eax
0x1800ede97  test    eax, eax
0x1800ede99  jle     short loc_1800EDEA4
0x1800ede9b  movzx   ebx, ax
0x1800ede9e  or      ebx, 80070000h
0x1800edea4  test    ebx, ebx
0x1800edea6  jns     loc_1800EDF31
0x1800edeac  mov     eax, cs:CallbackContext
0x1800edeb2  cmp     eax, 2
0x1800edeb5  jbe     short loc_1800EDF36
0x1800edeb7  lea     rax, aCertfindcertif_0; "CertFindCertificateInStore failed"
0x1800edebe  mov     [rbp+arg_0], 101Bh
0x1800edec5  mov     [rbp+arg_10], rax
0x1800edec9  lea     rdx, byte_1801BFCBD
0x1800eded0  lea     rax, aGetcertificate_2; "GetCertificate"
0x1800eded7  mov     [rbp+arg_8], ebx
0x1800ededa  mov     [rbp+arg_18], rax
0x1800edede  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800edee5  mov     [rbp+var_18], rax
0x1800edee9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800edef0  mov     [rbp+var_20], rax
0x1800edef4  lea     rax, [rbp+arg_10]
0x1800edef8  mov     [rsp+70h+var_28], rax
0x1800edefd  lea     rax, [rbp+arg_18]
0x1800edf01  mov     [rsp+70h+var_30], rax
0x1800edf06  lea     rax, [rbp+arg_0]
0x1800edf0a  mov     [rsp+70h+var_38], rax
0x1800edf0f  lea     rax, [rbp+var_18]
0x1800edf13  mov     [rsp+70h+var_40], rax
0x1800edf18  lea     rax, [rbp+arg_8]
0x1800edf1c  mov     [rsp+70h+pPrevCertContext], rax
0x1800edf21  lea     rax, [rbp+var_20]
0x1800edf25  mov     [rsp+70h+pvPara], rax
0x1800edf2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800edf2f  jmp     short loc_1800EDF36
0x1800edf31  mov     [r14], rsi
0x1800edf34  xor     ebx, ebx
0x1800edf36  test    rdi, rdi
0x1800edf39  jz      short loc_1800EDF46
0x1800edf3b  xor     edx, edx; dwFlags
0x1800edf3d  mov     rcx, rdi; hCertStore
0x1800edf40  call    cs:__imp_CertCloseStore
0x1800edf46  mov     eax, ebx
0x1800edf48  add     rsp, 70h
0x1800edf4c  pop     r14
0x1800edf4e  pop     rdi
0x1800edf4f  pop     rsi
0x1800edf50  pop     rbx
0x1800edf51  pop     rbp
0x1800edf52  retn
```
