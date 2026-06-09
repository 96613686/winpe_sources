# microsoft::fs::cryptography::CngNCryptCipher::SetProperty(ushort const *,uchar const *,ulong,ulong,microsoft::fs::common::FsException *)

- ea: `0x180037750`
- end: `0x1800379fb`
- name: `?SetProperty@CngNCryptCipher@cryptography@fs@microsoft@@UEAAXPEBGPEBEKKPEAVFsException@common@34@@Z`
- size: `683`
- prototype: `void(microsoft::fs::cryptography::CngNCryptCipher *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x18002e4dc`
- `0x18002eedc`
- `0x180032aa0`
- `0x180037750`
- `0x18003970a`
- `0x18003f010`

## string_xrefs

- `0x1800377a7`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x1800377e3`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x18003784d`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x1800378a9`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x18003790d`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x180037975`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x1800379c3`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CngNCryptCipher::SetProperty(
        microsoft::fs::cryptography::CngNCryptCipher *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        DWORD a5,
        struct microsoft::fs::common::FsException *a6)
{
  int v10; // eax
  struct microsoft::fs::common::FsException *v11; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  int v13; // eax
  int v14; // eax
  const struct microsoft::fs::common::FsException *v15; // rax
  const microsoft::fs::common::FsException *v16; // [rsp+40h] [rbp-1B8h] BYREF
  _QWORD v17[6]; // [rsp+48h] [rbp-1B0h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-180h] BYREF
  _BYTE v19[48]; // [rsp+A8h] [rbp-150h] BYREF
  _BYTE v20[48]; // [rsp+D8h] [rbp-120h] BYREF
  _BYTE v21[48]; // [rsp+108h] [rbp-F0h] BYREF
  _BYTE v22[48]; // [rsp+138h] [rbp-C0h] BYREF
  _BYTE v23[48]; // [rsp+168h] [rbp-90h] BYREF
  _BYTE v24[96]; // [rsp+198h] [rbp-60h] BYREF

  try
  {
    if ( a6 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a6 + 8LL))(a6);
    v10 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
    if ( v10 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        0x170u,
        L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
        v10);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a3 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v19,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        0x171u,
        L"pbValue",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v19;
    }
    PropertyLookupEntry = microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(a2, v11);
    if ( (*((_BYTE *)PropertyLookupEntry + 32) & 1) != 0 )
    {
      if ( wcscmp_0(a2, L"ASYM_ENCRYPT_PAD_FLAG") )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v21,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          0x17Eu,
          &psz,
          -2147024809,
          L"Invalid property %s.",
          a2);
        throw (microsoft::fs::common::FsException *)v21;
      }
      if ( a4 != 4 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v20,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          0x179u,
          L"sizeof (m_fAsymEncryptPad) == cbValue",
          -2147024809);
        throw (microsoft::fs::common::FsException *)v20;
      }
      *((_DWORD *)this + 132) = *(_DWORD *)a3;
    }
    else if ( (*((_BYTE *)PropertyLookupEntry + 32) & 2) != 0 )
    {
      v13 = fsNCryptSetProperty(
              *((_QWORD *)this + 68),
              *((const unsigned __int16 **)PropertyLookupEntry + 5),
              a3,
              a4,
              a5);
      if ( v13 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v22,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          0x188u,
          L"NCryptSetProperty( m_hKey, ple->pszNCryptProperty, const_cast<BYTE*>(pbValue), cbValue, fFlags)",
          v13);
        throw (microsoft::fs::common::FsException *)v22;
      }
    }
    else
    {
      if ( (*((_BYTE *)PropertyLookupEntry + 32) & 8) == 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v24,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          0x195u,
          &psz,
          -2147024809,
          L"Invalid property %s.",
          a2);
        throw (microsoft::fs::common::FsException *)v24;
      }
      v14 = fsNCryptSetProperty(
              *((_QWORD *)this + 67),
              *((const unsigned __int16 **)PropertyLookupEntry + 5),
              a3,
              a4,
              a5);
      if ( v14 < 0 )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v23,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          0x191u,
          L"NCryptSetProperty( m_hProv, ple->pszNCryptProperty, const_cast<BYTE*>(pbValue), cbValue, fFlags)",
          v14);
        throw (microsoft::fs::common::FsException *)v23;
      }
    }
  }
  catch ( const microsoft::fs::common::FsException *v16 )
  {
    if ( !a6 )
      throw;
    microsoft::fs::common::FsException::assign(a6, v16);
    return;
  }
  catch ( ... )
  {
    if ( !a6 )
      throw;
    v15 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v17,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
                                                               0x1A0u,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a6, v15);
    v17[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v17[1]);
    operator delete[]((void *)v17[2]);
    operator delete[]((void *)v17[3]);
    operator delete[]((void *)v17[5]);
  }
}

