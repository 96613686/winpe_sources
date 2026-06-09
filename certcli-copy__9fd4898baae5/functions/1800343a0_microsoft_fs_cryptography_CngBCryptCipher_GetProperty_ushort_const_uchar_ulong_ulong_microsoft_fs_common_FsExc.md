# microsoft::fs::cryptography::CngBCryptCipher::GetProperty(ushort const *,uchar *,ulong *,ulong,microsoft::fs::common::FsException *)

- ea: `0x1800343a0`
- end: `0x180034757`
- name: `?GetProperty@CngBCryptCipher@cryptography@fs@microsoft@@UEBAXPEBGPEAEPEAKKPEAVFsException@common@34@@Z`
- size: `951`
- prototype: `void(microsoft::fs::cryptography::CngBCryptCipher *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180002306`
- `0x18000f628`
- `0x180019448`
- `0x18002e4dc`
- `0x18002e5e4`
- `0x18002eedc`
- `0x1800323e4`
- `0x1800343a0`
- `0x18003970a`
- `0x18003f010`

## string_xrefs

- `0x1800343f7`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034433`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x1800344bd`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034517`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x18003459a`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x1800345f6`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034663`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x1800346d0`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x18003471e`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall microsoft::fs::cryptography::CngBCryptCipher::GetProperty(
        microsoft::fs::cryptography::CngBCryptCipher *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        ULONG a5,
        struct microsoft::fs::common::FsException *a6)
{
  int v10; // eax
  struct microsoft::fs::common::FsException *v11; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  int v13; // edx
  unsigned int v14; // ecx
  size_t v15; // rax
  int v16; // eax
  unsigned int v17; // eax
  int v18; // eax
  int Property; // eax
  int v20; // eax
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-1E0h] BYREF
  _BYTE v22[48]; // [rsp+A8h] [rbp-1B0h] BYREF
  _BYTE v23[48]; // [rsp+D8h] [rbp-180h] BYREF
  _BYTE v24[48]; // [rsp+108h] [rbp-150h] BYREF
  _BYTE v25[48]; // [rsp+138h] [rbp-120h] BYREF
  _BYTE v26[48]; // [rsp+168h] [rbp-F0h] BYREF
  _BYTE v27[48]; // [rsp+198h] [rbp-C0h] BYREF
  _BYTE v28[48]; // [rsp+1C8h] [rbp-90h] BYREF
  _BYTE v29[96]; // [rsp+1F8h] [rbp-60h] BYREF

  if ( a6 )
    (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a6 + 8LL))(a6);
  v10 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
  if ( v10 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
      0x12Du,
      L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
      v10);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  if ( !a4 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)v22,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
      0x12Fu,
      L"pcbValue",
      -2147024809);
    throw (microsoft::fs::common::FsException *)v22;
  }
  PropertyLookupEntry = microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(a2, v11);
  if ( (*((_BYTE *)PropertyLookupEntry + 20) & 1) != 0 )
  {
    v13 = *a2 - 73;
    if ( *a2 == 73 )
    {
      v13 = a2[1] - 86;
      if ( a2[1] == 86 )
        v13 = a2[2];
    }
    if ( v13 )
    {
      if ( wcscmp_0(a2, L"ASYM_ENCRYPT_PAD_FLAG") )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v26,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
          0x14Bu,
          &psz,
          -2147024809,
          L"Invalid property %s.",
          a2);
        throw (microsoft::fs::common::FsException *)v26;
      }
      v17 = *a4;
      *a4 = 4;
      if ( a3 )
      {
        if ( v17 < 4 )
        {
          v18 = HR_FROM_WIN32(0x7Au);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v25,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
            0x145u,
            L"cbMax >= sizeof (m_fAsymEncryptPad)",
            v18);
          throw (microsoft::fs::common::FsException *)v25;
        }
        *(_DWORD *)a3 = *((_DWORD *)this + 132);
      }
    }
    else
    {
      if ( !*((_BYTE *)this + 540) )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v23,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
          0x137u,
          &psz,
          -2147024809,
          L"IV is valid only for block ciphers.");
        throw (microsoft::fs::common::FsException *)v23;
      }
      v14 = *a4;
      v15 = *((unsigned int *)this + 134);
      *a4 = v15;
      if ( a3 )
      {
        if ( v14 < (unsigned int)v15 )
        {
          v16 = HR_FROM_WIN32(0x7Au);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v24,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
            0x13Cu,
            &psz,
            v16);
          throw (microsoft::fs::common::FsException *)v24;
        }
        memcpy_0(a3, *((const void **)this + 68), v15);
      }
    }
  }
  else if ( (*((_BYTE *)PropertyLookupEntry + 20) & 2) != 0 )
  {
    Property = fsBCryptGetProperty(
                 *((void **)this + 73),
                 *((const unsigned __int16 **)PropertyLookupEntry + 3),
                 a3,
                 *a4,
                 a4,
                 a5);
    if ( Property < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v27,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        0x157u,
        L"BCryptGetProperty( m_hKey, ple->pszBCryptProperty, pbValue, *pcbValue, pcbValue, fFlags)",
        Property);
      throw (microsoft::fs::common::FsException *)v27;
    }
  }
  else
  {
    if ( (*((_BYTE *)PropertyLookupEntry + 20) & 8) == 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v29,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        0x165u,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v29;
    }
    v20 = fsBCryptGetProperty(
            *((void **)this + 71),
            *((const unsigned __int16 **)PropertyLookupEntry + 3),
            a3,
            *a4,
            a4,
            a5);
    if ( v20 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v28,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        0x161u,
        L"BCryptGetProperty( m_hProv, ple->pszBCryptProperty, pbValue, *pcbValue, pcbValue, fFlags)",
        v20);
      throw (microsoft::fs::common::FsException *)v28;
    }
  }
}

