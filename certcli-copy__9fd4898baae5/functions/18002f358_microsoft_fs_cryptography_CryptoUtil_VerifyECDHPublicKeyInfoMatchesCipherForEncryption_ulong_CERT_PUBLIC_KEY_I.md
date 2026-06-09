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
  void *v18; // rax
  BYTE *v19; // rdi
  int v20; // eax
  const unsigned __int16 *v21; // rcx
  const unsigned __int16 *v22; // r8
  __int64 v23; // r9
  struct microsoft::fs::cryptography::ICipher *AsymmetricCipher; // rax
  ULONG v25; // ebx
  __int64 v26; // r14
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // rdx
  const unsigned __int16 *v29; // r8
  struct _BCryptBufferDesc *v30; // r9
  int v31; // eax
  void *v32; // rsi
  NCRYPT_KEY_HANDLE v33; // rbx
  unsigned __int64 v34; // rax
  __int64 v35; // rax
  unsigned __int64 v36; // rax
  struct _BCryptBufferDesc *v37; // r9
  int v38; // eax
  void *v39; // rax
  DWORD v40; // ebx
  unsigned __int64 v41; // rax
  BYTE *v42; // rbx
  struct _BCryptBufferDesc *v43; // r9
  int v44; // eax
  unsigned __int64 v45; // rdx
  const unsigned __int16 *v46; // r8
  struct _BCryptBufferDesc *v47; // r9
  int v48; // eax
  void *v49; // rax
  __int64 v50; // rax
  void *v51; // rax
  void *v52; // rsi
  void *v53; // rax
  void *v54; // r14
  unsigned int v55; // [rsp+28h] [rbp-D8h]
  DWORD v56; // [rsp+28h] [rbp-D8h]
  unsigned int v57; // [rsp+30h] [rbp-D0h]
  unsigned int v58; // [rsp+30h] [rbp-D0h]
  unsigned int v59; // [rsp+30h] [rbp-D0h]
  unsigned int v60; // [rsp+38h] [rbp-C8h]
  unsigned int v61; // [rsp+38h] [rbp-C8h]
  unsigned int v62; // [rsp+38h] [rbp-C8h]
  unsigned int v63; // [rsp+38h] [rbp-C8h]
  unsigned int v64; // [rsp+38h] [rbp-C8h]
  bool v65; // [rsp+40h] [rbp-C0h]
  bool v66; // [rsp+48h] [rbp-B8h]
  struct microsoft::fs::common::FsException *v67; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v68; // [rsp+58h] [rbp-A8h]
  ULONG v69; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v70; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int Size; // [rsp+68h] [rbp-98h] BYREF
  unsigned int Size_4; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD v73; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v74[4]; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v76[8]; // [rsp+80h] [rbp-80h] BYREF
  void *Buf1; // [rsp+88h] [rbp-78h] BYREF
  DWORD v78; // [rsp+90h] [rbp-70h] BYREF
  __int64 v79; // [rsp+98h] [rbp-68h] BYREF
  NCRYPT_KEY_HANDLE v80; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v81; // [rsp+A8h] [rbp-58h] BYREF
  NCRYPT_KEY_HANDLE v82; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+B8h] [rbp-48h] BYREF
  void *Buf2; // [rsp+E8h] [rbp-18h] BYREF
  PBYTE v85; // [rsp+F0h] [rbp-10h] BYREF
  PBYTE v86; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v87[8]; // [rsp+100h] [rbp+0h] BYREF
  BCRYPT_KEY_HANDLE v88[3]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 v89[256]; // [rsp+120h] [rbp+20h] BYREF

  v73 = 0;
  v7 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 80LL))(a3);
  Property = fsNCryptGetProperty(v7, L"Algorithm Name", (unsigned __int8 *)v89, 0x200u, &v73, 0);
  if ( Property < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x436u,
      L"NCryptGetProperty( (NCRYPT_KEY_HANDLE)pCipher->GetHandle(), NCRYPT_ALGORITHM_PROPERTY, reinterpret_cast<BYTE*>(szA"
       "lgorithmName), sizeof(szAlgorithmName), &cbOut, 0)",
      Property);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  *(_DWORD *)v74 = 0;
  v9 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 80LL))(a3);
  v10 = fsNCryptGetProperty(v9, L"Length", v74, 4u, &v73, 0);
  if ( v10 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x43Fu,
      L"NCryptGetProperty( (NCRYPT_KEY_HANDLE)pCipher->GetHandle(), NCRYPT_LENGTH_PROPERTY, reinterpret_cast<BYTE*>(&cBits"
       "InKey), sizeof(cBitsInKey), &cbOut, 0)",
      v10);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  *(_QWORD *)v76 = 0;
  v78 = 8;
  v11 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 80LL))(a3);
  v12 = fsNCryptGetProperty(v11, L"Provider Handle", v76, 8u, &v78, 0);
  if ( v12 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x449u,
      L"NCryptGetProperty( (NCRYPT_KEY_HANDLE)pCipher->GetHandle(), NCRYPT_PROVIDER_HANDLE_PROPERTY, reinterpret_cast<BYTE"
       "*>(&hProv), cbProv, &cbProv, 0)",
      v12);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v88[0] = 0;
  v88[1] = 0;
  if ( !(unsigned int)fsCryptImportPublicKeyInfoEx2(v13, a2, 0x40000000u, v14, v88) )
  {
    LastError = GetLastError();
    v16 = HR_FROM_WIN32(LastError);
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x451u,
      L"CryptImportPublicKeyInfoEx2( nCertEncodingType, const_cast<CERT_PUBLIC_KEY_INFO*>(pcpki), CRYPT_OID_INFO_PUBKEY_EN"
       "CRYPT_KEY_FLAG, 0, &hBCryptKey)",
      v16);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v69 = 0;
  v17 = fsBCryptExportKey(v88[0], 0, L"ECCPUBLICBLOB", 0, 0, &v69, v57);
  if ( v17 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x45Bu,
      L"BCryptExportKey( hBCryptKey, 0, BCRYPT_ECCPUBLIC_BLOB, 0, 0, &cbPublicKey1, 0)",
      v17);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v18 = operator new[](v69);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&v86, v18);
  v19 = v86;
  v20 = fsBCryptExportKey(v88[0], 0, L"ECCPUBLICBLOB", v86, v69, &v69, v58);
  if ( v20 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x465u,
      L"BCryptExportKey( hBCryptKey, 0, BCRYPT_ECCPUBLIC_BLOB, pbPublicKey1, cbPublicKey1, &cbPublicKey1, 0)",
      v20);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v75 = 0;
  AsymmetricCipher = microsoft::fs::cryptography::CngCryptoFactory::CreateAsymmetricCipher(
                       v21,
                       v89,
                       v22,
                       v23,
                       *(unsigned int *)v74,
                       v55,
                       v59,
                       v60,
                       v65,
                       v66,
                       v67,
                       v68);
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v75, AsymmetricCipher);
  v82 = 0;
  v25 = v69;
  v26 = v75;
  v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v75 + 112LL))(v75);
  v31 = fsNCryptImportKey(v27, v28, v29, v30, &v82, v19, v25, v61);
  if ( v31 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x47Fu,
      L"NCryptImportKey( (NCRYPT_PROV_HANDLE)pEphemeralCipher->GetProviderHandle(), 0, BCRYPT_ECCPUBLIC_BLOB, 0, &hNCryptP"
       "ubKey1, pbPublicKey1, cbPublicKey1, 0)",
      v31);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v81 = 0;
  v32 = operator new(0x230u);
  Buf1 = v32;
  if ( v32 )
  {
    v33 = v82;
    v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 112LL))(v26);
    v35 = microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(
            (microsoft::fs::cryptography::CngNCryptCipher *)v32,
            v34,
            v33,
            0,
            0);
  }
  else
  {
    v35 = 0;
  }
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v81, v35);
  v70 = 0;
  v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
  v38 = fsNCryptExportKey(v36, 0, L"ECCPUBLICBLOB", v37, 0, 0, &v70, v62);
  if ( v38 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x491u,
      L"NCryptExportKey( (NCRYPT_KEY_HANDLE)pEphemeralCipher->GetHandle(), 0, BCRYPT_ECCPUBLIC_BLOB, 0, 0, 0, &cbPublicKey2, 0)",
      v38);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v39 = operator new[](v70);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&v85, v39);
  v40 = v70;
  v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 80LL))(v26);
  v56 = v40;
  v42 = v85;
  v44 = fsNCryptExportKey(v41, 0, L"ECCPUBLICBLOB", v43, v85, v56, &v70, v63);
  if ( v44 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x49Cu,
      L"NCryptExportKey( (NCRYPT_KEY_HANDLE)pEphemeralCipher->GetHandle(), 0, BCRYPT_ECCPUBLIC_BLOB, 0, pbPublicKey2, cbPu"
       "blicKey2, &cbPublicKey2, 0)",
      v44);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v80 = 0;
  v48 = fsNCryptImportKey(*(unsigned __int64 *)v76, v45, v46, v47, &v80, v42, v70, v64);
  if ( v48 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
      0x4A7u,
      L"NCryptImportKey( hProv, 0, BCRYPT_ECCPUBLIC_BLOB, 0, &hNCryptPubKey2, pbPublicKey2, cbPublicKey2, 0)",
      v48);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  v79 = 0;
  v49 = operator new(0x230u);
  Buf1 = v49;
  if ( v49 )
    v50 = microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(
            (microsoft::fs::cryptography::CngNCryptCipher *)v49,
            *(unsigned __int64 *)v76,
            v80,
            0,
            0);
  else
    v50 = 0;
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v79, v50);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 176LL))(v26, v81);
  Size = 0;
  (*(void (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 192LL))(v26, 0, &Size);
  v51 = operator new[](Size);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&Buf1, v51);
  v52 = Buf1;
  (*(void (__fastcall **)(__int64, void *, unsigned int *))(*(_QWORD *)v26 + 192LL))(v26, Buf1, &Size);
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v75);
  v75 = 0;
  (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, __int64))(*(_QWORD *)a3 + 176LL))(a3, v79);
  Size_4 = 0;
  (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, _QWORD, unsigned int *))(*(_QWORD *)a3 + 192LL))(
    a3,
    0,
    &Size_4);
  v53 = operator new[](Size_4);
  microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&Buf2, v53);
  v54 = Buf2;
  (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, void *, unsigned int *))(*(_QWORD *)a3 + 192LL))(
    a3,
    Buf2,
    &Size_4);
  *a4 = 0;
  if ( Size != Size_4 || memcmp_0(v52, v54, Size) )
  {
    *a4 = -2146893821;
    CSPrintErrorLineFile(0x4D10C20u, -2146893821);
  }
  operator delete[](v54);
  Buf2 = 0;
  operator delete[](v52);
  Buf1 = 0;
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v79);
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(&v80);
  operator delete[](v42);
  v85 = 0;
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v81);
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(&v82);
  microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v75);
  operator delete[](v19);
  v86 = 0;
  microsoft::fs::cryptography::auto_bcrypt_handle_t<void *,0,microsoft::fs::cryptography::CloseCngBCryptKeyFunctor>::~auto_bcrypt_handle_t<void *,0,microsoft::fs::cryptography::CloseCngBCryptKeyFunctor>(v87);
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(v76);
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
