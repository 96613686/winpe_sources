# microsoft::fs::cryptography::CngBCryptCipher::Sign(uchar *,ulong *,uchar const *,ulong,void const *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180034bf0`
- end: `0x180034dbf`
- name: `?Sign@CngBCryptCipher@cryptography@fs@microsoft@@UEAAXPEAEPEAKPEBEKPEBXKPEAVFsException@common@34@@Z`
- size: `463`
- prototype: `void(microsoft::fs::cryptography::CngBCryptCipher *__hidden this, unsigned __int8 *, unsigned int *, const unsigned __int8 *, unsigned int, const void *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e71c`
- `0x180034bf0`
- `0x18003f010`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180034d26`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180034d26`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d37`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d49`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d57`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d64`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d37`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d49`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d57`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034d64`
- `bcrypt!BCryptSignHash` at `0x180034d15`
- `bcrypt!BCryptSignHash` at `0x180034d15`

## string_xrefs

- `0x180034c42`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034c84`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034d7f`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall microsoft::fs::cryptography::CngBCryptCipher::Sign(
        microsoft::fs::cryptography::CngBCryptCipher *this,
        unsigned __int8 *a2,
        struct microsoft::fs::common::FsException *a3,
        UCHAR *a4,
        ULONG cbInput,
        const unsigned __int16 **pPaddingInfo,
        ULONG a7,
        struct microsoft::fs::common::FsException *a8)
{
  ULONG dwFlags; // edi
  const wchar_t **v13; // rbx
  ULONG v14; // r12d
  NTSTATUS v15; // ebx
  const struct microsoft::fs::common::FsException *v16; // rax
  const wchar_t *v17; // [rsp+40h] [rbp-108h] BYREF
  const microsoft::fs::common::FsException *v18; // [rsp+48h] [rbp-100h] BYREF
  _QWORD v19[6]; // [rsp+50h] [rbp-F8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+80h] [rbp-C8h] BYREF
  _BYTE v21[48]; // [rsp+B0h] [rbp-98h] BYREF
  _BYTE v22[104]; // [rsp+E0h] [rbp-68h] BYREF

  try
  {
    if ( a8 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a8 + 8LL))(a8);
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        0x1F3u,
        L"pcbSignature",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a4 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v21,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        0x1F4u,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v21;
    }
    dwFlags = a7;
    v13 = pPaddingInfo;
    microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(pPaddingInfo, a7, a3);
    v17 = L"SHA1";
    if ( *((_BYTE *)this + 542) && !pPaddingInfo )
    {
      v13 = &v17;
      dwFlags = 2;
    }
    v14 = *(_DWORD *)a3;
    v15 = BCryptSignHash(*((BCRYPT_KEY_HANDLE *)this + 73), v13, a4, cbInput, a2, *(_DWORD *)a3, (ULONG *)a3, dwFlags);
    if ( v15 || DbgIsSSActive(0x404u) )
    {
      CSPrintErrorLineFile(0x4340C25u, v15);
      CSPrintErrorLineFile(0x4350C25u, cbInput);
      CSPrintErrorLineFile(0x4360C25u, v14);
      CSPrintErrorLineFile(0x4370C25u, dwFlags);
      if ( v15 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v22,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
          0x20Bu,
          L"BCryptSignHash( m_hKey, const_cast<void*>(pPaddingInfo), const_cast<BYTE*>(pbHash), cbHash, pbSignature, *pcbS"
           "ignature, pcbSignature, fPadding)",
          v15);
        throw (microsoft::fs::common::FsException *)v22;
      }
    }
  }
  catch ( const microsoft::fs::common::FsException *v18 )
  {
    if ( !a8 )
      throw;
    microsoft::fs::common::FsException::assign(a8, v18);
    return;
  }
  catch ( ... )
  {
    if ( !a8 )
      throw;
    v16 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v19,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
                                                               0x215u,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a8, v16);
    v19[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v19[1]);
    operator delete[]((void *)v19[2]);
    operator delete[]((void *)v19[3]);
    operator delete[]((void *)v19[5]);
  }
}

