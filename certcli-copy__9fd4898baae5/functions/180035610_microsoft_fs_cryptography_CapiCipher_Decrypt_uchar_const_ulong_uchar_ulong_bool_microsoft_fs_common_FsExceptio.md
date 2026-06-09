# microsoft::fs::cryptography::CapiCipher::Decrypt(uchar const *,ulong,uchar *,ulong *,bool,microsoft::fs::common::FsException *)

- ea: `0x180035610`
- end: `0x18003580e`
- name: `?Decrypt@CapiCipher@cryptography@fs@microsoft@@UEAAXPEBEKPEAEPEAK_NPEAVFsException@common@34@@Z`
- size: `510`
- prototype: `void(microsoft::fs::cryptography::CapiCipher *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *, bool, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180002306`
- `0x180019448`
- `0x18002e5e4`
- `0x18002f19c`
- `0x180035610`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800357a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800357a9`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180035773`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180035773`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180035790`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003579d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180035790`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003579d`
- `CRYPTSP!CryptDecrypt` at `0x180035762`
- `CRYPTSP!CryptDecrypt` at `0x180035762`

## string_xrefs

- `0x18003565e`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800356a2`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800356fa`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800357d1`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CapiCipher::Decrypt(
        microsoft::fs::cryptography::CapiCipher *this,
        unsigned __int8 *a2,
        struct microsoft::fs::common::FsException *a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        bool a6,
        struct microsoft::fs::common::FsException *a7)
{
  size_t v8; // rdi
  int v12; // eax
  BOOL v13; // edi
  DWORD LastError; // ebx
  DWORD v15; // eax
  int v16; // eax
  const struct microsoft::fs::common::FsException *v17; // rax
  const microsoft::fs::common::FsException *v18; // [rsp+30h] [rbp-128h] BYREF
  _QWORD v19[6]; // [rsp+38h] [rbp-120h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+68h] [rbp-F0h] BYREF
  _BYTE v21[48]; // [rsp+98h] [rbp-C0h] BYREF
  _BYTE v22[48]; // [rsp+C8h] [rbp-90h] BYREF
  _BYTE v23[96]; // [rsp+F8h] [rbp-60h] BYREF

  v8 = (unsigned int)a3;
  try
  {
    if ( a7 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a7 + 8LL))(a7);
    if ( !a2 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x99u,
        L"pbCipherText",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a5 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v21,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x9Bu,
        L"pcbPlainText",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v21;
    }
  }
  catch ( const microsoft::fs::common::FsException *v18 )
  {
    if ( !a7 )
      throw;
    microsoft::fs::common::FsException::assign(a7, v18);
    return;
  }
  catch ( ... )
  {
    if ( !a7 )
      throw;
    v17 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v19,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
                                                               0xC7u,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a7, v17);
    v19[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v19[1]);
    operator delete[]((void *)v19[2]);
    operator delete[]((void *)v19[3]);
    operator delete[]((void *)v19[5]);
    return;
  }
  if ( !a4 )
  {
    *a5 = v8;
    return;
  }
  if ( a2 != a4 )
  {
    if ( *a5 < (unsigned int)v8 )
    {
      v12 = HR_FROM_WIN32(0x80090004);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v22,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0xABu,
        L"*pcbPlainText >= cbCipherText",
        v12);
      throw (microsoft::fs::common::FsException *)v22;
    }
    memcpy_0(a4, a2, v8);
  }
  *a5 = v8;
  if ( *((_DWORD *)this + 6) == 41984 )
    microsoft::fs::cryptography::CryptoUtil::OsToI(a4, v8, a3);
  v13 = CryptDecrypt(*((_QWORD *)this + 6), 0, a6, 0, a4, a5);
  if ( !v13 )
  {
    LastError = GetLastError();
LABEL_20:
    CSPrintErrorLineFile(0x31C0C22u, LastError);
    CSPrintErrorLineFile(0x31D0C22u, 0);
    if ( LastError )
      SetLastError(LastError);
    goto LABEL_22;
  }
  if ( DbgIsSSActive(0x404u) )
  {
    LastError = 0;
    goto LABEL_20;
  }
LABEL_22:
  if ( !v13 )
  {
    v15 = GetLastError();
    v16 = HR_FROM_WIN32(v15);
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)v23,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
      0xBDu,
      L"CryptDecrypt( m_hKey, 0, fFinal ? TRUE : FALSE, 0, pbPlainText, pcbPlainText)",
      v16);
    throw (microsoft::fs::common::FsException *)v23;
  }
}

```

## disassembly

