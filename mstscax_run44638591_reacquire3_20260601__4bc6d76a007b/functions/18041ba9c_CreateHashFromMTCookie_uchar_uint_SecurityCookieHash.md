# CreateHashFromMTCookie(uchar *,uint,SecurityCookieHash *)

- ea: `0x18041ba9c`
- end: `0x18041bfc6`
- name: `?CreateHashFromMTCookie@@YAJPEAEIPEAUSecurityCookieHash@@@Z`
- size: `1322`
- prototype: `__int64 __fastcall(BYTE *pbData, unsigned int, struct SecurityCookieHash *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180157e50`

## callees

- `0x1800011f4`
- `0x180001e8c`
- `0x180082910`
- `0x180082ad8`
- `0x18041ba9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18041bba1`
- `KERNEL32!GetLastError` at `0x18041bc47`
- `KERNEL32!GetLastError` at `0x18041bce3`
- `KERNEL32!GetLastError` at `0x18041bd98`
- `KERNEL32!GetLastError` at `0x18041bec0`
- `KERNEL32!GetLastError` at `0x18041bba1`
- `KERNEL32!GetLastError` at `0x18041bc47`
- `KERNEL32!GetLastError` at `0x18041bce3`
- `KERNEL32!GetLastError` at `0x18041bd98`
- `KERNEL32!GetLastError` at `0x18041bec0`
- `ADVAPI32!CryptAcquireContextW` at `0x18041bb93`
- `ADVAPI32!CryptAcquireContextW` at `0x18041bb93`
- `ADVAPI32!CryptCreateHash` at `0x18041bc39`
- `ADVAPI32!CryptCreateHash` at `0x18041bc39`
- `ADVAPI32!CryptReleaseContext` at `0x18041bf6d`
- `ADVAPI32!CryptReleaseContext` at `0x18041bf6d`
- `ADVAPI32!CryptHashData` at `0x18041bcd5`
- `ADVAPI32!CryptHashData` at `0x18041bcd5`
- `ADVAPI32!CryptGetHashParam` at `0x18041bd8a`
- `ADVAPI32!CryptGetHashParam` at `0x18041beb2`
- `ADVAPI32!CryptGetHashParam` at `0x18041bd8a`
- `ADVAPI32!CryptGetHashParam` at `0x18041beb2`
- `ADVAPI32!CryptDestroyHash` at `0x18041bf5c`
- `ADVAPI32!CryptDestroyHash` at `0x18041bf5c`

## string_xrefs

- `0x18041bad0`: `Entering CreateHashFromMTCookie`
- `0x18041bc8f`: `Cryptographic error calling CryptCreateHash`
- `0x18041bb13`: `CreateHashFromMTCookie`
- `0x18041bbc5`: `CreateHashFromMTCookie`
- `0x18041bc6b`: `CreateHashFromMTCookie`
- `0x18041bd07`: `CreateHashFromMTCookie`
- `0x18041bdbc`: `CreateHashFromMTCookie`
- `0x18041be3f`: `CreateHashFromMTCookie`
- `0x18041beed`: `CreateHashFromMTCookie`
- `0x18041bb37`: `CreateHashFromMTCookie error invalid parameter`
- `0x18041bf81`: `Exiting CreateHashFromMTCookie`

## pseudocode

