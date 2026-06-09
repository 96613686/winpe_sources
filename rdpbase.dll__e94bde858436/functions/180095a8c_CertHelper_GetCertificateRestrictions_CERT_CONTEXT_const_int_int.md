# CertHelper::GetCertificateRestrictions(_CERT_CONTEXT const *,int *,int *)

- ea: `0x180095a8c`
- end: `0x180095fb3`
- name: `?GetCertificateRestrictions@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEAH1@Z`
- size: `1319`
- prototype: `__int64 __fastcall(CertHelper *__hidden this, const struct _CERT_CONTEXT *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008f6a0`

## callees

- `0x180001aa0`
- `0x180005090`
- `0x180078820`
- `0x1800957e8`
- `0x180095a8c`
- `0x180095fbc`
- `0x180096438`
- `0x1800967cc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095df2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095ebd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095df2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180095ebd`
- `ncrypt!NCryptFreeObject` at `0x180095f8a`
- `ncrypt!NCryptFreeObject` at `0x180095f8a`
- `ncrypt!NCryptIsKeyHandle` at `0x180095d28`
- `ncrypt!NCryptIsKeyHandle` at `0x180095f7c`
- `ncrypt!NCryptIsKeyHandle` at `0x180095d28`
- `ncrypt!NCryptIsKeyHandle` at `0x180095f7c`
- `CRYPTSP!CryptReleaseContext` at `0x180095f94`
- `CRYPTSP!CryptReleaseContext` at `0x180095f94`

## string_xrefs

- `0x180095b0f`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095ba8`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095c3a`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095cd8`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095d7f`: `onecore\termsrv\rdp\win\security\certhelper.cpp`
- `0x180095e4a`: `onecore\termsrv\rdp\win\security\certhelper.cpp`

## pseudocode

