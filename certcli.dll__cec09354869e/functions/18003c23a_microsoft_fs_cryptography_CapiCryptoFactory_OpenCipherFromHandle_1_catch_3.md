# _microsoft::fs::cryptography::CapiCryptoFactory::OpenCipherFromHandle_::_1_::catch$3

- ea: `0x18003c23a`
- end: `0x18003c2f6`
- name: `_microsoft::fs::cryptography::CapiCryptoFactory::OpenCipherFromHandle_::_1_::catch$3`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019b88`
- `0x18002e4dc`
- `0x180030f40`
- `0x18003c23a`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2bf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2c9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2d3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2dd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2bf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2c9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2d3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c2dd`

## string_xrefs

- `0x18003c293`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`

## pseudocode

```c
__int64 __fastcall microsoft::fs::cryptography::CapiCryptoFactory::OpenCipherFromHandle_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  HCRYPTKEY v3; // rcx
  unsigned __int16 **v4; // rbx
  unsigned __int16 **v5; // rax

  if ( *(_BYTE *)(a2 + 48) )
  {
    v3 = *(_QWORD *)(a2 + 56);
    if ( v3 )
      fsCryptDestroyKey(v3);
  }
  v4 = *(unsigned __int16 ***)(a2 + 280);
  if ( !v4 )
    throw;
  v5 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                              (microsoft::fs::common::FsException *)(a2 + 80),
                              L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
                              708,
                              &psz,
                              -2147467259,
                              L"Caught exception of unknown type");
  microsoft::fs::common::FsException::assign(v4, v5);
  *(_QWORD *)(a2 + 80) = &microsoft::fs::common::FsException::`vftable';
  operator delete[](*(void **)(a2 + 88));
  operator delete[](*(void **)(a2 + 96));
  operator delete[](*(void **)(a2 + 104));
  operator delete[](*(void **)(a2 + 120));
  return 0;
}

```

## disassembly

```asm
0x18003c23a  mov     [rsp+arg_8], rdx
0x18003c23f  push    rbx
0x18003c240  push    rbp
0x18003c241  sub     rsp, 38h
0x18003c245  mov     rbp, rdx
0x18003c248  cmp     byte ptr [rbp+30h], 0
0x18003c24c  jz      short loc_18003C25C
0x18003c24e  mov     rcx, [rbp+38h]; unsigned __int64
0x18003c252  test    rcx, rcx
0x18003c255  jz      short loc_18003C25C
0x18003c257  call    ?fsCryptDestroyKey@@YAH_K@Z; fsCryptDestroyKey(unsigned __int64)
0x18003c25c  mov     rbx, [rbp+118h]
0x18003c263  test    rbx, rbx
0x18003c266  jnz     short loc_18003C272
0x18003c268  xor     edx, edx; pThrowInfo
0x18003c26a  xor     ecx, ecx; pExceptionObject
0x18003c26c  call    _CxxThrowException_0
0x18003c272  lea     rax, aCaughtExceptio; "Caught exception of unknown type"
0x18003c279  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x18003c27e  mov     [rsp+48h+var_28], 80004005h; int
0x18003c286  lea     r9, psz; unsigned __int16 *
0x18003c28d  mov     r8d, 2C4h; unsigned int
0x18003c293  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003c29a  lea     rcx, [rbp+50h]; this
0x18003c29e  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003c2a3  nop
0x18003c2a4  mov     rdx, rax; struct microsoft::fs::common::FsException *
0x18003c2a7  mov     rcx, rbx; this
0x18003c2aa  call    ?assign@FsException@common@fs@microsoft@@AEAAXAEBV1234@@Z; microsoft::fs::common::FsException::assign(microsoft::fs::common::FsException const &)
0x18003c2af  nop
0x18003c2b0  lea     rax, ??_7FsException@common@fs@microsoft@@6B@; const microsoft::fs::common::FsException::`vftable'
0x18003c2b7  mov     [rbp+50h], rax
0x18003c2bb  mov     rcx, [rbp+58h]
0x18003c2bf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c2c5  mov     rcx, [rbp+60h]
0x18003c2c9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c2cf  mov     rcx, [rbp+68h]
0x18003c2d3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c2d9  mov     rcx, [rbp+78h]
0x18003c2dd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c2e3  nop
0x18003c2e4  mov     rax, 0
0x18003c2ee  add     rsp, 38h
0x18003c2f2  pop     rbp
0x18003c2f3  pop     rbx
0x18003c2f4  retn
```
