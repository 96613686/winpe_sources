# microsoft::fs::cryptography::CapiCipher::Sign(uchar *,ulong *,uchar const *,ulong,void const *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180036600`
- end: `0x1800367ab`
- name: `?Sign@CapiCipher@cryptography@fs@microsoft@@UEAAXPEAEPEAKPEBEKPEBXKPEAVFsException@common@34@@Z`
- size: `427`
- prototype: `void(microsoft::fs::cryptography::CapiCipher *__hidden this, unsigned __int8 *, unsigned int *, const unsigned __int8 *, unsigned int, const void *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e5e4`
- `0x18002e71c`
- `0x180030788`
- `0x180030a5c`
- `0x180031718`
- `0x180035234`
- `0x180036600`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036746`

## string_xrefs

- `0x18003664e`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x18003668a`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180036764`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall microsoft::fs::cryptography::CapiCipher::Sign(
        microsoft::fs::cryptography::CapiCipher *this,
        unsigned __int8 *a2,
        struct microsoft::fs::common::FsException *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        const unsigned __int16 **a6,
        unsigned int a7,
        struct microsoft::fs::common::FsException *a8)
{
  __int64 v12; // r9
  struct microsoft::fs::cryptography::IHash *HashForProvider; // rax
  __int64 v14; // rdi
  unsigned int v15; // ebx
  unsigned __int64 v16; // rax
  const unsigned __int16 *v17; // r8
  unsigned int v18; // r9d
  DWORD LastError; // eax
  int v20; // eax
  const struct microsoft::fs::common::FsException *v21; // rax
  unsigned __int8 *v22; // [rsp+20h] [rbp-108h]
  __int64 v23; // [rsp+30h] [rbp-F8h] BYREF
  const microsoft::fs::common::FsException *v24; // [rsp+38h] [rbp-F0h] BYREF
  _QWORD v25[6]; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp-B8h] BYREF
  _BYTE v27[48]; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE v28[88]; // [rsp+D0h] [rbp-58h] BYREF

  try
  {
    if ( a8 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a8 + 8LL))(a8);
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x234u,
        L"pcbSignature",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a4 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v27,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x235u,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v27;
    }
    microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(a6, a7, a3);
    HashForProvider = microsoft::fs::cryptography::CapiCryptoFactory::CreateHashForProvider(
                        *((_QWORD *)this + 5),
                        a6,
                        a7,
                        v12,
                        (struct microsoft::fs::common::FsException *)v22);
    microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::auto_pointer<microsoft::fs::cryptography::IHash>(
      &v23,
      HashForProvider);
    v14 = v23;
    (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int8 *, _QWORD, _DWORD))(*(_QWORD *)v23 + 32LL))(
      v23,
      L"HASH_VALUE",
      a4,
      a5,
      0);
    v15 = *((_DWORD *)this + 7);
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14);
    if ( !(unsigned int)fsCryptSignHash(v16, v15, v17, v18, a2, (unsigned int *)a3) )
    {
      LastError = GetLastError();
      v20 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v28,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x247u,
        L"CryptSignHash( reinterpret_cast<HCRYPTHASH>(pHash->GetHandle()), m_nKeySpec, 0, 0, pbSignature, pcbSignature)",
        v20);
      throw (microsoft::fs::common::FsException *)v28;
    }
    microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v23);
  }
  catch ( const microsoft::fs::common::FsException *v24 )
  {
    if ( !a8 )
      throw;
    microsoft::fs::common::FsException::assign(a8, v24);
    return;
  }
  catch ( ... )
  {
    if ( !a8 )
      throw;
    v21 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v25,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
                                                               0x251u,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a8, v21);
    v25[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v25[1]);
    operator delete[]((void *)v25[2]);
    operator delete[]((void *)v25[3]);
    operator delete[]((void *)v25[5]);
  }
}

```

## disassembly

