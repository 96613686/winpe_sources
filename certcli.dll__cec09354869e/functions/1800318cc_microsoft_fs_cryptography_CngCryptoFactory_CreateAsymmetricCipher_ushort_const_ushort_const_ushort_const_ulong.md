# microsoft::fs::cryptography::CngCryptoFactory::CreateAsymmetricCipher(ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,ulong,ulong,bool,bool,microsoft::fs::common::FsException *,ushort const *)

- ea: `0x1800318cc`
- end: `0x180031c40`
- name: `?CreateAsymmetricCipher@CngCryptoFactory@cryptography@fs@microsoft@@SAPEAVICipher@234@PEBG00KKKKK_N1PEAVFsException@common@34@0@Z`
- size: `884`
- prototype: `struct microsoft::fs::cryptography::ICipher *__fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int64, unsigned int, unsigned int, unsigned int, unsigned int, bool, bool, struct microsoft::fs::common::FsException *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002f358`

## callees

- `0x180001514`
- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x180019c44`
- `0x18002e6f4`
- `0x18002e704`
- `0x18003075c`
- `0x1800318cc`
- `0x18003253c`
- `0x180032830`
- `0x180032a3c`
- `0x180032aa0`
- `0x180032b58`
- `0x180036980`

## string_xrefs

- `0x180031a87`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031aba`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031af4`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031b2e`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031b67`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031ba0`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031bd9`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031c16`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031ae7`: `NCryptOpenStorageProvider(&hProv, pwszProvider, acquireToOpenStorageFlags(fAcquire))`
- `0x180031b21`: `SUCCEEDED(hr) || (fOverwriteIfNecessary && NTE_EXISTS == hr)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct microsoft::fs::cryptography::ICipher *__fastcall microsoft::fs::cryptography::CngCryptoFactory::CreateAsymmetricCipher(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        bool a9,
        bool a10,
        struct microsoft::fs::common::FsException *a11,
        const unsigned __int16 *a12)
{
  unsigned __int64 *v13; // r8
  unsigned __int64 v14; // r11
  int v15; // eax
  struct microsoft::fs::common::FsException *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  struct microsoft::fs::common::FsException *v20; // r8
  const unsigned __int16 *v21; // rdx
  int v22; // eax
  const unsigned __int16 *v23; // r9
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  microsoft::fs::cryptography::CngNCryptCipher *v28; // rax
  microsoft::fs::cryptography::CngNCryptCipher *v29; // rbx
  DWORD v31; // [rsp+20h] [rbp-1C8h]
  unsigned __int64 v32; // [rsp+30h] [rbp-1B8h] BYREF
  unsigned __int8 v33[8]; // [rsp+38h] [rbp-1B0h] BYREF
  unsigned __int64 v34[2]; // [rsp+40h] [rbp-1A8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-198h] BYREF
  _BYTE v36[48]; // [rsp+80h] [rbp-168h] BYREF
  _BYTE v37[48]; // [rsp+B0h] [rbp-138h] BYREF
  _BYTE v38[48]; // [rsp+E0h] [rbp-108h] BYREF
  _BYTE v39[48]; // [rsp+110h] [rbp-D8h] BYREF
  _BYTE v40[48]; // [rsp+140h] [rbp-A8h] BYREF
  _BYTE v41[48]; // [rsp+170h] [rbp-78h] BYREF
  _BYTE v42[48]; // [rsp+1A0h] [rbp-48h] BYREF
  const microsoft::fs::common::FsException *v43; // [rsp+1D0h] [rbp-18h] BYREF

  *(_DWORD *)v33 = 0;
  try
  {
    if ( (int)StringCchLengthW(L"Microsoft Software Key Storage Provider", 0x7FFFFFFFu, 0) < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        82,
        L"SUCCEEDED(StringCchLengthW(pwszProvider, STRSAFE_MAX_CCH, 0))",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v15 = StringCchLengthW(a2, v14, v13);
    if ( v15 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v36,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        83,
        L"StringCchLengthW(pwszAlgorithm, STRSAFE_MAX_CCH, 0)",
        v15);
      throw (microsoft::fs::common::FsException *)v36;
    }
    microsoft::fs::cryptography::CryptoUtil::CheckAcquireFlags(v17, v16);
    microsoft::fs::cryptography::CryptoUtil::CheckGenKeyFlags(v19, v18, v20);
    v34[0] = 0;
    v22 = fsNCryptOpenStorageProvider(v34, v21, 0);
    if ( v22 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v37,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        99,
        L"NCryptOpenStorageProvider(&hProv, pwszProvider, acquireToOpenStorageFlags(fAcquire))",
        v22);
      throw (microsoft::fs::common::FsException *)v37;
    }
    v32 = 0;
    v24 = fsNCryptCreatePersistedKey(v34[0], &v32, a2, v23, 0, 0);
    if ( v24 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v38,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        115,
        L"SUCCEEDED(hr) || (fOverwriteIfNecessary && NTE_EXISTS == hr)",
        v24);
      throw (microsoft::fs::common::FsException *)v38;
    }
    anonymous_namespace_::setExportPolicy(v32);
    if ( !(unsigned int)cryptIsParameterSetAlgorithmName(a2) )
    {
      v25 = fsNCryptSetProperty(v32, L"Length", (unsigned __int8 *)&a5, 4u, 0);
      if ( v25 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v39,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
          138,
          L"NCryptSetProperty(hKey, NCRYPT_LENGTH_PROPERTY, reinterpret_cast<BYTE*>(&cBitsInKey), sizeof (cBitsInKey), 0)",
          v25);
        throw (microsoft::fs::common::FsException *)v39;
      }
    }
    if ( *(_DWORD *)v33 )
    {
      v26 = fsNCryptSetProperty(v32, L"Key Usage", v33, 4u, 0);
      if ( v26 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v40,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
          143,
          L"NCryptSetProperty(hKey, NCRYPT_KEY_USAGE_PROPERTY , reinterpret_cast<BYTE*>(&fKeyUsage), sizeof (fKeyUsage), 0)",
          v26);
        throw (microsoft::fs::common::FsException *)v40;
      }
    }
    v27 = fsNCryptFinalizeKey(v32, 0);
    if ( v27 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v41,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        146,
        L"NCryptFinalizeKey(hKey, acquireToFinalizeKeyFlags(fAcquire))",
        v27);
      throw (microsoft::fs::common::FsException *)v41;
    }
    v28 = (microsoft::fs::cryptography::CngNCryptCipher *)operator new(0x230u);
    if ( v28 )
    {
      LOBYTE(v31) = 1;
      v29 = microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(v28, v34[0], v32, 1, v31);
    }
    else
    {
      v29 = 0;
    }
    v34[1] = (unsigned __int64)v29;
    if ( !v29 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v42,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        149,
        L"pCipher",
        -2147024882);
      throw (microsoft::fs::common::FsException *)v42;
    }
    v32 = 0;
    v34[0] = 0;
    microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(&v32);
  }
  catch ( const microsoft::fs::common::FsException *v43 )
  {
    throw;
  }
  catch ( ... )
  {
    throw;
  }
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(v34);
  return v29;
}

