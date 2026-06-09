# microsoft::fs::cryptography::CapiCipher::Verify(uchar const *,ulong,uchar const *,ulong,void const *,ulong,long *,microsoft::fs::common::FsException *)

- ea: `0x1800367c0`
- end: `0x18003694b`
- name: `?Verify@CapiCipher@cryptography@fs@microsoft@@UEAAXPEBEK0KPEBXKPEAJPEAVFsException@common@34@@Z`
- size: `395`
- prototype: `void(microsoft::fs::cryptography::CapiCipher *__hidden this, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, const void *, unsigned int, int *, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x18002e71c`
- `0x180030788`
- `0x180030a5c`
- `0x1800317b8`
- `0x180035234`
- `0x1800367c0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036914`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036924`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036924`

## string_xrefs

- `0x180036810`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x18003684c`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall microsoft::fs::cryptography::CapiCipher::Verify(
        microsoft::fs::cryptography::CapiCipher *this,
        const unsigned __int8 *a2,
        struct microsoft::fs::common::FsException *a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        const unsigned __int16 **a6,
        unsigned int a7,
        int *a8,
        struct microsoft::fs::common::FsException *a9)
{
  unsigned int v10; // r12d
  __int64 v13; // r9
  struct microsoft::fs::cryptography::IHash *HashForProvider; // rax
  __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rax
  DWORD LastError; // eax
  const struct microsoft::fs::common::FsException *v19; // rax
  unsigned __int16 *v20; // [rsp+20h] [rbp-E8h]
  unsigned __int16 *v21; // [rsp+20h] [rbp-E8h]
  unsigned int v22; // [rsp+28h] [rbp-E0h]
  __int64 v23; // [rsp+30h] [rbp-D8h] BYREF
  const microsoft::fs::common::FsException *v24; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v25[6]; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v27[104]; // [rsp+A0h] [rbp-68h] BYREF

  v10 = (unsigned int)a3;
  try
  {
    if ( a9 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a9 + 8LL))(a9);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x264u,
        L"pbSignature",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a4 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v27,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x265u,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v27;
    }
    microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(a6, a7, a3);
    HashForProvider = microsoft::fs::cryptography::CapiCryptoFactory::CreateHashForProvider(
                        *((_QWORD *)this + 5),
                        a6,
                        a7,
                        v13,
                        (struct microsoft::fs::common::FsException *)v20);
    microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::auto_pointer<microsoft::fs::cryptography::IHash>(
      &v23,
      HashForProvider);
    v15 = v23;
    LODWORD(v21) = 0;
    (*(void (__fastcall **)(__int64, const wchar_t *, const unsigned __int8 *, _QWORD))(*(_QWORD *)v23 + 32LL))(
      v23,
      L"HASH_VALUE",
      a4,
      a5);
    *a8 = 0;
    v16 = *((_QWORD *)this + 6);
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 56LL))(v15);
    if ( !(unsigned int)fsCryptVerifySignature(v17, a2, v10, v16, v21, v22) )
    {
      LastError = GetLastError();
      *a8 = LastError;
      CSPrintErrorLineFile(0x27C0C1Du, LastError);
    }
    microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(&v23);
  }
  catch ( const microsoft::fs::common::FsException *v24 )
  {
    if ( !a9 )
      throw;
    microsoft::fs::common::FsException::assign(a9, v24);
    return;
  }
  catch ( ... )
  {
    if ( !a9 )
      throw;
    v19 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v25,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
                                                               0x287u,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a9, v19);
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
0x1800367c0  push    rbx
0x1800367c2  push    rsi
0x1800367c3  push    rdi
0x1800367c4  push    r12
0x1800367c6  push    r14
0x1800367c8  push    r15
0x1800367ca  sub     rsp, 0D8h
0x1800367d1  mov     rbx, r9
0x1800367d4  mov     r12d, r8d
0x1800367d7  mov     rsi, rdx
0x1800367da  mov     r15, rcx
0x1800367dd  mov     rcx, [rsp+108h+arg_40]
0x1800367e5  test    rcx, rcx
0x1800367e8  jz      short loc_1800367F6
0x1800367ea  mov     rax, [rcx]
0x1800367ed  mov     rax, [rax+8]
0x1800367f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367f6  test    rsi, rsi
0x1800367f9  jnz     short loc_180036832
0x1800367fb  mov     dword ptr [rsp+108h+var_E8], 80070057h; int
0x180036803  lea     r9, aPbsignature; "pbSignature"
0x18003680a  mov     r8d, 264h; unsigned int
0x180036810  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180036817  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18003681c  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180036821  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036828  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18003682d  call    _CxxThrowException_0
0x180036832  test    rbx, rbx
0x180036835  jnz     short loc_180036874
0x180036837  mov     dword ptr [rsp+108h+var_E8], 80070057h; int
0x18003683f  lea     r9, aPbhash; "pbHash"
0x180036846  mov     r8d, 265h; unsigned int
0x18003684c  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180036853  lea     rcx, [rsp+108h+var_68]; this
0x18003685b  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180036860  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036867  lea     rcx, [rsp+108h+var_68]; pExceptionObject
0x18003686f  call    _CxxThrowException_0
0x180036874  mov     edx, [rsp+108h+arg_30]; unsigned int
0x18003687b  mov     rcx, [rsp+108h+arg_28]; void *
0x180036883  call    ?CheckSignaturePaddingInfo@CryptoUtil@cryptography@fs@microsoft@@SAXPEBXKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::CheckSignaturePaddingInfo(void const *,ulong,microsoft::fs::common::FsException *)
0x180036888  mov     r8d, [rsp+108h+arg_30]; unsigned int
0x180036890  mov     rdx, [rsp+108h+arg_28]; void *
0x180036898  mov     rcx, [r15+28h]; unsigned __int64
0x18003689c  call    ?CreateHashForProvider@CapiCryptoFactory@cryptography@fs@microsoft@@SAPEAVIHash@234@_KPEBXK_NPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CapiCryptoFactory::CreateHashForProvider(unsigned __int64,void const *,ulong,bool,microsoft::fs::common::FsException *)
0x1800368a1  mov     rdx, rax
0x1800368a4  lea     rcx, [rsp+108h+var_D8]
0x1800368a9  call    ??0?$auto_pointer@VIHash@cryptography@fs@microsoft@@@common@fs@microsoft@@QEAA@PEAVIHash@cryptography@23@@Z; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::auto_pointer<microsoft::fs::cryptography::IHash>(microsoft::fs::cryptography::IHash *)
0x1800368ae  nop
0x1800368af  mov     rdi, [rsp+108h+var_D8]
0x1800368b4  mov     rax, [rdi]
0x1800368b7  mov     dword ptr [rsp+108h+var_E8], 0; unsigned __int16 *
0x1800368bf  mov     r9d, [rsp+108h+arg_20]
0x1800368c7  mov     r8, rbx
0x1800368ca  lea     rdx, aHashValue; "HASH_VALUE"
0x1800368d1  mov     rcx, rdi
0x1800368d4  mov     rax, [rax+20h]
0x1800368d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368dd  mov     r14, [rsp+108h+arg_38]
0x1800368e5  mov     dword ptr [r14], 0
0x1800368ec  mov     rbx, [r15+30h]
0x1800368f0  mov     rax, [rdi]
0x1800368f3  mov     rcx, rdi
0x1800368f6  mov     rax, [rax+38h]
0x1800368fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368ff  mov     r9, rbx; unsigned __int64
0x180036902  mov     r8d, r12d; unsigned int
0x180036905  mov     rdx, rsi; unsigned __int8 *
0x180036908  mov     rcx, rax; unsigned __int64
0x18003690b  call    ?fsCryptVerifySignature@@YAH_KPEBEK0PEBGK@Z; fsCryptVerifySignature(unsigned __int64,uchar const *,ulong,unsigned __int64,ushort const *,ulong)
0x180036910  test    eax, eax
0x180036912  jnz     short loc_18003692B
0x180036914  call    cs:__imp_GetLastError
0x18003691a  mov     [r14], eax
0x18003691d  mov     edx, eax
0x18003691f  mov     ecx, 27C0C1Dh
0x180036924  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003692a  nop
0x18003692b  lea     rcx, [rsp+108h+var_D8]
0x180036930  call    ?close@?$auto_pointer@VIHash@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_pointer<microsoft::fs::cryptography::IHash>::close(void)
0x180036935  nop
0x180036936  jmp     short loc_18003693A
0x180036938  jmp     short $+2
0x18003693a  add     rsp, 0D8h
0x180036941  pop     r15
0x180036943  pop     r14
0x180036945  pop     r12
0x180036947  pop     rdi
0x180036948  pop     rsi
0x180036949  pop     rbx
0x18003694a  retn
```
