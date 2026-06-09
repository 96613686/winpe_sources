# microsoft::fs::cryptography::CapiCipher::SetProperty(ushort const *,uchar const *,ulong,ulong,microsoft::fs::common::FsException *)

- ea: `0x1800361b0`
- end: `0x1800365ef`
- name: `?SetProperty@CapiCipher@cryptography@fs@microsoft@@UEAAXPEBGPEBEKKPEAVFsException@common@34@@Z`
- size: `1087`
- prototype: `void(microsoft::fs::cryptography::CapiCipher *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x18002e4dc`
- `0x18002e5e4`
- `0x18002eedc`
- `0x18003169c`
- `0x1800361b0`
- `0x18003970a`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003648d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003654b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003648d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003654b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003647f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003647f`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180036437`
- `certca!__imp_?DbgIsSSActive@@YAHK@Z` at `0x180036437`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036454`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036461`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036473`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036454`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036461`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180036473`
- `CRYPTSP!CryptSetKeyParam` at `0x180036426`
- `CRYPTSP!CryptSetKeyParam` at `0x180036426`

## string_xrefs

- `0x180036207`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180036243`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800362b2`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800362f5`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180036337`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180036391`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800363ea`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800364ab`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180036504`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180036569`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800365b7`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CapiCipher::SetProperty(
        microsoft::fs::cryptography::CapiCipher *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        int a4,
        DWORD dwFlags,
        struct microsoft::fs::common::FsException *a6)
{
  int v10; // eax
  struct microsoft::fs::common::FsException *v11; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  DWORD v13; // esi
  BOOL v14; // edi
  DWORD v15; // ebx
  DWORD LastError; // eax
  int v17; // eax
  DWORD v18; // eax
  int v19; // eax
  const struct microsoft::fs::common::FsException *v20; // rax
  const microsoft::fs::common::FsException *v21; // [rsp+40h] [rbp-278h] BYREF
  _QWORD v22[6]; // [rsp+48h] [rbp-270h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-240h] BYREF
  _BYTE v24[48]; // [rsp+A8h] [rbp-210h] BYREF
  _BYTE v25[48]; // [rsp+D8h] [rbp-1E0h] BYREF
  _BYTE v26[48]; // [rsp+108h] [rbp-1B0h] BYREF
  _BYTE v27[48]; // [rsp+138h] [rbp-180h] BYREF
  _BYTE v28[48]; // [rsp+168h] [rbp-150h] BYREF
  _BYTE v29[48]; // [rsp+198h] [rbp-120h] BYREF
  _BYTE v30[48]; // [rsp+1C8h] [rbp-F0h] BYREF
  _BYTE v31[48]; // [rsp+1F8h] [rbp-C0h] BYREF
  _BYTE v32[48]; // [rsp+228h] [rbp-90h] BYREF
  _BYTE v33[96]; // [rsp+258h] [rbp-60h] BYREF

