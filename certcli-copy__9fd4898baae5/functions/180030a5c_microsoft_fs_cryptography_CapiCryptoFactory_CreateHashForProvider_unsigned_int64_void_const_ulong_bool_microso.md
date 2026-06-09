# microsoft::fs::cryptography::CapiCryptoFactory::CreateHashForProvider(unsigned __int64,void const *,ulong,bool,microsoft::fs::common::FsException *)

- ea: `0x180030a5c`
- end: `0x180030c3f`
- name: `?CreateHashForProvider@CapiCryptoFactory@cryptography@fs@microsoft@@SAPEAVIHash@234@_KPEBXK_NPEAVFsException@common@34@@Z`
- size: `483`
- prototype: `static struct microsoft::fs::cryptography::IHash *(unsigned __int64, const void *, unsigned int, bool, struct microsoft::fs::common::FsException *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036600`
- `0x1800367c0`

## callees

- `0x180001514`
- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x18002ee04`
- `0x180030820`
- `0x180030a5c`
- `0x180030d90`
- `0x180030e4c`
- `0x180032bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ac2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b56`
- `CRYPTSP!CryptContextAddRef` at `0x180030ab8`
- `CRYPTSP!CryptContextAddRef` at `0x180030ab8`

## string_xrefs

- `0x180030a91`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x180030ae0`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x180030b74`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x180030beb`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x180030b67`: `CryptCreateHash(hProv, nAlgId, 0, 0, &hHash)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct microsoft::fs::cryptography::IHash *__fastcall microsoft::fs::cryptography::CapiCryptoFactory::CreateHashForProvider(
        HCRYPTPROV a1,
        const void *a2,
        unsigned int a3,
        __int64 a4,
        struct microsoft::fs::common::FsException *a5)
{
  DWORD LastError; // eax
  int v9; // eax
  struct microsoft::fs::common::FsException *v10; // r8
  unsigned int v11; // r9d
  DWORD dwValue; // edx
  DWORD v13; // eax
  int v14; // eax
  microsoft::fs::cryptography::CapiHash *v15; // rax
  bool v16; // r9
  __int64 v17; // rbx
  bool v19; // [rsp+20h] [rbp-F8h]
  unsigned __int64 v20; // [rsp+30h] [rbp-E8h] BYREF
  HCRYPTHASH v21[2]; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v23[48]; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v24[48]; // [rsp+A8h] [rbp-70h] BYREF
  _BYTE v25[48]; // [rsp+D8h] [rbp-40h] BYREF
  const microsoft::fs::common::FsException *v26; // [rsp+108h] [rbp-10h] BYREF

  try
  {
    if ( !a1 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        0xB9u,
        L"0 != hProvIn",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !CryptContextAddRef(a1, 0, 0) )
    {
      LastError = GetLastError();
      v9 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v23,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        0xBDu,
        L"CryptContextAddRef(hProvIn, 0, 0)",
        v9);
      throw (microsoft::fs::common::FsException *)v23;
    }
    microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>(
      &v20,
      a1);
    if ( a2 )
      dwValue = microsoft::fs::cryptography::CryptoUtil::GetCapiHashLookupEntry(a2, a3, v10)->dwValue;
    else
      dwValue = 32772;
    v21[0] = 0;
    if ( !(unsigned int)fsCryptCreateHash(v20, dwValue, (unsigned __int64)v10, v11, v21) )
    {
      v13 = GetLastError();
      v14 = HR_FROM_WIN32(v13);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        0xC5u,
        L"CryptCreateHash(hProv, nAlgId, 0, 0, &hHash)",
        v14);
      throw (microsoft::fs::common::FsException *)v24;
    }
    v15 = (microsoft::fs::cryptography::CapiHash *)operator new(0x20u);
    if ( v15 )
      v17 = microsoft::fs::cryptography::CapiHash::CapiHash(v15, v20, v21[0], v16, v19);
    else
      v17 = 0;
    v21[1] = v17;
    if ( !v17 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v25,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        0xC8u,
        L"pHash",
        -2147024882);
      throw (microsoft::fs::common::FsException *)v25;
    }
    v20 = 0;
  }
  catch ( const microsoft::fs::common::FsException *v26 )
  {
    throw;
  }
  catch ( ... )
  {
    throw;
  }
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::close(&v20);
  return (struct microsoft::fs::cryptography::IHash *)v17;
}

