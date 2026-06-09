# microsoft::fs::cryptography::CngBCryptCipher::Verify(uchar const *,ulong,uchar const *,ulong,void const *,ulong,long *,microsoft::fs::common::FsException *)

- ea: `0x180034e40`
- end: `0x180034fe1`
- name: `?Verify@CngBCryptCipher@cryptography@fs@microsoft@@UEAAXPEBEK0KPEBXKPEAJPEAVFsException@common@34@@Z`
- size: `417`
- prototype: `void(microsoft::fs::cryptography::CngBCryptCipher *__hidden this, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const void *, unsigned int, int *, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e71c`
- `0x180034e40`
- `0x18003f010`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180034f6c`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180034f6c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034f7d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034f8f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034f9d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034faa`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034fc5`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034f7d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034f8f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034f9d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034faa`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180034fc5`
- `bcrypt!BCryptVerifySignature` at `0x180034f5b`
- `bcrypt!BCryptVerifySignature` at `0x180034f5b`

## string_xrefs

- `0x180034e90`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034ed2`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CngBCryptCipher::Verify(
        microsoft::fs::cryptography::CngBCryptCipher *this,
        UCHAR *a2,
        struct microsoft::fs::common::FsException *a3,
        UCHAR *a4,
        ULONG cbHash,
        const unsigned __int16 **pPaddingInfo,
        ULONG a7,
        int *a8,
        unsigned __int16 **a9)
{
  ULONG cbSignature; // r12d
  ULONG dwFlags; // edi
  const wchar_t **v14; // rbx
  NTSTATUS v15; // ebx
  unsigned __int16 **v16; // rax
  const wchar_t *v17; // [rsp+40h] [rbp-D8h] BYREF
  unsigned __int16 **v18; // [rsp+48h] [rbp-D0h] BYREF
  _QWORD v19[6]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+80h] [rbp-98h] BYREF
  _BYTE v21[104]; // [rsp+B0h] [rbp-68h] BYREF

  cbSignature = (unsigned int)a3;
  try
  {
    if ( a9 )
      (*((void (__fastcall **)(unsigned __int16 **))*a9 + 1))(a9);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        552,
        L"pbSignature",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a4 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v21,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        553,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v21;
    }
    dwFlags = a7;
    v14 = pPaddingInfo;
    microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(pPaddingInfo, a7, a3);
    v17 = L"SHA1";
    if ( *((_BYTE *)this + 542) && !pPaddingInfo )
    {
      v14 = &v17;
      dwFlags = 2;
    }
    v15 = BCryptVerifySignature(*((BCRYPT_KEY_HANDLE *)this + 73), v14, a4, cbHash, a2, cbSignature, dwFlags);
    if ( v15 || DbgIsSSActive(0x404u) )
    {
      CSPrintErrorLineFile(0x4550C25u, v15);
      CSPrintErrorLineFile(0x4560C25u, cbHash);
      CSPrintErrorLineFile(0x4570C25u, cbSignature);
      CSPrintErrorLineFile(0x4580C25u, dwFlags);
    }
    *a8 = v15;
    if ( v15 )
      CSPrintErrorLineFile(0x23F0C1Eu, v15);
  }
  catch ( const microsoft::fs::common::FsException *v18 )
  {
    if ( !a9 )
      throw;
    microsoft::fs::common::FsException::assign(a9, v18);
    return;
  }
  catch ( ... )
  {
    if ( !a9 )
      throw;
    v16 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                                 (microsoft::fs::common::FsException *)v19,
                                 L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
                                 585,
                                 &psz,
                                 -2147467259,
                                 L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a9, v16);
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
0x180034e40  push    rbx
0x180034e42  push    rsi
0x180034e43  push    rdi
0x180034e44  push    r12
0x180034e46  push    r14
0x180034e48  push    r15
0x180034e4a  sub     rsp, 0E8h
0x180034e51  mov     rsi, r9
0x180034e54  mov     r12d, r8d
0x180034e57  mov     r14, rdx
0x180034e5a  mov     r15, rcx
0x180034e5d  mov     rcx, [rsp+118h+arg_40]
0x180034e65  test    rcx, rcx
0x180034e68  jz      short loc_180034E76
0x180034e6a  mov     rax, [rcx]
0x180034e6d  mov     rax, [rax+8]
0x180034e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e76  test    r14, r14
0x180034e79  jnz     short loc_180034EB8
0x180034e7b  mov     dword ptr [rsp+118h+pbSignature], 80070057h; int
0x180034e83  lea     r9, aPbsignature; "pbSignature"
0x180034e8a  mov     r8d, 228h; unsigned int
0x180034e90  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034e97  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180034e9f  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034ea4  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034eab  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180034eb3  call    _CxxThrowException_0
0x180034eb8  test    rsi, rsi
0x180034ebb  jnz     short loc_180034EFA
0x180034ebd  mov     dword ptr [rsp+118h+pbSignature], 80070057h; int
0x180034ec5  lea     r9, aPbhash; "pbHash"
0x180034ecc  mov     r8d, 229h; unsigned int
0x180034ed2  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034ed9  lea     rcx, [rsp+118h+var_68]; this
0x180034ee1  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034ee6  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034eed  lea     rcx, [rsp+118h+var_68]; pExceptionObject
0x180034ef5  call    _CxxThrowException_0
0x180034efa  mov     edi, [rsp+118h+arg_30]
0x180034f01  mov     edx, edi; unsigned int
0x180034f03  mov     rbx, [rsp+118h+pPaddingInfo]
0x180034f0b  mov     rcx, rbx; void *
0x180034f0e  call    ?CheckSignaturePaddingInfo@CryptoUtil@cryptography@fs@microsoft@@SAXPEBXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(void const *,ulong,microsoft::fs::common::FsException *)
0x180034f13  lea     rax, aSha1; "SHA1"
0x180034f1a  mov     [rsp+118h+var_D8], rax
0x180034f1f  cmp     byte ptr [r15+21Eh], 0
0x180034f27  jz      short loc_180034F38
0x180034f29  test    rbx, rbx
0x180034f2c  jnz     short loc_180034F38
0x180034f2e  lea     rbx, [rsp+118h+var_D8]
0x180034f33  mov     edi, 2
0x180034f38  mov     [rsp+118h+dwFlags], edi; dwFlags
0x180034f3c  mov     [rsp+118h+cbSignature], r12d; cbSignature
0x180034f41  mov     [rsp+118h+pbSignature], r14; pbSignature
0x180034f46  mov     r9d, [rsp+118h+cbHash]; cbHash
0x180034f4e  mov     r8, rsi; pbHash
0x180034f51  mov     rdx, rbx; pPaddingInfo
0x180034f54  mov     rcx, [r15+248h]; hKey
0x180034f5b  call    cs:__imp_BCryptVerifySignature
0x180034f61  mov     ebx, eax
0x180034f63  test    eax, eax
0x180034f65  jnz     short loc_180034F76
0x180034f67  mov     ecx, 404h
0x180034f6c  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180034f72  test    eax, eax
0x180034f74  jz      short loc_180034FB0
0x180034f76  mov     edx, ebx
0x180034f78  mov     ecx, 4550C25h
0x180034f7d  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034f83  mov     edx, [rsp+118h+cbHash]
0x180034f8a  mov     ecx, 4560C25h
0x180034f8f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034f95  mov     edx, r12d
0x180034f98  mov     ecx, 4570C25h
0x180034f9d  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034fa3  mov     edx, edi
0x180034fa5  mov     ecx, 4580C25h
0x180034faa  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034fb0  mov     rax, [rsp+118h+arg_38]
0x180034fb8  mov     [rax], ebx
0x180034fba  test    ebx, ebx
0x180034fbc  jz      short loc_180034FCC
0x180034fbe  mov     edx, ebx
0x180034fc0  mov     ecx, 23F0C1Eh
0x180034fc5  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180034fcb  nop
0x180034fcc  jmp     short loc_180034FD0
0x180034fce  jmp     short $+2
0x180034fd0  add     rsp, 0E8h
0x180034fd7  pop     r15
0x180034fd9  pop     r14
0x180034fdb  pop     r12
0x180034fdd  pop     rdi
0x180034fde  pop     rsi
0x180034fdf  pop     rbx
0x180034fe0  retn
```
