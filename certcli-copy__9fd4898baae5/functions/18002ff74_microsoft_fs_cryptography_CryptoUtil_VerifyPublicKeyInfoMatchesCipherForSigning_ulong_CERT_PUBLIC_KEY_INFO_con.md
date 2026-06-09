# microsoft::fs::cryptography::CryptoUtil::VerifyPublicKeyInfoMatchesCipherForSigning(ulong,_CERT_PUBLIC_KEY_INFO const *,microsoft::fs::cryptography::ICipher *,long *,ushort const *,uint,microsoft::fs::common::FsException *)

- ea: `0x18002ff74`
- end: `0x1800306b9`
- name: `?VerifyPublicKeyInfoMatchesCipherForSigning@CryptoUtil@cryptography@fs@microsoft@@SAXKPEBU_CERT_PUBLIC_KEY_INFO@@PEAVICipher@234@PEAJPEBGIPEAVFsException@common@34@@Z`
- size: `1861`
- prototype: `static void(unsigned int, const struct _CERT_PUBLIC_KEY_INFO *, struct microsoft::fs::cryptography::ICipher *, int *, const unsigned __int16 *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001b1dc`

## callees

- `0x180001514`
- `0x180001798`
- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x18002e604`
- `0x18002f044`
- `0x18002ff74`
- `0x1800306c0`
- `0x180030788`
- `0x1800307bc`
- `0x180030888`
- `0x180030f40`
- `0x1800310fc`
- `0x180031524`
- `0x180031598`
- `0x180031c48`
- `0x180032250`
- `0x18003373c`
- `0x180035284`
- `0x1800391cc`
- `0x18003953c`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18003047c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030631`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030654`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003047c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030631`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180030654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003009c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003009c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030255`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030627`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180030627`
- `ncrypt!NCryptIsKeyHandle` at `0x180030066`
- `ncrypt!NCryptIsKeyHandle` at `0x180030066`

## string_xrefs

- `0x18002ffe0`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x1800300ba`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x180030141`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x1800301fe`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x180030273`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x1800303ca`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x180030426`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall microsoft::fs::cryptography::CryptoUtil::VerifyPublicKeyInfoMatchesCipherForSigning(
        __int64 a1,
        struct _CERT_PUBLIC_KEY_INFO *a2,
        struct microsoft::fs::cryptography::ICipher *a3,
        int *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        struct microsoft::fs::common::FsException *a7)
{
  int *v7; // r14
  struct microsoft::fs::cryptography::ICipher *v8; // rsi
  bool IsPaddingRequired; // r13
  NCRYPT_KEY_HANDLE v11; // rax
  unsigned int v12; // ecx
  void *v13; // r9
  DWORD LastError; // eax
  int v15; // eax
  unsigned __int16 *v16; // rax
  void *v17; // rdx
  unsigned __int8 *v18; // r9
  __int64 v19; // rax
  int HashList; // eax
  const unsigned __int16 *v21; // rcx
  struct microsoft::fs::common::FsException *v22; // r8
  struct csp_hash_tag *v23; // rbx
  LPCWSTR pwszName; // r15
  struct microsoft::fs::cryptography::IHash *Hash; // rax
  unsigned __int64 v26; // rax
  unsigned int v27; // edx
  DWORD v28; // eax
  int v29; // eax
  unsigned __int16 *v30; // r15
  unsigned __int64 v31; // rbx
  unsigned __int64 v32; // rax
  __int64 v33; // rax
  void *v34; // rax
  unsigned __int16 *v35; // r12
  int v36; // eax
  unsigned int v37; // r8d
  const struct _CRYPT_OID_INFO *v38; // rax
  struct microsoft::fs::common::FsException *v39; // r9
  struct microsoft::fs::cryptography::IHash *v40; // rax
  void *v41; // rax
  char v42; // cl
  unsigned int v43; // edx
  _BYTE *v44; // r12
  unsigned __int64 v45; // r13
  void *v46; // rax
  unsigned __int16 *v47; // r15
  unsigned int v48; // ecx
  const struct microsoft::fs::common::FsException *v49; // rdi
  unsigned int v50; // r8d
  const wchar_t *v51; // rsi
  const struct _CRYPT_OID_INFO *OIDInfo; // rax
  const struct _CRYPT_OID_INFO *v53; // rbx
  const wchar_t *v54; // rax
  int v55; // r9d
  int v56; // r8d
  const unsigned __int16 *v57; // rcx
  struct microsoft::fs::common::FsException *v58; // r8
  struct microsoft::fs::cryptography::IHash *v59; // rax
  const struct microsoft::fs::common::FsException *v60; // rbx
  int v61; // eax
  int v62; // r8d
  microsoft::fs::common::FsException *v63; // rbx
  const struct microsoft::fs::common::FsException *v64; // rax
  bool v65; // [rsp+20h] [rbp-308h]
  unsigned int v66; // [rsp+20h] [rbp-308h]
  bool v67; // [rsp+28h] [rbp-300h]
  bool v68; // [rsp+30h] [rbp-2F8h]
  unsigned int v69; // [rsp+50h] [rbp-2D8h] BYREF
  unsigned int v70; // [rsp+54h] [rbp-2D4h] BYREF
  unsigned int v71[2]; // [rsp+58h] [rbp-2D0h] BYREF
  unsigned int v72; // [rsp+60h] [rbp-2C8h] BYREF
  struct csp_hash_tag *v73; // [rsp+68h] [rbp-2C0h] BYREF
  int v74; // [rsp+70h] [rbp-2B8h] BYREF
  wchar_t *v75; // [rsp+78h] [rbp-2B0h]
  __int64 v76; // [rsp+80h] [rbp-2A8h] BYREF
  BCRYPT_KEY_HANDLE v77; // [rsp+88h] [rbp-2A0h] BYREF
  unsigned __int64 v78; // [rsp+90h] [rbp-298h] BYREF
  __int64 v79; // [rsp+98h] [rbp-290h] BYREF
  int v80; // [rsp+A0h] [rbp-288h] BYREF
  unsigned __int16 *v81; // [rsp+A8h] [rbp-280h] BYREF
  _BYTE *v82; // [rsp+B0h] [rbp-278h] BYREF
  LPCWSTR v83; // [rsp+B8h] [rbp-270h] BYREF
  const microsoft::fs::common::FsException *v84; // [rsp+C0h] [rbp-268h] BYREF
  const microsoft::fs::common::FsException *v85; // [rsp+C8h] [rbp-260h] BYREF
  const microsoft::fs::common::FsException *v86; // [rsp+D0h] [rbp-258h] BYREF
  _QWORD v87[6]; // [rsp+D8h] [rbp-250h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+108h] [rbp-220h] BYREF
  _BYTE v89[48]; // [rsp+138h] [rbp-1F0h] BYREF
  _BYTE v90[48]; // [rsp+168h] [rbp-1C0h] BYREF
  _BYTE v91[48]; // [rsp+198h] [rbp-190h] BYREF
  _BYTE v92[48]; // [rsp+1C8h] [rbp-160h] BYREF
  _BYTE v93[48]; // [rsp+1F8h] [rbp-130h] BYREF
  _BYTE v94[48]; // [rsp+228h] [rbp-100h] BYREF
  _BYTE v95[48]; // [rsp+258h] [rbp-D0h] BYREF
  _BYTE v96[48]; // [rsp+288h] [rbp-A0h] BYREF
  _BYTE v97[112]; // [rsp+2B8h] [rbp-70h] BYREF
  int v98; // [rsp+330h] [rbp+8h]

  v7 = a4;
  v8 = a3;
  v77 = 0;
  v78 = 0;
  try
  {
    if ( a7 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a7 + 8LL))(a7);
    if ( !v8 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
        0x4F6u,
        L"pCipher",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v79 = 0;
    v76 = 0;
    v82 = 0;
    v73 = 0;
    v69 = 0;
    v74 = 0;
    v71[0] = 0;
    v83 = 0;
    v75 = 0;
    v71[1] = 0;
    IsPaddingRequired = microsoft::fs::cryptography::CryptoUtil::IsPaddingRequired(v8);
    v11 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)v8 + 80LL))(v8);
    if ( NCryptIsKeyHandle(v11) )
    {
      if ( a2 )
      {
        if ( !(unsigned int)fsCryptImportPublicKeyInfoEx2(v12, a2, 0x80000000, v13, &v77) )
        {
          LastError = GetLastError();
          v15 = HR_FROM_WIN32(LastError);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v89,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
            0x516u,
            L"CryptImportPublicKeyInfoEx2( nCertEncodingType, const_cast<CERT_PUBLIC_KEY_INFO*>(pcpki), CRYPT_OID_INFO_PUB"
             "KEY_SIGN_KEY_FLAG, 0, &hBCryptKey)",
            v15);
          throw (microsoft::fs::common::FsException *)v89;
        }
        v16 = (unsigned __int16 *)operator new(0x258u);
        a5 = v16;
        if ( v16 )
          v19 = microsoft::fs::cryptography::CngBCryptCipher::CngBCryptCipher(
                  (microsoft::fs::cryptography::CngBCryptCipher *)v16,
                  v17,
                  v77,
                  v18,
                  v66,
                  v67,
                  v68);
        else
          v19 = 0;
        microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v79, v19);
      }
      HashList = GetHashList(0, 0, &v73);
      if ( HashList < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v90,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x521u,
          L"GetHashList(0, NULL, &pHashList)",
          HashList);
        throw (microsoft::fs::common::FsException *)v90;
      }
      v23 = v73;
      pwszName = (LPCWSTR)*((_QWORD *)v73 + 1);
      v75 = (wchar_t *)pwszName;
      try
      {
        Hash = microsoft::fs::cryptography::CngCryptoFactory::CreateHash(v21, pwszName, v22);
        microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v76, Hash);
      }
      catch ( const microsoft::fs::common::FsException *v84 )
      {
        v49 = v84;
        if ( (*(unsigned int (__fastcall **)(const microsoft::fs::common::FsException *))(*(_QWORD *)v84 + 40LL))(v84) != -1073741637 )
        {
          microsoft::fs::common::FsException::FsException((microsoft::fs::common::FsException *)v91, v49);
          throw (microsoft::fs::common::FsException *)v91;
        }
        v51 = v75;
        OIDInfo = fsCryptFindOIDInfo(2u, v75, v50);
        v53 = OIDInfo;
        if ( OIDInfo && OIDInfo->cbSize >= 0x38 && *(_QWORD *)&OIDInfo[1].cbSize )
        {
          v54 = v51;
          do
          {
            v55 = *(const wchar_t *)((char *)v54 + *(_QWORD *)&v53[1].cbSize - (_QWORD)v51);
            v56 = *v54 - v55;
            if ( v56 )
              break;
            ++v54;
          }
          while ( v55 );
          if ( v56 )
          {
            if ( !_wcsicmp(v51, *(const wchar_t **)&v53[1].cbSize) )
            {
              v75 = *(wchar_t **)&v53[1].cbSize;
              v59 = microsoft::fs::cryptography::CngCryptoFactory::CreateHash(v57, v75, v58);
              microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v76, v59);
              v7 = a4;
              v8 = a3;
              v23 = v73;
              pwszName = v75;
              goto LABEL_31;
            }
          }
        }
        microsoft::fs::common::FsException::FsException((microsoft::fs::common::FsException *)v92, v49);
        throw (microsoft::fs::common::FsException *)v92;
      }
    }
    else
    {
      v81 = 0;
      v72 = 0;
      v80 = 4;
      if ( !(*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)v8 + 112LL))(v8) )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v93,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x557u,
          L"pCipher->GetProviderHandle()",
          -2147024809);
        throw (microsoft::fs::common::FsException *)v93;
      }
      if ( a2 )
      {
        v26 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)v8 + 112LL))(v8);
        if ( !(unsigned int)fsCryptImportPublicKeyInfo(v26, v27, a2, &v78) )
        {
          v28 = GetLastError();
          v29 = HR_FROM_WIN32(v28);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v94,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
            0x55Eu,
            L"CryptImportPublicKeyInfo( (HCRYPTPROV)pCipher->GetProviderHandle(), nCertEncodingType, const_cast<CERT_PUBLI"
             "C_KEY_INFO*>(pcpki), &hCapiKey)",
            v29);
          throw (microsoft::fs::common::FsException *)v94;
        }
        v30 = (unsigned __int16 *)operator new(0x38u);
        a5 = v30;
        if ( v30 )
        {
          v31 = v78;
          v32 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)v8 + 112LL))(v8);
          v33 = microsoft::fs::cryptography::CapiCipher::CapiCipher(
                  (microsoft::fs::cryptography::CapiCipher *)v30,
                  v32,
                  v31,
                  2u,
                  v65,
                  0);
        }
        else
        {
          v33 = 0;
        }
        microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v79, v33);
      }
      try
      {
        (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, const wchar_t *, _QWORD, unsigned int *, _DWORD))(*(_QWORD *)v8 + 16LL))(
          v8,
          L"PROVIDER_NAME",
          0,
          v71,
          0);
      }
      catch ( const microsoft::fs::common::FsException *v85 )
      {
        v60 = v85;
        (*(void (__fastcall **)(const microsoft::fs::common::FsException *))(*(_QWORD *)v85 + 40LL))(v85);
        v61 = HR_FROM_WIN32(0x7Au);
        if ( v61 != v62 )
        {
          microsoft::fs::common::FsException::FsException((microsoft::fs::common::FsException *)v95, v60);
          throw (microsoft::fs::common::FsException *)v95;
        }
        v7 = a4;
        v8 = a3;
      }
      v34 = operator new[](v71[0]);
      microsoft::fs::common::auto_array<unsigned char>::assign(&v81, v34);
      v35 = v81;
      (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, const wchar_t *, unsigned __int16 *, unsigned int *, _DWORD))(*(_QWORD *)v8 + 16LL))(
        v8,
        L"PROVIDER_NAME",
        v81,
        v71,
        0);
      (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, const wchar_t *, unsigned int *, int *, _DWORD))(*(_QWORD *)v8 + 16LL))(
        v8,
        L"PROVIDER_TYPE",
        &v72,
        &v80,
        0);
      v36 = GetHashList(v72, v35, &v73);
      if ( v36 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v96,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x587u,
          L"GetHashList(dwProvType, reinterpret_cast<WCHAR*>(pbProviderName.get()), &pHashList)",
          v36);
        throw (microsoft::fs::common::FsException *)v96;
      }
      v23 = v73;
      v71[1] = *(_DWORD *)v73;
      v38 = fsCryptFindOIDInfo(3u, &v71[1], v37);
      if ( !v38 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v97,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x595u,
          L"pcOIDInfo",
          -2146889726);
        throw (microsoft::fs::common::FsException *)v97;
      }
      pwszName = v38->pwszName;
      v75 = (wchar_t *)pwszName;
      v40 = microsoft::fs::cryptography::CapiCryptoFactory::CreateHash(v35, v72, v71[1], v39);
      microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v76, v40);
      operator delete[](v35);
      v81 = 0;
    }
LABEL_31:
    v74 = 4;
    (*(void (__fastcall **)(__int64, const wchar_t *, unsigned int *, int *, _DWORD))(*(_QWORD *)v76 + 16LL))(
      v76,
      L"HASH_LENGTH",
      &v69,
      &v74,
      0);
    v41 = operator new[](v69);
    microsoft::fs::common::auto_array<unsigned char>::assign(&v82, v41);
    v42 = 0;
    v43 = 0;
    v44 = v82;
    while ( v43 < v69 )
    {
      v44[v43] = v42;
      v42 = ++v43;
    }
    v83 = pwszName;
    v70 = 0;
    v98 = 2 * IsPaddingRequired;
    v45 = (unsigned __int64)&v83 & -(__int64)IsPaddingRequired;
    (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, _QWORD, unsigned int *, _BYTE *, unsigned int, unsigned __int64, int))(*(_QWORD *)v8 + 144LL))(
      v8,
      0,
      &v70,
      v44,
      v69,
      v45,
      v98);
    v46 = operator new[](v70);
    microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&a5, v46);
    v47 = a5;
    (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, unsigned __int16 *, unsigned int *, _BYTE *, unsigned int, unsigned __int64, int))(*(_QWORD *)v8 + 144LL))(
      v8,
      a5,
      &v70,
      v44,
      v69,
      v45,
      v98);
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _BYTE *, unsigned int, unsigned __int64, int, int *))(*(_QWORD *)v79 + 160LL))(
        v79,
        v47,
        v70,
        v44,
        v69,
        v45,
        v98,
        v7);
      if ( *v7 )
      {
        v48 = 97192992;
LABEL_39:
        CSPrintErrorLineFile(v48, *v7);
      }
    }
    else
    {
      (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, unsigned __int16 *, _QWORD, _BYTE *, unsigned int, unsigned __int64, int, int *))(*(_QWORD *)v8 + 160LL))(
        v8,
        v47,
        v70,
        v44,
        v69,
        v45,
        v98,
        v7);
      if ( *v7 )
      {
        v48 = 97979424;
        goto LABEL_39;
      }
    }
    operator delete[](v47);
    a5 = 0;
    if ( v23 )
    {
      freeHashInfoList(v23);
      v73 = 0;
    }
    operator delete[](v44);
    v82 = 0;
    microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v76);
    microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v79);
  }
  catch ( const microsoft::fs::common::FsException *v86 )
  {
    if ( !a7 )
    {
      if ( v77 )
        fsBCryptDestroyKey(v77);
      if ( v78 )
        fsCryptDestroyKey(v78);
      throw;
    }
    microsoft::fs::common::FsException::assign(a7, v86);
  }
  catch ( ... )
  {
    v63 = a7;
    if ( !a7 )
    {
      if ( v77 )
        fsBCryptDestroyKey(v77);
      if ( v78 )
        fsCryptDestroyKey(v78);
      throw;
    }
    v64 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v87,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
                                                               0x5ECu,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(v63, v64);
    v87[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v87[1]);
    operator delete[]((void *)v87[2]);
    operator delete[]((void *)v87[3]);
    operator delete[]((void *)v87[5]);
  }
  if ( v77 )
    fsBCryptDestroyKey(v77);
  if ( v78 )
    fsCryptDestroyKey(v78);
}

```

