# microsoft::fs::cryptography::CngBCryptCipher::SetProperty(ushort const *,uchar const *,ulong,ulong,microsoft::fs::common::FsException *)

- ea: `0x180034810`
- end: `0x180034b8d`
- name: `?SetProperty@CngBCryptCipher@cryptography@fs@microsoft@@UEAAXPEBGPEBEKKPEAVFsException@common@34@@Z`
- size: `893`
- prototype: `void(microsoft::fs::cryptography::CngBCryptCipher *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180002306`
- `0x18000f628`
- `0x180019448`
- `0x18002e4dc`
- `0x18002eedc`
- `0x1800324c8`
- `0x180034810`
- `0x18003970a`
- `0x18003f010`

## string_xrefs

- `0x180034867`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x1800348a3`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x18003492d`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034972`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x1800349de`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034a3a`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034a9e`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034b06`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`
- `0x180034b54`: `onecore\ds\security\services\ca\fs\crypto\cngbcryptcipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall microsoft::fs::cryptography::CngBCryptCipher::SetProperty(
        microsoft::fs::cryptography::CngBCryptCipher *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        ULONG a5,
        struct microsoft::fs::common::FsException *a6)
{
  size_t v6; // rsi
  int v10; // eax
  struct microsoft::fs::common::FsException *v11; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  int v13; // edx
  int v14; // eax
  int v15; // eax
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-1E0h] BYREF
  _BYTE v17[48]; // [rsp+A8h] [rbp-1B0h] BYREF
  _BYTE v18[48]; // [rsp+D8h] [rbp-180h] BYREF
  _BYTE v19[48]; // [rsp+108h] [rbp-150h] BYREF
  _BYTE v20[48]; // [rsp+138h] [rbp-120h] BYREF
  _BYTE v21[48]; // [rsp+168h] [rbp-F0h] BYREF
  _BYTE v22[48]; // [rsp+198h] [rbp-C0h] BYREF
  _BYTE v23[48]; // [rsp+1C8h] [rbp-90h] BYREF
  _BYTE v24[96]; // [rsp+1F8h] [rbp-60h] BYREF

  v6 = a4;
  if ( a6 )
    (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a6 + 8LL))(a6);
  v10 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
  if ( v10 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
      424,
      L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
      v10);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  if ( !a3 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)v17,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
      425,
      L"pbValue",
      -2147024809);
    throw (microsoft::fs::common::FsException *)v17;
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
          (microsoft::fs::common::FsException *)v21,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
          446,
          &psz,
          -2147024809,
          L"Invalid property %s.",
          a2);
        throw (microsoft::fs::common::FsException *)v21;
      }
      if ( (_DWORD)v6 != 4 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v20,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
          441,
          L"sizeof (m_fAsymEncryptPad) == cbValue",
          -2147024809);
        throw (microsoft::fs::common::FsException *)v20;
      }
      *((_DWORD *)this + 132) = *(_DWORD *)a3;
    }
    else
    {
      if ( !*((_BYTE *)this + 540) )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v18,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
          433,
          &psz,
          -2147024809,
          L"IV is valid only for block ciphers.");
        throw (microsoft::fs::common::FsException *)v18;
      }
      if ( (_DWORD)v6 != *((_DWORD *)this + 134) )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v19,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
          435,
          &psz,
          -2147024809);
        throw (microsoft::fs::common::FsException *)v19;
      }
      memcpy_0(*((void **)this + 68), a3, v6);
    }
  }
  else if ( (*((_BYTE *)PropertyLookupEntry + 20) & 2) != 0 )
  {
    v14 = fsBCryptSetProperty(*((void **)this + 73), *((const unsigned __int16 **)PropertyLookupEntry + 3), a3, v6, a5);
    if ( v14 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v22,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        456,
        L"BCryptSetProperty( m_hKey, ple->pszBCryptProperty, const_cast<BYTE*>(pbValue), cbValue, fFlags)",
        v14);
      throw (microsoft::fs::common::FsException *)v22;
    }
  }
  else
  {
    if ( (*((_BYTE *)PropertyLookupEntry + 20) & 8) == 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        469,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v24;
    }
    v15 = fsBCryptSetProperty(*((void **)this + 71), *((const unsigned __int16 **)PropertyLookupEntry + 3), a3, v6, a5);
    if ( v15 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v23,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngbcryptcipher.cpp",
        465,
        L"BCryptSetProperty( m_hProv, ple->pszBCryptProperty, const_cast<BYTE*>(pbValue), cbValue, fFlags)",
        v15);
      throw (microsoft::fs::common::FsException *)v23;
    }
  }
}

```

## disassembly

