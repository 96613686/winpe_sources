# microsoft::fs::cryptography::CngNCryptCipher::GetProperty(ushort const *,uchar *,ulong *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180037390`
- end: `0x1800376d5`
- name: `?GetProperty@CngNCryptCipher@cryptography@fs@microsoft@@UEBAXPEBGPEAEPEAKKPEAVFsException@common@34@@Z`
- size: `837`
- prototype: `void(microsoft::fs::cryptography::CngNCryptCipher *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x18002e4dc`
- `0x18002e5e4`
- `0x18002eedc`
- `0x1800328c0`
- `0x180037390`
- `0x18003970a`
- `0x18003f010`

## string_xrefs

- `0x1800373e7`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x180037423`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x1800374a4`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x18003751e`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x180037574`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x1800375e1`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x18003764e`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`
- `0x18003769c`: `onecore\ds\security\services\ca\fs\crypto\cngncryptcipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall microsoft::fs::cryptography::CngNCryptCipher::GetProperty(
        microsoft::fs::cryptography::CngNCryptCipher *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        DWORD a5,
        struct microsoft::fs::common::FsException *a6)
{
  int v10; // eax
  struct microsoft::fs::common::FsException *v11; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  int v16; // eax
  int Property; // eax
  int v18; // eax
  _BYTE pExceptionObject[48]; // [rsp+78h] [rbp-1B0h] BYREF
  _BYTE v20[48]; // [rsp+A8h] [rbp-180h] BYREF
  _BYTE v21[48]; // [rsp+D8h] [rbp-150h] BYREF
  _BYTE v22[48]; // [rsp+108h] [rbp-120h] BYREF
  _BYTE v23[48]; // [rsp+138h] [rbp-F0h] BYREF
  _BYTE v24[48]; // [rsp+168h] [rbp-C0h] BYREF
  _BYTE v25[48]; // [rsp+198h] [rbp-90h] BYREF
  _BYTE v26[96]; // [rsp+1C8h] [rbp-60h] BYREF

  if ( a6 )
    (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a6 + 8LL))(a6);
  v10 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
  if ( v10 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
      0xF6u,
      L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
      v10);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  if ( !a4 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)v20,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
      0xF8u,
      L"pcbValue",
      -2147024809);
    throw (microsoft::fs::common::FsException *)v20;
  }
  PropertyLookupEntry = microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(a2, v11);
  if ( (*((_BYTE *)PropertyLookupEntry + 32) & 1) != 0 )
  {
    if ( !wcscmp_0(a2, L"ASYM_ENCRYPT_PAD_FLAG") )
    {
      v13 = *a4;
      *a4 = 4;
      if ( a3 )
      {
        if ( v13 < 4 )
        {
          v14 = HR_FROM_WIN32(0x7Au);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v21,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
            0x103u,
            L"cbMax >= sizeof (m_fAsymEncryptPad)",
            v14);
          throw (microsoft::fs::common::FsException *)v21;
        }
        *(_DWORD *)a3 = *((_DWORD *)this + 132);
      }
    }
    else
    {
      if ( wcscmp_0(a2, L"PROVIDER_TYPE") )
      {
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v23,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
          0x112u,
          &psz,
          -2147024809,
          L"Invalid property %s.",
          a2);
        throw (microsoft::fs::common::FsException *)v23;
      }
      v15 = *a4;
      *a4 = 4;
      if ( a3 )
      {
        if ( v15 < 4 )
        {
          v16 = HR_FROM_WIN32(0x7Au);
          microsoft::fs::common::FsException::FsException(
            (microsoft::fs::common::FsException *)v22,
            L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
            0x10Cu,
            L"cbMax >= sizeof (DWORD)",
            v16);
          throw (microsoft::fs::common::FsException *)v22;
        }
        *(_DWORD *)a3 = 0;
      }
    }
  }
  else if ( (*((_BYTE *)PropertyLookupEntry + 32) & 2) != 0 )
  {
    Property = fsNCryptGetProperty(
                 *((_QWORD *)this + 68),
                 *((const unsigned __int16 **)PropertyLookupEntry + 5),
                 a3,
                 *a4,
                 a4,
                 a5);
    if ( Property < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        0x11Eu,
        L"NCryptGetProperty( m_hKey, ple->pszNCryptProperty, pbValue, *pcbValue, pcbValue, fFlags)",
        Property);
      throw (microsoft::fs::common::FsException *)v24;
    }
  }
  else
  {
    if ( (*((_BYTE *)PropertyLookupEntry + 32) & 8) == 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v26,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        0x12Cu,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v26;
    }
    v18 = fsNCryptGetProperty(
            *((_QWORD *)this + 67),
            *((const unsigned __int16 **)PropertyLookupEntry + 5),
            a3,
            *a4,
            a4,
            a5);
    if ( v18 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v25,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cngncryptcipher.cpp",
        0x128u,
        L"NCryptGetProperty( m_hProv, ple->pszNCryptProperty, pbValue, *pcbValue, pcbValue, fFlags)",
        v18);
      throw (microsoft::fs::common::FsException *)v25;
    }
  }
}