```c
__int64 __fastcall CreateHashFromMTCookie(BYTE *pbData, DWORD a2, BYTE *a3, int a4)
{
  unsigned int v6; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  int v12; // ecx
  signed int v13; // eax
  char *v14; // rdx
  const char **v15; // rax
  signed int LastError; // eax
  int v17; // ecx
  const char **v19; // [rsp+30h] [rbp-19h]
  const char **v20; // [rsp+40h] [rbp-9h]
  const char **v21; // [rsp+40h] [rbp-9h]
  DWORD pdwDataLen; // [rsp+50h] [rbp+7h] BYREF
  const char *v23; // [rsp+58h] [rbp+Fh] BYREF
  HCRYPTHASH phHash; // [rsp+60h] [rbp+17h] BYREF
  HCRYPTPROV phProv; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v26; // [rsp+70h] [rbp+27h] BYREF
  const char *v27; // [rsp+78h] [rbp+2Fh] BYREF
  _QWORD v28[4]; // [rsp+80h] [rbp+37h] BYREF
  DWORD pbDataa; // [rsp+B8h] [rbp+6Fh] BYREF
  const char *v30; // [rsp+C0h] [rbp+77h] BYREF
  int v31; // [rsp+C8h] [rbp+7Fh] BYREF

  pbDataa = a2;
  phProv = 0;
  phHash = 0;
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v30 = "Entering CreateHashFromMTCookie";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_1808B5850,
      (unsigned int)word_18087F8BA,
      0,
      a4,
      (__int64)&v30);
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    if ( (unsigned int)dword_1808B5850 <= 2 )
      goto LABEL_36;
    LODWORD(v30) = 2271;
    v23 = "CreateHashFromMTCookie";
    v7 = &word_18087F3C6;
    v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
    v27 = "CreateHashFromMTCookie error invalid parameter";
    v20 = &v23;
    v8 = &v27;
    goto LABEL_6;
  }
  if ( CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
  {
    if ( CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
    {
      if ( CryptHashData(phHash, pbData, 0x10u, 0) )
      {
        pbDataa = 0;
        pdwDataLen = 4;
        if ( CryptGetHashParam(phHash, 4u, (BYTE *)&pbDataa, &pdwDataLen, 0) )
        {
          if ( pbDataa == 32 )
          {
            v6 = 0;
            if ( CryptGetHashParam(phHash, 2u, a3 + 20, &pbDataa, 0) )
              goto LABEL_36;
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_36;
            v14 = byte_18087EB6D;
            LODWORD(v30) = pbDataa;
            v28[0] = "CreateHashFromMTCookie";
            v27 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
            v26 = "Cryptographic error calling CryptGetHashParam for hash data";
            v21 = (const char **)v28;
            v19 = &v27;
            v15 = &v26;
            v31 = 2363;
          }
          else
          {
            v6 = -2147467259;
            if ( (unsigned int)dword_1808B5850 <= 2 )
              goto LABEL_36;
            v14 = byte_18087F8D9;
            LODWORD(v30) = pbDataa;
            v27 = "CreateHashFromMTCookie";
            v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
            v28[0] = "Cryptographic error calling CryptGetHashParam returning hash size other than 32 as expected for SHA-256";
            v21 = &v27;
            v19 = &v26;
            v15 = (const char **)v28;
            v31 = 2347;
          }
          LODWORD(v23) = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v12,
            (_DWORD)v14,
            (_DWORD)a3,
            a4,
            (__int64)v15,
            (__int64)&v23,
            (__int64)v19,
            (__int64)&v31,
            (__int64)v21,
            (__int64)&v30);
          goto LABEL_36;
        }
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          LODWORD(v30) = 2338;
          v27 = "CreateHashFromMTCookie";
          v7 = (__int16 *)byte_18087F579;
          v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
          v23 = "Cryptographic error calling CryptGetHashParam for hash size";
          v20 = &v27;
          v8 = &v23;
          goto LABEL_6;
        }
      }
      else
      {
        v11 = GetLastError();
        v6 = v11;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          LODWORD(v30) = 2320;
          v27 = "CreateHashFromMTCookie";
          v7 = &word_18087F5E6;
          v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
          v23 = "Cryptographic error calling CryptHashData";
          v20 = &v27;
          v8 = &v23;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v10 = GetLastError();
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        LODWORD(v30) = 2305;
        v27 = "CreateHashFromMTCookie";
        v7 = (__int16 *)qword_18087EBE8;
        v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
        v23 = "Cryptographic error calling CryptCreateHash";
        v20 = &v27;
        v8 = &v23;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v9 = GetLastError();
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      LODWORD(v30) = 2289;
      v27 = "CreateHashFromMTCookie";
      v7 = &word_18087F0D6;
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v23 = "Cryptographic error calling CryptAcquireContext";
      v20 = &v27;
      v8 = &v23;
LABEL_6:
      v31 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)pbData,
        (_DWORD)v7,
        (_DWORD)a3,
        a4,
        (__int64)v8,
        (__int64)&v31,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)v20);
    }
  }
LABEL_36:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v17 = *((_DWORD *)a3 + 5);
    v28[0] = "Exiting CreateHashFromMTCookie";
    LODWORD(v30) = v17;
    v31 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&dword_18087EE44,
      (_DWORD)a3,
      a4,
      (__int64)v28,
      (__int64)&v31,
      (__int64)&v30);
  }
  return v6;
}

```

## disassembly