  try
  {
    if ( a6 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a6 + 8LL))(a6);
    v10 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
    if ( v10 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x1E9u,
        L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
        v10);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x1EAu,
        L"pbValue",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v24;
    }
    PropertyLookupEntry = microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(a2, v11);
    if ( (*((_BYTE *)PropertyLookupEntry + 12) & 1) != 0 )
    {
      if ( wcscmp_0(a2, L"ASYM_ENCRYPT_PAD_FLAG") )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v28,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0x1F9u,
          &psz,
          -2147024809,
          L"Invalid property %s.",
          a2);
        throw (microsoft::fs::common::FsException *)v28;
      }
      if ( *((_DWORD *)this + 6) != 41984 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v25,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0x1F2u,
          L"CALG_RSA_KEYX == m_nCipherAlgorithm",
          -2147024809);
        throw (microsoft::fs::common::FsException *)v25;
      }
      if ( a4 != 4 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v26,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0x1F3u,
          L"sizeof (m_fAsymEncryptPad) == cbValue",
          -2147024809);
        throw (microsoft::fs::common::FsException *)v26;
      }
      if ( *(_DWORD *)a3 != 1 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v27,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0x1F4u,
          L"*reinterpret_cast<const DWORD*>(pbValue) == crypto::FS_ASYM_ENCRYPT_FLAG_PAD_PKCS1",
          -2147467263);
        throw (microsoft::fs::common::FsException *)v27;
      }
      *((_DWORD *)this + 4) = 1;
      return;
    }
    if ( (*((_BYTE *)PropertyLookupEntry + 12) & 2) != 0 )
    {
      if ( *((_BYTE *)PropertyLookupEntry + 8) )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v29,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0x201u,
          L"!ple->fIsString",
          -2147467259,
          L"Conversion of string properties to ANSI not yet supported");
        throw (microsoft::fs::common::FsException *)v29;
      }
      v13 = *((_DWORD *)PropertyLookupEntry + 4);
      v14 = CryptSetKeyParam(*((_QWORD *)this + 6), v13, a3, dwFlags);
      if ( v14 )
      {
        if ( !DbgIsSSActive(0x404u) )
        {
LABEL_27:
          if ( !v14 )
          {
            LastError = GetLastError();
            v17 = HR_FROM_WIN32(LastError);
            microsoft::fs::common::FsException::FsException(
              (microsoft::fs::common::FsException *)v30,
              L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
              0x206u,
              L"CryptSetKeyParam( m_hKey, ple->nCapiProperty, pbValue, fFlags)",
              v17);
            throw (microsoft::fs::common::FsException *)v30;
          }
          return;
        }
        v15 = 0;
      }
      else
      {
        v15 = GetLastError();
      }
      CSPrintErrorLineFile(0x5150C22u, v15);
      CSPrintErrorLineFile(0x5160C22u, v13);
      CSPrintErrorLineFile(0x5170C22u, dwFlags);
      if ( v15 )
        SetLastError(v15);
      goto LABEL_27;
    }
    if ( (*((_BYTE *)PropertyLookupEntry + 12) & 8) == 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v33,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x216u,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v33;
    }
    if ( *((_BYTE *)PropertyLookupEntry + 8) )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v31,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x20Du,
        L"!ple->fIsString",
        -2147467259,
        L"Conversion of string properties to ANSI not yet supported");
      throw (microsoft::fs::common::FsException *)v31;
    }
    if ( !(unsigned int)fsCryptSetProvParam(*((_QWORD *)this + 5), *((_DWORD *)PropertyLookupEntry + 4), a3, dwFlags) )
    {
      v18 = GetLastError();
      v19 = HR_FROM_WIN32(v18);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v32,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x212u,
        L"CryptSetProvParam( m_hProv, ple->nCapiProperty, pbValue, fFlags)",
        v19);
      throw (microsoft::fs::common::FsException *)v32;
    }
  }
  catch ( const microsoft::fs::common::FsException *v21 )
  {
    if ( !a6 )
      throw;
    microsoft::fs::common::FsException::assign(a6, v21);
    return;
  }
  catch ( ... )
  {
    if ( !a6 )
      throw;
    v20 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v22,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
                                                               0x221u,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a6, v20);
    v22[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v22[1]);
    operator delete[]((void *)v22[2]);
    operator delete[]((void *)v22[3]);
    operator delete[]((void *)v22[5]);
  }
}