```asm
0x180034810  push    rbx
0x180034812  push    rsi
0x180034813  push    rdi
0x180034814  push    r14
0x180034816  sub     rsp, 238h
0x18003481d  mov     esi, r9d
0x180034820  mov     r14, r8
0x180034823  mov     rbx, rdx
0x180034826  mov     rdi, rcx
0x180034829  mov     rcx, [rsp+258h+arg_28]
0x180034831  test    rcx, rcx
0x180034834  jz      short loc_180034842
0x180034836  mov     rax, [rcx]
0x180034839  mov     rax, [rax+8]
0x18003483d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034842  xor     r8d, r8d; unsigned __int64 *
0x180034845  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003484a  mov     rcx, rbx; unsigned __int16 *
0x18003484d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180034852  test    eax, eax
0x180034854  jns     short loc_180034889
0x180034856  mov     [rsp+258h+var_238], eax; int
0x18003485a  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x180034861  mov     r8d, 1A8h; unsigned int
0x180034867  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003486e  lea     rcx, [rsp+258h+pExceptionObject]; this
0x180034873  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034878  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003487f  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x180034884  call    _CxxThrowException_0
0x180034889  test    r14, r14
0x18003488c  jnz     short loc_1800348CB
0x18003488e  mov     [rsp+258h+var_238], 80070057h; int
0x180034896  lea     r9, aPbvalue; "pbValue"
0x18003489d  mov     r8d, 1A9h; unsigned int
0x1800348a3  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800348aa  lea     rcx, [rsp+258h+var_1B0]; this
0x1800348b2  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800348b7  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800348be  lea     rcx, [rsp+258h+var_1B0]; pExceptionObject
0x1800348c6  call    _CxxThrowException_0
0x1800348cb  mov     rcx, rbx; unsigned __int16 *
0x1800348ce  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x1800348d3  mov     rdx, rax
0x1800348d6  test    byte ptr [rax+14h], 1
0x1800348da  jz      loc_180034A62
0x1800348e0  movzx   edx, word ptr [rbx]
0x1800348e3  sub     edx, 49h ; 'I'
0x1800348e6  jnz     short loc_1800348FC
0x1800348e8  movzx   edx, word ptr [rbx+2]
0x1800348ec  sub     edx, 56h ; 'V'
0x1800348ef  jnz     short loc_1800348FC
0x1800348f1  movzx   edx, word ptr [rbx+4]
0x1800348f5  xor     eax, eax
0x1800348f7  movzx   ecx, ax
0x1800348fa  sub     edx, ecx
0x1800348fc  test    edx, edx
0x1800348fe  jnz     loc_1800349B1
0x180034904  cmp     [rdi+21Ch], dl
0x18003490a  jnz     short loc_180034955
0x18003490c  lea     rax, aIvIsValidOnlyF; "IV is valid only for block ciphers."
0x180034913  mov     [rsp+258h+var_230], rax; unsigned __int16 *
0x180034918  mov     [rsp+258h+var_238], 80070057h; int
0x180034920  lea     r9, psz; unsigned __int16 *
0x180034927  mov     r8d, 1B1h; unsigned int
0x18003492d  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034934  lea     rcx, [rsp+258h+var_180]; this
0x18003493c  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180034941  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034948  lea     rcx, [rsp+258h+var_180]; pExceptionObject
0x180034950  call    _CxxThrowException_0
0x180034955  cmp     esi, [rdi+218h]
0x18003495b  jz      short loc_18003499A
0x18003495d  mov     [rsp+258h+var_238], 80070057h; int
0x180034965  lea     r9, psz; unsigned __int16 *
0x18003496c  mov     r8d, 1B3h; unsigned int
0x180034972  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034979  lea     rcx, [rsp+258h+var_150]; this
0x180034981  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034986  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003498d  lea     rcx, [rsp+258h+var_150]; pExceptionObject
0x180034995  call    _CxxThrowException_0
0x18003499a  mov     r8, rsi; Size
0x18003499d  mov     rdx, r14; Src
0x1800349a0  mov     rcx, [rdi+220h]; void *
0x1800349a7  call    memcpy_0
0x1800349ac  jmp     loc_180034B7F
0x1800349b1  lea     rdx, aAsymEncryptPad; "ASYM_ENCRYPT_PAD_FLAG"
0x1800349b8  mov     rcx, rbx; String1
0x1800349bb  call    wcscmp_0
0x1800349c0  test    eax, eax
0x1800349c2  jnz     short loc_180034A14
0x1800349c4  cmp     esi, 4
0x1800349c7  jz      short loc_180034A06
0x1800349c9  mov     [rsp+258h+var_238], 80070057h; int
0x1800349d1  lea     r9, aSizeofMFasymen; "sizeof (m_fAsymEncryptPad) == cbValue"
0x1800349d8  mov     r8d, 1B9h; unsigned int
0x1800349de  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800349e5  lea     rcx, [rsp+258h+var_120]; this
0x1800349ed  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800349f2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800349f9  lea     rcx, [rsp+258h+var_120]; pExceptionObject
0x180034a01  call    _CxxThrowException_0
0x180034a06  mov     eax, [r14]
0x180034a09  mov     [rdi+210h], eax
0x180034a0f  jmp     loc_180034B7F
0x180034a14  mov     [rsp+258h+var_228], rbx
0x180034a19  lea     rax, aInvalidPropert; "Invalid property %s."
0x180034a20  mov     [rsp+258h+var_230], rax; unsigned __int16 *
0x180034a25  mov     [rsp+258h+var_238], 80070057h; int
0x180034a2d  lea     r9, psz; unsigned __int16 *
0x180034a34  mov     r8d, 1BEh; unsigned int
0x180034a3a  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034a41  lea     rcx, [rsp+258h+var_F0]; this
0x180034a49  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180034a4e  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034a55  lea     rcx, [rsp+258h+var_F0]; pExceptionObject
0x180034a5d  call    _CxxThrowException_0
0x180034a62  test    byte ptr [rax+14h], 2
0x180034a66  jz      short loc_180034AC6
0x180034a68  mov     eax, [rsp+258h+arg_20]
0x180034a6f  mov     [rsp+258h+var_238], eax; ULONG
0x180034a73  mov     r9d, esi; unsigned int
0x180034a76  mov     r8, r14; unsigned __int8 *
0x180034a79  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180034a7d  mov     rcx, [rdi+248h]; void *
0x180034a84  call    ?fsBCryptSetProperty@@YAJPEAXPEBGPEAEKK@Z; fsBCryptSetProperty(void *,ushort const *,uchar *,ulong,ulong)
0x180034a89  test    eax, eax
0x180034a8b  jns     short loc_180034A0F
0x180034a8d  mov     [rsp+258h+var_238], eax; int
0x180034a91  lea     r9, aBcryptsetprope_1; "BCryptSetProperty( m_hKey, ple->pszBCry"...
0x180034a98  mov     r8d, 1C8h; unsigned int
0x180034a9e  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034aa5  lea     rcx, [rsp+258h+var_C0]; this
0x180034aad  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034ab2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034ab9  lea     rcx, [rsp+258h+var_C0]; pExceptionObject
0x180034ac1  call    _CxxThrowException_0
0x180034ac6  test    byte ptr [rax+14h], 8
0x180034aca  jz      short loc_180034B2E
0x180034acc  mov     eax, [rsp+258h+arg_20]
0x180034ad3  mov     [rsp+258h+var_238], eax; ULONG
0x180034ad7  mov     r9d, esi; unsigned int
0x180034ada  mov     r8, r14; unsigned __int8 *
0x180034add  mov     rdx, [rdx+18h]; unsigned __int16 *
0x180034ae1  mov     rcx, [rdi+238h]; void *
0x180034ae8  call    ?fsBCryptSetProperty@@YAJPEAXPEBGPEAEKK@Z; fsBCryptSetProperty(void *,ushort const *,uchar *,ulong,ulong)
0x180034aed  test    eax, eax
0x180034aef  jns     loc_180034A0F
0x180034af5  mov     [rsp+258h+var_238], eax; int
0x180034af9  lea     r9, aBcryptsetprope_2; "BCryptSetProperty( m_hProv, ple->pszBCr"...
0x180034b00  mov     r8d, 1D1h; unsigned int
0x180034b06  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034b0d  lea     rcx, [rsp+258h+var_90]; this
0x180034b15  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180034b1a  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034b21  lea     rcx, [rsp+258h+var_90]; pExceptionObject
0x180034b29  call    _CxxThrowException_0
0x180034b2e  mov     [rsp+258h+var_228], rbx
0x180034b33  lea     rax, aInvalidPropert; "Invalid property %s."
0x180034b3a  mov     [rsp+258h+var_230], rax; unsigned __int16 *
0x180034b3f  mov     [rsp+258h+var_238], 80070057h; int
0x180034b47  lea     r9, psz; unsigned __int16 *
0x180034b4e  mov     r8d, 1D5h; unsigned int
0x180034b54  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\services\\ca\\fs"...
0x180034b5b  lea     rcx, [rsp+258h+var_60]; this
0x180034b63  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180034b68  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180034b6f  lea     rcx, [rsp+258h+var_60]; pExceptionObject
0x180034b77  call    _CxxThrowException_0
0x180034b7d  jmp     short $+2
0x180034b7f  add     rsp, 238h
0x180034b86  pop     r14
0x180034b88  pop     rdi
0x180034b89  pop     rsi
0x180034b8a  pop     rbx
0x180034b8b  retn
```
