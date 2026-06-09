# microsoft::fs::cryptography::CngNCryptCipher::GenerateSecretAgreement(microsoft::fs::cryptography::ICipher *,microsoft::fs::common::FsException *)

- ea: `0x1800371a0`
- end: `0x180037330`
- name: `?GenerateSecretAgreement@CngNCryptCipher@cryptography@fs@microsoft@@UEAAXPEAVICipher@234@PEAVFsException@common@34@@Z`
- size: `400`
- prototype: `void __fastcall(microsoft::fs::cryptography::CngNCryptCipher *this, struct microsoft::fs::cryptography::ICipher *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x18003075c`
- `0x1800371a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800372c9`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180037243`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180037243`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037254`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037261`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037254`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180037261`
- `ncrypt!NCryptSecretAgreement` at `0x180037232`
- `ncrypt!NCryptSecretAgreement` at `0x180037232`

## string_xrefs

- `0x1800372e7`: `onecore\ds\security\services\ca\fs\common\auto_handle.h`
- `0x1800371e6`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x18003727c`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall microsoft::fs::cryptography::CngNCryptCipher::GenerateSecretAgreement(
        microsoft::fs::cryptography::CngNCryptCipher *this,
        struct microsoft::fs::cryptography::ICipher *a2,
        unsigned __int16 **a3)
{
  NCRYPT_KEY_HANDLE v5; // rax
  SECURITY_STATUS v6; // ebx
  unsigned __int64 *v7; // rbx
  NCRYPT_SECRET_HANDLE v8; // rdi
  DWORD LastError; // eax
  int v10; // eax
  unsigned __int16 **v11; // rax
  NCRYPT_SECRET_HANDLE phAgreedSecret; // [rsp+30h] [rbp-D8h] BYREF
  unsigned __int16 **v13; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v14[6]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v16[48]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v17[56]; // [rsp+D0h] [rbp-38h] BYREF

  try
  {
    if ( a3 )
      (*((void (__fastcall **)(unsigned __int16 **))*a3 + 1))(a3);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        514,
        L"pPublicCipher",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    phAgreedSecret = 0;
    v5 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a2 + 80LL))(a2);
    v6 = NCryptSecretAgreement(*((_QWORD *)this + 68), v5, &phAgreedSecret, 0);
    if ( v6 || DbgIsSSActive(0x404u) )
    {
      CSPrintErrorLineFile(0x5C40C25u, v6);
      CSPrintErrorLineFile(0x5C50C25u, 0);
      if ( v6 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v16,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          522,
          L"NCryptSecretAgreement( m_hKey, (NCRYPT_KEY_HANDLE)pPublicCipher->GetHandle(), &hSecret, 0)",
          v6);
        throw (microsoft::fs::common::FsException *)v16;
      }
    }
    v7 = (unsigned __int64 *)((char *)this + 552);
    v8 = phAgreedSecret;
    phAgreedSecret = 0;
    microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(v7);
    *v7 = v8;
    if ( !v8 )
    {
      LastError = GetLastError();
      v10 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v17,
        L"onecore\\ds\\security\\services\\ca\\fs\\common\\auto_handle.h",
        169,
        &psz,
        v10);
      throw (microsoft::fs::common::FsException *)v17;
    }
    microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(&phAgreedSecret);
  }
  catch ( const microsoft::fs::common::FsException *v13 )
  {
    if ( !a3 )
      throw;
    microsoft::fs::common::FsException::assign(a3, v13);
    return;
  }
  catch ( ... )
  {
    if ( !a3 )
      throw;
    v11 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                                 (microsoft::fs::common::FsException *)v14,
                                 L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
                                 534,
                                 &psz,
                                 -2147467259,
                                 L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a3, v11);
    v14[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v14[1]);
    operator delete[]((void *)v14[2]);
    operator delete[]((void *)v14[3]);
    operator delete[]((void *)v14[5]);
  }
}

```

## disassembly

