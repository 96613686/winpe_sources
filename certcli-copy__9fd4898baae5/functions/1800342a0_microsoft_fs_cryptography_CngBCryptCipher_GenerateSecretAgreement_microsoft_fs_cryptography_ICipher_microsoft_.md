# microsoft::fs::cryptography::CngBCryptCipher::GenerateSecretAgreement(microsoft::fs::cryptography::ICipher *,microsoft::fs::common::FsException *)

- ea: `0x1800342a0`
- end: `0x180034382`
- name: `?GenerateSecretAgreement@CngBCryptCipher@cryptography@fs@microsoft@@UEAAXPEAVICipher@234@PEAVFsException@common@34@@Z`
- size: `226`
- prototype: `void(microsoft::fs::cryptography::CngBCryptCipher *__hidden this, struct microsoft::fs::cryptography::ICipher *, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019b88`
- `0x18002e4dc`
- `0x1800342a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180034311`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003431c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180034327`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180034332`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180034311`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003431c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180034327`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180034332`

## string_xrefs

- `0x1800342e2`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x18003435f`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CngBCryptCipher::GenerateSecretAgreement(
        microsoft::fs::cryptography::CngBCryptCipher *this,
        struct microsoft::fs::cryptography::ICipher *a2,
        struct microsoft::fs::common::FsException *a3)
{
  const struct microsoft::fs::common::FsException *v4; // rax
  _QWORD pExceptionObject[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !a3 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
      0x259u,
      &psz,
      -2147024846,
      L"Not Supported");
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  (*(void (__fastcall **)(struct microsoft::fs::common::FsException *, struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a3 + 8LL))(
    a3,
    a2);
  v4 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                            (microsoft::fs::common::FsException *)pExceptionObject,
                                                            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
                                                            0x256u,
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
0x1800342a0  push    rbx
0x1800342a2  sub     rsp, 60h
0x1800342a6  mov     rbx, r8
0x1800342a9  test    r8, r8
0x1800342ac  jz      loc_18003433E
0x1800342b2  mov     rax, [r8]
0x1800342b5  mov     rcx, rbx
0x1800342b8  mov     rax, [rax+8]
0x1800342bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342c1  lea     rax, aNotSupported_0; "Not Supported"
0x1800342c8  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x1800342cd  mov     [rsp+68h+var_48], 80070032h; int
0x1800342d5  lea     r9, psz; unsigned __int16 *
0x1800342dc  mov     r8d, 256h; unsigned int
0x1800342e2  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800342e9  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800342ee  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800342f3  nop
0x1800342f4  mov     rdx, rax; struct microsoft::fs::common::FsException *
0x1800342f7  mov     rcx, rbx; this
0x1800342fa  call    ?assign@FsException@common@fs@microsoft@@AEAAXAEBV1234@@Z; microsoft::fs::common::FsException::assign(microsoft::fs::common::FsException const &)
0x1800342ff  nop
0x180034300  lea     rax, ??_7FsException@common@fs@microsoft@@6B@; const microsoft::fs::common::FsException::`vftable'
0x180034307  mov     [rsp+68h+pExceptionObject], rax
0x18003430c  mov     rcx, [rsp+68h+var_30]
0x180034311  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180034317  mov     rcx, [rsp+68h+var_28]
0x18003431c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180034322  mov     rcx, [rsp+68h+var_20]
0x180034327  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003432d  mov     rcx, [rsp+68h+var_10]
0x180034332  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180034338  add     rsp, 60h
0x18003433c  pop     rbx
0x18003433d  retn
0x18003433e  lea     rax, aNotSupported_0; "Not Supported"
0x180034345  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18003434a  mov     [rsp+68h+var_48], 80070032h; int
0x180034352  lea     r9, psz; unsigned __int16 *
0x180034359  mov     r8d, 259h; unsigned int
0x18003435f  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034366  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18003436b  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180034370  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034377  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18003437c  call    _CxxThrowException_0
```