```c
__int64 __fastcall CertHelper::GetCertificateRestrictions(
        CertHelper *this,
        const struct _CERT_CONTEXT *a2,
        int *a3,
        int *a4)
{
  BYTE *pbCertEncoded; // rsi
  void *v5; // rdi
  int CertificatePrivateKey; // ebx
  int v9; // r8d
  int v10; // r9d
  unsigned __int16 **v11; // r8
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned __int16 **v15; // r8
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  unsigned int *v19; // r8
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v24; // [rsp+58h] [rbp-9h] BYREF
  int v25; // [rsp+5Ch] [rbp-5h] BYREF
  struct _CERT_CONTEXT hKey; // [rsp+60h] [rbp-1h] BYREF
  _QWORD v27[6]; // [rsp+88h] [rbp+27h] BYREF
  unsigned __int64 v28; // [rsp+C8h] [rbp+67h] BYREF
  unsigned __int64 v29; // [rsp+E0h] [rbp+7Fh] BYREF

  pbCertEncoded = 0;
  memset(&hKey, 0, 24);
  v5 = 0;
  LODWORD(v29) = 0;
  LODWORD(v28) = 0;
  if ( !this )
  {
    CertificatePrivateKey = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v24 = 734;
      *(_QWORD *)&hKey.cbCertEncoded = "pCertContext is not specified";
      v25 = -2147024809;
      hKey.pbCertEncoded = (BYTE *)"GetCertificateRestrictions";
      hKey.pCertInfo = (PCERT_INFO)"onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
      hKey.hCertStore = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)byte_1801AFD6D,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&hKey.hCertStore,
        (__int64)&v25,
        (__int64)&hKey.pCertInfo,
        (__int64)&v24,
        (__int64)&hKey.pbCertEncoded,
        (__int64)&hKey.cbCertEncoded);
    }
    goto LABEL_35;
  }
  if ( !a2 )
  {
    CertificatePrivateKey = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v25 = 735;
      hKey.hCertStore = "pfNoTLS13 is not specified";
      v24 = -2147024809;
      hKey.pCertInfo = (PCERT_INFO)"GetCertificateRestrictions";
      *(_QWORD *)&hKey.cbCertEncoded = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
      hKey.pbCertEncoded = (BYTE *)"Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)word_1801AFD22,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&hKey.pbCertEncoded,
        (__int64)&v24,
        (__int64)&hKey.cbCertEncoded,
        (__int64)&v25,
        (__int64)&hKey.pCertInfo,
        (__int64)&hKey.hCertStore);
    }
    goto LABEL_35;
  }
  if ( !a3 )
  {
    CertificatePrivateKey = -2147024809;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v25 = 736;
      hKey.hCertStore = "pfNoRSAPSS is not specified";
      v24 = -2147024809;
      hKey.pCertInfo = (PCERT_INFO)"GetCertificateRestrictions";
      *(_QWORD *)&hKey.cbCertEncoded = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
      hKey.pbCertEncoded = (BYTE *)"Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)&byte_1801AFCD7,
        0,
        (_DWORD)a4,
        (__int64)&hKey.pbCertEncoded,
        (__int64)&v24,
        (__int64)&hKey.cbCertEncoded,
        (__int64)&v25,
        (__int64)&hKey.pCertInfo,
        (__int64)&hKey.hCertStore);
    }
    goto LABEL_35;
  }
  a2->dwCertEncodingType = 0;
  *a3 = 0;
  CertificatePrivateKey = CertHelper::GetCertificatePrivateKey(this, &hKey, &v29, a4);
  if ( CertificatePrivateKey < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v25 = 746;
      hKey.hCertStore = "GetCertificatePrivateKey failed";
      v24 = CertificatePrivateKey;
      hKey.pCertInfo = (PCERT_INFO)"GetCertificateRestrictions";
      *(_QWORD *)&hKey.cbCertEncoded = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
      hKey.pbCertEncoded = (BYTE *)"Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)&dword_1801AFC8C,
        v9,
        v10,
        (__int64)&hKey.pbCertEncoded,
        (__int64)&v24,
        (__int64)&hKey.cbCertEncoded,
        (__int64)&v25,
        (__int64)&hKey.pCertInfo,
        (__int64)&hKey.hCertStore);
    }
    goto LABEL_35;
  }
  if ( !NCryptIsKeyHandle(*(NCRYPT_KEY_HANDLE *)&hKey.dwCertEncodingType) )
    goto LABEL_30;
  CertificatePrivateKey = CertHelper::GetKeyAlgorithm(
                            *(NCRYPT_HANDLE *)&hKey.dwCertEncodingType,
                            (unsigned __int64)&hKey.pbCertEncoded,
                            v11);
  if ( CertificatePrivateKey < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v25 = 755;
      hKey.hCertStore = "GetKeyAlgorithm failed";
      v24 = CertificatePrivateKey;
      hKey.pCertInfo = (PCERT_INFO)"GetCertificateRestrictions";
      *(_QWORD *)&hKey.cbCertEncoded = "onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
      v27[0] = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)byte_1801AFC41,
        v13,
        v14,
        (__int64)v27,
        (__int64)&v24,
        (__int64)&hKey.cbCertEncoded,
        (__int64)&v25,
        (__int64)&hKey.pCertInfo,
        (__int64)&hKey.hCertStore);
    }
    pbCertEncoded = hKey.pbCertEncoded;
    goto LABEL_31;
  }
  pbCertEncoded = hKey.pbCertEncoded;
  if ( CompareStringOrdinal((LPCWCH)hKey.pbCertEncoded, -1, L"RSA", -1, 0) == 2 )
  {
    CertificatePrivateKey = CertHelper::GetKSPName(
                              *(CertHelper **)&hKey.dwCertEncodingType,
                              (unsigned __int64)&hKey.cbCertEncoded,
                              v15);
    if ( CertificatePrivateKey < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v25 = 764;
        v27[0] = "GetKSPName failed";
        v24 = CertificatePrivateKey;
        hKey.hCertStore = "GetCertificateRestrictions";
        hKey.pCertInfo = (PCERT_INFO)"onecore\\termsrv\\rdp\\win\\security\\certhelper.cpp";
        hKey.pbCertEncoded = (BYTE *)"Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v16,
          (unsigned int)&word_1801AFBF6,
          v17,
          v18,
          (__int64)&hKey.pbCertEncoded,
          (__int64)&v24,
          (__int64)&hKey.pCertInfo,
          (__int64)&v25,
          (__int64)&hKey.hCertStore,
          (__int64)v27);
      }
      v5 = *(void **)&hKey.cbCertEncoded;
      goto LABEL_31;
    }
    v5 = *(void **)&hKey.cbCertEncoded;
    if ( CompareStringOrdinal(*(LPCWCH *)&hKey.cbCertEncoded, -1, L"Microsoft Platform Crypto Provider", -1, 0) == 2 )
    {
      CertificatePrivateKey = CertHelper::GetPSSSaltSize(
                                *(CertHelper **)&hKey.dwCertEncodingType,
                                (unsigned __int64)&v28,
                                v19);
      if ( CertificatePrivateKey < 0 )
      {
        if ( (unsigned int)CallbackContext > 3 )
        {
          v25 = CertificatePrivateKey;
          v27[0] = "GetCertificateRestrictions";
          hKey.hCertStore = "GetPSSSaltSize failed";
          hKey.pCertInfo = (PCERT_INFO)"HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v20,
            (unsigned int)byte_1801AFBBD,
            v21,
            v22,
            (__int64)&hKey.pCertInfo,
            (__int64)&hKey.hCertStore,
            (__int64)&v25,
            (__int64)v27);
        }
        goto LABEL_29;
      }
      if ( (_DWORD)v28 != 2 )
      {
LABEL_29:
        CertificatePrivateKey = 0;
LABEL_30:
        *a3 = 1;
        a2->dwCertEncodingType = 1;
      }
    }
  }
LABEL_31:
  if ( pbCertEncoded )
    operator delete(pbCertEncoded);
  if ( v5 )
    operator delete(v5);
LABEL_35:
  if ( (_DWORD)v29 && *(_QWORD *)&hKey.dwCertEncodingType )
  {
    if ( NCryptIsKeyHandle(*(NCRYPT_KEY_HANDLE *)&hKey.dwCertEncodingType) )
      NCryptFreeObject(*(NCRYPT_HANDLE *)&hKey.dwCertEncodingType);
    else
      CryptReleaseContext(*(HCRYPTPROV *)&hKey.dwCertEncodingType, 0);
  }
  return (unsigned int)CertificatePrivateKey;
}

```