## disassembly

```asm
0x18002ff74  mov     rax, rsp
0x18002ff77  mov     [rax+20h], r9
0x18002ff7b  mov     [rax+18h], r8
0x18002ff7f  mov     [rax+8], ecx
0x18002ff82  push    rbx
0x18002ff83  push    rsi
0x18002ff84  push    rdi
0x18002ff85  push    r12
0x18002ff87  push    r13
0x18002ff89  push    r14
0x18002ff8b  push    r15
0x18002ff8d  sub     rsp, 2F0h
0x18002ff94  mov     r14, r9
0x18002ff97  mov     rsi, r8
0x18002ff9a  mov     rbx, rdx
0x18002ff9d  xor     edi, edi
0x18002ff9f  mov     [rax-2A0h], rdi
0x18002ffa6  mov     [rax-298h], rdi
0x18002ffad  mov     rcx, [rsp+328h+arg_30]
0x18002ffb5  test    rcx, rcx
0x18002ffb8  jz      short loc_18002FFC6
0x18002ffba  mov     rax, [rcx]
0x18002ffbd  mov     rax, [rax+8]
0x18002ffc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffc6  test    rsi, rsi
0x18002ffc9  jnz     short loc_180030008
0x18002ffcb  mov     dword ptr [rsp+328h+var_308], 80070057h; int
0x18002ffd3  lea     r9, aPcipher; "pCipher"
0x18002ffda  mov     r8d, 4F6h; unsigned int
0x18002ffe0  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002ffe7  lea     rcx, [rsp+328h+pExceptionObject]; this
0x18002ffef  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002fff4  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002fffb  lea     rcx, [rsp+328h+pExceptionObject]; pExceptionObject
0x180030003  call    _CxxThrowException_0
0x180030008  mov     [rsp+328h+var_290], rdi
0x180030010  mov     [rsp+328h+var_2A8], rdi
0x180030018  mov     [rsp+328h+var_278], rdi
0x180030020  mov     [rsp+328h+var_2C0], rdi
0x180030025  mov     dword ptr [rsp+328h+var_2D8], edi
0x180030029  mov     [rsp+328h+var_2B8], edi
0x18003002d  mov     [rsp+328h+var_2D0], edi
0x180030031  mov     [rsp+328h+var_270], rdi
0x180030039  mov     [rsp+328h+var_2B0], rdi
0x18003003e  mov     [rsp+328h+var_2D0+4], edi
0x180030042  mov     rcx, rsi; struct microsoft::fs::cryptography::ICipher *
0x180030045  call    ?IsPaddingRequired@CryptoUtil@cryptography@fs@microsoft@@SA_NPEAVICipher@234@@Z; microsoft::fs::cryptography::CryptoUtil::IsPaddingRequired(microsoft::fs::cryptography::ICipher *)
0x18003004a  mov     r13b, al
0x18003004d  mov     byte ptr [rsp+328h+arg_0], al
0x180030054  mov     rcx, [rsi]
0x180030057  mov     rax, [rcx+50h]
0x18003005b  mov     rcx, rsi
0x18003005e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030063  mov     rcx, rax; hKey
0x180030066  call    cs:__imp_NCryptIsKeyHandle
0x18003006c  test    eax, eax
0x18003006e  jz      loc_1800301BE
0x180030074  test    rbx, rbx
0x180030077  jz      loc_18003011E
0x18003007d  lea     rax, [rsp+328h+var_2A0]
0x180030085  mov     [rsp+328h+var_308], rax; unsigned int
0x18003008a  mov     r8d, 80000000h; unsigned int
0x180030090  mov     rdx, rbx; struct _CERT_PUBLIC_KEY_INFO *
0x180030093  call    ?fsCryptImportPublicKeyInfoEx2@@YAHKPEAU_CERT_PUBLIC_KEY_INFO@@KPEAXPEAPEAX@Z; fsCryptImportPublicKeyInfoEx2(ulong,_CERT_PUBLIC_KEY_INFO *,ulong,void *,void * *)
0x180030098  test    eax, eax
0x18003009a  jnz     short loc_1800300E2
0x18003009c  call    cs:__imp_GetLastError
0x1800300a2  mov     ecx, eax; unsigned int
0x1800300a4  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x1800300a9  mov     dword ptr [rsp+328h+var_308], eax; int
0x1800300ad  lea     r9, aCryptimportpub_2; "CryptImportPublicKeyInfoEx2( nCertEncod"...
0x1800300b4  mov     r8d, 516h; unsigned int
0x1800300ba  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800300c1  lea     rcx, [rsp+328h+var_1F0]; this
0x1800300c9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800300ce  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800300d5  lea     rcx, [rsp+328h+var_1F0]; pExceptionObject
0x1800300dd  call    _CxxThrowException_0
0x1800300e2  mov     ecx, 258h; Size
0x1800300e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800300ec  mov     [rsp+328h+arg_20], rax
0x1800300f4  test    rax, rax
0x1800300f7  jz      short loc_18003010B
0x1800300f9  mov     r8, [rsp+328h+var_2A0]; void *
0x180030101  mov     rcx, rax; this
0x180030104  call    ??0CngBCryptCipher@cryptography@fs@microsoft@@QEAA@PEAX0PEAEK_N2@Z; microsoft::fs::cryptography::CngBCryptCipher::CngBCryptCipher(void *,void *,uchar *,ulong,bool,bool)
0x180030109  jmp     short loc_18003010E
0x18003010b  mov     rax, rdi
0x18003010e  mov     rdx, rax
0x180030111  lea     rcx, [rsp+328h+var_290]
0x180030119  call    ?reset@?$auto_pointer@VICipher@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAXPEAVICipher@cryptography@34@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(microsoft::fs::cryptography::ICipher *)
0x18003011e  lea     r8, [rsp+328h+var_2C0]; struct csp_hash_tag **
0x180030123  xor     edx, edx; unsigned __int16 *
0x180030125  xor     ecx, ecx; unsigned int
0x180030127  call    ?GetHashList@@YAJKPEAGPEAPEAUcsp_hash_tag@@@Z; GetHashList(ulong,ushort *,csp_hash_tag * *)
0x18003012c  test    eax, eax
0x18003012e  jns     short loc_180030169
0x180030130  mov     dword ptr [rsp+328h+var_308], eax; int
0x180030134  lea     r9, aGethashlist0Nu; "GetHashList(0, NULL, &pHashList)"
0x18003013b  mov     r8d, 521h; unsigned int
0x180030141  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030148  lea     rcx, [rsp+328h+var_1C0]; this
0x180030150  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030155  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003015c  lea     rcx, [rsp+328h+var_1C0]; pExceptionObject
0x180030164  call    _CxxThrowException_0
0x180030169  mov     rbx, [rsp+328h+var_2C0]
0x18003016e  mov     r15, [rbx+8]
0x180030172  mov     [rsp+328h+var_2B0], r15
0x180030177  mov     rdx, r15; unsigned __int16 *
0x18003017a  call    ?CreateHash@CngCryptoFactory@cryptography@fs@microsoft@@SAPEAVIHash@234@PEBG0PEAVFsException@common@34@@Z; microsoft::fs::cryptography::CngCryptoFactory::CreateHash(ushort const *,ushort const *,microsoft::fs::common::FsException *)
0x18003017f  mov     rdx, rax
0x180030182  lea     rcx, [rsp+328h+var_2A8]
0x18003018a  call    ?reset@?$auto_pointer@VICipher@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAXPEAVICipher@cryptography@34@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(microsoft::fs::cryptography::ICipher *)
0x18003018f  nop
0x180030190  jmp     loc_18003048A
0x180030195  xor     edi, edi
0x180030197  mov     r14, [rsp+328h+arg_18]
0x18003019f  mov     rsi, [rsp+328h+arg_10]
0x1800301a7  mov     rbx, [rsp+328h+var_2C0]
0x1800301ac  mov     r15, [rsp+328h+var_2B0]
0x1800301b1  mov     r13b, byte ptr [rsp+328h+arg_0]
0x1800301b9  jmp     loc_18003048A
0x1800301be  mov     [rsp+328h+var_280], rdi
0x1800301c6  mov     [rsp+328h+var_2C8], edi
0x1800301ca  mov     [rsp+328h+var_288], 4
0x1800301d5  mov     rax, [rsi]
0x1800301d8  mov     rcx, rsi
0x1800301db  mov     rax, [rax+70h]
0x1800301df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301e4  test    rax, rax
0x1800301e7  jnz     short loc_180030226
0x1800301e9  mov     dword ptr [rsp+328h+var_308], 80070057h; int
0x1800301f1  lea     r9, aPcipherGetprov; "pCipher->GetProviderHandle()"
0x1800301f8  mov     r8d, 557h; unsigned int
0x1800301fe  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030205  lea     rcx, [rsp+328h+var_130]; this
0x18003020d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030212  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030219  lea     rcx, [rsp+328h+var_130]; pExceptionObject
0x180030221  call    _CxxThrowException_0
0x180030226  test    rbx, rbx
0x180030229  jz      loc_1800302FB
0x18003022f  mov     rax, [rsi]
0x180030232  mov     rcx, rsi
0x180030235  mov     rax, [rax+70h]
0x180030239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003023e  mov     rcx, rax; unsigned __int64
0x180030241  lea     r9, [rsp+328h+var_298]; unsigned __int64 *
0x180030249  mov     r8, rbx; struct _CERT_PUBLIC_KEY_INFO *
0x18003024c  call    ?fsCryptImportPublicKeyInfo@@YAH_KKPEAU_CERT_PUBLIC_KEY_INFO@@PEA_K@Z; fsCryptImportPublicKeyInfo(unsigned __int64,ulong,_CERT_PUBLIC_KEY_INFO *,unsigned __int64 *)
0x180030251  test    eax, eax
0x180030253  jnz     short loc_18003029B
0x180030255  call    cs:__imp_GetLastError
0x18003025b  mov     ecx, eax; unsigned int
0x18003025d  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180030262  mov     dword ptr [rsp+328h+var_308], eax; int
0x180030266  lea     r9, aCryptimportpub_3; "CryptImportPublicKeyInfo( (HCRYPTPROV)p"...
0x18003026d  mov     r8d, 55Eh; unsigned int
0x180030273  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003027a  lea     rcx, [rsp+328h+var_100]; this
0x180030282  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030287  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003028e  lea     rcx, [rsp+328h+var_100]; pExceptionObject
0x180030296  call    _CxxThrowException_0
0x18003029b  mov     ecx, 38h ; '8'; Size
0x1800302a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800302a5  mov     r15, rax
0x1800302a8  mov     [rsp+328h+arg_20], rax
0x1800302b0  test    rax, rax
0x1800302b3  jz      short loc_1800302E7
0x1800302b5  mov     rbx, [rsp+328h+var_298]
0x1800302bd  mov     rcx, [rsi]
0x1800302c0  mov     rax, [rcx+70h]
0x1800302c4  mov     rcx, rsi
0x1800302c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302cc  mov     [rsp+328h+var_300], dil; bool
0x1800302d1  mov     r9d, 2; unsigned int
0x1800302d7  mov     r8, rbx; unsigned __int64
0x1800302da  mov     rdx, rax; unsigned __int64
0x1800302dd  mov     rcx, r15; this
0x1800302e0  call    ??0CapiCipher@cryptography@fs@microsoft@@QEAA@_K0K_N1@Z; microsoft::fs::cryptography::CapiCipher::CapiCipher(unsigned __int64,unsigned __int64,ulong,bool,bool)
0x1800302e5  jmp     short loc_1800302EA
0x1800302e7  mov     rax, rdi
0x1800302ea  mov     rdx, rax
0x1800302ed  lea     rcx, [rsp+328h+var_290]
0x1800302f5  call    ?reset@?$auto_pointer@VICipher@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAXPEAVICipher@cryptography@34@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(microsoft::fs::cryptography::ICipher *)
0x1800302fa  nop
0x1800302fb  mov     rax, [rsi]
0x1800302fe  mov     dword ptr [rsp+328h+var_308], edi
0x180030302  lea     r9, [rsp+328h+var_2D0]
0x180030307  xor     r8d, r8d
0x18003030a  lea     rdx, aProviderName; "PROVIDER_NAME"
0x180030311  mov     rcx, rsi
0x180030314  mov     rax, [rax+10h]
0x180030318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003031d  nop
0x18003031e  jmp     short loc_18003033A
0x180030320  xor     edi, edi
0x180030322  mov     r14, [rsp+328h+arg_18]
0x18003032a  mov     rsi, [rsp+328h+arg_10]
0x180030332  mov     r13b, byte ptr [rsp+328h+arg_0]
0x18003033a  mov     ecx, [rsp+328h+var_2D0]; unsigned __int64
0x18003033e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180030343  mov     rdx, rax
0x180030346  lea     rcx, [rsp+328h+var_280]
0x18003034e  call    ?assign@?$auto_array@E@common@fs@microsoft@@AEAAXPEAE@Z; microsoft::fs::common::auto_array<uchar>::assign(uchar *)
0x180030353  mov     rax, [rsi]
0x180030356  mov     dword ptr [rsp+328h+var_308], edi
0x18003035a  lea     r9, [rsp+328h+var_2D0]
0x18003035f  mov     r12, [rsp+328h+var_280]
0x180030367  mov     r8, r12
0x18003036a  lea     rdx, aProviderName; "PROVIDER_NAME"
0x180030371  mov     rcx, rsi
0x180030374  mov     rax, [rax+10h]
0x180030378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003037d  mov     rax, [rsi]
0x180030380  mov     dword ptr [rsp+328h+var_308], edi
0x180030384  lea     r9, [rsp+328h+var_288]
0x18003038c  lea     r8, [rsp+328h+var_2C8]
0x180030391  lea     rdx, aProviderType; "PROVIDER_TYPE"
0x180030398  mov     rcx, rsi
0x18003039b  mov     rax, [rax+10h]
0x18003039f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303a4  lea     r8, [rsp+328h+var_2C0]; struct csp_hash_tag **
0x1800303a9  mov     rdx, r12; unsigned __int16 *
0x1800303ac  mov     ecx, [rsp+328h+var_2C8]; unsigned int
0x1800303b0  call    ?GetHashList@@YAJKPEAGPEAPEAUcsp_hash_tag@@@Z; GetHashList(ulong,ushort *,csp_hash_tag * *)
0x1800303b5  test    eax, eax
0x1800303b7  jns     short loc_1800303F2
0x1800303b9  mov     dword ptr [rsp+328h+var_308], eax; int
0x1800303bd  lea     r9, aGethashlistDwp; "GetHashList(dwProvType, reinterpret_cas"...
0x1800303c4  mov     r8d, 587h; unsigned int
0x1800303ca  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800303d1  lea     rcx, [rsp+328h+var_A0]; this
0x1800303d9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800303de  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800303e5  lea     rcx, [rsp+328h+var_A0]; pExceptionObject
0x1800303ed  call    _CxxThrowException_0
0x1800303f2  mov     rbx, [rsp+328h+var_2C0]
0x1800303f7  mov     eax, [rbx]
0x1800303f9  mov     [rsp+328h+var_2D0+4], eax
0x1800303fd  lea     rdx, [rsp+328h+var_2D0+4]; void *
0x180030402  mov     ecx, 3; unsigned int
0x180030407  call    ?fsCryptFindOIDInfo@@YAPEBU_CRYPT_OID_INFO@@KPEAXK@Z; fsCryptFindOIDInfo(ulong,void *,ulong)
0x18003040c  test    rax, rax
0x18003040f  jnz     short loc_18003044E
0x180030411  mov     dword ptr [rsp+328h+var_308], 80091002h; int
0x180030419  lea     r9, aPcoidinfo; "pcOIDInfo"
0x180030420  mov     r8d, 595h; unsigned int
0x180030426  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003042d  lea     rcx, [rsp+328h+var_70]; this
0x180030435  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003043a  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030441  lea     rcx, [rsp+328h+var_70]; pExceptionObject
0x180030449  call    _CxxThrowException_0
0x18003044e  mov     r15, [rax+10h]
0x180030452  mov     [rsp+328h+var_2B0], r15
0x180030457  mov     r8d, [rsp+328h+var_2D0+4]; unsigned int
0x18003045c  mov     edx, [rsp+328h+var_2C8]; unsigned int
0x180030460  mov     rcx, r12; unsigned __int16 *
0x180030463  call    ?CreateHash@CapiCryptoFactory@cryptography@fs@microsoft@@SAPEAVIHash@234@PEBGKKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CapiCryptoFactory::CreateHash(ushort const *,ulong,ulong,microsoft::fs::common::FsException *)
0x180030468  mov     rdx, rax
0x18003046b  lea     rcx, [rsp+328h+var_2A8]
0x180030473  call    ?reset@?$auto_pointer@VICipher@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAXPEAVICipher@cryptography@34@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(microsoft::fs::cryptography::ICipher *)
0x180030478  nop
0x180030479  mov     rcx, r12
0x18003047c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180030482  mov     [rsp+328h+var_280], rdi
0x18003048a  mov     [rsp+328h+var_2B8], 4
0x180030492  mov     rcx, [rsp+328h+var_2A8]
0x18003049a  mov     rax, [rcx]
0x18003049d  mov     dword ptr [rsp+328h+var_308], edi
0x1800304a1  lea     r9, [rsp+328h+var_2B8]
0x1800304a6  lea     r8, [rsp+328h+var_2D8]
0x1800304ab  lea     rdx, aHashLength; "HASH_LENGTH"
0x1800304b2  mov     rax, [rax+10h]
0x1800304b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304bb  mov     ecx, dword ptr [rsp+328h+var_2D8]; unsigned __int64
0x1800304bf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800304c4  mov     rdx, rax
0x1800304c7  lea     rcx, [rsp+328h+var_278]
0x1800304cf  call    ?assign@?$auto_array@E@common@fs@microsoft@@AEAAXPEAE@Z; microsoft::fs::common::auto_array<uchar>::assign(uchar *)
0x1800304d4  mov     ecx, edi
0x1800304d6  mov     [rsp+328h+arg_0], ecx
0x1800304dd  mov     edx, edi
0x1800304df  mov     r12, [rsp+328h+var_278]
0x1800304e7  mov     r8d, dword ptr [rsp+328h+var_2D8]
0x1800304ec  cmp     edx, r8d
0x1800304ef  jnb     short loc_180030505
0x1800304f1  mov     eax, edx
0x1800304f3  mov     [rax+r12], cl
0x1800304f7  lea     ecx, [rdx+1]
0x1800304fa  mov     [rsp+328h+arg_0], ecx
0x180030501  mov     edx, ecx
0x180030503  jmp     short loc_1800304E7
0x180030505  mov     [rsp+328h+var_270], r15
0x18003050d  mov     dword ptr [rsp+328h+var_2D8+4], edi
0x180030511  movzx   r15d, r13b
0x180030515  add     r15d, r15d
  ... truncated ...
```