```

## disassembly

```asm
0x180034bf0  push    rbx
0x180034bf2  push    rsi
0x180034bf3  push    rdi
0x180034bf4  push    r12
0x180034bf6  push    r13
0x180034bf8  push    r14
0x180034bfa  push    r15
0x180034bfc  sub     rsp, 110h
0x180034c03  mov     r14, r9
0x180034c06  mov     rsi, r8
0x180034c09  mov     r13, rdx
0x180034c0c  mov     r15, rcx
0x180034c0f  mov     rcx, [rsp+148h+arg_38]
0x180034c17  test    rcx, rcx
0x180034c1a  jz      short loc_180034C28
0x180034c1c  mov     rax, [rcx]
0x180034c1f  mov     rax, [rax+8]
0x180034c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c28  test    rsi, rsi
0x180034c2b  jnz     short loc_180034C6A
0x180034c2d  mov     dword ptr [rsp+148h+pbOutput], 80070057h; int
0x180034c35  lea     r9, aPcbsignature; "pcbSignature"
0x180034c3c  mov     r8d, 1F3h; unsigned int
0x180034c42  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034c49  lea     rcx, [rsp+148h+pExceptionObject]; this
0x180034c51  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034c56  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034c5d  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180034c65  call    _CxxThrowException_0
0x180034c6a  test    r14, r14
0x180034c6d  jnz     short loc_180034CAC
0x180034c6f  mov     dword ptr [rsp+148h+pbOutput], 80070057h; int
0x180034c77  lea     r9, aPbhash; "pbHash"
0x180034c7e  mov     r8d, 1F4h; unsigned int
0x180034c84  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034c8b  lea     rcx, [rsp+148h+var_98]; this
0x180034c93  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034c98  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034c9f  lea     rcx, [rsp+148h+var_98]; pExceptionObject
0x180034ca7  call    _CxxThrowException_0
0x180034cac  mov     edi, [rsp+148h+arg_30]
0x180034cb3  mov     edx, edi; unsigned int
0x180034cb5  mov     rbx, [rsp+148h+pPaddingInfo]
0x180034cbd  mov     rcx, rbx; void *
0x180034cc0  call    ?CheckSignaturePaddingInfo@CryptoUtil@cryptography@fs@microsoft@@SAXPEBXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(void const *,ulong,microsoft::fs::common::FsException *)
0x180034cc5  lea     rax, aSha1; "SHA1"
0x180034ccc  mov     [rsp+148h+var_108], rax
0x180034cd1  cmp     byte ptr [r15+21Eh], 0
0x180034cd9  jz      short loc_180034CEA
0x180034cdb  test    rbx, rbx
0x180034cde  jnz     short loc_180034CEA
0x180034ce0  lea     rbx, [rsp+148h+var_108]
0x180034ce5  mov     edi, 2
0x180034cea  mov     r12d, [rsi]
0x180034ced  mov     [rsp+148h+dwFlags], edi; dwFlags
0x180034cf1  mov     [rsp+148h+pcbResult], rsi; pcbResult
0x180034cf6  mov     [rsp+148h+cbOutput], r12d; cbOutput
0x180034cfb  mov     [rsp+148h+pbOutput], r13; pbOutput
0x180034d00  mov     r9d, [rsp+148h+cbInput]; cbInput
0x180034d08  mov     r8, r14; pbInput
0x180034d0b  mov     rdx, rbx; pPaddingInfo
0x180034d0e  mov     rcx, [r15+248h]; hKey
0x180034d15  call    cs:__imp_BCryptSignHash
0x180034d1b  mov     ebx, eax
0x180034d1d  test    eax, eax
0x180034d1f  jnz     short loc_180034D30
0x180034d21  mov     ecx, 404h
0x180034d26  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180034d2c  test    eax, eax
0x180034d2e  jz      short loc_180034DA8
0x180034d30  mov     edx, ebx
0x180034d32  mov     ecx, 4340C25h
0x180034d37  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034d3d  mov     edx, [rsp+148h+cbInput]
0x180034d44  mov     ecx, 4350C25h
0x180034d49  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034d4f  mov     edx, r12d
0x180034d52  mov     ecx, 4360C25h
0x180034d57  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034d5d  mov     edx, edi
0x180034d5f  mov     ecx, 4370C25h
0x180034d64  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034d6a  test    ebx, ebx
0x180034d6c  jns     short loc_180034DA8
0x180034d6e  mov     dword ptr [rsp+148h+pbOutput], ebx; int
0x180034d72  lea     r9, aBcryptsignhash_0; "BCryptSignHash( m_hKey, const_cast<void"...
0x180034d79  mov     r8d, 20Bh; unsigned int
0x180034d7f  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034d86  lea     rcx, [rsp+148h+var_68]; this
0x180034d8e  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034d93  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034d9a  lea     rcx, [rsp+148h+var_68]; pExceptionObject
0x180034da2  call    _CxxThrowException_0
0x180034da8  jmp     short loc_180034DAC
0x180034daa  jmp     short $+2
0x180034dac  add     rsp, 110h
0x180034db3  pop     r15
0x180034db5  pop     r14
0x180034db7  pop     r13
0x180034db9  pop     r12
0x180034dbb  pop     rdi
0x180034dbc  pop     rsi
0x180034dbd  pop     rbx
0x180034dbe  retn
```
