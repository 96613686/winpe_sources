# microsoft::fs::cryptography::CryptoUtil::VerifyPublicKeyInfoMatchesCipherForEncryption(ulong,_CERT_PUBLIC_KEY_INFO const *,microsoft::fs::cryptography::ICipher *,long *,microsoft::fs::common::FsException *)

- ea: `0x18002fa58`
- end: `0x18002ff6c`
- name: `?VerifyPublicKeyInfoMatchesCipherForEncryption@CryptoUtil@cryptography@fs@microsoft@@SAXKPEBU_CERT_PUBLIC_KEY_INFO@@PEAVICipher@234@PEAJPEAVFsException@common@34@@Z`
- size: `1300`
- prototype: `static void(unsigned int, const struct _CERT_PUBLIC_KEY_INFO *, struct microsoft::fs::cryptography::ICipher *, int *, struct microsoft::fs::common::FsException *)`
- caller_count: `1`
- callee_count: `19`
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
- `0x18002f358`
- `0x18002fa58`
- `0x180030788`
- `0x1800307bc`
- `0x180030f40`
- `0x180031524`
- `0x180031598`
- `0x180032250`
- `0x1800328c0`
- `0x18003373c`
- `0x180035284`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002fbac`
- `msvcrt!_wcsicmp` at `0x18002fbac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ff00`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ff14`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ff00`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002ff14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcbd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002fef6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002fef6`
- `ncrypt!NCryptIsKeyHandle` at `0x18002fb0c`
- `ncrypt!NCryptIsKeyHandle` at `0x18002fb0c`

## string_xrefs

- `0x18002fac9`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002fb75`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002fc00`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002fc72`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002fcdb`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall microsoft::fs::cryptography::CryptoUtil::VerifyPublicKeyInfoMatchesCipherForEncryption(
        __int64 a1,
        struct _CERT_PUBLIC_KEY_INFO *a2,
        struct microsoft::fs::cryptography::ICipher *a3,
        int *a4,
        struct microsoft::fs::common::FsException *a5)
{
  NCRYPT_KEY_HANDLE v8; // rax
  BOOL IsKeyHandle; // eax
  __int64 v10; // rdx
  unsigned __int64 v11; // rax
  int Property; // eax
  __int64 v13; // rcx
  void *v14; // r9
  DWORD LastError; // eax
  int v16; // eax
  microsoft::fs::cryptography::CngBCryptCipher *v17; // rax
  void *v18; // rdx
  unsigned __int8 *v19; // r9
  unsigned __int64 v20; // rax
  unsigned int v21; // edx
  DWORD v22; // eax
  int v23; // eax
  __int64 v24; // rbx
  void *v25; // rax
  void *v26; // rax
  microsoft::fs::cryptography::CngBCryptCipher *v27; // rbx
  unsigned __int64 v28; // rcx
  microsoft::fs::common::FsException *v29; // rbx
  const struct microsoft::fs::common::FsException *v30; // rax
  bool v31; // [rsp+20h] [rbp-3C8h]
  unsigned int v32; // [rsp+20h] [rbp-3C8h]
  DWORD v33; // [rsp+28h] [rbp-3C0h]
  DWORD v34; // [rsp+28h] [rbp-3C0h]
  bool v35; // [rsp+30h] [rbp-3B8h]
  unsigned int v36; // [rsp+40h] [rbp-3A8h] BYREF
  unsigned int v37; // [rsp+44h] [rbp-3A4h] BYREF
  BCRYPT_KEY_HANDLE v38; // [rsp+48h] [rbp-3A0h] BYREF
  unsigned __int64 v39; // [rsp+50h] [rbp-398h] BYREF
  void *v40; // [rsp+58h] [rbp-390h] BYREF
  __int64 v41; // [rsp+60h] [rbp-388h] BYREF
  microsoft::fs::cryptography::CngBCryptCipher *v42; // [rsp+68h] [rbp-380h] BYREF
  DWORD v43; // [rsp+70h] [rbp-378h] BYREF
  microsoft::fs::common::FsException *v44; // [rsp+78h] [rbp-370h]
  const microsoft::fs::common::FsException *v45; // [rsp+80h] [rbp-368h] BYREF
  _QWORD v46[6]; // [rsp+88h] [rbp-360h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+B8h] [rbp-330h] BYREF
  _BYTE v48[48]; // [rsp+E8h] [rbp-300h] BYREF
  _BYTE v49[48]; // [rsp+118h] [rbp-2D0h] BYREF
  _BYTE v50[48]; // [rsp+148h] [rbp-2A0h] BYREF
  _BYTE v51[48]; // [rsp+178h] [rbp-270h] BYREF
  __int64 v52; // [rsp+1A8h] [rbp-240h] BYREF
  __int64 v53; // [rsp+1B0h] [rbp-238h]
  unsigned int v54; // [rsp+1B8h] [rbp-230h]
  wchar_t String2[256]; // [rsp+1C0h] [rbp-228h] BYREF