```asm
0x18041ba9c  mov     [rsp-8+pbData], edx
0x18041baa0  push    rbp
0x18041baa1  push    rbx
0x18041baa2  push    rdi
0x18041baa3  lea     rbp, [rsp-47h]
0x18041baa8  sub     rsp, 90h
0x18041baaf  mov     eax, cs:dword_1808B5850
0x18041bab5  mov     rdi, r8
0x18041bab8  mov     [rbp+57h+phProv], 0
0x18041bac0  mov     rbx, rcx
0x18041bac3  mov     [rbp+57h+phHash], 0
0x18041bacb  cmp     eax, 4
0x18041bace  jbe     short loc_18041BAFA
0x18041bad0  lea     rax, aEnteringCreate; "Entering CreateHashFromMTCookie"
0x18041bad7  xor     r8d, r8d
0x18041bada  mov     [rbp+57h+arg_10], rax
0x18041bade  lea     rdx, word_18087F8BA
0x18041bae5  lea     rax, [rbp+57h+arg_10]
0x18041bae9  lea     rcx, dword_1808B5850
0x18041baf0  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x18041baf5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18041bafa  test    rdi, rdi
0x18041bafd  jnz     short loc_18041BB7C
0x18041baff  mov     eax, cs:dword_1808B5850
0x18041bb05  mov     ebx, 80070057h
0x18041bb0a  cmp     eax, 2
0x18041bb0d  jbe     loc_18041BF53
0x18041bb13  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18041bb1a  mov     dword ptr [rbp+57h+arg_10], 8DFh
0x18041bb21  mov     [rbp+57h+var_48], rax
0x18041bb25  lea     rdx, word_18087F3C6
0x18041bb2c  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18041bb33  mov     [rbp+57h+var_30], rax
0x18041bb37  lea     rax, aCreatehashfrom_0; "CreateHashFromMTCookie error invalid pa"...
0x18041bb3e  mov     [rbp+57h+var_28], rax
0x18041bb42  lea     rax, [rbp+57h+var_48]
0x18041bb46  mov     [rsp+0A0h+var_60], rax
0x18041bb4b  lea     rax, [rbp+57h+arg_10]
0x18041bb4f  mov     [rsp+0A0h+var_68], rax
0x18041bb54  lea     rax, [rbp+57h+var_30]
0x18041bb58  mov     [rsp+0A0h+var_70], rax
0x18041bb5d  lea     rax, [rbp+57h+arg_18]
0x18041bb61  mov     [rsp+0A0h+var_78], rax
0x18041bb66  lea     rax, [rbp+57h+var_28]
0x18041bb6a  mov     [rbp+57h+arg_18], ebx
0x18041bb6d  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x18041bb72  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18041bb77  jmp     loc_18041BF53
0x18041bb7c  mov     r9d, 18h; dwProvType
0x18041bb82  mov     [rsp+0A0h+dwFlags], 0F0000000h; dwFlags
0x18041bb8a  xor     r8d, r8d; szProvider
0x18041bb8d  lea     rcx, [rbp+57h+phProv]; phProv
0x18041bb91  xor     edx, edx; szContainer
0x18041bb93  call    cs:__imp_CryptAcquireContextW
0x18041bb99  test    eax, eax
0x18041bb9b  jnz     loc_18041BC21
0x18041bba1  call    cs:__imp_GetLastError
0x18041bba7  mov     ebx, eax
0x18041bba9  test    eax, eax
0x18041bbab  jle     short loc_18041BBB6
0x18041bbad  movzx   ebx, ax
0x18041bbb0  or      ebx, 80070000h
0x18041bbb6  mov     eax, cs:dword_1808B5850
0x18041bbbc  cmp     eax, 2
0x18041bbbf  jbe     loc_18041BF53
0x18041bbc5  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18041bbcc  mov     dword ptr [rbp+57h+arg_10], 8F1h
0x18041bbd3  mov     [rbp+57h+var_28], rax
0x18041bbd7  lea     rdx, word_18087F0D6
0x18041bbde  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18041bbe5  mov     [rbp+57h+var_30], rax
0x18041bbe9  lea     rax, aCryptographicE_0; "Cryptographic error calling CryptAcquir"...
0x18041bbf0  mov     [rbp+57h+var_48], rax
0x18041bbf4  lea     rax, [rbp+57h+var_28]
0x18041bbf8  mov     [rsp+0A0h+var_60], rax
0x18041bbfd  lea     rax, [rbp+57h+arg_10]
0x18041bc01  mov     [rsp+0A0h+var_68], rax
0x18041bc06  lea     rax, [rbp+57h+var_30]
0x18041bc0a  mov     [rsp+0A0h+var_70], rax
0x18041bc0f  lea     rax, [rbp+57h+arg_18]
0x18041bc13  mov     [rsp+0A0h+var_78], rax
0x18041bc18  lea     rax, [rbp+57h+var_48]
0x18041bc1c  jmp     loc_18041BB6A
0x18041bc21  mov     rcx, [rbp+57h+phProv]; hProv
0x18041bc25  lea     rax, [rbp+57h+phHash]
0x18041bc29  xor     r9d, r9d; dwFlags
0x18041bc2c  mov     qword ptr [rsp+0A0h+dwFlags], rax; phHash
0x18041bc31  xor     r8d, r8d; hKey
0x18041bc34  mov     edx, 800Ch; Algid
0x18041bc39  call    cs:__imp_CryptCreateHash
0x18041bc3f  test    eax, eax
0x18041bc41  jnz     loc_18041BCC7
0x18041bc47  call    cs:__imp_GetLastError
0x18041bc4d  mov     ebx, eax
0x18041bc4f  test    eax, eax
0x18041bc51  jle     short loc_18041BC5C
0x18041bc53  movzx   ebx, ax
0x18041bc56  or      ebx, 80070000h
0x18041bc5c  mov     eax, cs:dword_1808B5850
0x18041bc62  cmp     eax, 2
0x18041bc65  jbe     loc_18041BF53
0x18041bc6b  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18041bc72  mov     dword ptr [rbp+57h+arg_10], 901h
0x18041bc79  mov     [rbp+57h+var_28], rax
0x18041bc7d  lea     rdx, qword_18087EBE8
0x18041bc84  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18041bc8b  mov     [rbp+57h+var_30], rax
0x18041bc8f  lea     rax, aCryptographicE_4; "Cryptographic error calling CryptCreate"...
0x18041bc96  mov     [rbp+57h+var_48], rax
0x18041bc9a  lea     rax, [rbp+57h+var_28]
0x18041bc9e  mov     [rsp+0A0h+var_60], rax
0x18041bca3  lea     rax, [rbp+57h+arg_10]
0x18041bca7  mov     [rsp+0A0h+var_68], rax
0x18041bcac  lea     rax, [rbp+57h+var_30]
0x18041bcb0  mov     [rsp+0A0h+var_70], rax
0x18041bcb5  lea     rax, [rbp+57h+arg_18]
0x18041bcb9  mov     [rsp+0A0h+var_78], rax
0x18041bcbe  lea     rax, [rbp+57h+var_48]
0x18041bcc2  jmp     loc_18041BB6A
0x18041bcc7  mov     rcx, [rbp+57h+phHash]; hHash
0x18041bccb  xor     r9d, r9d; dwFlags
0x18041bcce  mov     rdx, rbx; pbData
0x18041bcd1  lea     r8d, [r9+10h]; dwDataLen
0x18041bcd5  call    cs:__imp_CryptHashData
0x18041bcdb  test    eax, eax
0x18041bcdd  jnz     loc_18041BD63
0x18041bce3  call    cs:__imp_GetLastError
0x18041bce9  mov     ebx, eax
0x18041bceb  test    eax, eax
0x18041bced  jle     short loc_18041BCF8
0x18041bcef  movzx   ebx, ax
0x18041bcf2  or      ebx, 80070000h
0x18041bcf8  mov     eax, cs:dword_1808B5850
0x18041bcfe  cmp     eax, 2
0x18041bd01  jbe     loc_18041BF53
0x18041bd07  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18041bd0e  mov     dword ptr [rbp+57h+arg_10], 910h
0x18041bd15  mov     [rbp+57h+var_28], rax
0x18041bd19  lea     rdx, word_18087F5E6
0x18041bd20  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18041bd27  mov     [rbp+57h+var_30], rax
0x18041bd2b  lea     rax, aCryptographicE_1; "Cryptographic error calling CryptHashDa"...
0x18041bd32  mov     [rbp+57h+var_48], rax
0x18041bd36  lea     rax, [rbp+57h+var_28]
0x18041bd3a  mov     [rsp+0A0h+var_60], rax
0x18041bd3f  lea     rax, [rbp+57h+arg_10]
0x18041bd43  mov     [rsp+0A0h+var_68], rax
0x18041bd48  lea     rax, [rbp+57h+var_30]
0x18041bd4c  mov     [rsp+0A0h+var_70], rax
0x18041bd51  lea     rax, [rbp+57h+arg_18]
0x18041bd55  mov     [rsp+0A0h+var_78], rax
0x18041bd5a  lea     rax, [rbp+57h+var_48]
0x18041bd5e  jmp     loc_18041BB6A
0x18041bd63  mov     rcx, [rbp+57h+phHash]; hHash
0x18041bd67  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18041bd6b  lea     r8, [rbp+57h+pbData]; pbData
0x18041bd6f  mov     [rbp+57h+pbData], 0
0x18041bd76  mov     edx, 4; dwParam
0x18041bd7b  mov     [rbp+57h+pdwDataLen], 4
0x18041bd82  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x18041bd8a  call    cs:__imp_CryptGetHashParam
0x18041bd90  test    eax, eax
0x18041bd92  jnz     loc_18041BE18
0x18041bd98  call    cs:__imp_GetLastError
0x18041bd9e  mov     ebx, eax
0x18041bda0  test    eax, eax
0x18041bda2  jle     short loc_18041BDAD
0x18041bda4  movzx   ebx, ax
0x18041bda7  or      ebx, 80070000h
0x18041bdad  mov     eax, cs:dword_1808B5850
0x18041bdb3  cmp     eax, 2
0x18041bdb6  jbe     loc_18041BF53
0x18041bdbc  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18041bdc3  mov     dword ptr [rbp+57h+arg_10], 922h
0x18041bdca  mov     [rbp+57h+var_28], rax
0x18041bdce  lea     rdx, byte_18087F579
0x18041bdd5  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18041bddc  mov     [rbp+57h+var_30], rax
0x18041bde0  lea     rax, aCryptographicE; "Cryptographic error calling CryptGetHas"...
0x18041bde7  mov     [rbp+57h+var_48], rax
0x18041bdeb  lea     rax, [rbp+57h+var_28]
0x18041bdef  mov     [rsp+0A0h+var_60], rax
0x18041bdf4  lea     rax, [rbp+57h+arg_10]
0x18041bdf8  mov     [rsp+0A0h+var_68], rax
0x18041bdfd  lea     rax, [rbp+57h+var_30]
0x18041be01  mov     [rsp+0A0h+var_70], rax
0x18041be06  lea     rax, [rbp+57h+arg_18]
0x18041be0a  mov     [rsp+0A0h+var_78], rax
0x18041be0f  lea     rax, [rbp+57h+var_48]
0x18041be13  jmp     loc_18041BB6A
0x18041be18  cmp     [rbp+57h+pbData], 20h ; ' '
0x18041be1c  jz      short loc_18041BE9D
0x18041be1e  mov     eax, cs:dword_1808B5850
0x18041be24  mov     ebx, 80004005h
0x18041be29  cmp     eax, 2
0x18041be2c  jbe     loc_18041BF53
0x18041be32  mov     eax, [rbp+57h+pbData]
0x18041be35  lea     rdx, byte_18087F8D9
0x18041be3c  mov     dword ptr [rbp+57h+arg_10], eax
0x18041be3f  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18041be46  mov     [rbp+57h+var_28], rax
0x18041be4a  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18041be51  mov     [rbp+57h+var_30], rax
0x18041be55  lea     rax, aCryptographicE_2; "Cryptographic error calling CryptGetHas"...
0x18041be5c  mov     [rbp+57h+var_20], rax
0x18041be60  lea     rax, [rbp+57h+arg_10]
0x18041be64  mov     [rsp+0A0h+var_58], rax
0x18041be69  lea     rax, [rbp+57h+var_28]
0x18041be6d  mov     [rsp+0A0h+var_60], rax
0x18041be72  lea     rax, [rbp+57h+arg_18]
0x18041be76  mov     [rsp+0A0h+var_68], rax
0x18041be7b  lea     rax, [rbp+57h+var_30]
0x18041be7f  mov     [rsp+0A0h+var_70], rax
0x18041be84  lea     rax, [rbp+57h+var_48]
0x18041be88  mov     [rsp+0A0h+var_78], rax
0x18041be8d  lea     rax, [rbp+57h+var_20]
0x18041be91  mov     [rbp+57h+arg_18], 92Bh
0x18041be98  jmp     loc_18041BF46
0x18041be9d  mov     rcx, [rbp+57h+phHash]; hHash
0x18041bea1  lea     r8, [rdi+14h]; pbData
0x18041bea5  xor     ebx, ebx
0x18041bea7  lea     r9, [rbp+57h+pbData]; pdwDataLen
0x18041beab  mov     [rsp+0A0h+dwFlags], ebx; dwFlags
0x18041beaf  lea     edx, [rbx+2]; dwParam
0x18041beb2  call    cs:__imp_CryptGetHashParam
0x18041beb8  test    eax, eax
0x18041beba  jnz     loc_18041BF53
0x18041bec0  call    cs:__imp_GetLastError
0x18041bec6  mov     ebx, eax
0x18041bec8  test    eax, eax
0x18041beca  jle     short loc_18041BED5
0x18041becc  movzx   ebx, ax
0x18041becf  or      ebx, 80070000h
0x18041bed5  mov     eax, cs:dword_1808B5850
0x18041bedb  cmp     eax, 2
0x18041bede  jbe     short loc_18041BF53
0x18041bee0  mov     eax, [rbp+57h+pbData]
0x18041bee3  lea     rdx, byte_18087EB6D
0x18041beea  mov     dword ptr [rbp+57h+arg_10], eax
0x18041beed  lea     rax, aCreatehashfrom; "CreateHashFromMTCookie"
0x18041bef4  mov     [rbp+57h+var_20], rax
0x18041bef8  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18041beff  mov     [rbp+57h+var_28], rax
0x18041bf03  lea     rax, aCryptographicE_5; "Cryptographic error calling CryptGetHas"...
0x18041bf0a  mov     [rbp+57h+var_30], rax
0x18041bf0e  lea     rax, [rbp+57h+arg_10]
0x18041bf12  mov     [rsp+0A0h+var_58], rax
0x18041bf17  lea     rax, [rbp+57h+var_20]
0x18041bf1b  mov     [rsp+0A0h+var_60], rax
0x18041bf20  lea     rax, [rbp+57h+arg_18]
0x18041bf24  mov     [rsp+0A0h+var_68], rax
0x18041bf29  lea     rax, [rbp+57h+var_28]
0x18041bf2d  mov     [rsp+0A0h+var_70], rax
0x18041bf32  lea     rax, [rbp+57h+var_48]
0x18041bf36  mov     [rsp+0A0h+var_78], rax
0x18041bf3b  lea     rax, [rbp+57h+var_30]
0x18041bf3f  mov     [rbp+57h+arg_18], 93Bh
0x18041bf46  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x18041bf4b  mov     dword ptr [rbp+57h+var_48], ebx
0x18041bf4e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18041bf53  mov     rcx, [rbp+57h+phHash]; hHash
0x18041bf57  test    rcx, rcx
0x18041bf5a  jz      short loc_18041BF62
0x18041bf5c  call    cs:__imp_CryptDestroyHash
0x18041bf62  mov     rcx, [rbp+57h+phProv]; hProv
0x18041bf66  test    rcx, rcx
0x18041bf69  jz      short loc_18041BF73
0x18041bf6b  xor     edx, edx; dwFlags
0x18041bf6d  call    cs:__imp_CryptReleaseContext
0x18041bf73  mov     eax, cs:dword_1808B5850
0x18041bf79  cmp     eax, 4
0x18041bf7c  jbe     short loc_18041BFB9
0x18041bf7e  mov     ecx, [rdi+14h]
0x18041bf81  lea     rax, aExitingCreateh; "Exiting CreateHashFromMTCookie"
0x18041bf88  mov     [rbp+57h+var_20], rax
0x18041bf8c  lea     rdx, dword_18087EE44
0x18041bf93  lea     rax, [rbp+57h+arg_10]
0x18041bf97  mov     dword ptr [rbp+57h+arg_10], ecx
0x18041bf9a  mov     [rsp+0A0h+var_70], rax
0x18041bf9f  lea     rax, [rbp+57h+arg_18]
0x18041bfa3  mov     [rsp+0A0h+var_78], rax
0x18041bfa8  lea     rax, [rbp+57h+var_20]
0x18041bfac  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x18041bfb1  mov     [rbp+57h+arg_18], ebx
0x18041bfb4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18041bfb9  mov     eax, ebx
0x18041bfbb  add     rsp, 90h
0x18041bfc2  pop     rdi
0x18041bfc3  pop     rbx
0x18041bfc4  pop     rbp
0x18041bfc5  retn
```