```asm
0x180036600  push    rbx
0x180036602  push    rsi
0x180036603  push    rdi
0x180036604  push    r14
0x180036606  push    r15
0x180036608  sub     rsp, 100h
0x18003660f  mov     rbx, r9
0x180036612  mov     rsi, r8
0x180036615  mov     r15, rdx
0x180036618  mov     r14, rcx
0x18003661b  mov     rcx, [rsp+128h+arg_38]
0x180036623  test    rcx, rcx
0x180036626  jz      short loc_180036634
0x180036628  mov     rax, [rcx]
0x18003662b  mov     rax, [rax+8]
0x18003662f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036634  test    rsi, rsi
0x180036637  jnz     short loc_180036670
0x180036639  mov     dword ptr [rsp+128h+var_108], 80070057h; int
0x180036641  lea     r9, aPcbsignature; "pcbSignature"
0x180036648  mov     r8d, 234h; unsigned int
0x18003664e  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180036655  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18003665a  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003665f  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036666  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18003666b  call    _CxxThrowException_0
0x180036670  test    rbx, rbx
0x180036673  jnz     short loc_1800366B2
0x180036675  mov     dword ptr [rsp+128h+var_108], 80070057h; int
0x18003667d  lea     r9, aPbhash; "pbHash"
0x180036684  mov     r8d, 235h; unsigned int
0x18003668a  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180036691  lea     rcx, [rsp+128h+var_88]; this
0x180036699  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003669e  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800366a5  lea     rcx, [rsp+128h+var_88]; pExceptionObject
0x1800366ad  call    _CxxThrowException_0
0x1800366b2  mov     edx, [rsp+128h+arg_30]; unsigned int
0x1800366b9  mov     rcx, [rsp+128h+arg_28]; void *
0x1800366c1  call    ?CheckSignaturePaddingInfo@CryptoUtil@cryptography@fs@microsoft@@SAXPEBXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(void const *,ulong,microsoft::fs::common::FsException *)
0x1800366c6  mov     r8d, [rsp+128h+arg_30]; unsigned int
0x1800366ce  mov     rdx, [rsp+128h+arg_28]; void *
0x1800366d6  mov     rcx, [r14+28h]; unsigned __int64
0x1800366da  call    ?CreateHashForProvider@CapiCryptoFactory@cryptography@fs@microsoft@@SAPEAVIHash@234@_KPEBXK_NPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CapiCryptoFactory::CreateHashForProvider(unsigned __int64,void const *,ulong,bool,microsoft::fs::common::FsException *)
0x1800366df  mov     rdx, rax
0x1800366e2  lea     rcx, [rsp+128h+var_F8]
0x1800366e7  call    ??0?$auto_pointer@VIHash@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAA@PEAVIHash@cryptography@23@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::auto_pointer<microsoft::fs::cryptography::IHash>(microsoft::fs::cryptography::IHash *)
0x1800366ec  nop
0x1800366ed  mov     rdi, [rsp+128h+var_F8]
0x1800366f2  mov     rax, [rdi]
0x1800366f5  mov     dword ptr [rsp+128h+var_108], 0
0x1800366fd  mov     r9d, [rsp+128h+arg_20]
0x180036705  mov     r8, rbx
0x180036708  lea     rdx, aHashValue; "HASH_VALUE"
0x18003670f  mov     rcx, rdi
0x180036712  mov     rax, [rax+20h]
0x180036716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003671b  mov     ebx, [r14+1Ch]
0x18003671f  mov     rax, [rdi]
0x180036722  mov     rcx, rdi
0x180036725  mov     rax, [rax+38h]
0x180036729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003672e  mov     [rsp+128h+var_100], rsi; unsigned int *
0x180036733  mov     [rsp+128h+var_108], r15; unsigned __int8 *
0x180036738  mov     edx, ebx; unsigned int
0x18003673a  mov     rcx, rax; unsigned __int64
0x18003673d  call    ?fsCryptSignHash@@YAH_KKPEBGKPEAEPEAK@Z; fsCryptSignHash(unsigned __int64,ulong,ushort const *,ulong,uchar *,ulong *)
0x180036742  test    eax, eax
0x180036744  jnz     short loc_18003678D
0x180036746  call    cs:__imp_GetLastError
0x18003674c  mov     ecx, eax; unsigned int
0x18003674e  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180036753  mov     dword ptr [rsp+128h+var_108], eax; int
0x180036757  lea     r9, aCryptsignhashR; "CryptSignHash( reinterpret_cast<HCRYPTH"...
0x18003675e  mov     r8d, 247h; unsigned int
0x180036764  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003676b  lea     rcx, [rsp+128h+var_58]; this
0x180036773  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180036778  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003677f  lea     rcx, [rsp+128h+var_58]; pExceptionObject
0x180036787  call    _CxxThrowException_0
0x18003678d  lea     rcx, [rsp+128h+var_F8]
0x180036792  call    ?close@?$auto_pointer@VIHash@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(void)
0x180036797  nop
0x180036798  jmp     short loc_18003679C
0x18003679a  jmp     short $+2
0x18003679c  add     rsp, 100h
0x1800367a3  pop     r15
0x1800367a5  pop     r14
0x1800367a7  pop     rdi
0x1800367a8  pop     rsi
0x1800367a9  pop     rbx
0x1800367aa  retn
```
