# microsoft::fs::cryptography::CapiCipher::GetProperty(ushort const *,uchar *,ulong *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180035d40`
- end: `0x180036142`
- name: `?GetProperty@CapiCipher@cryptography@fs@microsoft@@UEBAXPEBGPEAEPEAKKPEAVFsException@common@34@@Z`
- size: `1026`
- prototype: `void(microsoft::fs::cryptography::CapiCipher *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180002306`
- `0x18000f628`
- `0x180019448`
- `0x180019728`
- `0x18002e4dc`
- `0x18002e5e4`
- `0x18002eedc`
- `0x1800312ec`
- `0x180031388`
- `0x180032ca0`
- `0x180035d40`
- `0x18003970a`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036070`

## string_xrefs

- `0x180035d99`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035ddb`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035e4e`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035ea7`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035f00`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035f59`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180035fc4`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x180036018`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x18003608e`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`
- `0x1800360d6`: `onecore\ds\security\services\ca\fs\crypto\capicipher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall microsoft::fs::cryptography::CapiCipher::GetProperty(
        microsoft::fs::cryptography::CapiCipher *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        DWORD a5,
        struct microsoft::fs::common::FsException *a6)
{
  int v10; // eax
  struct microsoft::fs::common::FsException *v11; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *v13; // rsi
  unsigned int v14; // eax
  int v15; // eax
  DWORD LastError; // eax
  int v17; // eax
  unsigned int v18; // r14d
  int ProvParam; // eax
  unsigned __int64 v20; // r8
  DWORD v21; // eax
  int v22; // eax
  int v23; // eax
  void *Src[9]; // [rsp+40h] [rbp-258h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+88h] [rbp-210h] BYREF
  _BYTE v26[48]; // [rsp+B8h] [rbp-1E0h] BYREF
  _BYTE v27[48]; // [rsp+E8h] [rbp-1B0h] BYREF
  _BYTE v28[48]; // [rsp+118h] [rbp-180h] BYREF
  _BYTE v29[48]; // [rsp+148h] [rbp-150h] BYREF
  _BYTE v30[48]; // [rsp+178h] [rbp-120h] BYREF
  _BYTE v31[48]; // [rsp+1A8h] [rbp-F0h] BYREF
  _BYTE v32[48]; // [rsp+1D8h] [rbp-C0h] BYREF
  _BYTE v33[48]; // [rsp+208h] [rbp-90h] BYREF
  _BYTE v34[96]; // [rsp+238h] [rbp-60h] BYREF

  if ( a6 )
    (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a6 + 8LL))(a6);
  v10 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
  if ( v10 < 0 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)pExceptionObject,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
      0x152u,
      L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
      v10);
    throw (microsoft::fs::common::FsException *)pExceptionObject;
  }
  if ( !a4 )
  {
    microsoft::fs::common::FsException::FsException(
      (microsoft::fs::common::FsException *)v26,
      L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
      0x154u,
      L"pcbValue",
      -2147024809);
    throw (microsoft::fs::common::FsException *)v26;
  }
  PropertyLookupEntry = microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(a2, v11);
  v13 = PropertyLookupEntry;
  if ( (*((_BYTE *)PropertyLookupEntry + 12) & 1) != 0 )
  {
    if ( wcscmp_0(a2, L"ASYM_ENCRYPT_PAD_FLAG") )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v29,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x167u,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v29;
    }
    if ( *((_DWORD *)this + 6) != 41984 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v27,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x15Cu,
        L"CALG_RSA_KEYX == m_nCipherAlgorithm",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v27;
    }
    v14 = *a4;
    *a4 = 4;
    if ( a3 )
    {
      if ( v14 < 4 )
      {
        v15 = HR_FROM_WIN32(0x7Au);
        microsoft::fs::common::FsException::FsException(
          (microsoft::fs::common::FsException *)v28,
          L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
          0x161u,
          L"cbMax >= sizeof (m_fAsymEncryptPad)",
          v15);
        throw (microsoft::fs::common::FsException *)v28;
      }
      *(_DWORD *)a3 = *((_DWORD *)this + 4);
    }
  }
  else if ( (*((_BYTE *)PropertyLookupEntry + 12) & 2) != 0 )
  {
    if ( *((_BYTE *)PropertyLookupEntry + 8) )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v30,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x16Fu,
        L"!ple->fIsString",
        -2147467259,
        L"Translation of key string properties to unicode not currently supported");
      throw (microsoft::fs::common::FsException *)v30;
    }
    if ( !(unsigned int)fsCryptGetKeyParam(*((_QWORD *)this + 6), *((_DWORD *)PropertyLookupEntry + 4), a3, a4, a5) )
    {
      LastError = GetLastError();
      v17 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v31,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x176u,
        L"CryptGetKeyParam( m_hKey, ple->nCapiProperty, pbValue, pcbValue, fFlags)",
        v17);
      throw (microsoft::fs::common::FsException *)v31;
    }
  }
  else
  {
    if ( (*((_BYTE *)PropertyLookupEntry + 12) & 8) == 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v32,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x1A5u,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v32;
    }
    v18 = *a4;
    ProvParam = fsCryptGetProvParam(*((_QWORD *)this + 5), *((_DWORD *)PropertyLookupEntry + 4), a3, a4, a5);
    if ( *((_BYTE *)v13 + 8) )
      *a4 *= 2;
    if ( !ProvParam )
    {
      v21 = GetLastError();
      v22 = HR_FROM_WIN32(v21);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v33,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x199u,
        L"fSuccess",
        v22);
      throw (microsoft::fs::common::FsException *)v33;
    }
    if ( v18 < *a4 )
    {
      v23 = HR_FROM_WIN32(0x7Au);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v34,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicipher.cpp",
        0x19Au,
        L"cbAvail >= *pcbValue",
        v23);
      throw (microsoft::fs::common::FsException *)v34;
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      microsoft::fs::common::str_w::str_w((microsoft::fs::common::str_w *)Src, (const char *)a3, v20);
      memcpy_0(a3, Src[0], *a4);
      microsoft::fs::common::str_w::~str_w((microsoft::fs::common::str_w *)Src);
    }
  }
}

```

