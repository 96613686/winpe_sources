# microsoft::fs::cryptography::CngNCryptCipher::Verify(uchar const *,ulong,uchar const *,ulong,void const *,ulong,long *,microsoft::fs::common::FsException *)

- ea: `0x180037bc0`
- end: `0x180037d34`
- name: `?Verify@CngNCryptCipher@cryptography@fs@microsoft@@UEAAXPEBEK0KPEBXKPEAJPEAVFsException@common@34@@Z`
- size: `372`
- prototype: `void(microsoft::fs::cryptography::CngNCryptCipher *__hidden this, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const void *, unsigned int, int *, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e71c`
- `0x180037bc0`
- `0x18003f010`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180037cc1`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180037cc1`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037cd2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037ce4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037cf2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037cff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037d1a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037cd2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037ce4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037cf2`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037cff`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037d1a`
- `ncrypt!NCryptVerifySignature` at `0x180037cb0`
- `ncrypt!NCryptVerifySignature` at `0x180037cb0`

## string_xrefs

- `0x180037c0e`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x180037c4a`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CngNCryptCipher::Verify(
        microsoft::fs::cryptography::CngNCryptCipher *this,
        BYTE *a2,
        struct microsoft::fs::common::FsException *a3,
        BYTE *a4,
        DWORD cbHashValue,
        const unsigned __int16 **pPaddingInfo,
        DWORD dwFlags,
        int *a8,
        unsigned __int16 **a9)
{
  DWORD cbSignature; // r14d
  SECURITY_STATUS v13; // ebx
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v16[6]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v18[96]; // [rsp+A8h] [rbp-60h] BYREF

  cbSignature = (unsigned int)a3;
  try
  {
    if ( a9 )
      (*((void (__fastcall **)(unsigned __int16 **))*a9 + 1))(a9);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        478,
        L"pbSignature",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a4 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v18,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        479,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v18;
    }
    microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(pPaddingInfo, dwFlags, a3);
    v13 = NCryptVerifySignature(*((_QWORD *)this + 68), pPaddingInfo, a4, cbHashValue, a2, cbSignature, dwFlags);
    if ( v13 || DbgIsSSActive(0x404u) )
    {
      CSPrintErrorLineFile(0x62C0C25u, v13);
      CSPrintErrorLineFile(0x62D0C25u, cbHashValue);
      CSPrintErrorLineFile(0x62E0C25u, cbSignature);
      CSPrintErrorLineFile(0x62F0C25u, dwFlags);
    }
    *a8 = v13;
    if ( v13 )
      CSPrintErrorLineFile(0x1EB0C1Fu, v13);
  }
  catch ( const microsoft::fs::common::FsException *v15 )
  {
    if ( !a9 )
      throw;
    microsoft::fs::common::FsException::assign(a9, v15);
    return;
  }
  catch ( ... )
  {
    if ( !a9 )
      throw;
    v14 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                                 (microsoft::fs::common::FsException *)v16,
                                 L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
                                 501,
                                 &psz,
                                 -2147467259,
                                 L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a9, v14);
    v16[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v16[1]);
    operator delete[]((void *)v16[2]);
    operator delete[]((void *)v16[3]);
    operator delete[]((void *)v16[5]);
  }
}

```

## disassembly

```asm
0x180037bc0  push    rbx
0x180037bc2  push    rsi
0x180037bc3  push    rdi
0x180037bc4  push    r14
0x180037bc6  push    r15
0x180037bc8  sub     rsp, 0E0h
0x180037bcf  mov     rbx, r9
0x180037bd2  mov     r14d, r8d
0x180037bd5  mov     rdi, rdx
0x180037bd8  mov     r15, rcx
0x180037bdb  mov     rcx, [rsp+108h+arg_40]
0x180037be3  test    rcx, rcx
0x180037be6  jz      short loc_180037BF4
0x180037be8  mov     rax, [rcx]
0x180037beb  mov     rax, [rax+8]
0x180037bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bf4  test    rdi, rdi
0x180037bf7  jnz     short loc_180037C30
0x180037bf9  mov     dword ptr [rsp+108h+pbSignature], 80070057h; int
0x180037c01  lea     r9, aPbsignature; "pbSignature"
0x180037c08  mov     r8d, 1DEh; unsigned int
0x180037c0e  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037c15  lea     rcx, [rsp+108h+pExceptionObject]; this
0x180037c1a  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037c1f  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037c26  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180037c2b  call    _CxxThrowException_0
0x180037c30  test    rbx, rbx
0x180037c33  jnz     short loc_180037C72
0x180037c35  mov     dword ptr [rsp+108h+pbSignature], 80070057h; int
0x180037c3d  lea     r9, aPbhash; "pbHash"
0x180037c44  mov     r8d, 1DFh; unsigned int
0x180037c4a  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037c51  lea     rcx, [rsp+108h+var_60]; this
0x180037c59  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037c5e  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037c65  lea     rcx, [rsp+108h+var_60]; pExceptionObject
0x180037c6d  call    _CxxThrowException_0
0x180037c72  mov     esi, [rsp+108h+arg_30]
0x180037c79  mov     edx, esi; unsigned int
0x180037c7b  mov     rcx, [rsp+108h+pPaddingInfo]; void *
0x180037c83  call    ?CheckSignaturePaddingInfo@CryptoUtil@cryptography@fs@microsoft@@SAXPEBXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(void const *,ulong,microsoft::fs::common::FsException *)
0x180037c88  mov     [rsp+108h+dwFlags], esi; dwFlags
0x180037c8c  mov     [rsp+108h+cbSignature], r14d; cbSignature
0x180037c91  mov     [rsp+108h+pbSignature], rdi; pbSignature
0x180037c96  mov     r9d, [rsp+108h+cbHashValue]; cbHashValue
0x180037c9e  mov     r8, rbx; pbHashValue
0x180037ca1  mov     rdx, [rsp+108h+pPaddingInfo]; pPaddingInfo
0x180037ca9  mov     rcx, [r15+220h]; hKey
0x180037cb0  call    cs:__imp_NCryptVerifySignature
0x180037cb6  mov     ebx, eax
0x180037cb8  test    eax, eax
0x180037cba  jnz     short loc_180037CCB
0x180037cbc  mov     ecx, 404h
0x180037cc1  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180037cc7  test    eax, eax
0x180037cc9  jz      short loc_180037D05
0x180037ccb  mov     edx, ebx
0x180037ccd  mov     ecx, 62C0C25h
0x180037cd2  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037cd8  mov     edx, [rsp+108h+cbHashValue]
0x180037cdf  mov     ecx, 62D0C25h
0x180037ce4  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037cea  mov     edx, r14d
0x180037ced  mov     ecx, 62E0C25h
0x180037cf2  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037cf8  mov     edx, esi
0x180037cfa  mov     ecx, 62F0C25h
0x180037cff  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037d05  mov     rax, [rsp+108h+arg_38]
0x180037d0d  mov     [rax], ebx
0x180037d0f  test    ebx, ebx
0x180037d11  jz      short loc_180037D21
0x180037d13  mov     edx, ebx
0x180037d15  mov     ecx, 1EB0C1Fh
0x180037d1a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037d20  nop
0x180037d21  jmp     short loc_180037D25
0x180037d23  jmp     short $+2
0x180037d25  add     rsp, 0E0h
0x180037d2c  pop     r15
0x180037d2e  pop     r14
0x180037d30  pop     rdi
0x180037d31  pop     rsi
0x180037d32  pop     rbx
0x180037d33  retn
```
