# microsoft::fs::cryptography::CapiHash::SetProperty(ushort const *,uchar const *,ulong,ulong,microsoft::fs::common::FsException *)

- ea: `0x1800334d0`
- end: `0x180033707`
- name: `?SetProperty@CapiHash@cryptography@fs@microsoft@@UEAAXPEBGPEBEKKPEAVFsException@common@34@@Z`
- size: `567`
- prototype: `void(microsoft::fs::cryptography::CapiHash *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x18002e4dc`
- `0x18002e5e4`
- `0x18002eedc`
- `0x1800334d0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003361c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003361c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033660`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033656`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033656`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x18003360e`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x18003360e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003362b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180033638`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003364a`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003362b`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180033638`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18003364a`
- `CRYPTSP!CryptSetHashParam` at `0x1800335fd`
- `CRYPTSP!CryptSetHashParam` at `0x1800335fd`

## string_xrefs

- `0x180033524`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x180033560`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x1800335c1`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x18003367e`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x1800336cf`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall microsoft::fs::cryptography::CapiHash::SetProperty(
        microsoft::fs::cryptography::CapiHash *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        __int64 a4,
        DWORD dwFlags,
        unsigned __int16 **a6)
{
  int v9; // eax
  struct microsoft::fs::common::FsException *v10; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  DWORD v12; // esi
  BOOL v13; // edi
  DWORD v14; // ebx
  DWORD LastError; // eax
  int v16; // eax
  unsigned __int16 **v17; // rax
  unsigned __int16 **v18; // [rsp+40h] [rbp-158h] BYREF
  _QWORD v19[6]; // [rsp+48h] [rbp-150h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-120h] BYREF
  _BYTE v21[48]; // [rsp+A8h] [rbp-F0h] BYREF
  _BYTE v22[48]; // [rsp+D8h] [rbp-C0h] BYREF
  _BYTE v23[48]; // [rsp+108h] [rbp-90h] BYREF
  _BYTE v24[96]; // [rsp+138h] [rbp-60h] BYREF

  try
  {
    if ( a6 )
      (*((void (__fastcall **)(unsigned __int16 **))*a6 + 1))(a6);
    v9 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
    if ( v9 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        217,
        L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
        v9);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v21,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        218,
        L"pbValue",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v21;
    }
    PropertyLookupEntry = microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(a2, v10);
    if ( (*((_BYTE *)PropertyLookupEntry + 12) & 4) == 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        236,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v24;
    }
    if ( *((_BYTE *)PropertyLookupEntry + 8) )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v22,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        227,
        L"!ple->fIsString",
        -2147467259,
        L"Conversion of string properties to ANSI not yet supported");
      throw (microsoft::fs::common::FsException *)v22;
    }
    v12 = *((_DWORD *)PropertyLookupEntry + 4);
    v13 = CryptSetHashParam(*((_QWORD *)this + 3), v12, a3, dwFlags);
    if ( v13 )
    {
      if ( !DbgIsSSActive(0x404u) )
      {
LABEL_17:
        if ( !v13 )
        {
          LastError = GetLastError();
          v16 = HR_FROM_WIN32(LastError);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v23,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
            232,
            L"CryptSetHashParam( m_hHash, ple->nCapiProperty, pbValue, fFlags)",
            v16);
          throw (microsoft::fs::common::FsException *)v23;
        }
        return;
      }
      v14 = 0;
    }
    else
    {
      v14 = GetLastError();
    }
    CSPrintErrorLineFile(0x5000C22u, v14);
    CSPrintErrorLineFile(0x5010C22u, v12);
    CSPrintErrorLineFile(0x5020C22u, dwFlags);
    if ( v14 )
      SetLastError(v14);
    goto LABEL_17;
  }
  catch ( const microsoft::fs::common::FsException *v18 )
  {
    if ( !a6 )
      throw;
    microsoft::fs::common::FsException::assign(a6, v18);
    return;
  }
  catch ( ... )
  {
    if ( !a6 )
      throw;
    v17 = (unsigned __int16 **)microsoft::fs::common::FsException::FsException(
                                 (microsoft::fs::common::FsException *)v19,
                                 L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
                                 247,
                                 &psz,
                                 -2147467259,
                                 L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a6, v17);
    v19[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v19[1]);
    operator delete[]((void *)v19[2]);
    operator delete[]((void *)v19[3]);
    operator delete[]((void *)v19[5]);
  }
}

