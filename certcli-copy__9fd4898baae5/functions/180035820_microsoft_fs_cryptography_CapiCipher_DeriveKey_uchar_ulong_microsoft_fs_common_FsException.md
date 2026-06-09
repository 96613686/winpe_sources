# microsoft::fs::cryptography::CapiCipher::DeriveKey(uchar *,ulong *,microsoft::fs::common::FsException *)

- ea: `0x180035820`
- end: `0x180035902`
- name: `?DeriveKey@CapiCipher@cryptography@fs@microsoft@@UEAAXPEAEPEAKPEAVFsException@common@34@@Z`
- size: `226`
- prototype: `void(microsoft::fs::cryptography::CapiCipher *__hidden this, unsigned __int8 *, unsigned int *, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019b88`
- `0x18002e4dc`
- `0x180035820`
- `0x18003f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180035891`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003589c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800358a7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800358b2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180035891`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003589c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800358a7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800358b2`

## string_xrefs

- `0x180035862`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800358df`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CapiCipher::DeriveKey(
        microsoft::fs::cryptography::CapiCipher *this,
        unsigned __int8 *a2,
        unsigned int *a3,
        struct microsoft::fs::common::FsException *a4)
{
  const struct microsoft::fs::common::FsException *v5; // rax
  _QWORD pExceptionObject[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !a4 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
      0x2A7u,
      &psz,
      -2147024846,
      L"Not Supported");
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  (*(void (__fastcall **)(struct microsoft::fs::common::FsException *, unsigned __int8 *, unsigned int *))(*(_QWORD *)a4 + 8LL))(
    a4,
    a2,
    a3);
  v5 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                            (microsoft::fs::common::FsException *)pExceptionObject,
                                                            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
                                                            0x2A4u,
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
0x180035820  push    rbx
0x180035822  sub     rsp, 60h
0x180035826  mov     rbx, r9
0x180035829  test    r9, r9
0x18003582c  jz      loc_1800358BE
0x180035832  mov     rax, [r9]
0x180035835  mov     rcx, rbx
0x180035838  mov     rax, [rax+8]
0x18003583c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035841  lea     rax, aNotSupported_0; "Not Supported"
0x180035848  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18003584d  mov     [rsp+68h+var_48], 80070032h; int
0x180035855  lea     r9, psz; unsigned __int16 *
0x18003585c  mov     r8d, 2A4h; unsigned int
0x180035862  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035869  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18003586e  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180035873  nop
0x180035874  mov     rdx, rax; struct microsoft::fs::common::FsException *
0x180035877  mov     rcx, rbx; this
0x18003587a  call    ?assign@FsException@common@fs@microsoft@@AEAAXAEBV1234@@Z; microsoft::fs::common::FsException::assign(microsoft::fs::common::FsException const &)
0x18003587f  nop
0x180035880  lea     rax, ??_7FsException@common@fs@microsoft@@6B@; const microsoft::fs::common::FsException::`vftable'
0x180035887  mov     [rsp+68h+pExceptionObject], rax
0x18003588c  mov     rcx, [rsp+68h+var_30]
0x180035891  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180035897  mov     rcx, [rsp+68h+var_28]
0x18003589c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800358a2  mov     rcx, [rsp+68h+var_20]
0x1800358a7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800358ad  mov     rcx, [rsp+68h+var_10]
0x1800358b2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800358b8  add     rsp, 60h
0x1800358bc  pop     rbx
0x1800358bd  retn
0x1800358be  lea     rax, aNotSupported_0; "Not Supported"
0x1800358c5  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x1800358ca  mov     [rsp+68h+var_48], 80070032h; int
0x1800358d2  lea     r9, psz; unsigned __int16 *
0x1800358d9  mov     r8d, 2A7h; unsigned int
0x1800358df  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800358e6  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800358eb  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800358f0  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800358f7  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800358fc  call    _CxxThrowException_0
```