## disassembly

```asm
0x180095a8c  mov     r11, rsp
0x180095a8f  mov     [r11+10h], rbx
0x180095a93  push    rbp
0x180095a94  push    rsi
0x180095a95  push    rdi
0x180095a96  push    r14
0x180095a98  push    r15
0x180095a9a  lea     rbp, [r11-5Fh]
0x180095a9e  sub     rsp, 90h
0x180095aa5  xor     esi, esi
0x180095aa7  mov     [rbp+57h+hKey], 0
0x180095aaf  xor     edi, edi
0x180095ab1  mov     dword ptr [rbp+57h+arg_18], 0
0x180095ab8  mov     [rbp+57h+lpString1], rsi
0x180095abc  mov     r14, r8
0x180095abf  mov     [rbp+57h+var_48], rdi
0x180095ac3  mov     r15, rdx
0x180095ac6  mov     dword ptr [rbp+57h+arg_0], esi
0x180095ac9  test    rcx, rcx
0x180095acc  jnz     loc_180095B62
0x180095ad2  mov     eax, cs:CallbackContext
0x180095ad8  mov     ecx, 80070057h
0x180095add  mov     ebx, ecx
0x180095adf  cmp     eax, 2
0x180095ae2  jbe     loc_180095F6D
0x180095ae8  lea     rax, aPcertcontextIs; "pCertContext is not specified"
0x180095aef  mov     [rbp+57h+var_60], 2DEh
0x180095af6  mov     [rbp+57h+var_48], rax
0x180095afa  lea     rdx, byte_1801AFD6D
0x180095b01  lea     rax, aGetcertificate_5; "GetCertificateRestrictions"
0x180095b08  mov     [rbp+57h+var_5C], ecx
0x180095b0b  mov     [rbp+57h+lpString1], rax
0x180095b0f  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180095b16  mov     [rbp+57h+var_40], rax
0x180095b1a  lea     rax, aErrorCondition; "Error condition failed"
0x180095b21  mov     [rbp+57h+var_38], rax
0x180095b25  lea     rax, [rbp+57h+var_48]
0x180095b29  mov     [r11-70h], rax
0x180095b2d  lea     rax, [rbp+57h+lpString1]
0x180095b31  mov     [r11-78h], rax
0x180095b35  lea     rax, [rbp+57h+var_60]
0x180095b39  mov     [r11-80h], rax
0x180095b3d  lea     rax, [rbp+57h+var_40]
0x180095b41  mov     [rsp+0B0h+var_80], rax
0x180095b46  lea     rax, [rbp+57h+var_5C]
0x180095b4a  mov     [rsp+0B0h+var_88], rax
0x180095b4f  lea     rax, [rbp+57h+var_38]
0x180095b53  mov     qword ptr [rsp+0B0h+bIgnoreCase], rax
0x180095b58  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180095b5d  jmp     loc_180095F6D
0x180095b62  test    r15, r15
0x180095b65  jnz     loc_180095BF4
0x180095b6b  mov     eax, cs:CallbackContext
0x180095b71  mov     ecx, 80070057h
0x180095b76  mov     ebx, ecx
0x180095b78  cmp     eax, 2
0x180095b7b  jbe     loc_180095F6D
0x180095b81  lea     rax, aPfnotls13IsNot; "pfNoTLS13 is not specified"
0x180095b88  mov     [rbp+57h+var_5C], 2DFh
0x180095b8f  mov     [rbp+57h+var_38], rax
0x180095b93  lea     rdx, word_1801AFD22
0x180095b9a  lea     rax, aGetcertificate_5; "GetCertificateRestrictions"
0x180095ba1  mov     [rbp+57h+var_60], ecx
0x180095ba4  mov     [rbp+57h+var_40], rax
0x180095ba8  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180095baf  mov     [rbp+57h+var_48], rax
0x180095bb3  lea     rax, aErrorCondition; "Error condition failed"
0x180095bba  mov     [rbp+57h+lpString1], rax
0x180095bbe  lea     rax, [rbp+57h+var_38]
0x180095bc2  mov     [rsp+48h], rax
0x180095bc7  lea     rax, [rbp+57h+var_40]
0x180095bcb  mov     [rsp+0B0h+var_70], rax
0x180095bd0  lea     rax, [rbp+57h+var_5C]
0x180095bd4  mov     [rsp+0B0h+var_78], rax
0x180095bd9  lea     rax, [rbp+57h+var_48]
0x180095bdd  mov     [rsp+0B0h+var_80], rax
0x180095be2  lea     rax, [rbp+57h+var_60]
0x180095be6  mov     [rsp+0B0h+var_88], rax
0x180095beb  lea     rax, [rbp+57h+lpString1]
0x180095bef  jmp     loc_180095B53
0x180095bf4  test    r14, r14
0x180095bf7  jnz     loc_180095C86
0x180095bfd  mov     eax, cs:CallbackContext
0x180095c03  mov     ecx, 80070057h; this
0x180095c08  mov     ebx, ecx
0x180095c0a  cmp     eax, 2
0x180095c0d  jbe     loc_180095F6D
0x180095c13  lea     rax, aPfnorsapssIsNo; "pfNoRSAPSS is not specified"
0x180095c1a  mov     [rbp+57h+var_5C], 2E0h
0x180095c21  mov     [rbp+57h+var_38], rax
0x180095c25  lea     rdx, byte_1801AFCD7
0x180095c2c  lea     rax, aGetcertificate_5; "GetCertificateRestrictions"
0x180095c33  mov     [rbp+57h+var_60], ecx
0x180095c36  mov     [rbp+57h+var_40], rax
0x180095c3a  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180095c41  mov     [rbp+57h+var_48], rax
0x180095c45  lea     rax, aErrorCondition; "Error condition failed"
0x180095c4c  mov     [rbp+57h+lpString1], rax
0x180095c50  lea     rax, [rbp+57h+var_38]
0x180095c54  mov     [rsp+48h], rax
0x180095c59  lea     rax, [rbp+57h+var_40]
0x180095c5d  mov     [rsp+0B0h+var_70], rax
0x180095c62  lea     rax, [rbp+57h+var_5C]
0x180095c66  mov     [rsp+0B0h+var_78], rax
0x180095c6b  lea     rax, [rbp+57h+var_48]
0x180095c6f  mov     [rsp+0B0h+var_80], rax
0x180095c74  lea     rax, [rbp+57h+var_60]
0x180095c78  mov     [rsp+0B0h+var_88], rax
0x180095c7d  lea     rax, [rbp+57h+lpString1]
0x180095c81  jmp     loc_180095B53
0x180095c86  mov     [rdx], esi
0x180095c88  lea     rdx, [rbp+57h+hKey]; struct _CERT_CONTEXT *
0x180095c8c  mov     [r8], esi
0x180095c8f  lea     r8, [rbp+57h+arg_18]; unsigned __int64 *
0x180095c93  call    ?GetCertificatePrivateKey@CertHelper@@YAJPEBU_CERT_CONTEXT@@PEA_KPEAH@Z; CertHelper::GetCertificatePrivateKey(_CERT_CONTEXT const *,unsigned __int64 *,int *)
0x180095c98  mov     ebx, eax
0x180095c9a  test    eax, eax
0x180095c9c  jns     loc_180095D24
0x180095ca2  mov     ecx, cs:CallbackContext
0x180095ca8  cmp     ecx, 2
0x180095cab  jbe     loc_180095F6D
0x180095cb1  lea     rax, aGetcertificate; "GetCertificatePrivateKey failed"
0x180095cb8  mov     [rbp+57h+var_5C], 2EAh
0x180095cbf  mov     [rbp+57h+var_38], rax
0x180095cc3  lea     rdx, dword_1801AFC8C
0x180095cca  lea     rax, aGetcertificate_5; "GetCertificateRestrictions"
0x180095cd1  mov     [rbp+57h+var_60], ebx
0x180095cd4  mov     [rbp+57h+var_40], rax
0x180095cd8  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180095cdf  mov     [rbp+57h+var_48], rax
0x180095ce3  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180095cea  mov     [rbp+57h+lpString1], rax
0x180095cee  lea     rax, [rbp+57h+var_38]
0x180095cf2  mov     [rsp+48h], rax
0x180095cf7  lea     rax, [rbp+57h+var_40]
0x180095cfb  mov     [rsp+0B0h+var_70], rax
0x180095d00  lea     rax, [rbp+57h+var_5C]
0x180095d04  mov     [rsp+0B0h+var_78], rax
0x180095d09  lea     rax, [rbp+57h+var_48]
0x180095d0d  mov     [rsp+0B0h+var_80], rax
0x180095d12  lea     rax, [rbp+57h+var_60]
0x180095d16  mov     [rsp+0B0h+var_88], rax
0x180095d1b  lea     rax, [rbp+57h+lpString1]
0x180095d1f  jmp     loc_180095B53
0x180095d24  mov     rcx, [rbp+57h+hKey]; hKey
0x180095d28  call    cs:__imp_NCryptIsKeyHandle
0x180095d2e  test    eax, eax
0x180095d30  jz      loc_180095F48
0x180095d36  mov     rcx, [rbp+57h+hKey]; hObject
0x180095d3a  lea     rdx, [rbp+57h+lpString1]; unsigned __int64
0x180095d3e  call    ?GetKeyAlgorithm@CertHelper@@YAJ_KPEAPEAG@Z; CertHelper::GetKeyAlgorithm(unsigned __int64,ushort * *)
0x180095d43  mov     ebx, eax
0x180095d45  test    eax, eax
0x180095d47  jns     loc_180095DD9
0x180095d4d  mov     eax, cs:CallbackContext
0x180095d53  cmp     eax, 2
0x180095d56  jbe     short loc_180095DD0
0x180095d58  lea     rax, aGetkeyalgorith; "GetKeyAlgorithm failed"
0x180095d5f  mov     [rbp+57h+var_5C], 2F3h
0x180095d66  mov     [rbp+57h+var_38], rax
0x180095d6a  lea     rdx, byte_1801AFC41
0x180095d71  lea     rax, aGetcertificate_5; "GetCertificateRestrictions"
0x180095d78  mov     [rbp+57h+var_60], ebx
0x180095d7b  mov     [rbp+57h+var_40], rax
0x180095d7f  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180095d86  mov     [rbp+57h+var_48], rax
0x180095d8a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180095d91  mov     [rbp+57h+var_30], rax
0x180095d95  lea     rax, [rbp+57h+var_38]
0x180095d99  mov     [rsp+48h], rax
0x180095d9e  lea     rax, [rbp+57h+var_40]
0x180095da2  mov     [rsp+0B0h+var_70], rax
0x180095da7  lea     rax, [rbp+57h+var_5C]
0x180095dab  mov     [rsp+0B0h+var_78], rax
0x180095db0  lea     rax, [rbp+57h+var_48]
0x180095db4  mov     [rsp+0B0h+var_80], rax
0x180095db9  lea     rax, [rbp+57h+var_60]
0x180095dbd  mov     [rsp+0B0h+var_88], rax
0x180095dc2  lea     rax, [rbp+57h+var_30]
0x180095dc6  mov     qword ptr [rsp+0B0h+bIgnoreCase], rax
0x180095dcb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180095dd0  mov     rsi, [rbp+57h+lpString1]
0x180095dd4  jmp     loc_180095F53
0x180095dd9  or      r9d, 0FFFFFFFFh; cchCount2
0x180095ddd  mov     [rsp+0B0h+bIgnoreCase], esi; bIgnoreCase
0x180095de1  mov     rsi, [rbp+57h+lpString1]
0x180095de5  lea     r8, aRsa; "RSA"
0x180095dec  mov     rcx, rsi; lpString1
0x180095def  or      edx, r9d; cchCount1
0x180095df2  call    cs:__imp_CompareStringOrdinal
0x180095df8  cmp     eax, 2
0x180095dfb  jnz     loc_180095F53
0x180095e01  mov     rcx, [rbp+57h+hKey]; this
0x180095e05  lea     rdx, [rbp+57h+var_48]; unsigned __int64
0x180095e09  call    ?GetKSPName@CertHelper@@YAJ_KPEAPEAG@Z; CertHelper::GetKSPName(unsigned __int64,ushort * *)
0x180095e0e  mov     ebx, eax
0x180095e10  test    eax, eax
0x180095e12  jns     loc_180095EA4
0x180095e18  mov     eax, cs:CallbackContext
0x180095e1e  cmp     eax, 2
0x180095e21  jbe     short loc_180095E9B
0x180095e23  lea     rax, aGetkspnameFail; "GetKSPName failed"
0x180095e2a  mov     [rbp+57h+var_5C], 2FCh
0x180095e31  mov     [rbp+57h+var_30], rax
0x180095e35  lea     rdx, word_1801AFBF6
0x180095e3c  lea     rax, aGetcertificate_5; "GetCertificateRestrictions"
0x180095e43  mov     [rbp+57h+var_60], ebx
0x180095e46  mov     [rbp+57h+var_38], rax
0x180095e4a  lea     rax, aOnecoreTermsrv_51; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180095e51  mov     [rbp+57h+var_40], rax
0x180095e55  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180095e5c  mov     [rbp+57h+lpString1], rax
0x180095e60  lea     rax, [rbp+57h+var_30]
0x180095e64  mov     [rsp+48h], rax
0x180095e69  lea     rax, [rbp+57h+var_38]
0x180095e6d  mov     [rsp+0B0h+var_70], rax
0x180095e72  lea     rax, [rbp+57h+var_5C]
0x180095e76  mov     [rsp+0B0h+var_78], rax
0x180095e7b  lea     rax, [rbp+57h+var_40]
0x180095e7f  mov     [rsp+0B0h+var_80], rax
0x180095e84  lea     rax, [rbp+57h+var_60]
0x180095e88  mov     [rsp+0B0h+var_88], rax
0x180095e8d  lea     rax, [rbp+57h+lpString1]
0x180095e91  mov     qword ptr [rsp+0B0h+bIgnoreCase], rax
0x180095e96  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180095e9b  mov     rdi, [rbp+57h+var_48]
0x180095e9f  jmp     loc_180095F53
0x180095ea4  or      r9d, 0FFFFFFFFh; cchCount2
0x180095ea8  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x180095eac  mov     rdi, [rbp+57h+var_48]
0x180095eb0  lea     r8, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180095eb7  mov     rcx, rdi; lpString1
0x180095eba  or      edx, r9d; cchCount1
0x180095ebd  call    cs:__imp_CompareStringOrdinal
0x180095ec3  cmp     eax, 2
0x180095ec6  jnz     loc_180095F53
0x180095ecc  mov     rcx, [rbp+57h+hKey]; this
0x180095ed0  lea     rdx, [rbp+57h+arg_0]; unsigned __int64
0x180095ed4  call    ?GetPSSSaltSize@CertHelper@@YAK_KPEAK@Z; CertHelper::GetPSSSaltSize(unsigned __int64,ulong *)
0x180095ed9  mov     ebx, eax
0x180095edb  test    eax, eax
0x180095edd  jns     short loc_180095F40
0x180095edf  mov     eax, cs:CallbackContext
0x180095ee5  cmp     eax, 3
0x180095ee8  jbe     short loc_180095F46
0x180095eea  lea     rax, aGetcertificate_5; "GetCertificateRestrictions"
0x180095ef1  mov     [rbp+57h+var_5C], ebx
0x180095ef4  mov     [rbp+57h+var_30], rax
0x180095ef8  lea     rdx, byte_1801AFBBD
0x180095eff  lea     rax, aGetpsssaltsize_0; "GetPSSSaltSize failed"
0x180095f06  mov     [rbp+57h+var_38], rax
0x180095f0a  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180095f11  mov     [rbp+57h+var_40], rax
0x180095f15  lea     rax, [rbp+57h+var_30]
0x180095f19  mov     [rsp+0B0h+var_78], rax
0x180095f1e  lea     rax, [rbp+57h+var_5C]
0x180095f22  mov     [rsp+0B0h+var_80], rax
0x180095f27  lea     rax, [rbp+57h+var_38]
0x180095f2b  mov     [rsp+0B0h+var_88], rax
0x180095f30  lea     rax, [rbp+57h+var_40]
0x180095f34  mov     qword ptr [rsp+0B0h+bIgnoreCase], rax
0x180095f39  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180095f3e  jmp     short loc_180095F46
0x180095f40  cmp     dword ptr [rbp+57h+arg_0], 2
0x180095f44  jz      short loc_180095F53
0x180095f46  xor     ebx, ebx
0x180095f48  mov     eax, 1
0x180095f4d  mov     [r14], eax
0x180095f50  mov     [r15], eax
0x180095f53  test    rsi, rsi
0x180095f56  jz      short loc_180095F60
0x180095f58  mov     rcx, rsi; Block
0x180095f5b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180095f60  test    rdi, rdi
0x180095f63  jz      short loc_180095F6D
0x180095f65  mov     rcx, rdi; Block
0x180095f68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180095f6d  cmp     dword ptr [rbp+57h+arg_18], 0
0x180095f71  jz      short loc_180095F9A
0x180095f73  mov     rcx, [rbp+57h+hKey]; hKey
0x180095f77  test    rcx, rcx
0x180095f7a  jz      short loc_180095F9A
0x180095f7c  call    cs:__imp_NCryptIsKeyHandle
0x180095f82  mov     rcx, [rbp+57h+hKey]; hProv
0x180095f86  test    eax, eax
0x180095f88  jz      short loc_180095F92
0x180095f8a  call    cs:__imp_NCryptFreeObject
0x180095f90  jmp     short loc_180095F9A
0x180095f92  xor     edx, edx; dwFlags
0x180095f94  call    cs:__imp_CryptReleaseContext
0x180095f9a  mov     eax, ebx
0x180095f9c  mov     rbx, [rsp+0B0h+arg_8]
0x180095fa4  add     rsp, 90h
0x180095fab  pop     r15
0x180095fad  pop     r14
0x180095faf  pop     rdi
0x180095fb0  pop     rsi
0x180095fb1  pop     rbp
0x180095fb2  retn
```