```

## disassembly

```asm
0x180037750  push    rbx
0x180037752  push    rsi
0x180037753  push    rdi
0x180037754  push    r14
0x180037756  sub     rsp, 1D8h
0x18003775d  mov     esi, r9d
0x180037760  mov     rbx, r8
0x180037763  mov     rdi, rdx
0x180037766  mov     r14, rcx
0x180037769  mov     rcx, [rsp+1F8h+arg_28]
0x180037771  test    rcx, rcx
0x180037774  jz      short loc_180037782
0x180037776  mov     rax, [rcx]
0x180037779  mov     rax, [rax+8]
0x18003777d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037782  xor     r8d, r8d; unsigned __int64 *
0x180037785  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003778a  mov     rcx, rdi; unsigned __int16 *
0x18003778d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180037792  test    eax, eax
0x180037794  jns     short loc_1800377C9
0x180037796  mov     [rsp+1F8h+var_1D8], eax; int
0x18003779a  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x1800377a1  mov     r8d, 170h; unsigned int
0x1800377a7  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800377ae  lea     rcx, [rsp+1F8h+pExceptionObject]; this
0x1800377b3  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800377b8  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800377bf  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x1800377c4  call    _CxxThrowException_0
0x1800377c9  test    rbx, rbx
0x1800377cc  jnz     short loc_18003780B
0x1800377ce  mov     [rsp+1F8h+var_1D8], 80070057h; int
0x1800377d6  lea     r9, aPbvalue; "pbValue"
0x1800377dd  mov     r8d, 171h; unsigned int
0x1800377e3  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800377ea  lea     rcx, [rsp+1F8h+var_150]; this
0x1800377f2  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800377f7  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800377fe  lea     rcx, [rsp+1F8h+var_150]; pExceptionObject
0x180037806  call    _CxxThrowException_0
0x18003780b  mov     rcx, rdi; unsigned __int16 *
0x18003780e  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x180037813  mov     rdx, rax
0x180037816  test    byte ptr [rax+20h], 1
0x18003781a  jz      loc_1800378D1
0x180037820  lea     rdx, aAsymEncryptPad; "ASYM_ENCRYPT_PAD_FLAG"
0x180037827  mov     rcx, rdi; String1
0x18003782a  call    wcscmp_0
0x18003782f  test    eax, eax
0x180037831  jnz     short loc_180037883
0x180037833  cmp     esi, 4
0x180037836  jz      short loc_180037875
0x180037838  mov     [rsp+1F8h+var_1D8], 80070057h; int
0x180037840  lea     r9, aSizeofMFasymen; "sizeof (m_fAsymEncryptPad) == cbValue"
0x180037847  mov     r8d, 179h; unsigned int
0x18003784d  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037854  lea     rcx, [rsp+1F8h+var_120]; this
0x18003785c  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037861  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037868  lea     rcx, [rsp+1F8h+var_120]; pExceptionObject
0x180037870  call    _CxxThrowException_0
0x180037875  mov     eax, [rbx]
0x180037877  mov     [r14+210h], eax
0x18003787e  jmp     loc_1800379EE
0x180037883  mov     [rsp+1F8h+var_1C8], rdi
0x180037888  lea     rax, aInvalidPropert; "Invalid property %s."
0x18003788f  mov     [rsp+1F8h+var_1D0], rax; unsigned __int16 *
0x180037894  mov     [rsp+1F8h+var_1D8], 80070057h; int
0x18003789c  lea     r9, psz; unsigned __int16 *
0x1800378a3  mov     r8d, 17Eh; unsigned int
0x1800378a9  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800378b0  lea     rcx, [rsp+1F8h+var_F0]; this
0x1800378b8  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800378bd  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800378c4  lea     rcx, [rsp+1F8h+var_F0]; pExceptionObject
0x1800378cc  call    _CxxThrowException_0
0x1800378d1  test    byte ptr [rax+20h], 2
0x1800378d5  jz      short loc_180037935
0x1800378d7  mov     eax, [rsp+1F8h+arg_20]
0x1800378de  mov     [rsp+1F8h+var_1D8], eax; DWORD
0x1800378e2  mov     r9d, esi; unsigned int
0x1800378e5  mov     r8, rbx; unsigned __int8 *
0x1800378e8  mov     rdx, [rdx+28h]; unsigned __int16 *
0x1800378ec  mov     rcx, [r14+220h]; unsigned __int64
0x1800378f3  call    ?fsNCryptSetProperty@@YAJ_KPEBGPEAEKK@Z; fsNCryptSetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong)
0x1800378f8  test    eax, eax
0x1800378fa  jns     short loc_18003787E
0x1800378fc  mov     [rsp+1F8h+var_1D8], eax; int
0x180037900  lea     r9, aNcryptsetprope_1; "NCryptSetProperty( m_hKey, ple->pszNCry"...
0x180037907  mov     r8d, 188h; unsigned int
0x18003790d  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037914  lea     rcx, [rsp+1F8h+var_C0]; this
0x18003791c  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037921  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037928  lea     rcx, [rsp+1F8h+var_C0]; pExceptionObject
0x180037930  call    _CxxThrowException_0
0x180037935  test    byte ptr [rax+20h], 8
0x180037939  jz      short loc_18003799D
0x18003793b  mov     eax, [rsp+1F8h+arg_20]
0x180037942  mov     [rsp+1F8h+var_1D8], eax; DWORD
0x180037946  mov     r9d, esi; unsigned int
0x180037949  mov     r8, rbx; unsigned __int8 *
0x18003794c  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180037950  mov     rcx, [r14+218h]; unsigned __int64
0x180037957  call    ?fsNCryptSetProperty@@YAJ_KPEBGPEAEKK@Z; fsNCryptSetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong)
0x18003795c  test    eax, eax
0x18003795e  jns     loc_18003787E
0x180037964  mov     [rsp+1F8h+var_1D8], eax; int
0x180037968  lea     r9, aNcryptsetprope_0; "NCryptSetProperty( m_hProv, ple->pszNCr"...
0x18003796f  mov     r8d, 191h; unsigned int
0x180037975  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003797c  lea     rcx, [rsp+1F8h+var_90]; this
0x180037984  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037989  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037990  lea     rcx, [rsp+1F8h+var_90]; pExceptionObject
0x180037998  call    _CxxThrowException_0
0x18003799d  mov     [rsp+1F8h+var_1C8], rdi
0x1800379a2  lea     rax, aInvalidPropert; "Invalid property %s."
0x1800379a9  mov     [rsp+1F8h+var_1D0], rax; unsigned __int16 *
0x1800379ae  mov     [rsp+1F8h+var_1D8], 80070057h; int
0x1800379b6  lea     r9, psz; unsigned __int16 *
0x1800379bd  mov     r8d, 195h; unsigned int
0x1800379c3  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800379ca  lea     rcx, [rsp+1F8h+var_60]; this
0x1800379d2  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800379d7  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800379de  lea     rcx, [rsp+1F8h+var_60]; pExceptionObject
0x1800379e6  call    _CxxThrowException_0
0x1800379ec  jmp     short $+2
0x1800379ee  add     rsp, 1D8h
0x1800379f5  pop     r14
0x1800379f7  pop     rdi
0x1800379f8  pop     rsi
0x1800379f9  pop     rbx
0x1800379fa  retn
```