```

## disassembly

```asm
0x1800318cc  mov     [rsp+arg_10], r8
0x1800318d1  push    rbx
0x1800318d2  sub     rsp, 1E0h
0x1800318d9  mov     rbx, rdx
0x1800318dc  mov     dword ptr [rsp+1E8h+var_1B0], 0
0x1800318e4  xor     r8d, r8d; unsigned __int64 *
0x1800318e7  mov     r11d, 7FFFFFFFh
0x1800318ed  mov     edx, r11d; unsigned __int64
0x1800318f0  lea     rcx, pszProviderName; "Microsoft Software Key Storage Provider"
0x1800318f7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800318fc  test    eax, eax
0x1800318fe  js      loc_180031A72
0x180031904  mov     rdx, r11; unsigned __int64
0x180031907  mov     rcx, rbx; unsigned __int16 *
0x18003190a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003190f  test    eax, eax
0x180031911  js      loc_180031AA9
0x180031917  call    ?CheckAcquireFlags@CryptoUtil@cryptography@fs@microsoft@@SAXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckAcquireFlags(ulong,microsoft::fs::common::FsException *)
0x18003191c  call    ?CheckGenKeyFlags@CryptoUtil@cryptography@fs@microsoft@@SAXK_NPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckGenKeyFlags(ulong,bool,microsoft::fs::common::FsException *)
0x180031921  mov     [rsp+1E8h+var_1A8], 0
0x18003192a  xor     r8d, r8d; unsigned int
0x18003192d  lea     rcx, [rsp+1E8h+var_1A8]; unsigned __int64 *
0x180031932  call    ?fsNCryptOpenStorageProvider@@YAJPEA_KPEBGK@Z; fsNCryptOpenStorageProvider(unsigned __int64 *,ushort const *,ulong)
0x180031937  test    eax, eax
0x180031939  js      loc_180031AE3
0x18003193f  mov     [rsp+1E8h+var_1B8], 0
0x180031948  mov     [rsp+1E8h+var_1C0], 0; unsigned int
0x180031950  mov     [rsp+1E8h+var_1C8], 0; DWORD
0x180031958  mov     r8, rbx; unsigned __int16 *
0x18003195b  lea     rdx, [rsp+1E8h+var_1B8]; unsigned __int64 *
0x180031960  mov     rcx, [rsp+1E8h+var_1A8]; unsigned __int64
0x180031965  call    ?fsNCryptCreatePersistedKey@@YAJ_KPEA_KPEBG2KK@Z; fsNCryptCreatePersistedKey(unsigned __int64,unsigned __int64 *,ushort const *,ushort const *,ulong,ulong)
0x18003196a  test    eax, eax
0x18003196c  js      loc_180031B1D
0x180031972  mov     rcx, [rsp+1E8h+var_1B8]
0x180031977  call    _anonymous_namespace___setExportPolicy
0x18003197c  mov     rcx, rbx; unsigned __int16 *
0x18003197f  call    ?cryptIsParameterSetAlgorithmName@@YAHPEBG@Z; cryptIsParameterSetAlgorithmName(ushort const *)
0x180031984  test    eax, eax
0x180031986  jnz     short loc_1800319B1
0x180031988  mov     [rsp+1E8h+var_1C8], eax; DWORD
0x18003198c  lea     r9d, [rax+4]; unsigned int
0x180031990  lea     r8, [rsp+1E8h+arg_20]; unsigned __int8 *
0x180031998  lea     rdx, aLength; "Length"
0x18003199f  mov     rcx, [rsp+1E8h+var_1B8]; unsigned __int64
0x1800319a4  call    ?fsNCryptSetProperty@@YAJ_KPEBGPEAEKK@Z; fsNCryptSetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong)
0x1800319a9  test    eax, eax
0x1800319ab  js      loc_180031B56
0x1800319b1  cmp     dword ptr [rsp+1E8h+var_1B0], 0
0x1800319b6  jz      short loc_1800319E4
0x1800319b8  mov     [rsp+1E8h+var_1C8], 0; DWORD
0x1800319c0  mov     r9d, 4; unsigned int
0x1800319c6  lea     r8, [rsp+1E8h+var_1B0]; unsigned __int8 *
0x1800319cb  lea     rdx, aKeyUsage; "Key Usage"
0x1800319d2  mov     rcx, [rsp+1E8h+var_1B8]; unsigned __int64
0x1800319d7  call    ?fsNCryptSetProperty@@YAJ_KPEBGPEAEKK@Z; fsNCryptSetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong)
0x1800319dc  test    eax, eax
0x1800319de  js      loc_180031B8F
0x1800319e4  xor     edx, edx; unsigned int
0x1800319e6  mov     rcx, [rsp+1E8h+var_1B8]; unsigned __int64
0x1800319eb  call    ?fsNCryptFinalizeKey@@YAJ_KK@Z; fsNCryptFinalizeKey(unsigned __int64,ulong)
0x1800319f0  test    eax, eax
0x1800319f2  js      loc_180031BC8
0x1800319f8  mov     ecx, 230h; Size
0x1800319fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031a02  mov     [rsp+1E8h+arg_10], rax
0x180031a0a  test    rax, rax
0x180031a0d  jz      short loc_180031A2E
0x180031a0f  mov     byte ptr [rsp+1E8h+var_1C8], 1; bool
0x180031a14  mov     r9b, 1; bool
0x180031a17  mov     r8, [rsp+1E8h+var_1B8]; unsigned __int64
0x180031a1c  mov     rdx, [rsp+1E8h+var_1A8]; unsigned __int64
0x180031a21  mov     rcx, rax; this
0x180031a24  call    ??0CngNCryptCipher@cryptography@fs@microsoft@@QEAA@_K0_N1@Z; microsoft::fs::cryptography::CngNCryptCipher::CngNCryptCipher(unsigned __int64,unsigned __int64,bool,bool)
0x180031a29  mov     rbx, rax
0x180031a2c  jmp     short loc_180031A30
0x180031a2e  xor     ebx, ebx
0x180031a30  mov     [rsp+1E8h+var_1A0], rbx
0x180031a35  test    rbx, rbx
0x180031a38  jz      loc_180031C01
0x180031a3e  mov     [rsp+1E8h+var_1B8], 0
0x180031a47  mov     [rsp+1E8h+var_1A8], 0
0x180031a50  lea     rcx, [rsp+1E8h+var_1B8]
0x180031a55  call    ?close@?$auto_handle_t@_K$0A@VCloseCngNCryptSecretFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(void)
0x180031a5a  nop
0x180031a5b  lea     rcx, [rsp+1E8h+var_1A8]
0x180031a60  call    ?close@?$auto_handle_t@_K$0A@VCloseCngNCryptSecretFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(void)
0x180031a65  nop
0x180031a66  mov     rax, rbx
0x180031a69  add     rsp, 1E0h
0x180031a70  pop     rbx
0x180031a71  retn
0x180031a72  mov     [rsp+1E8h+var_1C8], 80070057h; int
0x180031a7a  lea     r9, aSucceededStrin; "SUCCEEDED(StringCchLengthW(pwszProvider"...
0x180031a81  mov     r8d, 52h ; 'R'; unsigned int
0x180031a87  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031a8e  lea     rcx, [rsp+1E8h+pExceptionObject]; this
0x180031a93  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031a98  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031a9f  lea     rcx, [rsp+1E8h+pExceptionObject]; pExceptionObject
0x180031aa4  call    _CxxThrowException_0
0x180031aa9  mov     [rsp+1E8h+var_1C8], eax; int
0x180031aad  lea     r9, aStringcchlengt_2; "StringCchLengthW(pwszAlgorithm, STRSAFE"...
0x180031ab4  mov     r8d, 53h ; 'S'; unsigned int
0x180031aba  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031ac1  lea     rcx, [rsp+1E8h+var_168]; this
0x180031ac9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031ace  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031ad5  lea     rcx, [rsp+1E8h+var_168]; pExceptionObject
0x180031add  call    _CxxThrowException_0
0x180031ae3  mov     [rsp+1E8h+var_1C8], eax; int
0x180031ae7  lea     r9, aNcryptopenstor_0; "NCryptOpenStorageProvider(&hProv, pwszP"...
0x180031aee  mov     r8d, 63h ; 'c'; unsigned int
0x180031af4  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031afb  lea     rcx, [rsp+1E8h+var_138]; this
0x180031b03  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031b08  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031b0f  lea     rcx, [rsp+1E8h+var_138]; pExceptionObject
0x180031b17  call    _CxxThrowException_0
0x180031b1d  mov     [rsp+1E8h+var_1C8], eax; int
0x180031b21  lea     r9, aSucceededHrFov; "SUCCEEDED(hr) || (fOverwriteIfNecessary"...
0x180031b28  mov     r8d, 73h ; 's'; unsigned int
0x180031b2e  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031b35  lea     rcx, [rsp+1E8h+var_108]; this
0x180031b3d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031b42  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031b49  lea     rcx, [rsp+1E8h+var_108]; pExceptionObject
0x180031b51  call    _CxxThrowException_0
0x180031b56  mov     [rsp+1E8h+var_1C8], eax; int
0x180031b5a  lea     r9, aNcryptsetprope_2; "NCryptSetProperty(hKey, NCRYPT_LENGTH_P"...
0x180031b61  mov     r8d, 8Ah; unsigned int
0x180031b67  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031b6e  lea     rcx, [rsp+1E8h+var_D8]; this
0x180031b76  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031b7b  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031b82  lea     rcx, [rsp+1E8h+var_D8]; pExceptionObject
0x180031b8a  call    _CxxThrowException_0
0x180031b8f  mov     [rsp+1E8h+var_1C8], eax; int
0x180031b93  lea     r9, aNcryptsetprope_4; "NCryptSetProperty(hKey, NCRYPT_KEY_USAG"...
0x180031b9a  mov     r8d, 8Fh; unsigned int
0x180031ba0  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031ba7  lea     rcx, [rsp+1E8h+var_A8]; this
0x180031baf  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031bb4  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031bbb  lea     rcx, [rsp+1E8h+var_A8]; pExceptionObject
0x180031bc3  call    _CxxThrowException_0
0x180031bc8  mov     [rsp+1E8h+var_1C8], eax; int
0x180031bcc  lea     r9, aNcryptfinalize_0; "NCryptFinalizeKey(hKey, acquireToFinali"...
0x180031bd3  mov     r8d, 92h; unsigned int
0x180031bd9  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031be0  lea     rcx, [rsp+1E8h+var_78]; this
0x180031be8  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031bed  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031bf4  lea     rcx, [rsp+1E8h+var_78]; pExceptionObject
0x180031bfc  call    _CxxThrowException_0
0x180031c01  mov     [rsp+1E8h+var_1C8], 8007000Eh; int
0x180031c09  lea     r9, aPcipher; "pCipher"
0x180031c10  mov     r8d, 95h; unsigned int
0x180031c16  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031c1d  lea     rcx, [rsp+1E8h+var_48]; this
0x180031c25  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031c2a  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031c31  lea     rcx, [rsp+1E8h+var_48]; pExceptionObject
0x180031c39  call    _CxxThrowException_0
```
