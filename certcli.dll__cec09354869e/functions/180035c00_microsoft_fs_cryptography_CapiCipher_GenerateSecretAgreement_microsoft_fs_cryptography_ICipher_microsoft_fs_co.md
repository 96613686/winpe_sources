# microsoft::fs::cryptography::CapiCipher::GenerateSecretAgreement(microsoft::fs::cryptography::ICipher *,microsoft::fs::common::FsException *)

- ea: `0x180035c00`
- end: `0x180035ce2`
- name: `?GenerateSecretAgreement@CapiCipher@cryptography@fs@microsoft@@UEAAXPEAVICipher@234@PEAVFsException@common@34@@Z`
- size: `226`
- prototype: `void __fastcall(microsoft::fs::cryptography::CapiCipher *this, struct microsoft::fs::cryptography::ICipher *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019b88`
- `0x18002e4dc`
- `0x180035c00`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c71`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c7c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c87`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c92`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c71`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c7c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c87`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035c92`

## string_xrefs

- `0x180035c42`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035cbf`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CapiCipher::GenerateSecretAgreement(
        microsoft::fs::cryptography::CapiCipher *this,
        struct microsoft::fs::cryptography::ICipher *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 **v4; // rax
  _QWORD pExceptionObject[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !a3 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
      662,
      &psz,
      -2147024846,
      L"Not Supported");
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  (*((void (__fastcall **)(unsigned __int16 **, struct microsoft::fs::cryptography::ICipher *))*a3 + 1))(a3, a2);
  v4 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                              (microsoft::fs::common::FsException *)pExceptionObject,
                              L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
                              659,
                              &psz,
                              -2147024846,
                              L"Not Supported");
  microsoft::fs::common::FsException::assign(a3, v4);
  pExceptionObject[0] = &microsoft::fs::common::FsException::`vftable';
  operator delete[]((void *)pExceptionObject[1]);
  operator delete[]((void *)pExceptionObject[2]);
  operator delete[]((void *)pExceptionObject[3]);
  operator delete[]((void *)pExceptionObject[5]);
}

```

## disassembly

```asm
0x180035c00  push    rbx
0x180035c02  sub     rsp, 60h
0x180035c06  mov     rbx, r8
0x180035c09  test    r8, r8
0x180035c0c  jz      loc_180035C9E
0x180035c12  mov     rax, [r8]
0x180035c15  mov     rcx, rbx
0x180035c18  mov     rax, [rax+8]
0x180035c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c21  lea     rax, aNotSupported_0; "Not Supported"
0x180035c28  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180035c2d  mov     [rsp+68h+var_48], 80070032h; int
0x180035c35  lea     r9, psz; unsigned __int16 *
0x180035c3c  mov     r8d, 293h; unsigned int
0x180035c42  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035c49  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180035c4e  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180035c53  nop
0x180035c54  mov     rdx, rax; struct microsoft::fs::common::FsException *
0x180035c57  mov     rcx, rbx; this
0x180035c5a  call    ?assign@FsException@common@fs@microsoft@@AEAAXAEBV1234@@Z; microsoft::fs::common::FsException::assign(microsoft::fs::common::FsException const &)
0x180035c5f  nop
0x180035c60  lea     rax, ??_7FsException@common@fs@microsoft@@6B@; const microsoft::fs::common::FsException::`vftable'
0x180035c67  mov     [rsp+68h+pExceptionObject], rax
0x180035c6c  mov     rcx, [rsp+68h+var_30]
0x180035c71  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180035c77  mov     rcx, [rsp+68h+var_28]
0x180035c7c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180035c82  mov     rcx, [rsp+68h+var_20]
0x180035c87  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180035c8d  mov     rcx, [rsp+68h+var_10]
0x180035c92  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180035c98  add     rsp, 60h
0x180035c9c  pop     rbx
0x180035c9d  retn
0x180035c9e  lea     rax, aNotSupported_0; "Not Supported"
0x180035ca5  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180035caa  mov     [rsp+68h+var_48], 80070032h; int
0x180035cb2  lea     r9, psz; unsigned __int16 *
0x180035cb9  mov     r8d, 296h; unsigned int
0x180035cbf  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035cc6  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180035ccb  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180035cd0  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035cd7  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180035cdc  call    _CxxThrowException_0
```