```asm
0x180035610  push    rbx
0x180035612  push    rsi
0x180035613  push    rdi
0x180035614  push    r14
0x180035616  push    r15
0x180035618  sub     rsp, 130h
0x18003561f  mov     rsi, r9
0x180035622  mov     edi, r8d
0x180035625  mov     r14, rdx
0x180035628  mov     r15, rcx
0x18003562b  mov     rcx, [rsp+158h+arg_30]
0x180035633  test    rcx, rcx
0x180035636  jz      short loc_180035644
0x180035638  mov     rax, [rcx]
0x18003563b  mov     rax, [rax+8]
0x18003563f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035644  test    r14, r14
0x180035647  jnz     short loc_180035680
0x180035649  mov     dword ptr [rsp+158h+pbData], 80070057h; int
0x180035651  lea     r9, aPbciphertext; "pbCipherText"
0x180035658  mov     r8d, 99h; unsigned int
0x18003565e  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035665  lea     rcx, [rsp+158h+pExceptionObject]; this
0x18003566a  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003566f  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035676  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x18003567b  call    _CxxThrowException_0
0x180035680  mov     rbx, [rsp+158h+arg_20]
0x180035688  test    rbx, rbx
0x18003568b  jnz     short loc_1800356CA
0x18003568d  mov     dword ptr [rsp+158h+pbData], 80070057h; int
0x180035695  lea     r9, aPcbplaintext; "pcbPlainText"
0x18003569c  mov     r8d, 9Bh; unsigned int
0x1800356a2  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800356a9  lea     rcx, [rsp+158h+var_C0]; this
0x1800356b1  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800356b6  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800356bd  lea     rcx, [rsp+158h+var_C0]; pExceptionObject
0x1800356c5  call    _CxxThrowException_0
0x1800356ca  test    rsi, rsi
0x1800356cd  jnz     short loc_1800356D6
0x1800356cf  mov     [rbx], edi
0x1800356d1  jmp     loc_1800357FE
0x1800356d6  cmp     r14, rsi
0x1800356d9  jz      short loc_180035730
0x1800356db  cmp     [rbx], edi
0x1800356dd  jnb     short loc_180035722
0x1800356df  mov     ecx, 80090004h; unsigned int
0x1800356e4  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x1800356e9  mov     dword ptr [rsp+158h+pbData], eax; int
0x1800356ed  lea     r9, aPcbplaintextCb; "*pcbPlainText >= cbCipherText"
0x1800356f4  mov     r8d, 0ABh; unsigned int
0x1800356fa  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035701  lea     rcx, [rsp+158h+var_90]; this
0x180035709  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003570e  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035715  lea     rcx, [rsp+158h+var_90]; pExceptionObject
0x18003571d  call    _CxxThrowException_0
0x180035722  mov     r8, rdi; Size
0x180035725  mov     rdx, r14; Src
0x180035728  mov     rcx, rsi; void *
0x18003572b  call    memcpy_0
0x180035730  mov     [rbx], edi
0x180035732  cmp     dword ptr [r15+18h], 0A400h
0x18003573a  jnz     short loc_180035746
0x18003573c  mov     edx, edi; unsigned int
0x18003573e  mov     rcx, rsi; unsigned __int8 *
0x180035741  call    ?OsToI@CryptoUtil@cryptography@fs@microsoft@@SAXPEAEKPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::OsToI(uchar *,ulong,microsoft::fs::common::FsException *)
0x180035746  movzx   r8d, [rsp+158h+arg_28]; Final
0x18003574f  mov     [rsp+158h+pdwDataLen], rbx; pdwDataLen
0x180035754  mov     [rsp+158h+pbData], rsi; pbData
0x180035759  xor     r9d, r9d; dwFlags
0x18003575c  xor     edx, edx; hHash
0x18003575e  mov     rcx, [r15+30h]; hKey
0x180035762  call    cs:__imp_CryptDecrypt
0x180035768  mov     edi, eax
0x18003576a  test    eax, eax
0x18003576c  jz      short loc_180035781
0x18003576e  mov     ecx, 404h
0x180035773  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180035779  test    eax, eax
0x18003577b  jz      short loc_1800357AF
0x18003577d  xor     ebx, ebx
0x18003577f  jmp     short loc_180035789
0x180035781  call    cs:__imp_GetLastError
0x180035787  mov     ebx, eax
0x180035789  mov     edx, ebx
0x18003578b  mov     ecx, 31C0C22h
0x180035790  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035796  xor     edx, edx
0x180035798  mov     ecx, 31D0C22h
0x18003579d  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800357a3  test    ebx, ebx
0x1800357a5  jz      short loc_1800357AF
0x1800357a7  mov     ecx, ebx; dwErrCode
0x1800357a9  call    cs:__imp_SetLastError
0x1800357af  test    edi, edi
0x1800357b1  jnz     short loc_1800357FA
0x1800357b3  call    cs:__imp_GetLastError
0x1800357b9  mov     ecx, eax; unsigned int
0x1800357bb  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x1800357c0  mov     dword ptr [rsp+158h+pbData], eax; int
0x1800357c4  lea     r9, aCryptdecryptMH; "CryptDecrypt( m_hKey, 0, fFinal ? TRUE "...
0x1800357cb  mov     r8d, 0BDh; unsigned int
0x1800357d1  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800357d8  lea     rcx, [rsp+158h+var_60]; this
0x1800357e0  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800357e5  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800357ec  lea     rcx, [rsp+158h+var_60]; pExceptionObject
0x1800357f4  call    _CxxThrowException_0
0x1800357fa  jmp     short loc_1800357FE
0x1800357fc  jmp     short $+2
0x1800357fe  add     rsp, 130h
0x180035805  pop     r15
0x180035807  pop     r14
0x180035809  pop     rdi
0x18003580a  pop     rsi
0x18003580b  pop     rbx
0x18003580c  retn
```
