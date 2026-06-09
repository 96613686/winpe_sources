# _microsoft::fs::cryptography::CngCryptoFactory::OpenCipherFromHandle_::_1_::catch$3

- ea: `0x18003c3d6`
- end: `0x18003c492`
- name: `_microsoft::fs::cryptography::CngCryptoFactory::OpenCipherFromHandle_::_1_::catch$3`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019b88`
- `0x18002e4dc`
- `0x180032884`
- `0x18003c3d6`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c45b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c465`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c46f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c479`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c45b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c465`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c46f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003c479`

## string_xrefs

- `0x18003c42f`: `onecore\ds\security\services\ca\fs\crypto\cngcryptofactory.cpp`

## pseudocode

```c
__int64 __fastcall microsoft::fs::cryptography::CngCryptoFactory::OpenCipherFromHandle_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  unsigned __int64 v3; // rcx
  microsoft::fs::common::FsException *v4; // rbx
  const struct microsoft::fs::common::FsException *v5; // rax

  if ( *(_BYTE *)(a2 + 48) )
  {
    v3 = *(_QWORD *)(a2 + 56);
    if ( v3 )
      fsNCryptFreeObject(v3);
  }
  v4 = *(microsoft::fs::common::FsException **)(a2 + 320);
  if ( !v4 )
    throw;
  v5 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                            (microsoft::fs::common::FsException *)(a2 + 80),
                                                            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngcryptofactory.cpp",
                                                            0x223u,
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
0x18003c3d6  mov     [rsp+arg_8], rdx
0x18003c3db  push    rbx
0x18003c3dc  push    rbp
0x18003c3dd  sub     rsp, 38h
0x18003c3e1  mov     rbp, rdx
0x18003c3e4  cmp     byte ptr [rbp+30h], 0
0x18003c3e8  jz      short loc_18003C3F8
0x18003c3ea  mov     rcx, [rbp+38h]; unsigned __int64
0x18003c3ee  test    rcx, rcx
0x18003c3f1  jz      short loc_18003C3F8
0x18003c3f3  call    ?fsNCryptFreeObject@@YAJ_K@Z; fsNCryptFreeObject(unsigned __int64)
0x18003c3f8  mov     rbx, [rbp+140h]
0x18003c3ff  test    rbx, rbx
0x18003c402  jnz     short loc_18003C40E
0x18003c404  xor     edx, edx; pThrowInfo
0x18003c406  xor     ecx, ecx; pExceptionObject
0x18003c408  call    _CxxThrowException_0
0x18003c40e  lea     rax, aCaughtExceptio; "Caught exception of unknown type"
0x18003c415  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x18003c41a  mov     [rsp+48h+var_28], 80004005h; int
0x18003c422  lea     r9, psz; unsigned __int16 *
0x18003c429  mov     r8d, 223h; unsigned int
0x18003c42f  lea     rdx, aOnecoreDsSecur_0; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003c436  lea     rcx, [rbp+50h]; this
0x18003c43a  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003c43f  nop
0x18003c440  mov     rdx, rax; struct microsoft::fs::common::FsException *
0x18003c443  mov     rcx, rbx; this
0x18003c446  call    ?assign@FsException@common@fs@microsoft@@AEAAXAEBV1234@@Z; microsoft::fs::common::FsException::assign(microsoft::fs::common::FsException const &)
0x18003c44b  nop
0x18003c44c  lea     rax, ??_7FsException@common@fs@microsoft@@6B@; const microsoft::fs::common::FsException::`vftable'
0x18003c453  mov     [rbp+50h], rax
0x18003c457  mov     rcx, [rbp+58h]
0x18003c45b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c461  mov     rcx, [rbp+60h]
0x18003c465  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c46b  mov     rcx, [rbp+68h]
0x18003c46f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c475  mov     rcx, [rbp+78h]
0x18003c479  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18003c47f  nop
0x18003c480  mov     rax, 0
0x18003c48a  add     rsp, 38h
0x18003c48e  pop     rbp
0x18003c48f  pop     rbx
0x18003c490  retn
```
