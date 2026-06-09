# microsoft::fs::cryptography::CngBCryptHash::Finalize(uchar *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180038030`
- end: `0x180038144`
- name: `?Finalize@CngBCryptHash@cryptography@fs@microsoft@@UEAAXPEAEKPEAVFsException@common@34@@Z`
- size: `276`
- prototype: `void(microsoft::fs::cryptography::CngBCryptHash *__hidden this, unsigned __int8 *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180019448`
- `0x180038030`
- `0x18003f010`

## import_xrefs

- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x1800380bc`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x1800380bc`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800380cd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800380da`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800380e7`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800380cd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800380da`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800380e7`
- `bcrypt!BCryptFinishHash` at `0x1800380ab`
- `bcrypt!BCryptFinishHash` at `0x1800380ab`

## string_xrefs

- `0x18003807c`: `onecore\ds\security\services\ca\fs\crypto\cngbcrypthash.cpp`
- `0x180038102`: `onecore\ds\security\services\ca\fs\crypto\cngbcrypthash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall microsoft::fs::cryptography::CngBCryptHash::Finalize(
        BCRYPT_HASH_HANDLE *this,
        unsigned __int8 *a2,
        ULONG a3,
        struct microsoft::fs::common::FsException *a4)
{
  NTSTATUS v7; // ebx
  const struct microsoft::fs::common::FsException *v8; // rax
  const microsoft::fs::common::FsException *v9; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v10[6]; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v12[56]; // [rsp+98h] [rbp-40h] BYREF

  try
  {
    if ( a4 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a4 + 8LL))(a4);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcrypthash.cpp",
        0x57u,
        L"pbHash",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v7 = BCryptFinishHash(this[3], a2, a3, 0);
    if ( v7 || DbgIsSSActive(0x404u) )
    {
      CSPrintErrorLineFile(0x37F0C25u, v7);
      CSPrintErrorLineFile(0x3800C25u, a3);
      CSPrintErrorLineFile(0x3810C25u, 0);
      if ( v7 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v12,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcrypthash.cpp",
          0x5Au,
          L"BCryptFinishHash(m_hHash, pbHash, cbHash, 0)",
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
    v8 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                              (microsoft::fs::common::FsException *)v10,
                                                              L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcrypthash.cpp",
                                                              0x64u,
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
0x180038030  mov     [rsp+arg_0], rbx
0x180038035  mov     [rsp+arg_8], rsi
0x18003803a  mov     [rsp+arg_18], r9
0x18003803f  push    rdi
0x180038040  sub     rsp, 0D0h
0x180038047  mov     edi, r8d
0x18003804a  mov     rbx, rdx
0x18003804d  mov     rsi, rcx
0x180038050  test    r9, r9
0x180038053  jz      short loc_180038064
0x180038055  mov     rax, [r9]
0x180038058  mov     rcx, r9
0x18003805b  mov     rax, [rax+8]
0x18003805f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038064  test    rbx, rbx
0x180038067  jnz     short loc_18003809E
0x180038069  mov     [rsp+0D8h+var_B8], 80070057h; int
0x180038071  lea     r9, aPbhash; "pbHash"
0x180038078  lea     r8d, [rbx+57h]; unsigned int
0x18003807c  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\services\\ca\\fs"...
0x180038083  lea     rcx, [rsp+0D8h+pExceptionObject]; this
0x180038088  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003808d  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180038094  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180038099  call    _CxxThrowException_0
0x18003809e  xor     r9d, r9d; dwFlags
0x1800380a1  mov     r8d, edi; cbOutput
0x1800380a4  mov     rdx, rbx; pbOutput
0x1800380a7  mov     rcx, [rsi+18h]; hHash
0x1800380ab  call    cs:__imp_BCryptFinishHash
0x1800380b1  mov     ebx, eax
0x1800380b3  test    eax, eax
0x1800380b5  jnz     short loc_1800380C6
0x1800380b7  mov     ecx, 404h
0x1800380bc  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x1800380c2  test    eax, eax
0x1800380c4  jz      short loc_18003812B
0x1800380c6  mov     edx, ebx
0x1800380c8  mov     ecx, 37F0C25h
0x1800380cd  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800380d3  mov     edx, edi
0x1800380d5  mov     ecx, 3800C25h
0x1800380da  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800380e0  xor     edx, edx
0x1800380e2  mov     ecx, 3810C25h
0x1800380e7  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800380ed  test    ebx, ebx
0x1800380ef  jns     short loc_18003812B
0x1800380f1  mov     [rsp+0D8h+var_B8], ebx; int
0x1800380f5  lea     r9, aBcryptfinishha_0; "BCryptFinishHash(m_hHash, pbHash, cbHas"...
0x1800380fc  mov     r8d, 5Ah ; 'Z'; unsigned int
0x180038102  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\services\\ca\\fs"...
0x180038109  lea     rcx, [rsp+0D8h+var_40]; this
0x180038111  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180038116  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003811d  lea     rcx, [rsp+0D8h+var_40]; pExceptionObject
0x180038125  call    _CxxThrowException_0
0x18003812b  jmp     short loc_18003812F
0x18003812d  jmp     short $+2
0x18003812f  lea     r11, [rsp+0D8h+var_8]
0x180038137  mov     rbx, [r11+10h]
0x18003813b  mov     rsi, [r11+18h]
0x18003813f  mov     rsp, r11
0x180038142  pop     rdi
0x180038143  retn
```
