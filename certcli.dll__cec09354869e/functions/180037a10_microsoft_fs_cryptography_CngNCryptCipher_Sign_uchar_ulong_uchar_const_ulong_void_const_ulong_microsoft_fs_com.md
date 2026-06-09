# microsoft::fs::cryptography::CngNCryptCipher::Sign(uchar *,ulong *,uchar const *,ulong,void const *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180037a10`
- end: `0x180037bb2`
- name: `?Sign@CngNCryptCipher@cryptography@fs@microsoft@@UEAAXPEAEPEAKPEBEKPEBXKPEAVFsException@common@34@@Z`
- size: `418`
- prototype: `void(microsoft::fs::cryptography::CngNCryptCipher *__hidden this, unsigned __int8 *, unsigned int *, const unsigned __int8 *, unsigned int, const void *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e71c`
- `0x180037a10`
- `0x18003f010`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180037b1b`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180037b1b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b2c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b3e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b4c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b59`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b2c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b3e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b4c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037b59`
- `ncrypt!NCryptSignHash` at `0x180037b0a`
- `ncrypt!NCryptSignHash` at `0x180037b0a`

## string_xrefs

- `0x180037a60`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x180037a9c`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x180037b74`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CngNCryptCipher::Sign(
        microsoft::fs::cryptography::CngNCryptCipher *this,
        unsigned __int8 *a2,
        struct microsoft::fs::common::FsException *a3,
        BYTE *a4,
        DWORD cbHashValue,
        const unsigned __int16 **pPaddingInfo,
        DWORD dwFlags,
        unsigned __int16 **a8)
{
  DWORD v12; // r14d
  SECURITY_STATUS v13; // ebx
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // [rsp+40h] [rbp-108h] BYREF
  _QWORD v16[6]; // [rsp+48h] [rbp-100h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-D0h] BYREF
  _BYTE v18[48]; // [rsp+A8h] [rbp-A0h] BYREF
  _BYTE v19[112]; // [rsp+D8h] [rbp-70h] BYREF

  try
  {
    if ( a8 )
      (*((void (__fastcall **)(unsigned __int16 **))*a8 + 1))(a8);
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        435,
        L"pcbSignature",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a4 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v18,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        436,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v18;
    }
    microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(pPaddingInfo, dwFlags, a3);
    v12 = *(_DWORD *)a3;
    v13 = NCryptSignHash(*((_QWORD *)this + 68), pPaddingInfo, a4, cbHashValue, a2, *(_DWORD *)a3, (DWORD *)a3, dwFlags);
    if ( v13 || DbgIsSSActive(0x404u) )
    {
      CSPrintErrorLineFile(0x60B0C25u, v13);
      CSPrintErrorLineFile(0x60C0C25u, cbHashValue);
      CSPrintErrorLineFile(0x60D0C25u, v12);
      CSPrintErrorLineFile(0x60E0C25u, dwFlags);
      if ( v13 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v19,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          449,
          L"NCryptSignHash( m_hKey, const_cast<void*>(pPaddingInfo), const_cast<BYTE*>(pbHash), cbHash, pbSignature, *pcbS"
           "ignature, pcbSignature, fPadding)",
          v13);
        throw (microsoft::fs::common::FsException *)v19;
      }
    }
  }
  catch ( const microsoft::fs::common::FsException *v15 )
  {
    if ( !a8 )
      throw;
    microsoft::fs::common::FsException::assign(a8, v15);
    return;
  }
  catch ( ... )
  {
    if ( !a8 )
      throw;
    v14 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                                 (microsoft::fs::common::FsException *)v16,
                                 L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
                                 459,
                                 &psz,
                                 -2147467259,
                                 L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a8, v14);
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
0x180037a10  push    rbx
0x180037a12  push    rsi
0x180037a13  push    rdi
0x180037a14  push    r13
0x180037a16  push    r14
0x180037a18  push    r15
0x180037a1a  sub     rsp, 118h
0x180037a21  mov     rdi, r9
0x180037a24  mov     rbx, r8
0x180037a27  mov     r15, rdx
0x180037a2a  mov     r13, rcx
0x180037a2d  mov     rcx, [rsp+148h+arg_38]
0x180037a35  test    rcx, rcx
0x180037a38  jz      short loc_180037A46
0x180037a3a  mov     rax, [rcx]
0x180037a3d  mov     rax, [rax+8]
0x180037a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a46  test    rbx, rbx
0x180037a49  jnz     short loc_180037A82
0x180037a4b  mov     dword ptr [rsp+148h+pbSignature], 80070057h; int
0x180037a53  lea     r9, aPcbsignature; "pcbSignature"
0x180037a5a  mov     r8d, 1B3h; unsigned int
0x180037a60  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037a67  lea     rcx, [rsp+148h+pExceptionObject]; this
0x180037a6c  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037a71  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037a78  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180037a7d  call    _CxxThrowException_0
0x180037a82  test    rdi, rdi
0x180037a85  jnz     short loc_180037AC4
0x180037a87  mov     dword ptr [rsp+148h+pbSignature], 80070057h; int
0x180037a8f  lea     r9, aPbhash; "pbHash"
0x180037a96  mov     r8d, 1B4h; unsigned int
0x180037a9c  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037aa3  lea     rcx, [rsp+148h+var_A0]; this
0x180037aab  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037ab0  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037ab7  lea     rcx, [rsp+148h+var_A0]; pExceptionObject
0x180037abf  call    _CxxThrowException_0
0x180037ac4  mov     esi, [rsp+148h+arg_30]
0x180037acb  mov     edx, esi; unsigned int
0x180037acd  mov     rcx, [rsp+148h+pPaddingInfo]; void *
0x180037ad5  call    ?CheckSignaturePaddingInfo@CryptoUtil@cryptography@fs@microsoft@@SAXPEBXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(void const *,ulong,microsoft::fs::common::FsException *)
0x180037ada  mov     r14d, [rbx]
0x180037add  mov     [rsp+148h+dwFlags], esi; dwFlags
0x180037ae1  mov     [rsp+148h+pcbResult], rbx; pcbResult
0x180037ae6  mov     [rsp+148h+cbSignature], r14d; cbSignature
0x180037aeb  mov     [rsp+148h+pbSignature], r15; pbSignature
0x180037af0  mov     r9d, [rsp+148h+cbHashValue]; cbHashValue
0x180037af8  mov     r8, rdi; pbHashValue
0x180037afb  mov     rdx, [rsp+148h+pPaddingInfo]; pPaddingInfo
0x180037b03  mov     rcx, [r13+220h]; hKey
0x180037b0a  call    cs:__imp_NCryptSignHash
0x180037b10  mov     ebx, eax
0x180037b12  test    eax, eax
0x180037b14  jnz     short loc_180037B25
0x180037b16  mov     ecx, 404h
0x180037b1b  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180037b21  test    eax, eax
0x180037b23  jz      short loc_180037B9D
0x180037b25  mov     edx, ebx
0x180037b27  mov     ecx, 60B0C25h
0x180037b2c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037b32  mov     edx, [rsp+148h+cbHashValue]
0x180037b39  mov     ecx, 60C0C25h
0x180037b3e  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037b44  mov     edx, r14d
0x180037b47  mov     ecx, 60D0C25h
0x180037b4c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037b52  mov     edx, esi
0x180037b54  mov     ecx, 60E0C25h
0x180037b59  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037b5f  test    ebx, ebx
0x180037b61  jns     short loc_180037B9D
0x180037b63  mov     dword ptr [rsp+148h+pbSignature], ebx; int
0x180037b67  lea     r9, aNcryptsignhash_0; "NCryptSignHash( m_hKey, const_cast<void"...
0x180037b6e  mov     r8d, 1C1h; unsigned int
0x180037b74  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037b7b  lea     rcx, [rsp+148h+var_70]; this
0x180037b83  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037b88  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037b8f  lea     rcx, [rsp+148h+var_70]; pExceptionObject
0x180037b97  call    _CxxThrowException_0
0x180037b9d  jmp     short loc_180037BA1
0x180037b9f  jmp     short $+2
0x180037ba1  add     rsp, 118h
0x180037ba8  pop     r15
0x180037baa  pop     r14
0x180037bac  pop     r13
0x180037bae  pop     rdi
0x180037baf  pop     rsi
0x180037bb0  pop     rbx
0x180037bb1  retn
```
