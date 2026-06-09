# microsoft::fs::cryptography::CngCryptoFactory::CreateHash(ushort const *,ushort const *,microsoft::fs::common::FsException *)

- ea: `0x180031c48`
- end: `0x180031e9a`
- name: `?CreateHash@CngCryptoFactory@cryptography@fs@microsoft@@SAPEAVIHash@234@PEBG0PEAVFsException@common@34@@Z`
- size: `594`
- prototype: `struct microsoft::fs::cryptography::IHash *__fastcall(const unsigned __int16 *, const unsigned __int16 *, struct microsoft::fs::common::FsException *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002ff74`
- `0x18003bed3`

## callees

- `0x180001514`
- `0x180001798`
- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x18002e604`
- `0x180031c48`
- `0x180032048`
- `0x1800320c0`
- `0x1800323e4`
- `0x180032464`
- `0x180037dbc`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180031e74`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180031e74`

## string_xrefs

- `0x180031c7d`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031cc6`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031d3e`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031db4`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031e38`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`
- `0x180031cb9`: `BCryptOpenAlgorithmProvider(&hProv, pwszAlgorithm, pwszProvider, 0)`
- `0x180031da7`: `BCryptCreateHash(hProv, &hHash, pbHashObject, cbHashObject, 0, 0, 0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
struct microsoft::fs::cryptography::IHash *__fastcall microsoft::fs::cryptography::CngCryptoFactory::CreateHash(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct microsoft::fs::common::FsException *a3)
{
  int v3; // eax
  void *v4; // r8
  unsigned int v5; // r9d
  const unsigned __int16 *v6; // r11
  int v7; // eax
  int Property; // eax
  int Hash; // eax
  microsoft::fs::cryptography::CngBCryptHash *v10; // rax
  microsoft::fs::cryptography::CngBCryptHash *v11; // rbx
  unsigned int v12; // edx
  unsigned __int8 *v14; // [rsp+20h] [rbp-158h]
  ULONG v15; // [rsp+28h] [rbp-150h]
  unsigned int v16; // [rsp+30h] [rbp-148h]
  unsigned int v17; // [rsp+40h] [rbp-138h] BYREF
  void *v18; // [rsp+48h] [rbp-130h] BYREF
  unsigned __int8 *v19; // [rsp+50h] [rbp-128h] BYREF
  ULONG v20; // [rsp+58h] [rbp-120h] BYREF
  void *v21[2]; // [rsp+60h] [rbp-118h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp-108h] BYREF
  _BYTE v23[48]; // [rsp+A0h] [rbp-D8h] BYREF
  _BYTE v24[48]; // [rsp+D0h] [rbp-A8h] BYREF
  _BYTE v25[48]; // [rsp+100h] [rbp-78h] BYREF
  _BYTE v26[48]; // [rsp+130h] [rbp-48h] BYREF
  const microsoft::fs::common::FsException *v27; // [rsp+160h] [rbp-18h] BYREF

  try
  {
    v3 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
    if ( v3 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        181,
        L"StringCchLengthW(pwszAlgorithm, STRSAFE_MAX_CCH, 0)",
        v3);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v18 = v4;
    v7 = fsBCryptOpenAlgorithmProvider(&v18, v6, (const unsigned __int16 *)v4, v5);
    if ( v7 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v23,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        186,
        L"BCryptOpenAlgorithmProvider(&hProv, pwszAlgorithm, pwszProvider, 0)",
        v7);
      throw (microsoft::fs::common::FsException *)v23;
    }
    v17 = 0;
    v20 = 4;
    Property = fsBCryptGetProperty(v18, L"ObjectLength", (unsigned __int8 *)&v17, 4u, &v20, 0);
    if ( Property < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        197,
        L"BCryptGetProperty( hProv, BCRYPT_OBJECT_LENGTH, reinterpret_cast<BYTE*>(&cbHashObject), cbcbHashObject, &cbcbHashObject, 0)",
        Property);
      throw (microsoft::fs::common::FsException *)v24;
    }
    operator new[](v17);
    microsoft::fs::common::auto_array<unsigned char>::auto_array<unsigned char>(&v19);
    v21[0] = 0;
    Hash = fsBCryptCreateHash(v18, v21, v19, v17, v14, v15, v16);
    if ( Hash < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v25,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        201,
        L"BCryptCreateHash(hProv, &hHash, pbHashObject, cbHashObject, 0, 0, 0)",
        Hash);
      throw (microsoft::fs::common::FsException *)v25;
    }
    v10 = (microsoft::fs::cryptography::CngBCryptHash *)operator new(0x28u);
    if ( v10 )
      v11 = microsoft::fs::cryptography::CngBCryptHash::CngBCryptHash(v10, v18, v21[0], v19, v17);
    else
      v11 = 0;
    v21[1] = v11;
    if ( !v11 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v26,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
        204,
        L"pHash",
        -2147024882);
      throw (microsoft::fs::common::FsException *)v26;
    }
    v19 = 0;
    v18 = 0;
    operator delete[](0);
    v19 = 0;
  }
  catch ( const microsoft::fs::common::FsException *v27 )
  {
    throw;
  }
  catch ( ... )
  {
    throw;
  }
  microsoft::fs::common::auto_handle_t<void *,0,microsoft::fs::cryptography::CloseCngBCryptProviderFunctor>::close(
    &v18,
    v12);
  return v11;
}

```