```

## disassembly

```asm
0x180037390  push    rbx
0x180037392  push    rsi
0x180037393  push    rdi
0x180037394  push    r14
0x180037396  sub     rsp, 208h
0x18003739d  mov     rbx, r9
0x1800373a0  mov     rdi, r8
0x1800373a3  mov     rsi, rdx
0x1800373a6  mov     r14, rcx
0x1800373a9  mov     rcx, [rsp+228h+arg_28]
0x1800373b1  test    rcx, rcx
0x1800373b4  jz      short loc_1800373C2
0x1800373b6  mov     rax, [rcx]
0x1800373b9  mov     rax, [rax+8]
0x1800373bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373c2  xor     r8d, r8d; unsigned __int64 *
0x1800373c5  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800373ca  mov     rcx, rsi; unsigned __int16 *
0x1800373cd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800373d2  test    eax, eax
0x1800373d4  jns     short loc_180037409
0x1800373d6  mov     dword ptr [rsp+228h+var_208], eax; int
0x1800373da  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x1800373e1  mov     r8d, 0F6h; unsigned int
0x1800373e7  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800373ee  lea     rcx, [rsp+228h+pExceptionObject]; this
0x1800373f3  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800373f8  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800373ff  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x180037404  call    _CxxThrowException_0
0x180037409  test    rbx, rbx
0x18003740c  jnz     short loc_18003744B
0x18003740e  mov     dword ptr [rsp+228h+var_208], 80070057h; int
0x180037416  lea     r9, aPcbvalue; "pcbValue"
0x18003741d  mov     r8d, 0F8h; unsigned int
0x180037423  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003742a  lea     rcx, [rsp+228h+var_180]; this
0x180037432  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037437  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003743e  lea     rcx, [rsp+228h+var_180]; pExceptionObject
0x180037446  call    _CxxThrowException_0
0x18003744b  mov     rcx, rsi; unsigned __int16 *
0x18003744e  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x180037453  mov     rdx, rax
0x180037456  test    byte ptr [rax+20h], 1
0x18003745a  jz      loc_18003759C
0x180037460  lea     rdx, aAsymEncryptPad; "ASYM_ENCRYPT_PAD_FLAG"
0x180037467  mov     rcx, rsi; String1
0x18003746a  call    wcscmp_0
0x18003746f  test    eax, eax
0x180037471  jnz     short loc_1800374DA
0x180037473  mov     eax, [rbx]
0x180037475  mov     dword ptr [rbx], 4
0x18003747b  test    rdi, rdi
0x18003747e  jz      loc_1800376C7
0x180037484  cmp     eax, 4
0x180037487  jnb     short loc_1800374CC
0x180037489  mov     ecx, 7Ah ; 'z'; unsigned int
0x18003748e  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180037493  mov     dword ptr [rsp+228h+var_208], eax; int
0x180037497  lea     r9, aCbmaxSizeofMFa; "cbMax >= sizeof (m_fAsymEncryptPad)"
0x18003749e  mov     r8d, 103h; unsigned int
0x1800374a4  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800374ab  lea     rcx, [rsp+228h+var_150]; this
0x1800374b3  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800374b8  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800374bf  lea     rcx, [rsp+228h+var_150]; pExceptionObject
0x1800374c7  call    _CxxThrowException_0
0x1800374cc  mov     eax, [r14+210h]
0x1800374d3  mov     [rdi], eax
0x1800374d5  jmp     loc_1800376C7
0x1800374da  lea     rdx, aProviderType; "PROVIDER_TYPE"
0x1800374e1  mov     rcx, rsi; String1
0x1800374e4  call    wcscmp_0
0x1800374e9  test    eax, eax
0x1800374eb  jnz     short loc_18003754E
0x1800374ed  mov     eax, [rbx]
0x1800374ef  mov     dword ptr [rbx], 4
0x1800374f5  test    rdi, rdi
0x1800374f8  jz      loc_1800376C7
0x1800374fe  cmp     eax, 4
0x180037501  jnb     short loc_180037546
0x180037503  mov     ecx, 7Ah ; 'z'; unsigned int
0x180037508  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18003750d  mov     dword ptr [rsp+228h+var_208], eax; int
0x180037511  lea     r9, aCbmaxSizeofDwo; "cbMax >= sizeof (DWORD)"
0x180037518  mov     r8d, 10Ch; unsigned int
0x18003751e  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037525  lea     rcx, [rsp+228h+var_120]; this
0x18003752d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037532  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037539  lea     rcx, [rsp+228h+var_120]; pExceptionObject
0x180037541  call    _CxxThrowException_0
0x180037546  mov     dword ptr [rdi], 0
0x18003754c  jmp     short loc_1800374D5
0x18003754e  mov     [rsp+228h+var_1F8], rsi
0x180037553  lea     rax, aInvalidPropert; "Invalid property %s."
0x18003755a  mov     qword ptr [rsp+228h+var_200], rax; unsigned __int16 *
0x18003755f  mov     dword ptr [rsp+228h+var_208], 80070057h; int
0x180037567  lea     r9, psz; unsigned __int16 *
0x18003756e  mov     r8d, 112h; unsigned int
0x180037574  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003757b  lea     rcx, [rsp+228h+var_F0]; this
0x180037583  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180037588  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003758f  lea     rcx, [rsp+228h+var_F0]; pExceptionObject
0x180037597  call    _CxxThrowException_0
0x18003759c  test    byte ptr [rax+20h], 2
0x1800375a0  jz      short loc_180037609
0x1800375a2  mov     eax, [rsp+228h+arg_20]
0x1800375a9  mov     [rsp+228h+var_200], eax; DWORD
0x1800375ad  mov     [rsp+228h+var_208], rbx; DWORD *
0x1800375b2  mov     r9d, [rbx]; unsigned int
0x1800375b5  mov     r8, rdi; unsigned __int8 *
0x1800375b8  mov     rdx, [rdx+28h]; unsigned __int16 *
0x1800375bc  mov     rcx, [r14+220h]; unsigned __int64
0x1800375c3  call    ?fsNCryptGetProperty@@YAJ_KPEBGPEAEKPEAKK@Z; fsNCryptGetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong *,ulong)
0x1800375c8  test    eax, eax
0x1800375ca  jns     loc_1800374D5
0x1800375d0  mov     dword ptr [rsp+228h+var_208], eax; int
0x1800375d4  lea     r9, aNcryptgetprope_0; "NCryptGetProperty( m_hKey, ple->pszNCry"...
0x1800375db  mov     r8d, 11Eh; unsigned int
0x1800375e1  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800375e8  lea     rcx, [rsp+228h+var_C0]; this
0x1800375f0  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800375f5  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800375fc  lea     rcx, [rsp+228h+var_C0]; pExceptionObject
0x180037604  call    _CxxThrowException_0
0x180037609  test    byte ptr [rax+20h], 8
0x18003760d  jz      short loc_180037676
0x18003760f  mov     eax, [rsp+228h+arg_20]
0x180037616  mov     [rsp+228h+var_200], eax; DWORD
0x18003761a  mov     [rsp+228h+var_208], rbx; DWORD *
0x18003761f  mov     r9d, [rbx]; unsigned int
0x180037622  mov     r8, rdi; unsigned __int8 *
0x180037625  mov     rdx, [rdx+28h]; unsigned __int16 *
0x180037629  mov     rcx, [r14+218h]; unsigned __int64
0x180037630  call    ?fsNCryptGetProperty@@YAJ_KPEBGPEAEKPEAKK@Z; fsNCryptGetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong *,ulong)
0x180037635  test    eax, eax
0x180037637  jns     loc_1800374D5
0x18003763d  mov     dword ptr [rsp+228h+var_208], eax; int
0x180037641  lea     r9, aNcryptgetprope_6; "NCryptGetProperty( m_hProv, ple->pszNCr"...
0x180037648  mov     r8d, 128h; unsigned int
0x18003764e  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x180037655  lea     rcx, [rsp+228h+var_90]; this
0x18003765d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180037662  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180037669  lea     rcx, [rsp+228h+var_90]; pExceptionObject
0x180037671  call    _CxxThrowException_0
0x180037676  mov     [rsp+228h+var_1F8], rsi
0x18003767b  lea     rax, aInvalidPropert; "Invalid property %s."
0x180037682  mov     qword ptr [rsp+228h+var_200], rax; unsigned __int16 *
0x180037687  mov     dword ptr [rsp+228h+var_208], 80070057h; int
0x18003768f  lea     r9, psz; unsigned __int16 *
0x180037696  mov     r8d, 12Ch; unsigned int
0x18003769c  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800376a3  lea     rcx, [rsp+228h+var_60]; this
0x1800376ab  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800376b0  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800376b7  lea     rcx, [rsp+228h+var_60]; pExceptionObject
0x1800376bf  call    _CxxThrowException_0
0x1800376c5  jmp     short $+2
0x1800376c7  add     rsp, 208h
0x1800376ce  pop     r14
0x1800376d0  pop     rdi
0x1800376d1  pop     rsi
0x1800376d2  pop     rbx
0x1800376d3  retn
```