  v44 = a5;
  v38 = 0;
  v39 = 0;
  try
  {
    if ( a5 )
      (*(void (**)(void))(*(_QWORD *)a5 + 8LL))();
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
        0x3B5u,
        L"pCipher",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v41 = 0;
    v8 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 80LL))(a3);
    IsKeyHandle = NCryptIsKeyHandle(v8);
    v10 = *(_QWORD *)a3;
    if ( IsKeyHandle )
    {
      v43 = 512;
      v11 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(v10 + 80))(a3);
      Property = fsNCryptGetProperty(v11, L"Algorithm Group", (unsigned __int8 *)String2, 0x200u, &v43, 0);
      if ( Property < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v48,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x3C8u,
          L"NCryptGetProperty( (NCRYPT_KEY_HANDLE)pCipher->GetHandle(), NCRYPT_ALGORITHM_GROUP_PROPERTY, reinterpret_cast<"
           "BYTE*>(szAlgorithmGroup), cbLength, &cbLength, 0)",
          Property);
        throw (microsoft::fs::common::FsException *)v48;
      }
      if ( !_wcsicmp(L"ECDH", String2) )
      {
        microsoft::fs::cryptography::CryptoUtil::VerifyECDHPublicKeyInfoMatchesCipherForEncryption(v13, a2, a3, a4);
LABEL_29:
        microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v41);
        goto LABEL_51;
      }
      if ( !(unsigned int)fsCryptImportPublicKeyInfoEx2(v13, a2, 0x40000000u, v14, &v38) )
      {
        LastError = GetLastError();
        v16 = HR_FROM_WIN32(LastError);
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v49,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x3D9u,
          L"CryptImportPublicKeyInfoEx2( nCertEncodingType, const_cast<CERT_PUBLIC_KEY_INFO*>(pcpki), CRYPT_OID_INFO_PUBKE"
           "Y_ENCRYPT_KEY_FLAG, 0, &hBCryptKey)",
          v16);
        throw (microsoft::fs::common::FsException *)v49;
      }
      v17 = (microsoft::fs::cryptography::CngBCryptCipher *)operator new(0x258u);
      v42 = v17;
      if ( v17 )
        v17 = (microsoft::fs::cryptography::CngBCryptCipher *)microsoft::fs::cryptography::CngBCryptCipher::CngBCryptCipher(
                                                                v17,
                                                                v18,
                                                                v38,
                                                                v19,
                                                                v32,
                                                                v33,
                                                                v35);
    }
    else
    {
      if ( !(*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(v10 + 112))(a3) )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v50,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x3E5u,
          L"pCipher->GetProviderHandle()",
          -2147024809);
        throw (microsoft::fs::common::FsException *)v50;
      }
      v20 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 112LL))(a3);
      if ( !(unsigned int)fsCryptImportPublicKeyInfo(v20, v21, a2, &v39) )
      {
        v22 = GetLastError();
        v23 = HR_FROM_WIN32(v22);
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v51,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
          0x3EAu,
          L"CryptImportPublicKeyInfo( (HCRYPTPROV)pCipher->GetProviderHandle(), nCertEncodingType, const_cast<CERT_PUBLIC_"
           "KEY_INFO*>(pcpki), &hCapiKey)",
          v23);
        throw (microsoft::fs::common::FsException *)v51;
      }
      v17 = (microsoft::fs::cryptography::CngBCryptCipher *)operator new(0x38u);
      v42 = v17;
      if ( v17 )
        v17 = (microsoft::fs::cryptography::CngBCryptCipher *)microsoft::fs::cryptography::CapiCipher::CapiCipher(
                                                                v17,
                                                                0,
                                                                v39,
                                                                1u,
                                                                v31,
                                                                0);
    }
    microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(&v41, v17);
    v52 = 0x706050403020100LL;
    v53 = 0xF0E0D0C0B0A0908LL;
    v54 = 319951120;
    v36 = 0;
    v24 = v41;
    (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v41 + 64LL))(v41, &v52, 20);
    v25 = operator new[](v36);
    microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&v40, v25);
    LOBYTE(v33) = 1;
    (*(void (__fastcall **)(__int64, __int64 *, __int64, void *, unsigned int *, DWORD))(*(_QWORD *)v24 + 64LL))(
      v24,
      &v52,
      20,
      v40,
      &v36,
      v33);
    v37 = v36;
    v26 = operator new[](v36);
    microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&v42, v26);
    LOBYTE(v34) = 1;
    v27 = v42;
    (*(void (__fastcall **)(struct microsoft::fs::cryptography::ICipher *, void *, _QWORD, microsoft::fs::cryptography::CngBCryptCipher *, unsigned int *, DWORD))(*(_QWORD *)a3 + 48LL))(
      a3,
      v40,
      v36,
      v42,
      &v37,
      v34);
    *a4 = 0;
    if ( v37 != 20 )
      goto LABEL_27;
    v28 = v52 - *(_QWORD *)v27;
    if ( v52 == *(_QWORD *)v27 )
    {
      v28 = v53 - *((_QWORD *)v27 + 1);
      if ( v53 == *((_QWORD *)v27 + 1) )
        v28 = v54 - (unsigned __int64)*((unsigned int *)v27 + 4);
    }
    if ( v28 )
    {
LABEL_27:
      *a4 = -2146893821;
      CSPrintErrorLineFile(0x4080C20u, -2146893821);
    }
    operator delete[](v27);
    v42 = 0;
    operator delete[](v40);
    v40 = 0;
    goto LABEL_29;
  }
  catch ( const microsoft::fs::common::FsException *v45 )
  {
    if ( !v44 )
    {
      if ( v38 )
        fsBCryptDestroyKey(v38);
      if ( v39 )
        fsCryptDestroyKey(v39);
      throw;
    }
    microsoft::fs::common::FsException::assign(v44, v45);
  }
  catch ( ... )
  {
    v29 = v44;
    if ( !v44 )
    {
      if ( v38 )
        fsBCryptDestroyKey(v38);
      if ( v39 )
        fsCryptDestroyKey(v39);
      throw;
    }
    v30 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v46,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
                                                               0x41Eu,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(v29, v30);
    v46[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v46[1]);
    operator delete[]((void *)v46[2]);
    operator delete[]((void *)v46[3]);
    operator delete[]((void *)v46[5]);
  }
