# microsoft::fs::cryptography::CryptoUtil::VerifyECDHPublicKeyInfoMatchesCipherForEncryption(ulong,_CERT_PUBLIC_KEY_INFO const *,microsoft::fs::cryptography::ICipher *,long *)

- ea: `0x18002f358`
- end: `0x18002fa50`
- name: `?VerifyECDHPublicKeyInfoMatchesCipherForEncryption@CryptoUtil@cryptography@fs@microsoft@@SAXKPEBU_CERT_PUBLIC_KEY_INFO@@PEAVICipher@234@PEAJ@Z`
- size: `1784`
- prototype: `static void(unsigned int, const struct _CERT_PUBLIC_KEY_INFO *, struct microsoft::fs::cryptography::ICipher *, int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002fa58`

## callees

- `0x180001514`
- `0x180001798`
- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x18002e604`
- `0x18002e628`
- `0x18002f358`
- `0x18003075c`
- `0x180030788`
- `0x1800307bc`
- `0x180031598`
- `0x1800318cc`
- `0x180032358`
- `0x180032784`
- `0x1800328c0`
- `0x180032998`
- `0x180036980`
- `0x1800396e6`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002f9af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002f9bc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002f9dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002fa09`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002f9af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002f9bc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002f9dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002fa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f511`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002f9a5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002f9a5`

## string_xrefs