```

## disassembly

```asm
0x1800343a0  push    rbx
0x1800343a2  push    rsi
0x1800343a3  push    rdi
0x1800343a4  push    r14
0x1800343a6  sub     rsp, 238h
0x1800343ad  mov     rbx, r9
0x1800343b0  mov     r14, r8
0x1800343b3  mov     rdi, rdx
0x1800343b6  mov     rsi, rcx
0x1800343b9  mov     rcx, [rsp+258h+arg_28]
0x1800343c1  test    rcx, rcx
0x1800343c4  jz      short loc_1800343D2
0x1800343c6  mov     rax, [rcx]
0x1800343c9  mov     rax, [rax+8]
0x1800343cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343d2  xor     r8d, r8d; unsigned __int64 *
0x1800343d5  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800343da  mov     rcx, rdi; unsigned __int16 *
0x1800343dd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800343e2  test    eax, eax
0x1800343e4  jns     short loc_180034419
0x1800343e6  mov     dword ptr [rsp+258h+var_238], eax; int
0x1800343ea  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x1800343f1  mov     r8d, 12Dh; unsigned int
0x1800343f7  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800343fe  lea     rcx, [rsp+258h+pExceptionObject]; this
0x180034403  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034408  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003440f  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x180034414  call    _CxxThrowException_0
0x180034419  test    rbx, rbx
0x18003441c  jnz     short loc_18003445B
0x18003441e  mov     dword ptr [rsp+258h+var_238], 80070057h; int
0x180034426  lea     r9, aPcbvalue; "pcbValue"
0x18003442d  mov     r8d, 12Fh; unsigned int
0x180034433  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003443a  lea     rcx, [rsp+258h+var_1B0]; this
0x180034442  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034447  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003444e  lea     rcx, [rsp+258h+var_1B0]; pExceptionObject
0x180034456  call    _CxxThrowException_0
0x18003445b  mov     rcx, rdi; unsigned __int16 *
0x18003445e  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x180034463  mov     rdx, rax
0x180034466  test    byte ptr [rax+14h], 1
0x18003446a  jz      loc_18003461E
0x180034470  movzx   edx, word ptr [rdi]
0x180034473  sub     edx, 49h ; 'I'
0x180034476  jnz     short loc_18003448C
0x180034478  movzx   edx, word ptr [rdi+2]
0x18003447c  sub     edx, 56h ; 'V'
0x18003447f  jnz     short loc_18003448C
0x180034481  movzx   edx, word ptr [rdi+4]
0x180034485  xor     eax, eax
0x180034487  movzx   ecx, ax
0x18003448a  sub     edx, ecx
0x18003448c  test    edx, edx
0x18003448e  jnz     loc_180034556
0x180034494  cmp     [rsi+21Ch], dl
0x18003449a  jnz     short loc_1800344E5
0x18003449c  lea     rax, aIvIsValidOnlyF; "IV is valid only for block ciphers."
0x1800344a3  mov     qword ptr [rsp+258h+var_230], rax; unsigned __int16 *
0x1800344a8  mov     dword ptr [rsp+258h+var_238], 80070057h; int
0x1800344b0  lea     r9, psz; unsigned __int16 *
0x1800344b7  mov     r8d, 137h; unsigned int
0x1800344bd  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800344c4  lea     rcx, [rsp+258h+var_180]; this
0x1800344cc  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800344d1  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800344d8  lea     rcx, [rsp+258h+var_180]; pExceptionObject
0x1800344e0  call    _CxxThrowException_0
0x1800344e5  mov     ecx, [rbx]
0x1800344e7  mov     eax, [rsi+218h]
0x1800344ed  mov     [rbx], eax
0x1800344ef  test    r14, r14
0x1800344f2  jz      loc_180034749
0x1800344f8  cmp     ecx, eax
0x1800344fa  jnb     short loc_18003453F
0x1800344fc  mov     ecx, 7Ah ; 'z'; unsigned int
0x180034501  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180034506  mov     dword ptr [rsp+258h+var_238], eax; int
0x18003450a  lea     r9, psz; unsigned __int16 *
0x180034511  mov     r8d, 13Ch; unsigned int
0x180034517  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003451e  lea     rcx, [rsp+258h+var_150]; this
0x180034526  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003452b  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034532  lea     rcx, [rsp+258h+var_150]; pExceptionObject
0x18003453a  call    _CxxThrowException_0
0x18003453f  mov     r8, rax; Size
0x180034542  mov     rdx, [rsi+220h]; Src
0x180034549  mov     rcx, r14; void *
0x18003454c  call    memcpy_0
0x180034551  jmp     loc_180034749
0x180034556  lea     rdx, aAsymEncryptPad; "ASYM_ENCRYPT_PAD_FLAG"
0x18003455d  mov     rcx, rdi; String1
0x180034560  call    wcscmp_0
0x180034565  test    eax, eax
0x180034567  jnz     short loc_1800345D0
0x180034569  mov     eax, [rbx]
0x18003456b  mov     dword ptr [rbx], 4
0x180034571  test    r14, r14
0x180034574  jz      loc_180034749
0x18003457a  cmp     eax, 4
0x18003457d  jnb     short loc_1800345C2
0x18003457f  mov     ecx, 7Ah ; 'z'; unsigned int
0x180034584  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180034589  mov     dword ptr [rsp+258h+var_238], eax; int
0x18003458d  lea     r9, aCbmaxSizeofMFa; "cbMax >= sizeof (m_fAsymEncryptPad)"
0x180034594  mov     r8d, 145h; unsigned int
0x18003459a  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800345a1  lea     rcx, [rsp+258h+var_120]; this
0x1800345a9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800345ae  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800345b5  lea     rcx, [rsp+258h+var_120]; pExceptionObject
0x1800345bd  call    _CxxThrowException_0
0x1800345c2  mov     eax, [rsi+210h]
0x1800345c8  mov     [r14], eax
0x1800345cb  jmp     loc_180034749
0x1800345d0  mov     [rsp+258h+var_228], rdi
0x1800345d5  lea     rax, aInvalidPropert; "Invalid property %s."
0x1800345dc  mov     qword ptr [rsp+258h+var_230], rax; unsigned __int16 *
0x1800345e1  mov     dword ptr [rsp+258h+var_238], 80070057h; int
0x1800345e9  lea     r9, psz; unsigned __int16 *
0x1800345f0  mov     r8d, 14Bh; unsigned int
0x1800345f6  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800345fd  lea     rcx, [rsp+258h+var_F0]; this
0x180034605  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003460a  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034611  lea     rcx, [rsp+258h+var_F0]; pExceptionObject
0x180034619  call    _CxxThrowException_0
0x18003461e  test    byte ptr [rax+14h], 2
0x180034622  jz      short loc_18003468B
0x180034624  mov     eax, [rsp+258h+arg_20]
0x18003462b  mov     [rsp+258h+var_230], eax; ULONG
0x18003462f  mov     [rsp+258h+var_238], rbx; ULONG *
0x180034634  mov     r9d, [rbx]; unsigned int
0x180034637  mov     r8, r14; unsigned __int8 *
0x18003463a  mov     rdx, [rdx+18h]; unsigned __int16 *
0x18003463e  mov     rcx, [rsi+248h]; void *
0x180034645  call    ?fsBCryptGetProperty@@YAJPEAXPEBGPEAEKPEAKK@Z; fsBCryptGetProperty(void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x18003464a  test    eax, eax
0x18003464c  jns     loc_1800345CB
0x180034652  mov     dword ptr [rsp+258h+var_238], eax; int
0x180034656  lea     r9, aBcryptgetprope_2; "BCryptGetProperty( m_hKey, ple->pszBCry"...
0x18003465d  mov     r8d, 157h; unsigned int
0x180034663  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003466a  lea     rcx, [rsp+258h+var_C0]; this
0x180034672  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034677  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003467e  lea     rcx, [rsp+258h+var_C0]; pExceptionObject
0x180034686  call    _CxxThrowException_0
0x18003468b  test    byte ptr [rax+14h], 8
0x18003468f  jz      short loc_1800346F8
0x180034691  mov     eax, [rsp+258h+arg_20]
0x180034698  mov     [rsp+258h+var_230], eax; ULONG
0x18003469c  mov     [rsp+258h+var_238], rbx; ULONG *
0x1800346a1  mov     r9d, [rbx]; unsigned int
0x1800346a4  mov     r8, r14; unsigned __int8 *
0x1800346a7  mov     rdx, [rdx+18h]; unsigned __int16 *
0x1800346ab  mov     rcx, [rsi+238h]; void *
0x1800346b2  call    ?fsBCryptGetProperty@@YAJPEAXPEBGPEAEKPEAKK@Z; fsBCryptGetProperty(void *,ushort const *,uchar *,ulong,ulong *,ulong)
0x1800346b7  test    eax, eax
0x1800346b9  jns     loc_1800345CB
0x1800346bf  mov     dword ptr [rsp+258h+var_238], eax; int
0x1800346c3  lea     r9, aBcryptgetprope_4; "BCryptGetProperty( m_hProv, ple->pszBCr"...
0x1800346ca  mov     r8d, 161h; unsigned int
0x1800346d0  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800346d7  lea     rcx, [rsp+258h+var_90]; this
0x1800346df  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800346e4  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800346eb  lea     rcx, [rsp+258h+var_90]; pExceptionObject
0x1800346f3  call    _CxxThrowException_0
0x1800346f8  mov     [rsp+258h+var_228], rdi
0x1800346fd  lea     rax, aInvalidPropert; "Invalid property %s."
0x180034704  mov     qword ptr [rsp+258h+var_230], rax; unsigned __int16 *
0x180034709  mov     dword ptr [rsp+258h+var_238], 80070057h; int
0x180034711  lea     r9, psz; unsigned __int16 *
0x180034718  mov     r8d, 165h; unsigned int
0x18003471e  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034725  lea     rcx, [rsp+258h+var_60]; this
0x18003472d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180034732  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034739  lea     rcx, [rsp+258h+var_60]; pExceptionObject
0x180034741  call    _CxxThrowException_0
0x180034747  jmp     short $+2
0x180034749  add     rsp, 238h
0x180034750  pop     r14
0x180034752  pop     rdi
0x180034753  pop     rsi
0x180034754  pop     rbx
0x180034755  retn
```