LABEL_51:
  if ( v38 )
    fsBCryptDestroyKey(v38);
  if ( v39 )
    fsCryptDestroyKey(v39);
}

```

## disassembly

```asm
0x18002fa58  push    rbx
0x18002fa5a  push    rsi
0x18002fa5b  push    r14
0x18002fa5d  sub     rsp, 3D0h
0x18002fa64  mov     rax, cs:__security_cookie
0x18002fa6b  xor     rax, rsp
0x18002fa6e  mov     [rsp+3E8h+var_28], rax
0x18002fa76  mov     r14, r9
0x18002fa79  mov     rsi, r8
0x18002fa7c  mov     rbx, rdx
0x18002fa7f  mov     rcx, [rsp+3E8h+arg_20]
0x18002fa87  mov     [rsp+3E8h+var_370], rcx
0x18002fa8c  mov     [rsp+3E8h+var_3A0], 0
0x18002fa95  mov     [rsp+3E8h+var_398], 0
0x18002fa9e  test    rcx, rcx
0x18002faa1  jz      short loc_18002FAAF
0x18002faa3  mov     rax, [rcx]
0x18002faa6  mov     rax, [rax+8]
0x18002faaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faaf  test    rsi, rsi
0x18002fab2  jnz     short loc_18002FAF1
0x18002fab4  mov     dword ptr [rsp+3E8h+var_3C8], 80070057h; int
0x18002fabc  lea     r9, aPcipher; "pCipher"
0x18002fac3  mov     r8d, 3B5h; unsigned int
0x18002fac9  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002fad0  lea     rcx, [rsp+3E8h+pExceptionObject]; this
0x18002fad8  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002fadd  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002fae4  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x18002faec  call    _CxxThrowException_0
0x18002faf1  mov     [rsp+3E8h+var_388], 0
0x18002fafa  mov     rax, [rsi]
0x18002fafd  mov     rcx, rsi
0x18002fb00  mov     rax, [rax+50h]
0x18002fb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb09  mov     rcx, rax; hKey
0x18002fb0c  call    cs:__imp_NCryptIsKeyHandle
0x18002fb12  mov     rdx, [rsi]
0x18002fb15  mov     rcx, rsi
0x18002fb18  test    eax, eax
0x18002fb1a  jz      loc_18002FC4F
0x18002fb20  mov     [rsp+3E8h+var_378], 200h
0x18002fb28  mov     rax, [rdx+50h]
0x18002fb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb31  mov     [rsp+3E8h+var_3C0], 0; bool
0x18002fb39  lea     rcx, [rsp+3E8h+var_378]
0x18002fb3e  mov     [rsp+3E8h+var_3C8], rcx; DWORD *
0x18002fb43  mov     r9d, 200h; unsigned int
0x18002fb49  lea     r8, [rsp+3E8h+String2]; unsigned __int8 *
0x18002fb51  lea     rdx, aAlgorithmGroup; "Algorithm Group"
0x18002fb58  mov     rcx, rax; unsigned __int64
0x18002fb5b  call    ?fsNCryptGetProperty@@YAJ_KPEBGPEAEKPEAKK@Z; fsNCryptGetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong *,ulong)
0x18002fb60  test    eax, eax
0x18002fb62  jns     short loc_18002FB9D
0x18002fb64  mov     dword ptr [rsp+3E8h+var_3C8], eax; int
0x18002fb68  lea     r9, aNcryptgetprope_2; "NCryptGetProperty( (NCRYPT_KEY_HANDLE)p"...
0x18002fb6f  mov     r8d, 3C8h; unsigned int
0x18002fb75  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002fb7c  lea     rcx, [rsp+3E8h+var_300]; this
0x18002fb84  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002fb89  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002fb90  lea     rcx, [rsp+3E8h+var_300]; pExceptionObject
0x18002fb98  call    _CxxThrowException_0
0x18002fb9d  lea     rdx, [rsp+3E8h+String2]; String2
0x18002fba5  lea     rcx, aEcdh; "ECDH"
0x18002fbac  call    cs:__imp__wcsicmp
0x18002fbb2  mov     rdx, rbx; struct _CERT_PUBLIC_KEY_INFO *
0x18002fbb5  test    eax, eax
0x18002fbb7  jnz     short loc_18002FBC9
0x18002fbb9  mov     r9, r14; int *
0x18002fbbc  mov     r8, rsi; struct microsoft::fs::cryptography::ICipher *
0x18002fbbf  call    ?VerifyECDHPublicKeyInfoMatchesCipherForEncryption@CryptoUtil@cryptography@fs@microsoft@@SAXKPEBU_CERT_PUBLIC_KEY_INFO@@PEAVICipher@234@PEAJ@Z; microsoft::fs::cryptography::CryptoUtil::VerifyECDHPublicKeyInfoMatchesCipherForEncryption(ulong,_CERT_PUBLIC_KEY_INFO const *,microsoft::fs::cryptography::ICipher *,long *)
0x18002fbc4  jmp     loc_18002FF23
0x18002fbc9  lea     rax, [rsp+3E8h+var_3A0]
0x18002fbce  mov     [rsp+3E8h+var_3C8], rax; unsigned int
0x18002fbd3  mov     r8d, 40000000h; unsigned int
0x18002fbd9  call    ?fsCryptImportPublicKeyInfoEx2@@YAHKPEAU_CERT_PUBLIC_KEY_INFO@@KPEAXPEAPEAX@Z; fsCryptImportPublicKeyInfoEx2(ulong,_CERT_PUBLIC_KEY_INFO *,ulong,void *,void * *)
0x18002fbde  test    eax, eax
0x18002fbe0  jnz     short loc_18002FC28
0x18002fbe2  call    cs:__imp_GetLastError
0x18002fbe8  mov     ecx, eax; unsigned int
0x18002fbea  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18002fbef  mov     dword ptr [rsp+3E8h+var_3C8], eax; int
0x18002fbf3  lea     r9, aCryptimportpub_1; "CryptImportPublicKeyInfoEx2( nCertEncod"...
0x18002fbfa  mov     r8d, 3D9h; unsigned int
0x18002fc00  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002fc07  lea     rcx, [rsp+3E8h+var_2D0]; this
0x18002fc0f  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002fc14  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002fc1b  lea     rcx, [rsp+3E8h+var_2D0]; pExceptionObject
0x18002fc23  call    _CxxThrowException_0
0x18002fc28  mov     ecx, 258h; Size
0x18002fc2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fc32  mov     [rsp+3E8h+var_380], rax
0x18002fc37  test    rax, rax
0x18002fc3a  jz      short loc_18002FC4A
0x18002fc3c  mov     r8, [rsp+3E8h+var_3A0]; void *
0x18002fc41  mov     rcx, rax; this
0x18002fc44  call    ??0CngBCryptCipher@cryptography@fs@microsoft@@QEAA@PEAX0PEAEK_N2@Z; microsoft::fs::cryptography::CngBCryptCipher::CngBCryptCipher(void *,void *,uchar *,ulong,bool,bool)
0x18002fc49  nop
0x18002fc4a  jmp     loc_18002FD32
0x18002fc4f  mov     rax, [rdx+70h]
0x18002fc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc58  test    rax, rax
0x18002fc5b  jnz     short loc_18002FC9A
0x18002fc5d  mov     dword ptr [rsp+3E8h+var_3C8], 80070057h; int
0x18002fc65  lea     r9, aPcipherGetprov; "pCipher->GetProviderHandle()"
0x18002fc6c  mov     r8d, 3E5h; unsigned int
0x18002fc72  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002fc79  lea     rcx, [rsp+3E8h+var_2A0]; this
0x18002fc81  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002fc86  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002fc8d  lea     rcx, [rsp+3E8h+var_2A0]; pExceptionObject
0x18002fc95  call    _CxxThrowException_0
0x18002fc9a  mov     rax, [rsi]
0x18002fc9d  mov     rcx, rsi
0x18002fca0  mov     rax, [rax+70h]
0x18002fca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fca9  mov     rcx, rax; unsigned __int64
0x18002fcac  lea     r9, [rsp+3E8h+var_398]; unsigned __int64 *
0x18002fcb1  mov     r8, rbx; struct _CERT_PUBLIC_KEY_INFO *
0x18002fcb4  call    ?fsCryptImportPublicKeyInfo@@YAH_KKPEAU_CERT_PUBLIC_KEY_INFO@@PEA_K@Z; fsCryptImportPublicKeyInfo(unsigned __int64,ulong,_CERT_PUBLIC_KEY_INFO *,unsigned __int64 *)
0x18002fcb9  test    eax, eax
0x18002fcbb  jnz     short loc_18002FD03
0x18002fcbd  call    cs:__imp_GetLastError
0x18002fcc3  mov     ecx, eax; unsigned int
0x18002fcc5  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18002fcca  mov     dword ptr [rsp+3E8h+var_3C8], eax; int
0x18002fcce  lea     r9, aCryptimportpub_3; "CryptImportPublicKeyInfo( (HCRYPTPROV)p"...
0x18002fcd5  mov     r8d, 3EAh; unsigned int
0x18002fcdb  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002fce2  lea     rcx, [rsp+3E8h+var_270]; this
0x18002fcea  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002fcef  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002fcf6  lea     rcx, [rsp+3E8h+var_270]; pExceptionObject
0x18002fcfe  call    _CxxThrowException_0
0x18002fd03  mov     ecx, 38h ; '8'; Size
0x18002fd08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fd0d  mov     [rsp+3E8h+var_380], rax
0x18002fd12  test    rax, rax
0x18002fd15  jz      short loc_18002FD32
0x18002fd17  mov     byte ptr [rsp+3E8h+var_3C0], 0; bool
0x18002fd1c  mov     r9d, 1; unsigned int
0x18002fd22  mov     r8, [rsp+3E8h+var_398]; unsigned __int64
0x18002fd27  xor     edx, edx; unsigned __int64
0x18002fd29  mov     rcx, rax; this
0x18002fd2c  call    ??0CapiCipher@cryptography@fs@microsoft@@QEAA@_K0K_N1@Z; microsoft::fs::cryptography::CapiCipher::CapiCipher(unsigned __int64,unsigned __int64,ulong,bool,bool)
0x18002fd31  nop
0x18002fd32  mov     rdx, rax
0x18002fd35  lea     rcx, [rsp+3E8h+var_388]
0x18002fd3a  call    ?reset@?$auto_pointer@VICipher@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAAXPEAVICipher@cryptography@34@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::ICipher>::reset(microsoft::fs::cryptography::ICipher *)
0x18002fd3f  mov     byte ptr [rsp+3E8h+var_240], 0
0x18002fd47  mov     byte ptr [rsp+3E8h+var_240+1], 1
0x18002fd4f  mov     byte ptr [rsp+3E8h+var_240+2], 2
0x18002fd57  mov     byte ptr [rsp+3E8h+var_240+3], 3
0x18002fd5f  mov     byte ptr [rsp+3E8h+var_240+4], 4
0x18002fd67  mov     byte ptr [rsp+3E8h+var_240+5], 5
0x18002fd6f  mov     byte ptr [rsp+3E8h+var_240+6], 6
0x18002fd77  mov     byte ptr [rsp+3E8h+var_240+7], 7
0x18002fd7f  mov     byte ptr [rsp+3E8h+var_238], 8
0x18002fd87  mov     byte ptr [rsp+3E8h+var_238+1], 9
0x18002fd8f  mov     byte ptr [rsp+3E8h+var_238+2], 0Ah
0x18002fd97  mov     byte ptr [rsp+3E8h+var_238+3], 0Bh
0x18002fd9f  mov     byte ptr [rsp+3E8h+var_238+4], 0Ch
0x18002fda7  mov     byte ptr [rsp+3E8h+var_238+5], 0Dh
0x18002fdaf  mov     byte ptr [rsp+3E8h+var_238+6], 0Eh
0x18002fdb7  mov     byte ptr [rsp+3E8h+var_238+7], 0Fh
0x18002fdbf  mov     byte ptr [rsp+3E8h+var_230], 10h
0x18002fdc7  mov     byte ptr [rsp+3E8h+var_230+1], 11h
0x18002fdcf  mov     byte ptr [rsp+3E8h+var_230+2], 12h
0x18002fdd7  mov     byte ptr [rsp+3E8h+var_230+3], 13h
0x18002fddf  mov     dword ptr [rsp+3E8h+var_3A8], 0
0x18002fde7  mov     rbx, [rsp+3E8h+var_388]
0x18002fdec  mov     rax, [rbx]
0x18002fdef  mov     byte ptr [rsp+3E8h+var_3C0], 1
0x18002fdf4  lea     rcx, [rsp+3E8h+var_3A8]
0x18002fdf9  mov     [rsp+3E8h+var_3C8], rcx
0x18002fdfe  xor     r9d, r9d
0x18002fe01  lea     r8d, [r9+14h]
0x18002fe05  lea     rdx, [rsp+3E8h+var_240]
0x18002fe0d  mov     rcx, rbx
0x18002fe10  mov     rax, [rax+40h]
0x18002fe14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe19  mov     ecx, dword ptr [rsp+3E8h+var_3A8]; unsigned __int64
0x18002fe1d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002fe22  mov     rdx, rax
0x18002fe25  lea     rcx, [rsp+3E8h+var_390]
0x18002fe2a  call    ??0?$auto_array@E@common@fs@microsoft@@QEAA@PEAE_N@Z; microsoft::fs::common::auto_array<uchar>::auto_array<uchar>(uchar *,bool)
0x18002fe2f  nop
0x18002fe30  mov     rax, [rbx]
0x18002fe33  mov     byte ptr [rsp+3E8h+var_3C0], 1
0x18002fe38  lea     rcx, [rsp+3E8h+var_3A8]
0x18002fe3d  mov     [rsp+3E8h+var_3C8], rcx
0x18002fe42  mov     r9, [rsp+3E8h+var_390]
0x18002fe47  mov     r8d, 14h
0x18002fe4d  lea     rdx, [rsp+3E8h+var_240]
0x18002fe55  mov     rcx, rbx
0x18002fe58  mov     rax, [rax+40h]
0x18002fe5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe61  mov     eax, dword ptr [rsp+3E8h+var_3A8]
0x18002fe65  mov     dword ptr [rsp+3E8h+var_3A8+4], eax
0x18002fe69  mov     ecx, eax; unsigned __int64
0x18002fe6b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002fe70  mov     rdx, rax
0x18002fe73  lea     rcx, [rsp+3E8h+var_380]
0x18002fe78  call    ??0?$auto_array@E@common@fs@microsoft@@QEAA@PEAE_N@Z; microsoft::fs::common::auto_array<uchar>::auto_array<uchar>(uchar *,bool)
0x18002fe7d  nop
0x18002fe7e  mov     rax, [rsi]
0x18002fe81  mov     byte ptr [rsp+3E8h+var_3C0], 1
0x18002fe86  lea     rcx, [rsp+3E8h+var_3A8+4]
0x18002fe8b  mov     [rsp+3E8h+var_3C8], rcx
0x18002fe90  mov     rbx, [rsp+3E8h+var_380]
0x18002fe95  mov     r9, rbx
0x18002fe98  mov     r8d, dword ptr [rsp+3E8h+var_3A8]
0x18002fe9d  mov     rdx, [rsp+3E8h+var_390]
0x18002fea2  mov     rcx, rsi
0x18002fea5  mov     rax, [rax+30h]
0x18002fea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feae  mov     dword ptr [r14], 0
0x18002feb5  cmp     dword ptr [rsp+3E8h+var_3A8+4], 14h
0x18002feba  jnz     short loc_18002FEE9
0x18002febc  mov     rcx, [rsp+3E8h+var_240]
0x18002fec4  sub     rcx, [rbx]
0x18002fec7  jnz     short loc_18002FEE4
0x18002fec9  mov     rcx, [rsp+3E8h+var_238]
0x18002fed1  sub     rcx, [rbx+8]
0x18002fed5  jnz     short loc_18002FEE4
0x18002fed7  mov     ecx, [rsp+3E8h+var_230]
0x18002fede  mov     eax, [rbx+10h]
0x18002fee1  sub     rcx, rax
0x18002fee4  test    rcx, rcx
0x18002fee7  jz      short loc_18002FEFD
0x18002fee9  mov     edx, 80090003h
0x18002feee  mov     [r14], edx
0x18002fef1  mov     ecx, 4080C20h
0x18002fef6  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002fefc  nop
0x18002fefd  mov     rcx, rbx
0x18002ff00  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ff06  mov     [rsp+3E8h+var_380], 0
0x18002ff0f  mov     rcx, [rsp+3E8h+var_390]
0x18002ff14  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002ff1a  mov     [rsp+3E8h+var_390], 0
0x18002ff23  lea     rcx, [rsp+3E8h+var_388]
0x18002ff28  call    ?close@?$auto_pointer@VIHash@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(void)
0x18002ff2d  nop
0x18002ff2e  jmp     short loc_18002FF32
0x18002ff30  jmp     short $+2
0x18002ff32  mov     rcx, [rsp+3E8h+var_3A0]; void *
0x18002ff37  test    rcx, rcx
0x18002ff3a  jz      short loc_18002FF41
0x18002ff3c  call    ?fsBCryptDestroyKey@@YAJPEAX@Z; fsBCryptDestroyKey(void *)
0x18002ff41  mov     rcx, [rsp+3E8h+var_398]; unsigned __int64
0x18002ff46  test    rcx, rcx
0x18002ff49  jz      short loc_18002FF50
0x18002ff4b  call    ?fsCryptDestroyKey@@YAH_K@Z; fsCryptDestroyKey(unsigned __int64)
0x18002ff50  mov     rcx, [rsp+3E8h+var_28]
0x18002ff58  xor     rcx, rsp; StackCookie
0x18002ff5b  call    __security_check_cookie
0x18002ff60  add     rsp, 3D0h
0x18002ff67  pop     r14
0x18002ff69  pop     rsi
0x18002ff6a  pop     rbx
0x18002ff6b  retn
```