```

## disassembly

```asm
0x1800361b0  push    rbx
0x1800361b2  push    rsi
0x1800361b3  push    rdi
0x1800361b4  push    r14
0x1800361b6  sub     rsp, 298h
0x1800361bd  mov     r14d, r9d
0x1800361c0  mov     rdi, r8
0x1800361c3  mov     rsi, rdx
0x1800361c6  mov     rbx, rcx
0x1800361c9  mov     rcx, [rsp+2B8h+arg_28]
0x1800361d1  test    rcx, rcx
0x1800361d4  jz      short loc_1800361E2
0x1800361d6  mov     rax, [rcx]
0x1800361d9  mov     rax, [rax+8]
0x1800361dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361e2  xor     r8d, r8d; unsigned __int64 *
0x1800361e5  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800361ea  mov     rcx, rsi; unsigned __int16 *
0x1800361ed  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800361f2  test    eax, eax
0x1800361f4  jns     short loc_180036229
0x1800361f6  mov     [rsp+2B8h+var_298], eax; int
0x1800361fa  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x180036201  mov     r8d, 1E9h; unsigned int
0x180036207  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003620e  lea     rcx, [rsp+2B8h+pExceptionObject]; this
0x180036213  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180036218  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003621f  lea     rcx, [rsp+2B8h+pExceptionObject]; pExceptionObject
0x180036224  call    _CxxThrowException_0
0x180036229  test    rdi, rdi
0x18003622c  jnz     short loc_18003626B
0x18003622e  mov     [rsp+2B8h+var_298], 80070057h; int
0x180036236  lea     r9, aPbvalue; "pbValue"
0x18003623d  mov     r8d, 1EAh; unsigned int
0x180036243  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003624a  lea     rcx, [rsp+2B8h+var_210]; this
0x180036252  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180036257  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003625e  lea     rcx, [rsp+2B8h+var_210]; pExceptionObject
0x180036266  call    _CxxThrowException_0
0x18003626b  mov     rcx, rsi; unsigned __int16 *
0x18003626e  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x180036273  test    byte ptr [rax+0Ch], 1
0x180036277  jz      loc_1800363B9
0x18003627d  lea     rdx, aAsymEncryptPad; "ASYM_ENCRYPT_PAD_FLAG"
0x180036284  mov     rcx, rsi; String1
0x180036287  call    wcscmp_0
0x18003628c  test    eax, eax
0x18003628e  jnz     loc_18003636B
0x180036294  cmp     dword ptr [rbx+18h], 0A400h
0x18003629b  jz      short loc_1800362DA
0x18003629d  mov     [rsp+2B8h+var_298], 80070057h; int
0x1800362a5  lea     r9, aCalgRsaKeyxMNc; "CALG_RSA_KEYX == m_nCipherAlgorithm"
0x1800362ac  mov     r8d, 1F2h; unsigned int
0x1800362b2  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800362b9  lea     rcx, [rsp+2B8h+var_1E0]; this
0x1800362c1  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800362c6  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800362cd  lea     rcx, [rsp+2B8h+var_1E0]; pExceptionObject
0x1800362d5  call    _CxxThrowException_0
0x1800362da  cmp     r14d, 4
0x1800362de  jz      short loc_18003631D
0x1800362e0  mov     [rsp+2B8h+var_298], 80070057h; int
0x1800362e8  lea     r9, aSizeofMFasymen; "sizeof (m_fAsymEncryptPad) == cbValue"
0x1800362ef  mov     r8d, 1F3h; unsigned int
0x1800362f5  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800362fc  lea     rcx, [rsp+2B8h+var_1B0]; this
0x180036304  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180036309  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036310  lea     rcx, [rsp+2B8h+var_1B0]; pExceptionObject
0x180036318  call    _CxxThrowException_0
0x18003631d  cmp     dword ptr [rdi], 1
0x180036320  jz      short loc_18003635F
0x180036322  mov     [rsp+2B8h+var_298], 80004001h; int
0x18003632a  lea     r9, aReinterpretCas; "*reinterpret_cast<const DWORD*>(pbValue"...
0x180036331  mov     r8d, 1F4h; unsigned int
0x180036337  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003633e  lea     rcx, [rsp+2B8h+var_180]; this
0x180036346  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003634b  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036352  lea     rcx, [rsp+2B8h+var_180]; pExceptionObject
0x18003635a  call    _CxxThrowException_0
0x18003635f  mov     dword ptr [rbx+10h], 1
0x180036366  jmp     loc_1800365E2
0x18003636b  mov     [rsp+2B8h+var_288], rsi
0x180036370  lea     rax, aInvalidPropert; "Invalid property %s."
0x180036377  mov     [rsp+2B8h+var_290], rax; unsigned __int16 *
0x18003637c  mov     [rsp+2B8h+var_298], 80070057h; int
0x180036384  lea     r9, psz; unsigned __int16 *
0x18003638b  mov     r8d, 1F9h; unsigned int
0x180036391  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180036398  lea     rcx, [rsp+2B8h+var_150]; this
0x1800363a0  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800363a5  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800363ac  lea     rcx, [rsp+2B8h+var_150]; pExceptionObject
0x1800363b4  call    _CxxThrowException_0
0x1800363b9  test    byte ptr [rax+0Ch], 2
0x1800363bd  jz      loc_1800364D3
0x1800363c3  cmp     byte ptr [rax+8], 0
0x1800363c7  jz      short loc_180036412
0x1800363c9  lea     rax, aConversionOfSt; "Conversion of string properties to ANSI"...
0x1800363d0  mov     [rsp+2B8h+var_290], rax; unsigned __int16 *
0x1800363d5  mov     [rsp+2B8h+var_298], 80004005h; int
0x1800363dd  lea     r9, aPleFisstring; "!ple->fIsString"
0x1800363e4  mov     r8d, 201h; unsigned int
0x1800363ea  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800363f1  lea     rcx, [rsp+2B8h+var_120]; this
0x1800363f9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800363fe  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036405  lea     rcx, [rsp+2B8h+var_120]; pExceptionObject
0x18003640d  call    _CxxThrowException_0
0x180036412  mov     esi, [rax+10h]
0x180036415  mov     r9d, [rsp+2B8h+dwFlags]; dwFlags
0x18003641d  mov     r8, rdi; pbData
0x180036420  mov     edx, esi; dwParam
0x180036422  mov     rcx, [rbx+30h]; hKey
0x180036426  call    cs:__imp_CryptSetKeyParam
0x18003642c  mov     edi, eax
0x18003642e  test    eax, eax
0x180036430  jz      short loc_180036445
0x180036432  mov     ecx, 404h
0x180036437  call    cs:__imp_?DbgIsSSActive@@YAHK@Z; DbgIsSSActive(ulong)
0x18003643d  test    eax, eax
0x18003643f  jz      short loc_180036485
0x180036441  xor     ebx, ebx
0x180036443  jmp     short loc_18003644D
0x180036445  call    cs:__imp_GetLastError
0x18003644b  mov     ebx, eax
0x18003644d  mov     edx, ebx
0x18003644f  mov     ecx, 5150C22h
0x180036454  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003645a  mov     edx, esi
0x18003645c  mov     ecx, 5160C22h
0x180036461  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180036467  mov     edx, [rsp+2B8h+dwFlags]
0x18003646e  mov     ecx, 5170C22h
0x180036473  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180036479  test    ebx, ebx
0x18003647b  jz      short loc_180036485
0x18003647d  mov     ecx, ebx; dwErrCode
0x18003647f  call    cs:__imp_SetLastError
0x180036485  test    edi, edi
0x180036487  jnz     loc_180036366
0x18003648d  call    cs:__imp_GetLastError
0x180036493  mov     ecx, eax; unsigned int
0x180036495  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18003649a  mov     [rsp+2B8h+var_298], eax; int
0x18003649e  lea     r9, aCryptsetkeypar_0; "CryptSetKeyParam( m_hKey, ple->nCapiPro"...
0x1800364a5  mov     r8d, 206h; unsigned int
0x1800364ab  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800364b2  lea     rcx, [rsp+2B8h+var_F0]; this
0x1800364ba  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800364bf  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800364c6  lea     rcx, [rsp+2B8h+var_F0]; pExceptionObject
0x1800364ce  call    _CxxThrowException_0
0x1800364d3  test    byte ptr [rax+0Ch], 8
0x1800364d7  jz      loc_180036591
0x1800364dd  cmp     byte ptr [rax+8], 0
0x1800364e1  jz      short loc_18003652C
0x1800364e3  lea     rax, aConversionOfSt; "Conversion of string properties to ANSI"...
0x1800364ea  mov     [rsp+2B8h+var_290], rax; unsigned __int16 *
0x1800364ef  mov     [rsp+2B8h+var_298], 80004005h; int
0x1800364f7  lea     r9, aPleFisstring; "!ple->fIsString"
0x1800364fe  mov     r8d, 20Dh; unsigned int
0x180036504  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003650b  lea     rcx, [rsp+2B8h+var_C0]; this
0x180036513  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180036518  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003651f  lea     rcx, [rsp+2B8h+var_C0]; pExceptionObject
0x180036527  call    _CxxThrowException_0
0x18003652c  mov     r9d, [rsp+2B8h+dwFlags]; unsigned int
0x180036534  mov     r8, rdi; unsigned __int8 *
0x180036537  mov     edx, [rax+10h]; unsigned int
0x18003653a  mov     rcx, [rbx+28h]; unsigned __int64
0x18003653e  call    ?fsCryptSetProvParam@@YAH_KKPEBEK@Z; fsCryptSetProvParam(unsigned __int64,ulong,uchar const *,ulong)
0x180036543  test    eax, eax
0x180036545  jnz     loc_180036366
0x18003654b  call    cs:__imp_GetLastError
0x180036551  mov     ecx, eax; unsigned int
0x180036553  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180036558  mov     [rsp+2B8h+var_298], eax; int
0x18003655c  lea     r9, aCryptsetprovpa_0; "CryptSetProvParam( m_hProv, ple->nCapiP"...
0x180036563  mov     r8d, 212h; unsigned int
0x180036569  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180036570  lea     rcx, [rsp+2B8h+var_90]; this
0x180036578  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003657d  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036584  lea     rcx, [rsp+2B8h+var_90]; pExceptionObject
0x18003658c  call    _CxxThrowException_0
0x180036591  mov     [rsp+2B8h+var_288], rsi
0x180036596  lea     rax, aInvalidPropert; "Invalid property %s."
0x18003659d  mov     [rsp+2B8h+var_290], rax; unsigned __int16 *
0x1800365a2  mov     [rsp+2B8h+var_298], 80070057h; int
0x1800365aa  lea     r9, psz; unsigned __int16 *
0x1800365b1  mov     r8d, 216h; unsigned int
0x1800365b7  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800365be  lea     rcx, [rsp+2B8h+var_60]; this
0x1800365c6  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800365cb  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800365d2  lea     rcx, [rsp+2B8h+var_60]; pExceptionObject
0x1800365da  call    _CxxThrowException_0
0x1800365e0  jmp     short $+2
0x1800365e2  add     rsp, 298h
0x1800365e9  pop     r14
0x1800365eb  pop     rdi
0x1800365ec  pop     rsi
0x1800365ed  pop     rbx
0x1800365ee  retn
```
