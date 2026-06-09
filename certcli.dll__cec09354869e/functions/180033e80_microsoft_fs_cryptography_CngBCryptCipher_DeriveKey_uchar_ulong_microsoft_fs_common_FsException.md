# microsoft::fs::cryptography::CngBCryptCipher::DeriveKey(uchar *,ulong *,microsoft::fs::common::FsException *)

- ea: `0x180033e80`
- end: `0x180033f62`
- name: `?DeriveKey@CngBCryptCipher@cryptography@fs@microsoft@@UEAAXPEAEPEAKPEAVFsException@common@34@@Z`
- size: `226`
- prototype: `void __fastcall(microsoft::fs::cryptography::CngBCryptCipher *this, unsigned __int8 *, unsigned int *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019b88`
- `0x18002e4dc`
- `0x180033e80`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180033ef1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033efc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033f07`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033f12`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033ef1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033efc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033f07`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180033f12`

## string_xrefs

- `0x180033ec2`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180033f3f`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CngBCryptCipher::DeriveKey(
        microsoft::fs::cryptography::CngBCryptCipher *this,
        unsigned __int8 *a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 **v5; // rax
  _QWORD pExceptionObject[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !a4 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
      618,
      &psz,
      -2147024846,
      L"Not Supported");
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  (*((void (__fastcall **)(unsigned __int16 **, unsigned __int8 *, unsigned int *))*a4 + 1))(a4, a2, a3);
  v5 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                              (microsoft::fs::common::FsException *)pExceptionObject,
                              L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
                              615,
                              &psz,
                              -2147024846,
                              L"Not Supported");
  microsoft::fs::common::FsException::assign(a4, v5);
  pExceptionObject[0] = &microsoft::fs::common::FsException::`vftable';
  operator delete[]((void *)pExceptionObject[1]);
  operator delete[]((void *)pExceptionObject[2]);
  operator delete[]((void *)pExceptionObject[3]);
  operator delete[]((void *)pExceptionObject[5]);
}

```

## disassembly

```asm
0x180033e80  push    rbx
0x180033e82  sub     rsp, 60h
0x180033e86  mov     rbx, r9
0x180033e89  test    r9, r9
0x180033e8c  jz      loc_180033F1E
0x180033e92  mov     rax, [r9]
0x180033e95  mov     rcx, rbx
0x180033e98  mov     rax, [rax+8]
0x180033e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ea1  lea     rax, aNotSupported_0; "Not Supported"
0x180033ea8  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180033ead  mov     [rsp+68h+var_48], 80070032h; int
0x180033eb5  lea     r9, psz; unsigned __int16 *
0x180033ebc  mov     r8d, 267h; unsigned int
0x180033ec2  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180033ec9  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180033ece  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180033ed3  nop
0x180033ed4  mov     rdx, rax; struct microsoft::fs::common::FsException *
0x180033ed7  mov     rcx, rbx; this
0x180033eda  call    ?assign@FsException@common@fs@microsoft@@AEAAXAEBV1234@@Z; microsoft::fs::common::FsException::assign(microsoft::fs::common::FsException const &)
0x180033edf  nop
0x180033ee0  lea     rax, ??_7FsException@common@fs@microsoft@@6B@; const microsoft::fs::common::FsException::`vftable'
0x180033ee7  mov     [rsp+68h+pExceptionObject], rax
0x180033eec  mov     rcx, [rsp+68h+var_30]
0x180033ef1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033ef7  mov     rcx, [rsp+68h+var_28]
0x180033efc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033f02  mov     rcx, [rsp+68h+var_20]
0x180033f07  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033f0d  mov     rcx, [rsp+68h+var_10]
0x180033f12  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180033f18  add     rsp, 60h
0x180033f1c  pop     rbx
0x180033f1d  retn
0x180033f1e  lea     rax, aNotSupported_0; "Not Supported"
0x180033f25  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180033f2a  mov     [rsp+68h+var_48], 80070032h; int
0x180033f32  lea     r9, psz; unsigned __int16 *
0x180033f39  mov     r8d, 26Ah; unsigned int
0x180033f3f  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180033f46  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180033f4b  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180033f50  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180033f57  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180033f5c  call    _CxxThrowException_0
```
