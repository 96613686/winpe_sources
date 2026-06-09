# microsoft::fs::cryptography::CapiHash::GetProperty(ushort const *,uchar *,ulong *,ulong,microsoft::fs::common::FsException *)

- ea: `0x180033160`
- end: `0x180033384`
- name: `?GetProperty@CapiHash@cryptography@fs@microsoft@@UEBAXPEBGPEAEPEAKKPEAVFsException@common@34@@Z`
- size: `548`
- prototype: `void(microsoft::fs::cryptography::CapiHash *__hidden this, const unsigned __int16 *, unsigned __int8 *, unsigned int *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800022ec`
- `0x180002306`
- `0x18000f628`
- `0x180019448`
- `0x180019728`
- `0x18002e4dc`
- `0x18002e5e4`
- `0x18002eedc`
- `0x180031250`
- `0x180032ca0`
- `0x180033160`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033265`

## string_xrefs

- `0x1800331b9`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x1800331f9`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x180033283`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x1800332ca`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`
- `0x18003334a`: `onecore\ds\security\services\ca\fs\crypto\capihash.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall microsoft::fs::cryptography::CapiHash::GetProperty(
        microsoft::fs::cryptography::CapiHash *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int *a4,
        DWORD a5,
        struct microsoft::fs::common::FsException *a6)
{
  int v10; // eax
  struct microsoft::fs::common::FsException *v11; // rdx
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *PropertyLookupEntry; // rax
  const struct microsoft::fs::cryptography::CryptoUtil::PropertyLookupEntry *v13; // rdi
  unsigned int v14; // esi
  int HashParam; // eax
  unsigned __int64 v16; // r8
  DWORD LastError; // eax
  int v18; // eax
  int v19; // eax
  const struct microsoft::fs::common::FsException *v20; // rax
  void *Src[2]; // [rsp+40h] [rbp-168h] BYREF
  const microsoft::fs::common::FsException *v22; // [rsp+50h] [rbp-158h] BYREF
  _QWORD v23[6]; // [rsp+58h] [rbp-150h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+88h] [rbp-120h] BYREF
  _BYTE v25[48]; // [rsp+B8h] [rbp-F0h] BYREF
  _BYTE v26[48]; // [rsp+E8h] [rbp-C0h] BYREF
  _BYTE v27[48]; // [rsp+118h] [rbp-90h] BYREF
  _BYTE v28[96]; // [rsp+148h] [rbp-60h] BYREF