## disassembly

```asm
0x180031c48  mov     [rsp+arg_10], r8
0x180031c4d  push    rbx
0x180031c4e  sub     rsp, 170h
0x180031c55  mov     r11, rdx
0x180031c58  xor     r8d, r8d; unsigned __int64 *
0x180031c5b  mov     edx, 7FFFFFFFh; unsigned __int64
0x180031c60  mov     rcx, r11; unsigned __int16 *
0x180031c63  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031c68  test    eax, eax
0x180031c6a  jns     short loc_180031C9F
0x180031c6c  mov     dword ptr [rsp+178h+var_158], eax; int
0x180031c70  lea     r9, aStringcchlengt_2; "StringCchLengthW(pwszAlgorithm, STRSAFE"...
0x180031c77  mov     r8d, 0B5h; unsigned int
0x180031c7d  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031c84  lea     rcx, [rsp+178h+pExceptionObject]; this
0x180031c89  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031c8e  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031c95  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180031c9a  call    _CxxThrowException_0
0x180031c9f  mov     [rsp+178h+var_130], r8
0x180031ca4  mov     rdx, r11; unsigned __int16 *
0x180031ca7  lea     rcx, [rsp+178h+var_130]; void **
0x180031cac  call    ?fsBCryptOpenAlgorithmProvider@@YAJPEAPEAXPEBG1K@Z; fsBCryptOpenAlgorithmProvider(void * *,ushort const *,ushort const *,ulong)
0x180031cb1  test    eax, eax
0x180031cb3  jns     short loc_180031CEE
0x180031cb5  mov     dword ptr [rsp+178h+var_158], eax; int
0x180031cb9  lea     r9, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider(&hProv, pws"...
0x180031cc0  mov     r8d, 0BAh; unsigned int
0x180031cc6  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031ccd  lea     rcx, [rsp+178h+var_D8]; this
0x180031cd5  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031cda  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031ce1  lea     rcx, [rsp+178h+var_D8]; pExceptionObject
0x180031ce9  call    _CxxThrowException_0
0x180031cee  mov     [rsp+178h+var_138], 0
0x180031cf6  mov     r9d, 4; unsigned int
0x180031cfc  mov     [rsp+178h+var_120], r9d
0x180031d01  mov     [rsp+178h+var_150], 0; unsigned int
0x180031d09  lea     rax, [rsp+178h+var_120]
0x180031d0e  mov     [rsp+178h+var_158], rax; unsigned __int8 *
0x180031d13  lea     r8, [rsp+178h+var_138]; unsigned __int8 *
0x180031d18  lea     rdx, aObjectlength; "ObjectLength"
0x180031d1f  mov     rcx, [rsp+178h+var_130]; void *
0x180031d24  call    ?fsBCryptGetProperty@@YAJPEAXPEBGPEAEKPEAKK@Z; fsBCryptGetProperty(void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x180031d29  test    eax, eax
0x180031d2b  jns     short loc_180031D66
0x180031d2d  mov     dword ptr [rsp+178h+var_158], eax; int
0x180031d31  lea     r9, aBcryptgetprope_0; "BCryptGetProperty( hProv, BCRYPT_OBJECT"...
0x180031d38  mov     r8d, 0C5h; unsigned int
0x180031d3e  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031d45  lea     rcx, [rsp+178h+var_A8]; this
0x180031d4d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031d52  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031d59  lea     rcx, [rsp+178h+var_A8]; pExceptionObject
0x180031d61  call    _CxxThrowException_0
0x180031d66  mov     ecx, [rsp+178h+var_138]; unsigned __int64
0x180031d6a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180031d6f  mov     rdx, rax
0x180031d72  lea     rcx, [rsp+178h+var_128]
0x180031d77  call    ??0?$auto_array@E@common@fs@microsoft@@QEAA@PEAE_N@Z; microsoft::fs::common::auto_array<uchar>::auto_array<uchar>(uchar *,bool)
0x180031d7c  nop
0x180031d7d  mov     [rsp+178h+var_118], 0
0x180031d86  mov     r9d, [rsp+178h+var_138]; unsigned int
0x180031d8b  mov     r8, [rsp+178h+var_128]; unsigned __int8 *
0x180031d90  lea     rdx, [rsp+178h+var_118]; void **
0x180031d95  mov     rcx, [rsp+178h+var_130]; void *
0x180031d9a  call    ?fsBCryptCreateHash@@YAJPEAXPEAPEAXPEAEK2KK@Z; fsBCryptCreateHash(void *,void * *,uchar *,ulong,uchar *,ulong,ulong)
0x180031d9f  test    eax, eax
0x180031da1  jns     short loc_180031DDC
0x180031da3  mov     dword ptr [rsp+178h+var_158], eax; int
0x180031da7  lea     r9, aBcryptcreateha_0; "BCryptCreateHash(hProv, &hHash, pbHashO"...
0x180031dae  mov     r8d, 0C9h; unsigned int
0x180031db4  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031dbb  lea     rcx, [rsp+178h+var_78]; this
0x180031dc3  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031dc8  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031dcf  lea     rcx, [rsp+178h+var_78]; pExceptionObject
0x180031dd7  call    _CxxThrowException_0
0x180031ddc  mov     ecx, 28h ; '('; Size
0x180031de1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031de6  mov     [rsp+178h+arg_10], rax
0x180031dee  test    rax, rax
0x180031df1  jz      short loc_180031E17
0x180031df3  mov     ecx, [rsp+178h+var_138]
0x180031df7  mov     dword ptr [rsp+178h+var_158], ecx; unsigned int
0x180031dfb  mov     r9, [rsp+178h+var_128]; unsigned __int8 *
0x180031e00  mov     r8, [rsp+178h+var_118]; void *
0x180031e05  mov     rdx, [rsp+178h+var_130]; void *
0x180031e0a  mov     rcx, rax; this
0x180031e0d  call    ??0CngBCryptHash@cryptography@fs@microsoft@@QEAA@PEAX0PEAEK@Z; microsoft::fs::cryptography::CngBCryptHash::CngBCryptHash(void *,void *,uchar *,ulong)
0x180031e12  mov     rbx, rax
0x180031e15  jmp     short loc_180031E19
0x180031e17  xor     ebx, ebx
0x180031e19  mov     [rsp+178h+var_110], rbx
0x180031e1e  test    rbx, rbx
0x180031e21  jnz     short loc_180031E60
0x180031e23  mov     dword ptr [rsp+178h+var_158], 8007000Eh; int
0x180031e2b  lea     r9, aPhash; "pHash"
0x180031e32  mov     r8d, 0CCh; unsigned int
0x180031e38  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x180031e3f  lea     rcx, [rsp+178h+var_48]; this
0x180031e47  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180031e4c  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180031e53  lea     rcx, [rsp+178h+var_48]; pExceptionObject
0x180031e5b  call    _CxxThrowException_0
0x180031e60  mov     [rsp+178h+var_128], 0
0x180031e69  mov     [rsp+178h+var_130], 0
0x180031e72  xor     ecx, ecx
0x180031e74  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031e7a  mov     [rsp+178h+var_128], 0
0x180031e83  lea     rcx, [rsp+178h+var_130]
0x180031e88  call    ?close@?$auto_handle_t@PEAX$0A@VCloseCngBCryptProviderFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<void *,0,microsoft::fs::cryptography::CloseCngBCryptProviderFunctor>::close(void)
0x180031e8d  nop
0x180031e8e  mov     rax, rbx
0x180031e91  add     rsp, 170h
0x180031e98  pop     rbx
0x180031e99  retn
```