- `0x18002f3e5`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f458`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f4cd`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f52f`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f58e`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f605`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f694`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f757`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f7de`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002f837`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall microsoft::fs::cryptography::CryptoUtil::VerifyECDHPublicKeyInfoMatchesCipherForEncryption(
        __int64 a1,
        struct _CERT_PUBLIC_KEY_INFO *a2,
        struct microsoft::fs::cryptography::ICipher *a3,
        int *a4)
{
  unsigned __int64 v7; // rax
  int Property; // eax
  unsigned __int64 v9; // rax
  int v10; // eax
  unsigned __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ecx
  void *v14; // r9
  DWORD LastError; // eax
  int v16; // eax
  int v17; // eax
  BYTE *v18; // rdi
  int v19; // eax
  const unsigned __int16 *v20; // rcx
  const unsigned __int16 *v21; // r8
  __int64 v22; // r9
  struct microsoft::fs::cryptography::ICipher *AsymmetricCipher; // rax
  ULONG v24; // ebx
  __int64 (__fastcall ***v25)(_QWORD, __int64); // r14
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  const unsigned __int16 *v28; // r8
  struct _BCryptBufferDesc *v29; // r9
  int v30; // eax
  void *v31; // rsi
  NCRYPT_KEY_HANDLE v32; // rbx
  __int64 v33; // rax
  microsoft::fs::cryptography::CngNCryptCipher *v34; // rax
  unsigned __int64 v35; // rax
  struct _BCryptBufferDesc *v36; // r9
  int v37; // eax
  DWORD v38; // ebx
  unsigned __int64 v39; // rax
  BYTE *v40; // rbx
  struct _BCryptBufferDesc *v41; // r9
  int v42; // eax
  unsigned __int64 v43; // rdx
  const unsigned __int16 *v44; // r8
  struct _BCryptBufferDesc *v45; // r9
  int v46; // eax
  void *v47; // rax
  microsoft::fs::cryptography::CngNCryptCipher *v48; // rax
  void *v49; // rsi
  void *v50; // r14
  DWORD v51; // [rsp+20h] [rbp-E0h]
  DWORD v52; // [rsp+20h] [rbp-E0h]
  unsigned int v53; // [rsp+28h] [rbp-D8h]
  DWORD v54; // [rsp+28h] [rbp-D8h]
  unsigned int v55; // [rsp+30h] [rbp-D0h]
  unsigned int v56; // [rsp+30h] [rbp-D0h]
  unsigned int v57; // [rsp+30h] [rbp-D0h]
  unsigned int v58; // [rsp+38h] [rbp-C8h]
  unsigned int v59; // [rsp+38h] [rbp-C8h]
  unsigned int v60; // [rsp+38h] [rbp-C8h]
  unsigned int v61; // [rsp+38h] [rbp-C8h]
  unsigned int v62; // [rsp+38h] [rbp-C8h]
  bool v63; // [rsp+40h] [rbp-C0h]
  bool v64; // [rsp+48h] [rbp-B8h]
  struct microsoft::fs::common::FsException *v65; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v66; // [rsp+58h] [rbp-A8h]
  ULONG v67; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v68; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int Size; // [rsp+68h] [rbp-98h] BYREF
  unsigned int Size_4; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v71; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v72[4]; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 (__fastcall ***v73)(_QWORD, __int64); // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v74[8]; // [rsp+80h] [rbp-80h] BYREF
  void *Buf1; // [rsp+88h] [rbp-78h] BYREF
  DWORD v76; // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall ***v77)(_QWORD, __int64); // [rsp+98h] [rbp-68h] BYREF
  NCRYPT_KEY_HANDLE v78; // [rsp+A0h] [rbp-60h] BYREF
  __int64 (__fastcall ***v79)(_QWORD, __int64); // [rsp+A8h] [rbp-58h] BYREF
  NCRYPT_KEY_HANDLE v80; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+B8h] [rbp-48h] BYREF
  void *Buf2; // [rsp+E8h] [rbp-18h] BYREF
  PBYTE v83; // [rsp+F0h] [rbp-10h] BYREF
  PBYTE v84; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v85[8]; // [rsp+100h] [rbp+0h] BYREF
  BCRYPT_KEY_HANDLE v86[3]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 v87[256]; // [rsp+120h] [rbp+20h] BYREF

  v71 = 0;
  v7 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 80LL))(a3);
  Property = fsNCryptGetProperty(v7, L"Algorithm Name", (unsigned __int8 *)v87, 0x200u, &v71, 0);
  if ( Property < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1078,
      L"NCryptGetProperty( (NCRYPT_KEY_HANDLE)pCipher->GetHandle(), NCRYPT_ALGORITHM_PROPERTY, reinterpret_cast<BYTE*>(szA"
       "lgorithmName), sizeof(szAlgorithmName), &cbOut, 0)",
      Property);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  *(_DWORD *)v72 = 0;
  v9 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 80LL))(a3);
  v10 = fsNCryptGetProperty(v9, L"Length", v72, 4u, &v71, 0);
  if ( v10 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1087,
      L"NCryptGetProperty( (NCRYPT_KEY_HANDLE)pCipher->GetHandle(), NCRYPT_LENGTH_PROPERTY, reinterpret_cast<BYTE*>(&cBits"
       "InKey), sizeof(cBitsInKey), &cbOut, 0)",
      v10);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  *(_QWORD *)v74 = 0;
  v76 = 8;
  v11 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 80LL))(a3);
  v12 = fsNCryptGetProperty(v11, L"Provider Handle", v74, 8u, &v76, 0);
  if ( v12 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1097,
      L"NCryptGetProperty( (NCRYPT_KEY_HANDLE)pCipher->GetHandle(), NCRYPT_PROVIDER_HANDLE_PROPERTY, reinterpret_cast<BYTE"
       "*>(&hProv), cbProv, &cbProv, 0)",
      v12);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v86[0] = 0;
  v86[1] = 0;
  if ( !(unsigned int)fsCryptImportPublicKeyInfoEx2(v13, a2, 0x40000000u, v14, v86) )
  {
    LastError = GetLastError();
    v16 = HR_FROM_WIN32(LastError);
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1105,
      L"CryptImportPublicKeyInfoEx2( nCertEncodingType, const_cast<CERT_PUBLIC_KEY_INFO*>(pcpki), CRYPT_OID_INFO_PUBKEY_EN"
       "CRYPT_KEY_FLAG, 0, &hBCryptKey)",
      v16);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v67 = 0;
  v17 = fsBCryptExportKey(v86[0], 0, L"ECCPUBLICBLOB", 0, 0, &v67, v55);
  if ( v17 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1115,
      L"BCryptExportKey( hBCryptKey, 0, BCRYPT_ECCPUBLIC_BLOB, 0, 0, &cbPublicKey1, 0)",
      v17);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  operator new[](v67);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&v84);
  v18 = v84;
  v19 = fsBCryptExportKey(v86[0], 0, L"ECCPUBLICBLOB", v84, v67, &v67, v56);
  if ( v19 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1125,
      L"BCryptExportKey( hBCryptKey, 0, BCRYPT_ECCPUBLIC_BLOB, pbPublicKey1, cbPublicKey1, &cbPublicKey1, 0)",
      v19);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v73 = 0;
  AsymmetricCipher = microsoft::fs::cryptography::CngCryptoFactory::CreateAsymmetricCipher(
                       v20,
                       v87,
                       v21,
                       v22,
                       *(unsigned int *)v72,
                       v53,
                       v57,
                       v58,
                       v63,
                       v64,
                       v65,
                       v66);
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v73, AsymmetricCipher);
  v80 = 0;
  v24 = v67;
  v25 = v73;
  v26 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v73)[14])(v73);
  v30 = fsNCryptImportKey(v26, v27, v28, v29, &v80, v18, v24, v59);
  if ( v30 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1151,
      L"NCryptImportKey( (NCRYPT_PROV_HANDLE)pEphemeralCipher->GetProviderHandle(), 0, BCRYPT_ECCPUBLIC_BLOB, 0, &hNCryptP"
       "ubKey1, pbPublicKey1, cbPublicKey1, 0)",
      v30);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v79 = 0;
  v31 = operator new(0x230u);
  Buf1 = v31;
  if ( v31 )
  {
    v32 = v80;
    v33 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v25)[14])(v25);
    LOBYTE(v51) = 0;
    v34 = microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(
            (microsoft::fs::cryptography::CngNCryptCipher *)v31,
            v33,
            v32,
            0,
            v51);
  }
  else
  {
    v34 = 0;
  }
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v79, v34);
  v68 = 0;
  v35 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v25)[10])(v25);
  v37 = fsNCryptExportKey(v35, 0, L"ECCPUBLICBLOB", v36, 0, 0, &v68, v60);
  if ( v37 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1169,
      L"NCryptExportKey( (NCRYPT_KEY_HANDLE)pEphemeralCipher->GetHandle(), 0, BCRYPT_ECCPUBLIC_BLOB, 0, 0, 0, &cbPublicKey2, 0)",
      v37);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  operator new[](v68);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&v83);
  v38 = v68;
  v39 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64)))(*v25)[10])(v25);
  v54 = v38;
  v40 = v83;
  v42 = fsNCryptExportKey(v39, 0, L"ECCPUBLICBLOB", v41, v83, v54, &v68, v61);
  if ( v42 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1180,
      L"NCryptExportKey( (NCRYPT_KEY_HANDLE)pEphemeralCipher->GetHandle(), 0, BCRYPT_ECCPUBLIC_BLOB, 0, pbPublicKey2, cbPu"
       "blicKey2, &cbPublicKey2, 0)",
      v42);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v78 = 0;
  v46 = fsNCryptImportKey(*(unsigned __int64 *)v74, v43, v44, v45, &v78, v40, v68, v62);
  if ( v46 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      1191,
      L"NCryptImportKey( hProv, 0, BCRYPT_ECCPUBLIC_BLOB, 0, &hNCryptPubKey2, pbPublicKey2, cbPublicKey2, 0)",
      v46);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v77 = 0;
  v47 = operator new(0x230u);
  Buf1 = v47;
  if ( v47 )
  {
    LOBYTE(v52) = 0;
    v48 = microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(
            (microsoft::fs::cryptography::CngNCryptCipher *)v47,
            *(__int64 *)v74,
            v78,
            0,
            v52);
  }
  else
  {
    v48 = 0;
  }
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v77, v48);
  (*v25)[22](v25, (__int64)v79);
  Size = 0;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), _QWORD, unsigned int *))(*v25)[24])(v25, 0, &Size);
  operator new[](Size);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&Buf1);
  v49 = Buf1;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64), void *, unsigned int *))(*v25)[24])(v25, Buf1, &Size);
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v73);
  v73 = 0;
  (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, __int64 (__fastcall ***)(_QWORD, __int64)))(*(_QWORD *)a3 + 176LL))(
    a3,
    v77);
  Size_4 = 0;
  (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, _QWORD, unsigned int *))(*(_QWORD *)a3 + 192LL))(
    a3,
    0,
    &Size_4);
  operator new[](Size_4);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&Buf2);
  v50 = Buf2;
  (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, void *, unsigned int *))(*(_QWORD *)a3 + 192LL))(
    a3,
    Buf2,
    &Size_4);
  *a4 = 0;
  if ( Size != Size_4 || memcmp_0(v49, v50, Size) )
  {
    *a4 = -2146893821;
    CSPrintErrorLineFile(0x4D10C20u, -2146893821);
  }
  operator delete[](v50);
  Buf2 = 0;
  operator delete[](v49);
  Buf1 = 0;
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v77);
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(&v78);
  operator delete[](v40);
  v83 = 0;
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v79);
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(&v80);
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v73);
  operator delete[](v18);
  v84 = 0;
  microsoft::fs::cryptography::auto_bcrypt_handle_t<void *,0,microsoft::fs::cryptography::CloseCngBCryptKeyFunctor>::~auto_bcrypt_handle_t<void *,0,microsoft::fs::cryptography::CloseCngBCryptKeyFunctor>(v85);
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close((unsigned __int64 *)v74);
}

```