  try
  {
    if ( a6 )
      (*(void (__fastcall **)(struct microsoft::fs::common::FsException *))(*(_QWORD *)a6 + 8LL))(a6);
    v10 = StringCchLengthW(a2, 0x7FFFFFFFu, 0);
    if ( v10 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        0x7Cu,
        L"StringCchLength(pszName, STRSAFE_MAX_CCH, 0)",
        v10);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    if ( !a4 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v25,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        0x7Eu,
        L"pcbValue",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v25;
    }
    PropertyLookupEntry = microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(a2, v11);
    v13 = PropertyLookupEntry;
    if ( (*((_BYTE *)PropertyLookupEntry + 12) & 4) == 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v28,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        0xA0u,
        &psz,
        -2147024809,
        L"Invalid property %s.",
        a2);
      throw (microsoft::fs::common::FsException *)v28;
    }
    v14 = *a4;
    HashParam = fsCryptGetHashParam(*((_QWORD *)this + 3), *((_DWORD *)PropertyLookupEntry + 4), a3, a4, a5);
    if ( *((_BYTE *)v13 + 8) )
      *a4 *= 2;
    if ( !HashParam )
    {
      LastError = GetLastError();
      v18 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v26,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        0x92u,
        L"fSuccess",
        v18);
      throw (microsoft::fs::common::FsException *)v26;
    }
    if ( v14 < *a4 )
    {
      v19 = HR_FROM_WIN32(0x7Au);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v27,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
        0x93u,
        L"cbAvail >= *pcbValue",
        v19);
      throw (microsoft::fs::common::FsException *)v27;
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      microsoft::fs::common::str_w::str_w((microsoft::fs::common::str_w *)Src, (const char *)a3, v16);
      memcpy_0(a3, Src[0], *a4);
      microsoft::fs::common::str_w::~str_w((microsoft::fs::common::str_w *)Src);
    }
  }
  catch ( const microsoft::fs::common::FsException *v22 )
  {
    if ( !a6 )
      throw;
    microsoft::fs::common::FsException::assign(a6, v22);
    return;
  }
  catch ( ... )
  {
    if ( !a6 )
      throw;
    v20 = (const struct microsoft::fs::common::FsException *)microsoft::fs::common::FsException::FsException(
                                                               (microsoft::fs::common::FsException *)v23,
                                                               L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capihash.cpp",
                                                               0xADu,
                                                               &psz,
                                                               -2147467259,
                                                               L"Caught exception of unknown type");
    microsoft::fs::common::FsException::assign(a6, v20);
    v23[0] = &microsoft::fs::common::FsException::`vftable';
    operator delete[]((void *)v23[1]);
    operator delete[]((void *)v23[2]);
    operator delete[]((void *)v23[3]);
    operator delete[]((void *)v23[5]);
  }
}

```

## disassembly

```asm
0x180033160  push    rbx
0x180033162  push    rsi
0x180033163  push    rdi
0x180033164  push    r14
0x180033166  push    r15
0x180033168  sub     rsp, 180h
0x18003316f  mov     rbx, r9
0x180033172  mov     r14, r8
0x180033175  mov     rsi, rdx
0x180033178  mov     r15, rcx
0x18003317b  mov     rcx, [rsp+1A8h+arg_28]
0x180033183  test    rcx, rcx
0x180033186  jz      short loc_180033194
0x180033188  mov     rax, [rcx]
0x18003318b  mov     rax, [rax+8]
0x18003318f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033194  xor     r8d, r8d; unsigned __int64 *
0x180033197  mov     edx, 7FFFFFFFh; unsigned __int64
0x18003319c  mov     rcx, rsi; unsigned __int16 *
0x18003319f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800331a4  test    eax, eax
0x1800331a6  jns     short loc_1800331E1
0x1800331a8  mov     [rsp+1A8h+var_188], eax; int
0x1800331ac  lea     r9, aStringcchlengt_0; "StringCchLength(pszName, STRSAFE_MAX_CC"...
0x1800331b3  mov     r8d, 7Ch ; '|'; unsigned int
0x1800331b9  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800331c0  lea     rcx, [rsp+1A8h+pExceptionObject]; this
0x1800331c8  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800331cd  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800331d4  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x1800331dc  call    _CxxThrowException_0
0x1800331e1  test    rbx, rbx
0x1800331e4  jnz     short loc_180033221
0x1800331e6  mov     [rsp+1A8h+var_188], 80070057h; int
0x1800331ee  lea     r9, aPcbvalue; "pcbValue"
0x1800331f5  lea     r8d, [rbx+7Eh]; unsigned int
0x1800331f9  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x180033200  lea     rcx, [rsp+1A8h+var_F0]; this
0x180033208  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003320d  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180033214  lea     rcx, [rsp+1A8h+var_F0]; pExceptionObject
0x18003321c  call    _CxxThrowException_0
0x180033221  mov     rcx, rsi; unsigned __int16 *
0x180033224  call    ?GetPropertyLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUPropertyLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetPropertyLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x180033229  mov     rdi, rax
0x18003322c  test    byte ptr [rax+0Ch], 4
0x180033230  jz      loc_180033324
0x180033236  mov     esi, [rbx]
0x180033238  mov     ecx, [rsp+1A8h+arg_20]
0x18003323f  mov     [rsp+1A8h+var_188], ecx; DWORD
0x180033243  mov     r9, rbx; unsigned int *
0x180033246  mov     r8, r14; unsigned __int8 *
0x180033249  mov     edx, [rax+10h]; unsigned int
0x18003324c  mov     rcx, [r15+18h]; unsigned __int64
0x180033250  call    ?fsCryptGetHashParam@@YAH_KKPEAEPEAKK@Z; fsCryptGetHashParam(unsigned __int64,ulong,uchar *,ulong *,ulong)
0x180033255  cmp     byte ptr [rdi+8], 0
0x180033259  jz      short loc_180033261
0x18003325b  mov     ecx, [rbx]
0x18003325d  add     ecx, ecx
0x18003325f  mov     [rbx], ecx
0x180033261  test    eax, eax
0x180033263  jnz     short loc_1800332AB
0x180033265  call    cs:__imp_GetLastError
0x18003326b  mov     ecx, eax; unsigned int
0x18003326d  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180033272  mov     [rsp+1A8h+var_188], eax; int
0x180033276  lea     r9, aFsuccess; "fSuccess"
0x18003327d  mov     r8d, 92h; unsigned int
0x180033283  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x18003328a  lea     rcx, [rsp+1A8h+var_C0]; this
0x180033292  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180033297  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18003329e  lea     rcx, [rsp+1A8h+var_C0]; pExceptionObject
0x1800332a6  call    _CxxThrowException_0
0x1800332ab  cmp     esi, [rbx]
0x1800332ad  jnb     short loc_1800332F2
0x1800332af  mov     ecx, 7Ah ; 'z'; unsigned int
0x1800332b4  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x1800332b9  mov     [rsp+1A8h+var_188], eax; int
0x1800332bd  lea     r9, aCbavailPcbvalu; "cbAvail >= *pcbValue"
0x1800332c4  mov     r8d, 93h; unsigned int
0x1800332ca  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800332d1  lea     rcx, [rsp+1A8h+var_90]; this
0x1800332d9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800332de  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800332e5  lea     rcx, [rsp+1A8h+var_90]; pExceptionObject
0x1800332ed  call    _CxxThrowException_0
0x1800332f2  cmp     byte ptr [rdi+8], 0
0x1800332f6  jz      short loc_180033322
0x1800332f8  mov     rdx, r14; char *
0x1800332fb  lea     rcx, [rsp+1A8h+Src]; this
0x180033300  call    ??0str_w@common@fs@microsoft@@QEAA@PEBD_K@Z; microsoft::fs::common::str_w::str_w(char const *,unsigned __int64)
0x180033305  nop
0x180033306  mov     r8d, [rbx]; Size
0x180033309  mov     rdx, [rsp+1A8h+Src]; Src
0x18003330e  mov     rcx, r14; void *
0x180033311  call    memcpy_0
0x180033316  nop
0x180033317  lea     rcx, [rsp+1A8h+Src]; this
0x18003331c  call    ??1str_w@common@fs@microsoft@@QEAA@XZ; microsoft::fs::common::str_w::~str_w(void)
0x180033321  nop
0x180033322  jmp     short loc_180033375
0x180033324  mov     [rsp+1A8h+var_178], rsi
0x180033329  lea     rax, aInvalidPropert; "Invalid property %s."
0x180033330  mov     [rsp+1A8h+var_180], rax; unsigned __int16 *
0x180033335  mov     [rsp+1A8h+var_188], 80070057h; int
0x18003333d  lea     r9, psz; unsigned __int16 *
0x180033344  mov     r8d, 0A0h; unsigned int
0x18003334a  lea     rdx, aOnecoreDsSecur_1; "onecore\\ds\\security\\services\\ca\\fs"...
0x180033351  lea     rcx, [rsp+1A8h+var_60]; this
0x180033359  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J0ZZ; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18003335e  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180033365  lea     rcx, [rsp+1A8h+var_60]; pExceptionObject
0x18003336d  call    _CxxThrowException_0
0x180033373  jmp     short $+2
0x180033375  add     rsp, 180h
0x18003337c  pop     r15
0x18003337e  pop     r14
0x180033380  pop     rdi
0x180033381  pop     rsi
0x180033382  pop     rbx
0x180033383  retn
```