```asm
0x1800371a0  mov     [rsp+arg_0], rbx
0x1800371a5  mov     [rsp+arg_10], r8
0x1800371aa  push    rdi
0x1800371ab  sub     rsp, 100h
0x1800371b2  mov     rbx, rdx
0x1800371b5  mov     rdi, rcx
0x1800371b8  test    r8, r8
0x1800371bb  jz      short loc_1800371CC
0x1800371bd  mov     rax, [r8]
0x1800371c0  mov     rcx, r8
0x1800371c3  mov     rax, [rax+8]
0x1800371c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371cc  test    rbx, rbx
0x1800371cf  jnz     short loc_180037208
0x1800371d1  mov     [rsp+108h+var_E8], 80070057h; int
0x1800371d9  lea     r9, aPpubliccipher; "pPublicCipher"
0x1800371e0  mov     r8d, 202h; unsigned int
0x1800371e6  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800371ed  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800371f2  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800371f7  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800371fe  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180037203  call    _CxxThrowException_0
0x180037208  mov     [rsp+108h+phAgreedSecret], 0
0x180037211  mov     rax, [rbx]
0x180037214  mov     rcx, rbx
0x180037217  mov     rax, [rax+50h]
0x18003721b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037220  xor     r9d, r9d; dwFlags
0x180037223  lea     r8, [rsp+108h+phAgreedSecret]; phAgreedSecret
0x180037228  mov     rdx, rax; hPubKey
0x18003722b  mov     rcx, [rdi+220h]; hPrivKey
0x180037232  call    cs:__imp_NCryptSecretAgreement
0x180037238  mov     ebx, eax
0x18003723a  test    eax, eax
0x18003723c  jnz     short loc_18003724D
0x18003723e  mov     ecx, 404h
0x180037243  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180037249  test    eax, eax
0x18003724b  jz      short loc_1800372A4
0x18003724d  mov     edx, ebx
0x18003724f  mov     ecx, 5C40C25h
0x180037254  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003725a  xor     edx, edx
0x18003725c  mov     ecx, 5C50C25h
0x180037261  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180037267  test    ebx, ebx
0x180037269  jns     short loc_1800372A4
0x18003726b  mov     [rsp+108h+var_E8], ebx; int
0x18003726f  lea     r9, aNcryptsecretag_0; "NCryptSecretAgreement( m_hKey, (NCRYPT_"...
0x180037276  mov     r8d, 20Ah; unsigned int
0x18003727c  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037283  lea     rcx, [rsp+108h+var_68]; this
0x18003728b  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037290  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037297  lea     rcx, [rsp+108h+var_68]; pExceptionObject
0x18003729f  call    _CxxThrowException_0
0x1800372a4  lea     rbx, [rdi+228h]
0x1800372ab  mov     rdi, [rsp+108h+phAgreedSecret]
0x1800372b0  mov     [rsp+108h+phAgreedSecret], 0
0x1800372b9  mov     rcx, rbx
0x1800372bc  call    ?close@?$auto_handle_t@_K$0A@VCloseCngNCryptSecretFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(void)
0x1800372c1  mov     [rbx], rdi
0x1800372c4  test    rdi, rdi
0x1800372c7  jnz     short loc_180037310
0x1800372c9  call    cs:__imp_GetLastError
0x1800372cf  mov     ecx, eax; unsigned int
0x1800372d1  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x1800372d6  mov     [rsp+108h+var_E8], eax; int
0x1800372da  lea     r9, psz; unsigned __int16 *
0x1800372e1  mov     r8d, 0A9h; unsigned int
0x1800372e7  lea     rdx, aOnecoreDsSecur_10; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800372ee  lea     rcx, [rsp+108h+var_38]; this
0x1800372f6  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800372fb  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037302  lea     rcx, [rsp+108h+var_38]; pExceptionObject
0x18003730a  call    _CxxThrowException_0
0x180037310  lea     rcx, [rsp+108h+phAgreedSecret]
0x180037315  call    ?close@?$auto_handle_t@_K$0A@VCloseCngNCryptSecretFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCngNCryptSecretFunctor>::close(void)
0x18003731a  nop
0x18003731b  jmp     short loc_18003731F
0x18003731d  jmp     short $+2
0x18003731f  mov     rbx, [rsp+108h+arg_0]
0x180037327  add     rsp, 100h
0x18003732e  pop     rdi
0x18003732f  retn
```