```

## disassembly

```asm
0x1800334d0  push    rbx
0x1800334d2  push    rsi
0x1800334d3  push    rdi
0x1800334d4  push    r14
0x1800334d6  sub     rsp, 178h
0x1800334dd  mov     rdi, r8
0x1800334e0  mov     rbx, rdx
0x1800334e3  mov     r14, rcx
0x1800334e6  mov     rcx, [rsp+198h+arg_28]
0x1800334ee  test    rcx, rcx
0x1800334f1  jz      short loc_1800334FF
0x1800334f3  mov     rax, [rcx]
0x1800334f6  mov     rax, [rax+8]
0x1800334fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334ff  xor     r8d, r8d; unsigned __int64 *
0x180033502  mov     edx, 7FFFFFFFh; unsigned __int64
0x180033507  mov     rcx, rbx; unsigned __int16 *
0x18003350a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003350f  test    eax, eax
0x180033511  jns     short loc_180033546
0x180033513  mov     [rsp+198h+var_178], eax; int
0x180033517  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x18003351e  mov     r8d, 0D9h; unsigned int
0x180033524  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003352b  lea     rcx, [rsp+198h+pExceptionObject]; this
0x180033530  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180033535  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003353c  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x180033541  call    _CxxThrowException_0
0x180033546  test    rdi, rdi
0x180033549  jnz     short loc_180033588
0x18003354b  mov     [rsp+198h+var_178], 80070057h; int
0x180033553  lea     r9, aPbvalue; "pbValue"
0x18003355a  mov     r8d, 0DAh; unsigned int
0x180033560  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x180033567  lea     rcx, [rsp+198h+var_F0]; this
0x18003356f  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180033574  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003357b  lea     rcx, [rsp+198h+var_F0]; pExceptionObject
0x180033583  call    _CxxThrowException_0
0x180033588  mov     rcx, rbx; unsigned __int16 *
0x18003358b  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x180033590  test    byte ptr [rax+0Ch], 4
0x180033594  jz      loc_1800336A9
0x18003359a  cmp     byte ptr [rax+8], 0
0x18003359e  jz      short loc_1800335E9
0x1800335a0  lea     rax, aConversionOfSt; "Conversion of string properties to ANSI"...
0x1800335a7  mov     [rsp+198h+var_170], rax; unsigned __int16 *
0x1800335ac  mov     [rsp+198h+var_178], 80004005h; int
0x1800335b4  lea     r9, aPleFisstring; "!ple->fIsString"
0x1800335bb  mov     r8d, 0E3h; unsigned int
0x1800335c1  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800335c8  lea     rcx, [rsp+198h+var_C0]; this
0x1800335d0  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800335d5  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800335dc  lea     rcx, [rsp+198h+var_C0]; pExceptionObject
0x1800335e4  call    _CxxThrowException_0
0x1800335e9  mov     esi, [rax+10h]
0x1800335ec  mov     r9d, [rsp+198h+dwFlags]; dwFlags
0x1800335f4  mov     r8, rdi; pbData
0x1800335f7  mov     edx, esi; dwParam
0x1800335f9  mov     rcx, [r14+18h]; hHash
0x1800335fd  call    cs:__imp_CryptSetHashParam
0x180033603  mov     edi, eax
0x180033605  test    eax, eax
0x180033607  jz      short loc_18003361C
0x180033609  mov     ecx, 404h
0x18003360e  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x180033614  test    eax, eax
0x180033616  jz      short loc_18003365C
0x180033618  xor     ebx, ebx
0x18003361a  jmp     short loc_180033624
0x18003361c  call    cs:__imp_GetLastError
0x180033622  mov     ebx, eax
0x180033624  mov     edx, ebx
0x180033626  mov     ecx, 5000C22h
0x18003362b  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180033631  mov     edx, esi
0x180033633  mov     ecx, 5010C22h
0x180033638  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003363e  mov     edx, [rsp+198h+dwFlags]
0x180033645  mov     ecx, 5020C22h
0x18003364a  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180033650  test    ebx, ebx
0x180033652  jz      short loc_18003365C
0x180033654  mov     ecx, ebx; dwErrCode
0x180033656  call    cs:__imp_SetLastError
0x18003365c  test    edi, edi
0x18003365e  jnz     short loc_1800336A7
0x180033660  call    cs:__imp_GetLastError
0x180033666  mov     ecx, eax; unsigned int
0x180033668  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18003366d  mov     [rsp+198h+var_178], eax; int
0x180033671  lea     r9, aCryptsethashpa_0; "CryptSetHashParam( m_hHash, ple->nCapiP"...
0x180033678  mov     r8d, 0E8h; unsigned int
0x18003367e  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x180033685  lea     rcx, [rsp+198h+var_90]; this
0x18003368d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180033692  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180033699  lea     rcx, [rsp+198h+var_90]; pExceptionObject
0x1800336a1  call    _CxxThrowException_0
0x1800336a7  jmp     short loc_1800336FA
0x1800336a9  mov     [rsp+198h+var_168], rbx
0x1800336ae  lea     rax, aInvalidPropert; "Invalid property %s."
0x1800336b5  mov     [rsp+198h+var_170], rax; unsigned __int16 *
0x1800336ba  mov     [rsp+198h+var_178], 80070057h; int
0x1800336c2  lea     r9, psz; unsigned __int16 *
0x1800336c9  mov     r8d, 0ECh; unsigned int
0x1800336cf  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800336d6  lea     rcx, [rsp+198h+var_60]; this
0x1800336de  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800336e3  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800336ea  lea     rcx, [rsp+198h+var_60]; pExceptionObject
0x1800336f2  call    _CxxThrowException_0
0x1800336f8  jmp     short $+2
0x1800336fa  add     rsp, 178h
0x180033701  pop     r14
0x180033703  pop     rdi
0x180033704  pop     rsi
0x180033705  pop     rbx
0x180033706  retn
```
