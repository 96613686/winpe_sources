# microsoft::fs::cryptography::CapiCryptoFactory::OpenCipherFromHandle(unsigned __int64,unsigned __int64,ulong,bool,bool,microsoft::fs::common::FsException *)

- ea: `0x180030c48`
- end: `0x180030d88`
- name: `?OpenCipherFromHandle@CapiCryptoFactory@cryptography@fs@microsoft@@SAPEAVICipher@234@_K0K_N1PEAVFsException@common@34@@Z`
- size: `320`
- prototype: `struct microsoft::fs::cryptography::ICipher *__usercall@<rax>(unsigned __int64@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, bool@<r9b>, bool, struct microsoft::fs::common::FsException *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001af68`

## callees

- `0x180001514`
- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x180030c48`
- `0x180031424`
- `0x180035284`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030cb0`

## string_xrefs

- `0x180030cce`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x180030d45`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct microsoft::fs::cryptography::ICipher *__fastcall microsoft::fs::cryptography::CapiCryptoFactory::OpenCipherFromHandle(
        unsigned __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        bool a5,
        unsigned __int16 **a6)
{
  DWORD LastError; // eax
  int v9; // eax
  microsoft::fs::cryptography::CapiCipher *v10; // rax
  unsigned __int16 **v12; // rax
  unsigned int v13; // [rsp+20h] [rbp-C8h]
  unsigned __int64 v14; // [rsp+38h] [rbp-B0h] BYREF
  microsoft::fs::cryptography::CapiCipher *v15; // [rsp+40h] [rbp-A8h]
  unsigned __int16 **v16; // [rsp+48h] [rbp-A0h] BYREF
  _QWORD v17[6]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+80h] [rbp-68h] BYREF
  _BYTE v19[56]; // [rsp+B0h] [rbp-38h] BYREF

  v14 = 0;
  v15 = 0;
  try
  {
    if ( a6 )
      (*((void (__fastcall **)(unsigned __int16 **))*a6 + 1))(a6);
    if ( !(unsigned int)fsCryptGetUserKey(a1, a3, &v14) )
    {
      LastError = GetLastError();
      v9 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        690,
        L"CryptGetUserKey(hProv, nKeySpec, &hKey)",
        v9);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v10 = (microsoft::fs::cryptography::CapiCipher *)operator new(0x38u);
    if ( v10 )
      v10 = microsoft::fs::cryptography::CapiCipher::CapiCipher(v10, a1, v14, a3, v13, 1);
    v15 = v10;
    if ( !v10 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v19,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        694,
        L"pCipher",
        -2147024882);
      throw (microsoft::fs::common::FsException *)v19;
    }
  }
  catch ( const microsoft::fs::common::FsException *v16 )
  {
    if ( v14 )
      fsCryptDestroyKey(v14);
    if ( !a6 )
      throw;
    microsoft::fs::common::FsException::assign(a6, v16);
    return v15;
  }
  catch ( ... )
  {
    if ( v14 )
      fsCryptDestroyKey(v14);
    if ( !a6 )
      throw;
    v12 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                                 (microsoft::fs::common::FsException *)v17,
                                 L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
                                 708,
                                 &psz,
                                 -2147467259,
                                 L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a6, v12);
    v17[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v17[1]);
    operator delete[]((void *)v17[2]);
    operator delete[]((void *)v17[3]);
    operator delete[]((void *)v17[5]);
  }
  return v15;
}

```

## disassembly

```asm
0x180030c48  mov     [rsp+arg_0], rbx
0x180030c4d  mov     [rsp+arg_8], rdx
0x180030c52  push    rdi
0x180030c53  sub     rsp, 0E0h
0x180030c5a  mov     ebx, r8d
0x180030c5d  mov     rdi, rcx
0x180030c60  mov     [rsp+0E8h+var_B8], 1
0x180030c65  mov     [rsp+0E8h+var_B0], 0
0x180030c6e  mov     [rsp+0E8h+var_A8], 0
0x180030c77  mov     rcx, [rsp+0E8h+arg_28]
0x180030c7f  test    rcx, rcx
0x180030c82  jz      short loc_180030C90
0x180030c84  mov     rax, [rcx]
0x180030c87  mov     rax, [rax+8]
0x180030c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c90  cmp     [rsp+0E8h+var_B0], 0
0x180030c96  jnz     short loc_180030CF6
0x180030c98  mov     [rsp+0E8h+var_B8], 1
0x180030c9d  lea     r8, [rsp+0E8h+var_B0]; unsigned __int64 *
0x180030ca2  mov     edx, ebx; unsigned int
0x180030ca4  mov     rcx, rdi; unsigned __int64
0x180030ca7  call    ?fsCryptGetUserKey@@YAH_KKPEA_K@Z; fsCryptGetUserKey(unsigned __int64,ulong,unsigned __int64 *)
0x180030cac  test    eax, eax
0x180030cae  jnz     short loc_180030CF6
0x180030cb0  call    cs:__imp_GetLastError
0x180030cb6  mov     ecx, eax; unsigned int
0x180030cb8  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180030cbd  mov     [rsp+0E8h+var_C8], eax; int
0x180030cc1  lea     r9, aCryptgetuserke_0; "CryptGetUserKey(hProv, nKeySpec, &hKey)"
0x180030cc8  mov     r8d, 2B2h; unsigned int
0x180030cce  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030cd5  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x180030cdd  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030ce2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030ce9  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180030cf1  call    _CxxThrowException_0
0x180030cf6  mov     ecx, 38h ; '8'; Size
0x180030cfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030d00  mov     [rsp+0E8h+arg_8], rax
0x180030d08  test    rax, rax
0x180030d0b  jz      short loc_180030D26
0x180030d0d  mov     [rsp+0E8h+var_C0], 1; bool
0x180030d12  mov     r9d, ebx; unsigned int
0x180030d15  mov     r8, [rsp+0E8h+var_B0]; unsigned __int64
0x180030d1a  mov     rdx, rdi; unsigned __int64
0x180030d1d  mov     rcx, rax; this
0x180030d20  call    ??0CapiCipher@cryptography@fs@microsoft@@QEAA@_K0K_N1@Z; microsoft::fs::cryptography::CapiCipher::CapiCipher(unsigned __int64,unsigned __int64,ulong,bool,bool)
0x180030d25  nop
0x180030d26  mov     [rsp+0E8h+var_A8], rax
0x180030d2b  test    rax, rax
0x180030d2e  jnz     short loc_180030D6E
0x180030d30  mov     [rsp+0E8h+var_C8], 8007000Eh; int
0x180030d38  lea     r9, aPcipher; "pCipher"
0x180030d3f  mov     r8d, 2B6h; unsigned int
0x180030d45  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030d4c  lea     rcx, [rsp+0E8h+var_38]; this
0x180030d54  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030d59  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030d60  lea     rcx, [rsp+0E8h+var_38]; pExceptionObject
0x180030d68  call    _CxxThrowException_0
0x180030d6e  jmp     short loc_180030D72
0x180030d70  jmp     short $+2
0x180030d72  mov     rax, [rsp+0E8h+var_A8]
0x180030d77  mov     rbx, [rsp+0E8h+arg_0]
0x180030d7f  add     rsp, 0E0h
0x180030d86  pop     rdi
0x180030d87  retn
```
