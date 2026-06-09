# microsoft::fs::cryptography::CngBCryptHash::Hash(uchar const *,ulong,microsoft::fs::common::FsException *)

- ea: `0x1800382e0`
- end: `0x1800383f6`
- name: `?Hash@CngBCryptHash@cryptography@fs@microsoft@@UEAAXPEBEKPEAVFsException@common@34@@Z`
- size: `278`
- prototype: `void(microsoft::fs::cryptography::CngBCryptHash *__hidden this, const unsigned __int8 *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x1800382e0`
- `0x18003f010`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x18003836e`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x18003836e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003837f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003838c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180038399`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003837f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003838c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180038399`
- `bcrypt!BCryptHashData` at `0x18003835d`
- `bcrypt!BCryptHashData` at `0x18003835d`

## string_xrefs

- `0x18003832e`: `onecore\ds\security\services\ca\fs\crypto\cngbcrypthash.cpp`
- `0x1800383b4`: `onecore\ds\security\services\ca\fs\crypto\cngbcrypthash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall microsoft::fs::cryptography::CngBCryptHash::Hash(
        BCRYPT_HASH_HANDLE *this,
        UCHAR *a2,
        ULONG a3,
        unsigned __int16 **a4)
{
  NTSTATUS v7; // ebx
  unsigned __int16 **v8; // rax
  unsigned __int16 **v9; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v10[6]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v12[56]; // [rsp+98h] [rbp-40h] BYREF

  try
  {
    if ( a4 )
      (*((void (__fastcall **)(unsigned __int16 **))*a4 + 1))(a4);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcrypthash.cpp",
        165,
        L"pbData",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v7 = BCryptHashData(this[3], a2, a3, 0);
    if ( v7 || DbgIsSSActive(0x404u) )
    {
      CSPrintErrorLineFile(0x3EA0C25u, v7);
      CSPrintErrorLineFile(0x3EB0C25u, a3);
      CSPrintErrorLineFile(0x3EC0C25u, 0);
      if ( v7 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v12,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcrypthash.cpp",
          168,
          L"BCryptHashData(m_hHash, const_cast<BYTE*>(pbData), cbData, 0)",
          v7);
        throw (microsoft::fs::common::FsException *)v12;
      }
    }
  }
  catch ( const microsoft::fs::common::FsException *v9 )
  {
    if ( !a4 )
      throw;
    microsoft::fs::common::FsException::assign(a4, v9);
    return;
  }
  catch ( ... )
  {
    if ( !a4 )
      throw;
    v8 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                                (microsoft::fs::common::FsException *)v10,
                                L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcrypthash.cpp",
                                178,
                                &psz,
                                -2147467259,
                                L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a4, v8);
    v10[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v10[1]);
    operator delete[]((void *)v10[2]);
    operator delete[]((void *)v10[3]);
    operator delete[]((void *)v10[5]);
  }
}

```

## disassembly

```asm
0x1800382e0  mov     [rsp+arg_0], rbx
0x1800382e5  mov     [rsp+arg_8], rsi
0x1800382ea  mov     [rsp+arg_18], r9
0x1800382ef  push    rdi
0x1800382f0  sub     rsp, 0D0h
0x1800382f7  mov     edi, r8d
0x1800382fa  mov     rbx, rdx
0x1800382fd  mov     rsi, rcx
0x180038300  test    r9, r9
0x180038303  jz      short loc_180038314
0x180038305  mov     rax, [r9]
0x180038308  mov     rcx, r9
0x18003830b  mov     rax, [rax+8]
0x18003830f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038314  test    rbx, rbx
0x180038317  jnz     short loc_180038350
0x180038319  mov     [rsp+0D8h+var_B8], 80070057h; int
0x180038321  lea     r9, aPbdata; "pbData"
0x180038328  mov     r8d, 0A5h; unsigned int
0x18003832e  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\services\\ca\\fs"...
0x180038335  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x18003833a  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003833f  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180038346  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18003834b  call    _CxxThrowException_0
0x180038350  xor     r9d, r9d; dwFlags
0x180038353  mov     r8d, edi; cbInput
0x180038356  mov     rdx, rbx; pbInput
0x180038359  mov     rcx, [rsi+18h]; hHash
0x18003835d  call    cs:__imp_BCryptHashData
0x180038363  mov     ebx, eax
0x180038365  test    eax, eax
0x180038367  jnz     short loc_180038378
0x180038369  mov     ecx, 404h
0x18003836e  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180038374  test    eax, eax
0x180038376  jz      short loc_1800383DD
0x180038378  mov     edx, ebx
0x18003837a  mov     ecx, 3EA0C25h
0x18003837f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180038385  mov     edx, edi
0x180038387  mov     ecx, 3EB0C25h
0x18003838c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180038392  xor     edx, edx
0x180038394  mov     ecx, 3EC0C25h
0x180038399  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003839f  test    ebx, ebx
0x1800383a1  jns     short loc_1800383DD
0x1800383a3  mov     [rsp+0D8h+var_B8], ebx; int
0x1800383a7  lea     r9, aBcrypthashdata_0; "BCryptHashData(m_hHash, const_cast<BYTE"...
0x1800383ae  mov     r8d, 0A8h; unsigned int
0x1800383b4  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800383bb  lea     rcx, [rsp+0D8h+var_40]; this
0x1800383c3  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800383c8  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800383cf  lea     rcx, [rsp+0D8h+var_40]; pExceptionObject
0x1800383d7  call    _CxxThrowException_0
0x1800383dd  jmp     short loc_1800383E1
0x1800383df  jmp     short $+2
0x1800383e1  lea     r11, [rsp+0D8h+var_8]
0x1800383e9  mov     rbx, [r11+10h]
0x1800383ed  mov     rsi, [r11+18h]
0x1800383f1  mov     rsp, r11
0x1800383f4  pop     rdi
0x1800383f5  retn
```