```

## disassembly

```asm
0x180030a5c  mov     [rsp+arg_8], rbx
0x180030a61  mov     [rsp+arg_10], rsi
0x180030a66  push    rdi
0x180030a67  sub     rsp, 110h
0x180030a6e  mov     esi, r8d
0x180030a71  mov     rdi, rdx
0x180030a74  mov     rbx, rcx
0x180030a77  test    rcx, rcx
0x180030a7a  jnz     short loc_180030AB3
0x180030a7c  mov     dword ptr [rsp+118h+var_F8], 80070057h; int
0x180030a84  lea     r9, a0Hprovin; "0 != hProvIn"
0x180030a8b  mov     r8d, 0B9h; unsigned int
0x180030a91  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030a98  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180030a9d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030aa2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030aa9  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180030aae  call    _CxxThrowException_0
0x180030ab3  xor     r8d, r8d; dwFlags
0x180030ab6  xor     edx, edx; pdwReserved
0x180030ab8  call    cs:__imp_CryptContextAddRef
0x180030abe  test    eax, eax
0x180030ac0  jnz     short loc_180030B02
0x180030ac2  call    cs:__imp_GetLastError
0x180030ac8  mov     ecx, eax; unsigned int
0x180030aca  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180030acf  mov     dword ptr [rsp+118h+var_F8], eax; int
0x180030ad3  lea     r9, aCryptcontextad_0; "CryptContextAddRef(hProvIn, 0, 0)"
0x180030ada  mov     r8d, 0BDh; unsigned int
0x180030ae0  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030ae7  lea     rcx, [rsp+118h+var_A0]; this
0x180030aec  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030af1  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030af8  lea     rcx, [rsp+118h+var_A0]; pExceptionObject
0x180030afd  call    _CxxThrowException_0
0x180030b02  mov     rdx, rbx
0x180030b05  lea     rcx, [rsp+118h+var_E8]
0x180030b0a  call    ??0?$auto_handle_t@_K$0A@VCloseCapiProviderFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAA@_K_N@Z; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>(unsigned __int64,bool)
0x180030b0f  nop
0x180030b10  mov     [rsp+118h+arg_0], 0
0x180030b1c  test    rdi, rdi
0x180030b1f  jnz     short loc_180030B28
0x180030b21  mov     edx, 8004h
0x180030b26  jmp     short loc_180030B35
0x180030b28  mov     edx, esi; unsigned int
0x180030b2a  mov     rcx, rdi; void *
0x180030b2d  call    ?GetCapiHashLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBU_CRYPT_OID_INFO@@PEBXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetCapiHashLookupEntry(void const *,ulong,microsoft::fs::common::FsException *)
0x180030b32  mov     edx, [rax+1Ch]; unsigned int
0x180030b35  mov     [rsp+118h+var_E0], 0
0x180030b3e  lea     rax, [rsp+118h+var_E0]
0x180030b43  mov     qword ptr [rsp+118h+var_F8], rax; bool
0x180030b48  mov     rcx, [rsp+118h+var_E8]; unsigned __int64
0x180030b4d  call    ?fsCryptCreateHash@@YAH_KI0KPEA_K@Z; fsCryptCreateHash(unsigned __int64,uint,unsigned __int64,ulong,unsigned __int64 *)
0x180030b52  test    eax, eax
0x180030b54  jnz     short loc_180030B9C
0x180030b56  call    cs:__imp_GetLastError
0x180030b5c  mov     ecx, eax; unsigned int
0x180030b5e  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180030b63  mov     dword ptr [rsp+118h+var_F8], eax; int
0x180030b67  lea     r9, aCryptcreatehas_1; "CryptCreateHash(hProv, nAlgId, 0, 0, &h"...
0x180030b6e  mov     r8d, 0C5h; unsigned int
0x180030b74  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030b7b  lea     rcx, [rsp+118h+var_70]; this
0x180030b83  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030b88  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030b8f  lea     rcx, [rsp+118h+var_70]; pExceptionObject
0x180030b97  call    _CxxThrowException_0
0x180030b9c  mov     ecx, 20h ; ' '; Size
0x180030ba1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030ba6  mov     [rsp+118h+arg_20], rax
0x180030bae  test    rax, rax
0x180030bb1  jz      short loc_180030BCA
0x180030bb3  mov     r8, [rsp+118h+var_E0]; unsigned __int64
0x180030bb8  mov     rdx, [rsp+118h+var_E8]; unsigned __int64
0x180030bbd  mov     rcx, rax; this
0x180030bc0  call    ??0CapiHash@cryptography@fs@microsoft@@QEAA@_K0_N1@Z; microsoft::fs::cryptography::CapiHash::CapiHash(unsigned __int64,unsigned __int64,bool,bool)
0x180030bc5  mov     rbx, rax
0x180030bc8  jmp     short loc_180030BCC
0x180030bca  xor     ebx, ebx
0x180030bcc  mov     [rsp+118h+var_D8], rbx
0x180030bd1  test    rbx, rbx
0x180030bd4  jnz     short loc_180030C13
0x180030bd6  mov     dword ptr [rsp+118h+var_F8], 8007000Eh; int
0x180030bde  lea     r9, aPhash; "pHash"
0x180030be5  mov     r8d, 0C8h; unsigned int
0x180030beb  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030bf2  lea     rcx, [rsp+118h+var_40]; this
0x180030bfa  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030bff  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030c06  lea     rcx, [rsp+118h+var_40]; pExceptionObject
0x180030c0e  call    _CxxThrowException_0
0x180030c13  mov     [rsp+118h+var_E8], 0
0x180030c1c  lea     rcx, [rsp+118h+var_E8]
0x180030c21  call    ?close@?$auto_handle_t@_K$0A@VCloseCapiProviderFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::close(void)
0x180030c26  nop
0x180030c27  mov     rax, rbx
0x180030c2a  lea     r11, [rsp+118h+var_8]
0x180030c32  mov     rbx, [r11+18h]
0x180030c36  mov     rsi, [r11+20h]
0x180030c3a  mov     rsp, r11
0x180030c3d  pop     rdi
0x180030c3e  retn
```