## disassembly

```asm
0x18002f358  mov     [rsp-8+arg_0], rbx
0x18002f35d  push    rbp
0x18002f35e  push    rsi
0x18002f35f  push    rdi
0x18002f360  push    r12
0x18002f362  push    r13
0x18002f364  push    r14
0x18002f366  push    r15
0x18002f368  lea     rbp, [rsp-230h]
0x18002f370  sub     rsp, 330h
0x18002f377  mov     rax, cs:__security_cookie
0x18002f37e  xor     rax, rsp
0x18002f381  mov     [rbp+260h+var_40], rax
0x18002f388  mov     r12, r9
0x18002f38b  mov     r15, r8
0x18002f38e  mov     rbx, rdx
0x18002f391  xor     r13d, r13d
0x18002f394  mov     [rsp+360h+var_2F0], r13d
0x18002f399  mov     rax, [r8]
0x18002f39c  mov     rcx, r8
0x18002f39f  mov     rax, [rax+50h]
0x18002f3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3a8  mov     rcx, rax; unsigned __int64
0x18002f3ab  mov     [rsp+360h+var_338], r13d; DWORD
0x18002f3b0  lea     rax, [rsp+360h+var_2F0]
0x18002f3b5  mov     qword ptr [rsp+360h+var_340], rax; DWORD *
0x18002f3ba  mov     r9d, 200h; unsigned int
0x18002f3c0  lea     r8, [rbp+260h+var_240]; unsigned __int8 *
0x18002f3c4  lea     rdx, aAlgorithmName; "Algorithm Name"
0x18002f3cb  call    ?fsNCryptGetProperty@@YAJ_KPEBGPEAEKPEAKK@Z; fsNCryptGetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong *,ulong)
0x18002f3d0  test    eax, eax
0x18002f3d2  jns     short loc_18002F406
0x18002f3d4  mov     [rsp+360h+var_340], eax; int
0x18002f3d8  lea     r9, aNcryptgetprope_5; "NCryptGetProperty( (NCRYPT_KEY_HANDLE)p"...
0x18002f3df  mov     r8d, 436h; unsigned int
0x18002f3e5  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f3ec  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f3f0  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f3f5  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f3fc  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f400  call    _CxxThrowException_0
0x18002f406  mov     dword ptr [rsp+360h+var_2EC], r13d
0x18002f40b  mov     rax, [r15]
0x18002f40e  mov     rcx, r15
0x18002f411  mov     rax, [rax+50h]
0x18002f415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f41a  mov     rcx, rax; unsigned __int64
0x18002f41d  mov     [rsp+360h+var_338], r13d; DWORD
0x18002f422  lea     rax, [rsp+360h+var_2F0]
0x18002f427  mov     qword ptr [rsp+360h+var_340], rax; DWORD *
0x18002f42c  mov     r9d, 4; unsigned int
0x18002f432  lea     r8, [rsp+360h+var_2EC]; unsigned __int8 *
0x18002f437  lea     rdx, aLength; "Length"
0x18002f43e  call    ?fsNCryptGetProperty@@YAJ_KPEBGPEAEKPEAKK@Z; fsNCryptGetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong *,ulong)
0x18002f443  test    eax, eax
0x18002f445  jns     short loc_18002F479
0x18002f447  mov     [rsp+360h+var_340], eax; int
0x18002f44b  lea     r9, aNcryptgetprope_4; "NCryptGetProperty( (NCRYPT_KEY_HANDLE)p"...
0x18002f452  mov     r8d, 43Fh; unsigned int
0x18002f458  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f45f  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f463  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f468  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f46f  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f473  call    _CxxThrowException_0
0x18002f479  mov     qword ptr [rbp+260h+var_2E0], r13
0x18002f47d  mov     edi, 8
0x18002f482  mov     [rbp+260h+var_2D0], edi
0x18002f485  mov     rax, [r15]
0x18002f488  mov     rcx, r15
0x18002f48b  mov     rax, [rax+50h]
0x18002f48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f494  mov     [rsp+360h+var_338], r13d; DWORD
0x18002f499  lea     rcx, [rbp+260h+var_2D0]
0x18002f49d  mov     qword ptr [rsp+360h+var_340], rcx; DWORD *
0x18002f4a2  mov     r9d, edi; unsigned int
0x18002f4a5  lea     r8, [rbp+260h+var_2E0]; unsigned __int8 *
0x18002f4a9  lea     rdx, aProviderHandle; "Provider Handle"
0x18002f4b0  mov     rcx, rax; unsigned __int64
0x18002f4b3  call    ?fsNCryptGetProperty@@YAJ_KPEBGPEAEKPEAKK@Z; fsNCryptGetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong *,ulong)
0x18002f4b8  test    eax, eax
0x18002f4ba  jns     short loc_18002F4EE
0x18002f4bc  mov     [rsp+360h+var_340], eax; int
0x18002f4c0  lea     r9, aNcryptgetprope_7; "NCryptGetProperty( (NCRYPT_KEY_HANDLE)p"...
0x18002f4c7  mov     r8d, 449h; unsigned int
0x18002f4cd  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f4d4  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f4d8  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f4dd  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f4e4  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f4e8  call    _CxxThrowException_0
0x18002f4ee  mov     [rbp+260h+var_258], r13
0x18002f4f2  mov     [rbp+260h+var_250], r13
0x18002f4f6  lea     rax, [rbp+260h+var_258]
0x18002f4fa  mov     qword ptr [rsp+360h+var_340], rax; BCRYPT_KEY_HANDLE *
0x18002f4ff  mov     r8d, 40000000h; unsigned int
0x18002f505  mov     rdx, rbx; struct _CERT_PUBLIC_KEY_INFO *
0x18002f508  call    ?fsCryptImportPublicKeyInfoEx2@@YAHKPEAU_CERT_PUBLIC_KEY_INFO@@KPEAXPEAPEAX@Z; fsCryptImportPublicKeyInfoEx2(ulong,_CERT_PUBLIC_KEY_INFO *,ulong,void *,void * *)
0x18002f50d  test    eax, eax
0x18002f50f  jnz     short loc_18002F550
0x18002f511  call    cs:__imp_GetLastError
0x18002f517  mov     ecx, eax; unsigned int
0x18002f519  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18002f51e  mov     [rsp+360h+var_340], eax; int
0x18002f522  lea     r9, aCryptimportpub_1; "CryptImportPublicKeyInfoEx2( nCertEncod"...
0x18002f529  mov     r8d, 451h; unsigned int
0x18002f52f  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f536  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f53a  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f53f  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f546  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f54a  call    _CxxThrowException_0
0x18002f550  mov     [rsp+360h+var_300], r13d
0x18002f555  lea     rax, [rsp+360h+var_300]
0x18002f55a  mov     qword ptr [rsp+360h+var_338], rax; ULONG *
0x18002f55f  mov     [rsp+360h+var_340], r13d; ULONG
0x18002f564  xor     r9d, r9d; unsigned __int8 *
0x18002f567  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x18002f56e  xor     edx, edx; void *
0x18002f570  mov     rcx, [rbp+260h+var_258]; void *
0x18002f574  call    ?fsBCryptExportKey@@YAJPEAX0PEBGPEAEKPEAKK@Z; fsBCryptExportKey(void *,void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x18002f579  test    eax, eax
0x18002f57b  jns     short loc_18002F5AF
0x18002f57d  mov     [rsp+360h+var_340], eax; int
0x18002f581  lea     r9, aBcryptexportke_1; "BCryptExportKey( hBCryptKey, 0, BCRYPT_"...
0x18002f588  mov     r8d, 45Bh; unsigned int
0x18002f58e  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f595  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f599  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f59e  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f5a5  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f5a9  call    _CxxThrowException_0
0x18002f5af  mov     ecx, [rsp+360h+var_300]; unsigned __int64
0x18002f5b3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002f5b8  mov     rdx, rax
0x18002f5bb  lea     rcx, [rbp+260h+var_268]
0x18002f5bf  call    ??0?$auto_array@E@common@fs@microsoft@@QEAA@PEAE_N@Z; microsoft::fs::common::auto_array<uchar>::auto_array<uchar>(uchar *,bool)
0x18002f5c4  nop
0x18002f5c5  mov     eax, [rsp+360h+var_300]
0x18002f5c9  lea     rcx, [rsp+360h+var_300]
0x18002f5ce  mov     qword ptr [rsp+360h+var_338], rcx; unsigned int
0x18002f5d3  mov     [rsp+360h+var_340], eax; ULONG
0x18002f5d7  mov     rdi, [rbp+260h+var_268]
0x18002f5db  mov     r9, rdi; unsigned __int8 *
0x18002f5de  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x18002f5e5  xor     edx, edx; void *
0x18002f5e7  mov     rcx, [rbp+260h+var_258]; void *
0x18002f5eb  call    ?fsBCryptExportKey@@YAJPEAX0PEBGPEAEKPEAKK@Z; fsBCryptExportKey(void *,void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x18002f5f0  test    eax, eax
0x18002f5f2  jns     short loc_18002F626
0x18002f5f4  mov     [rsp+360h+var_340], eax; int
0x18002f5f8  lea     r9, aBcryptexportke_2; "BCryptExportKey( hBCryptKey, 0, BCRYPT_"...
0x18002f5ff  mov     r8d, 465h; unsigned int
0x18002f605  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f60c  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f610  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f615  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f61c  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f620  call    _CxxThrowException_0
0x18002f626  mov     [rsp+360h+var_2E8], r13
0x18002f62b  mov     eax, dword ptr [rsp+360h+var_2EC]
0x18002f62f  mov     [rsp+360h+var_340], eax; unsigned int
0x18002f633  lea     rdx, [rbp+260h+var_240]; unsigned __int16 *
0x18002f637  call    ?CreateAsymmetricCipher@CngCryptoFactory@cryptography@fs@microsoft@@SAPEAVICipher@234@PEBG00KKKKK_N1PEAVFsException@common@34@0@Z; microsoft::fs::cryptography::CngCryptoFactory::CreateAsymmetricCipher(ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,ulong,ulong,bool,bool,microsoft::fs::common::FsException *,ushort const *)
0x18002f63c  mov     rdx, rax
0x18002f63f  lea     rcx, [rsp+360h+var_2E8]
0x18002f644  call    ?reset@?$auto_pointer@VICipher@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAXPEAVICipher@cryptography@34@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(microsoft::fs::cryptography::ICipher *)
0x18002f649  mov     [rbp+260h+var_2B0], r13
0x18002f64d  mov     ebx, [rsp+360h+var_300]
0x18002f651  mov     r14, [rsp+360h+var_2E8]
0x18002f656  mov     rax, [r14]
0x18002f659  mov     rcx, r14
0x18002f65c  mov     rax, [rax+70h]
0x18002f660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f665  mov     [rsp+360h+var_330], ebx; DWORD
0x18002f669  mov     qword ptr [rsp+360h+var_338], rdi; PBYTE
0x18002f66e  lea     rcx, [rbp+260h+var_2B0]
0x18002f672  mov     qword ptr [rsp+360h+var_340], rcx; NCRYPT_KEY_HANDLE *
0x18002f677  mov     rcx, rax; unsigned __int64
0x18002f67a  call    ?fsNCryptImportKey@@YAJ_K0PEBGPEAU_BCryptBufferDesc@@PEA_KPEAEKK@Z; fsNCryptImportKey(unsigned __int64,unsigned __int64,ushort const *,_BCryptBufferDesc *,unsigned __int64 *,uchar *,ulong,ulong)
0x18002f67f  test    eax, eax
0x18002f681  jns     short loc_18002F6B5
0x18002f683  mov     [rsp+360h+var_340], eax; int
0x18002f687  lea     r9, aNcryptimportke_1; "NCryptImportKey( (NCRYPT_PROV_HANDLE)pE"...
0x18002f68e  mov     r8d, 47Fh; unsigned int
0x18002f694  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f69b  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f69f  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f6a4  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f6ab  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f6af  call    _CxxThrowException_0
0x18002f6b5  mov     [rbp+260h+var_2B8], r13
0x18002f6b9  mov     ecx, 230h; Size
0x18002f6be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f6c3  mov     rsi, rax
0x18002f6c6  mov     [rbp+260h+Buf1], rax
0x18002f6ca  test    rax, rax
0x18002f6cd  jz      short loc_18002F6FA
0x18002f6cf  mov     rbx, [rbp+260h+var_2B0]
0x18002f6d3  mov     rcx, [r14]
0x18002f6d6  mov     rax, [rcx+70h]
0x18002f6da  mov     rcx, r14
0x18002f6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6e2  mov     byte ptr [rsp+360h+var_340], r13b; bool
0x18002f6e7  xor     r9d, r9d; bool
0x18002f6ea  mov     r8, rbx; unsigned __int64
0x18002f6ed  mov     rdx, rax; unsigned __int64
0x18002f6f0  mov     rcx, rsi; this
0x18002f6f3  call    ??0CngNCryptCipher@cryptography@fs@microsoft@@QEAA@_K0_N1@Z; microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(unsigned __int64,unsigned __int64,bool,bool)
0x18002f6f8  jmp     short loc_18002F6FD
0x18002f6fa  mov     rax, r13
0x18002f6fd  mov     rdx, rax
0x18002f700  lea     rcx, [rbp+260h+var_2B8]
0x18002f704  call    ?reset@?$auto_pointer@VICipher@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAXPEAVICipher@cryptography@34@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(microsoft::fs::cryptography::ICipher *)
0x18002f709  mov     [rsp+360h+var_2FC], r13d
0x18002f70e  mov     rax, [r14]
0x18002f711  mov     rcx, r14
0x18002f714  mov     rax, [rax+50h]
0x18002f718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f71d  mov     rcx, rax; unsigned __int64
0x18002f720  lea     rax, [rsp+360h+var_2FC]
0x18002f725  mov     qword ptr [rsp+360h+var_330], rax; DWORD *
0x18002f72a  mov     [rsp+360h+var_338], r13d; DWORD
0x18002f72f  mov     qword ptr [rsp+360h+var_340], r13; PBYTE
0x18002f734  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x18002f73b  xor     edx, edx; unsigned __int64
0x18002f73d  call    ?fsNCryptExportKey@@YAJ_K0PEBGPEAU_BCryptBufferDesc@@PEAEKPEAKK@Z; fsNCryptExportKey(unsigned __int64,unsigned __int64,ushort const *,_BCryptBufferDesc *,uchar *,ulong,ulong *,ulong)
0x18002f742  test    eax, eax
0x18002f744  jns     short loc_18002F778
0x18002f746  mov     [rsp+360h+var_340], eax; int
0x18002f74a  lea     r9, aNcryptexportke_1; "NCryptExportKey( (NCRYPT_KEY_HANDLE)pEp"...
0x18002f751  mov     r8d, 491h; unsigned int
0x18002f757  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f75e  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f762  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f767  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f76e  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f772  call    _CxxThrowException_0
0x18002f778  mov     ecx, [rsp+360h+var_2FC]; unsigned __int64
0x18002f77c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002f781  mov     rdx, rax
0x18002f784  lea     rcx, [rbp+260h+var_270]
0x18002f788  call    ??0?$auto_array@E@common@fs@microsoft@@QEAA@PEAE_N@Z; microsoft::fs::common::auto_array<uchar>::auto_array<uchar>(uchar *,bool)
0x18002f78d  nop
0x18002f78e  mov     ebx, [rsp+360h+var_2FC]
0x18002f792  mov     rax, [r14]
0x18002f795  mov     rcx, r14
0x18002f798  mov     rax, [rax+50h]
0x18002f79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7a1  lea     rcx, [rsp+360h+var_2FC]
0x18002f7a6  mov     qword ptr [rsp+360h+var_330], rcx; DWORD *
0x18002f7ab  mov     [rsp+360h+var_338], ebx; DWORD
0x18002f7af  mov     rbx, [rbp+260h+var_270]
0x18002f7b3  mov     qword ptr [rsp+360h+var_340], rbx; PBYTE
0x18002f7b8  lea     r8, pszBlobType; "ECCPUBLICBLOB"
0x18002f7bf  xor     edx, edx; unsigned __int64
0x18002f7c1  mov     rcx, rax; unsigned __int64
0x18002f7c4  call    ?fsNCryptExportKey@@YAJ_K0PEBGPEAU_BCryptBufferDesc@@PEAEKPEAKK@Z; fsNCryptExportKey(unsigned __int64,unsigned __int64,ushort const *,_BCryptBufferDesc *,uchar *,ulong,ulong *,ulong)
0x18002f7c9  test    eax, eax
0x18002f7cb  jns     short loc_18002F7FF
0x18002f7cd  mov     [rsp+360h+var_340], eax; int
0x18002f7d1  lea     r9, aNcryptexportke_0; "NCryptExportKey( (NCRYPT_KEY_HANDLE)pEp"...
0x18002f7d8  mov     r8d, 49Ch; unsigned int
0x18002f7de  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f7e5  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f7e9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f7ee  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f7f5  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f7f9  call    _CxxThrowException_0
0x18002f7ff  mov     [rbp+260h+var_2C0], r13
0x18002f803  mov     eax, [rsp+360h+var_2FC]
0x18002f807  mov     [rsp+360h+var_330], eax; DWORD
0x18002f80b  mov     qword ptr [rsp+360h+var_338], rbx; PBYTE
0x18002f810  lea     rax, [rbp+260h+var_2C0]
0x18002f814  mov     qword ptr [rsp+360h+var_340], rax; NCRYPT_KEY_HANDLE *
0x18002f819  mov     rcx, qword ptr [rbp+260h+var_2E0]; unsigned __int64
0x18002f81d  call    ?fsNCryptImportKey@@YAJ_K0PEBGPEAU_BCryptBufferDesc@@PEA_KPEAEKK@Z; fsNCryptImportKey(unsigned __int64,unsigned __int64,ushort const *,_BCryptBufferDesc *,unsigned __int64 *,uchar *,ulong,ulong)
0x18002f822  test    eax, eax
0x18002f824  jns     short loc_18002F858
0x18002f826  mov     [rsp+360h+var_340], eax; int
0x18002f82a  lea     r9, aNcryptimportke_0; "NCryptImportKey( hProv, 0, BCRYPT_ECCPU"...
0x18002f831  mov     r8d, 4A7h; unsigned int
0x18002f837  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002f83e  lea     rcx, [rbp+260h+pExceptionObject]; this
0x18002f842  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002f847  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002f84e  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18002f852  call    _CxxThrowException_0
0x18002f858  mov     [rbp+260h+var_2C8], r13
0x18002f85c  mov     ecx, 230h; Size
0x18002f861  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f866  mov     [rbp+260h+Buf1], rax
0x18002f86a  test    rax, rax
0x18002f86d  jz      short loc_18002F889
0x18002f86f  mov     byte ptr [rsp+360h+var_340], r13b; bool
0x18002f874  xor     r9d, r9d; bool
0x18002f877  mov     r8, [rbp+260h+var_2C0]; unsigned __int64
0x18002f87b  mov     rdx, qword ptr [rbp+260h+var_2E0]; unsigned __int64
0x18002f87f  mov     rcx, rax; this
0x18002f882  call    ??0CngNCryptCipher@cryptography@fs@microsoft@@QEAA@_K0_N1@Z; microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(unsigned __int64,unsigned __int64,bool,bool)
  ... truncated ...
```