## disassembly

```asm
0x180035d40  push    rbx
0x180035d42  push    rsi
0x180035d43  push    rdi
0x180035d44  push    r14
0x180035d46  push    r15
0x180035d48  sub     rsp, 270h
0x180035d4f  mov     rbx, r9
0x180035d52  mov     rdi, r8
0x180035d55  mov     r14, rdx
0x180035d58  mov     r15, rcx
0x180035d5b  mov     rcx, [rsp+298h+arg_28]
0x180035d63  test    rcx, rcx
0x180035d66  jz      short loc_180035D74
0x180035d68  mov     rax, [rcx]
0x180035d6b  mov     rax, [rax+8]
0x180035d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d74  xor     r8d, r8d; unsigned __int64 *
0x180035d77  mov     edx, 7FFFFFFFh; unsigned __int64
0x180035d7c  mov     rcx, r14; unsigned __int16 *
0x180035d7f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180035d84  test    eax, eax
0x180035d86  jns     short loc_180035DC1
0x180035d88  mov     [rsp+298h+var_278], eax; int
0x180035d8c  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x180035d93  mov     r8d, 152h; unsigned int
0x180035d99  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035da0  lea     rcx, [rsp+298h+pExceptionObject]; this
0x180035da8  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035dad  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035db4  lea     rcx, [rsp+298h+pExceptionObject]; pExceptionObject
0x180035dbc  call    _CxxThrowException_0
0x180035dc1  test    rbx, rbx
0x180035dc4  jnz     short loc_180035E03
0x180035dc6  mov     [rsp+298h+var_278], 80070057h; int
0x180035dce  lea     r9, aPcbvalue; "pcbValue"
0x180035dd5  mov     r8d, 154h; unsigned int
0x180035ddb  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035de2  lea     rcx, [rsp+298h+var_1E0]; this
0x180035dea  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035def  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035df6  lea     rcx, [rsp+298h+var_1E0]; pExceptionObject
0x180035dfe  call    _CxxThrowException_0
0x180035e03  mov     rcx, r14; unsigned __int16 *
0x180035e06  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x180035e0b  mov     rsi, rax
0x180035e0e  test    byte ptr [rax+0Ch], 1
0x180035e12  jz      loc_180035F28
0x180035e18  lea     rdx, aAsymEncryptPad; "ASYM_ENCRYPT_PAD_FLAG"
0x180035e1f  mov     rcx, r14; String1
0x180035e22  call    wcscmp_0
0x180035e27  test    eax, eax
0x180035e29  jnz     loc_180035EDA
0x180035e2f  cmp     dword ptr [r15+18h], 0A400h
0x180035e37  jz      short loc_180035E76
0x180035e39  mov     [rsp+298h+var_278], 80070057h; int
0x180035e41  lea     r9, aCalgRsaKeyxMNc; "CALG_RSA_KEYX == m_nCipherAlgorithm"
0x180035e48  mov     r8d, 15Ch; unsigned int
0x180035e4e  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035e55  lea     rcx, [rsp+298h+var_1B0]; this
0x180035e5d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035e62  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035e69  lea     rcx, [rsp+298h+var_1B0]; pExceptionObject
0x180035e71  call    _CxxThrowException_0
0x180035e76  mov     eax, [rbx]
0x180035e78  mov     dword ptr [rbx], 4
0x180035e7e  test    rdi, rdi
0x180035e81  jz      loc_180036132
0x180035e87  cmp     eax, 4
0x180035e8a  jnb     short loc_180035ECF
0x180035e8c  mov     ecx, 7Ah ; 'z'; unsigned int
0x180035e91  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180035e96  mov     [rsp+298h+var_278], eax; int
0x180035e9a  lea     r9, aCbmaxSizeofMFa; "cbMax >= sizeof (m_fAsymEncryptPad)"
0x180035ea1  mov     r8d, 161h; unsigned int
0x180035ea7  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035eae  lea     rcx, [rsp+298h+var_180]; this
0x180035eb6  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035ebb  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035ec2  lea     rcx, [rsp+298h+var_180]; pExceptionObject
0x180035eca  call    _CxxThrowException_0
0x180035ecf  mov     eax, [r15+10h]
0x180035ed3  mov     [rdi], eax
0x180035ed5  jmp     loc_18003612E
0x180035eda  mov     [rsp+298h+var_268], r14
0x180035edf  lea     rax, aInvalidPropert; "Invalid property %s."
0x180035ee6  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x180035eeb  mov     [rsp+298h+var_278], 80070057h; int
0x180035ef3  lea     r9, psz; unsigned __int16 *
0x180035efa  mov     r8d, 167h; unsigned int
0x180035f00  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035f07  lea     rcx, [rsp+298h+var_150]; this
0x180035f0f  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180035f14  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035f1b  lea     rcx, [rsp+298h+var_150]; pExceptionObject
0x180035f23  call    _CxxThrowException_0
0x180035f28  test    byte ptr [rax+0Ch], 2
0x180035f2c  jz      loc_180035FEC
0x180035f32  cmp     byte ptr [rax+8], 0
0x180035f36  jz      short loc_180035F81
0x180035f38  lea     rax, aTranslationOfK; "Translation of key string properties to"...
0x180035f3f  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x180035f44  mov     [rsp+298h+var_278], 80004005h; int
0x180035f4c  lea     r9, aPleFisstring; "!ple->fIsString"
0x180035f53  mov     r8d, 16Fh; unsigned int
0x180035f59  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035f60  lea     rcx, [rsp+298h+var_120]; this
0x180035f68  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180035f6d  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035f74  lea     rcx, [rsp+298h+var_120]; pExceptionObject
0x180035f7c  call    _CxxThrowException_0
0x180035f81  mov     eax, [rsp+298h+arg_20]
0x180035f88  mov     [rsp+298h+var_278], eax; DWORD
0x180035f8c  mov     r9, rbx; unsigned int *
0x180035f8f  mov     r8, rdi; unsigned __int8 *
0x180035f92  mov     edx, [rsi+10h]; unsigned int
0x180035f95  mov     rcx, [r15+30h]; unsigned __int64
0x180035f99  call    ?fsCryptGetKeyParam@@YAH_KKPEAEPEAKK@Z; fsCryptGetKeyParam(unsigned __int64,ulong,uchar *,ulong *,ulong)
0x180035f9e  test    eax, eax
0x180035fa0  jnz     loc_18003612E
0x180035fa6  call    cs:__imp_GetLastError
0x180035fac  mov     ecx, eax; unsigned int
0x180035fae  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180035fb3  mov     [rsp+298h+var_278], eax; int
0x180035fb7  lea     r9, aCryptgetkeypar_0; "CryptGetKeyParam( m_hKey, ple->nCapiPro"...
0x180035fbe  mov     r8d, 176h; unsigned int
0x180035fc4  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180035fcb  lea     rcx, [rsp+298h+var_F0]; this
0x180035fd3  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180035fd8  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180035fdf  lea     rcx, [rsp+298h+var_F0]; pExceptionObject
0x180035fe7  call    _CxxThrowException_0
0x180035fec  test    byte ptr [rax+0Ch], 8
0x180035ff0  jnz     short loc_180036040
0x180035ff2  mov     [rsp+298h+var_268], r14
0x180035ff7  lea     rax, aInvalidPropert; "Invalid property %s."
0x180035ffe  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x180036003  mov     [rsp+298h+var_278], 80070057h; int
0x18003600b  lea     r9, psz; unsigned __int16 *
0x180036012  mov     r8d, 1A5h; unsigned int
0x180036018  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003601f  lea     rcx, [rsp+298h+var_C0]; this
0x180036027  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003602c  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180036033  lea     rcx, [rsp+298h+var_C0]; pExceptionObject
0x18003603b  call    _CxxThrowException_0
0x180036040  mov     r14d, [rbx]
0x180036043  mov     eax, [rsp+298h+arg_20]
0x18003604a  mov     [rsp+298h+var_278], eax; DWORD
0x18003604e  mov     r9, rbx; unsigned int *
0x180036051  mov     r8, rdi; unsigned __int8 *
0x180036054  mov     edx, [rsi+10h]; unsigned int
0x180036057  mov     rcx, [r15+28h]; unsigned __int64
0x18003605b  call    ?fsCryptGetProvParam@@YAH_KKPEAEPEAKK@Z; fsCryptGetProvParam(unsigned __int64,ulong,uchar *,ulong *,ulong)
0x180036060  cmp     byte ptr [rsi+8], 0
0x180036064  jz      short loc_18003606C
0x180036066  mov     ecx, [rbx]
0x180036068  add     ecx, ecx
0x18003606a  mov     [rbx], ecx
0x18003606c  test    eax, eax
0x18003606e  jnz     short loc_1800360B6
0x180036070  call    cs:__imp_GetLastError
0x180036076  mov     ecx, eax; unsigned int
0x180036078  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18003607d  mov     [rsp+298h+var_278], eax; int
0x180036081  lea     r9, aFsuccess; "fSuccess"
0x180036088  mov     r8d, 199h; unsigned int
0x18003608e  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x180036095  lea     rcx, [rsp+298h+var_90]; this
0x18003609d  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800360a2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800360a9  lea     rcx, [rsp+298h+var_90]; pExceptionObject
0x1800360b1  call    _CxxThrowException_0
0x1800360b6  cmp     r14d, [rbx]
0x1800360b9  jnb     short loc_1800360FE
0x1800360bb  mov     ecx, 7Ah ; 'z'; unsigned int
0x1800360c0  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x1800360c5  mov     [rsp+298h+var_278], eax; int
0x1800360c9  lea     r9, aCbavailPcbvalu; "cbAvail >= *pcbValue"
0x1800360d0  mov     r8d, 19Ah; unsigned int
0x1800360d6  lea     rdx, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800360dd  lea     rcx, [rsp+298h+var_60]; this
0x1800360e5  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800360ea  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800360f1  lea     rcx, [rsp+298h+var_60]; pExceptionObject
0x1800360f9  call    _CxxThrowException_0
0x1800360fe  cmp     byte ptr [rsi+8], 0
0x180036102  jz      short loc_18003612E
0x180036104  mov     rdx, rdi; char *
0x180036107  lea     rcx, [rsp+298h+Src]; this
0x18003610c  call    ??0str_w@common@fs@microsoft@@QEAA@PEBD_K@Z; microsoft::fs::common::str_w::str_w(char const *,unsigned __int64)
0x180036111  nop
0x180036112  mov     r8d, [rbx]; Size
0x180036115  mov     rdx, [rsp+298h+Src]; Src
0x18003611a  mov     rcx, rdi; void *
0x18003611d  call    memcpy_0
0x180036122  nop
0x180036123  lea     rcx, [rsp+298h+Src]; this
0x180036128  call    ??1str_w@common@fs@microsoft@@QEAA@XZ; microsoft::fs::common::str_w::~str_w(void)
0x18003612d  nop
0x18003612e  jmp     short loc_180036132
0x180036130  jmp     short $+2
0x180036132  add     rsp, 270h
0x180036139  pop     r15
0x18003613b  pop     r14
0x18003613d  pop     rdi
0x18003613e  pop     rsi
0x18003613f  pop     rbx
0x180036140  retn
```
