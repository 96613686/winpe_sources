# microsoft::fs::cryptography::CapiCryptoFactory::CreateHash(ushort const *,ulong,ulong,microsoft::fs::common::FsException *)

- ea: `0x180030888`
- end: `0x180030a54`
- name: `?CreateHash@CapiCryptoFactory@cryptography@fs@microsoft@@SAPEAVIHash@234@PEBGKKPEAVFsException@common@34@@Z`
- size: `460`
- prototype: `struct microsoft::fs::cryptography::IHash *__fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct microsoft::fs::common::FsException *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ff74`

## callees

- `0x180001514`
- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x18002e5e4`
- `0x180030888`
- `0x180030d90`
- `0x180030dbc`
- `0x180030e4c`
- `0x180032bcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003090c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003096f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003090c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003096f`

## string_xrefs

- `0x1800308cd`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x18003092a`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x18003098d`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x180030a04`: `onecore\ds\security\services\ca\fs\crypto\capicryptofactory.cpp`
- `0x180030980`: `CryptCreateHash(hProv, nAlgorithm, 0, 0, &hHash)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct microsoft::fs::cryptography::IHash *__fastcall microsoft::fs::cryptography::CapiCryptoFactory::CreateHash(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct microsoft::fs::common::FsException *a4)
{
  unsigned int v5; // edi
  const unsigned __int16 *v6; // r11
  unsigned __int64 v7; // r8
  unsigned int v8; // r9d
  DWORD LastError; // eax
  int v10; // eax
  DWORD v11; // eax
  int v12; // eax
  microsoft::fs::cryptography::CapiHash *v13; // rax
  unsigned int v14; // edx
  __int64 v15; // r9
  microsoft::fs::cryptography::CapiHash *v16; // rbx
  unsigned int v18; // [rsp+20h] [rbp-F8h]
  bool v19; // [rsp+20h] [rbp-F8h]
  unsigned __int64 v20; // [rsp+30h] [rbp-E8h] BYREF
  HCRYPTHASH v21[2]; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+48h] [rbp-D0h] BYREF
  _BYTE v23[48]; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v24[48]; // [rsp+A8h] [rbp-70h] BYREF
  _BYTE v25[48]; // [rsp+D8h] [rbp-40h] BYREF
  const microsoft::fs::common::FsException *v26; // [rsp+108h] [rbp-10h] BYREF

  v5 = (unsigned int)a2;
  v6 = a1;
  try
  {
    if ( a1 && (int)StringCchLengthW(a1, 0x7FFFFFFFu, 0) < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        139,
        L"!pszProvider || SUCCEEDED(StringCchLength(pszProvider, STRSAFE_MAX_CCH, 0))",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v20 = 0;
    if ( !(unsigned int)fsCryptAcquireContext(&v20, a2, v6, v5, v18) )
    {
      LastError = GetLastError();
      v10 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v23,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        148,
        L"CryptAcquireContext( &hProv, 0, pszProvider, nProviderType, CRYPT_VERIFYCONTEXT | CRYPT_SILENT)",
        v10);
      throw (microsoft::fs::common::FsException *)v23;
    }
    v21[0] = 0;
    if ( !(unsigned int)fsCryptCreateHash(v20, a3, v7, v8, v21) )
    {
      v11 = GetLastError();
      v12 = HR_FROM_WIN32(v11);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v24,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        151,
        L"CryptCreateHash(hProv, nAlgorithm, 0, 0, &hHash)",
        v12);
      throw (microsoft::fs::common::FsException *)v24;
    }
    v13 = (microsoft::fs::cryptography::CapiHash *)operator new(0x20u);
    if ( v13 )
      v16 = microsoft::fs::cryptography::CapiHash::CapiHash(v13, v20, v21[0], v15, v19);
    else
      v16 = 0;
    v21[1] = (HCRYPTHASH)v16;
    if ( !v16 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v25,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\capicryptofactory.cpp",
        154,
        L"pHash",
        -2147024882);
      throw (microsoft::fs::common::FsException *)v25;
    }
    v20 = 0;
  }
  catch ( const microsoft::fs::common::FsException *v26 )
  {
    throw;
  }
  catch ( ... )
  {
    throw;
  }
  microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::close(
    &v20,
    v14);
  return v16;
}

```

## disassembly

```asm
0x180030888  mov     [rsp+arg_0], rbx
0x18003088d  mov     [rsp+arg_18], r9
0x180030892  push    rdi
0x180030893  sub     rsp, 110h
0x18003089a  mov     ebx, r8d
0x18003089d  mov     edi, edx
0x18003089f  mov     r11, rcx
0x1800308a2  test    rcx, rcx
0x1800308a5  jz      short loc_1800308EF
0x1800308a7  xor     r8d, r8d; unsigned __int64 *
0x1800308aa  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800308af  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800308b4  test    eax, eax
0x1800308b6  jns     short loc_1800308EF
0x1800308b8  mov     [rsp+118h+var_F8], 80070057h; int
0x1800308c0  lea     r9, aPszproviderSuc; "!pszProvider || SUCCEEDED(StringCchLeng"...
0x1800308c7  mov     r8d, 8Bh; unsigned int
0x1800308cd  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x1800308d4  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800308d9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800308de  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800308e5  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800308ea  call    _CxxThrowException_0
0x1800308ef  mov     [rsp+118h+var_E8], 0
0x1800308f8  mov     r9d, edi; unsigned int
0x1800308fb  mov     r8, r11; unsigned __int16 *
0x1800308fe  lea     rcx, [rsp+118h+var_E8]; unsigned __int64 *
0x180030903  call    ?fsCryptAcquireContext@@YAHPEA_KPEBG1KK@Z; fsCryptAcquireContext(unsigned __int64 *,ushort const *,ushort const *,ulong,ulong)
0x180030908  test    eax, eax
0x18003090a  jnz     short loc_18003094C
0x18003090c  call    cs:__imp_GetLastError
0x180030912  mov     ecx, eax; unsigned int
0x180030914  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180030919  mov     [rsp+118h+var_F8], eax; int
0x18003091d  lea     r9, aCryptacquireco_0; "CryptAcquireContext( &hProv, 0, pszProv"...
0x180030924  mov     r8d, 94h; unsigned int
0x18003092a  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030931  lea     rcx, [rsp+118h+var_A0]; this
0x180030936  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18003093b  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030942  lea     rcx, [rsp+118h+var_A0]; pExceptionObject
0x180030947  call    _CxxThrowException_0
0x18003094c  mov     [rsp+118h+var_E0], 0
0x180030955  lea     rax, [rsp+118h+var_E0]
0x18003095a  mov     qword ptr [rsp+118h+var_F8], rax; bool
0x18003095f  mov     edx, ebx; unsigned int
0x180030961  mov     rcx, [rsp+118h+var_E8]; unsigned __int64
0x180030966  call    ?fsCryptCreateHash@@YAH_KI0KPEA_K@Z; fsCryptCreateHash(unsigned __int64,uint,unsigned __int64,ulong,unsigned __int64 *)
0x18003096b  test    eax, eax
0x18003096d  jnz     short loc_1800309B5
0x18003096f  call    cs:__imp_GetLastError
0x180030975  mov     ecx, eax; unsigned int
0x180030977  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18003097c  mov     [rsp+118h+var_F8], eax; int
0x180030980  lea     r9, aCryptcreatehas_0; "CryptCreateHash(hProv, nAlgorithm, 0, 0"...
0x180030987  mov     r8d, 97h; unsigned int
0x18003098d  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030994  lea     rcx, [rsp+118h+var_70]; this
0x18003099c  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x1800309a1  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x1800309a8  lea     rcx, [rsp+118h+var_70]; pExceptionObject
0x1800309b0  call    _CxxThrowException_0
0x1800309b5  mov     ecx, 20h ; ' '; Size
0x1800309ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800309bf  mov     [rsp+118h+arg_18], rax
0x1800309c7  test    rax, rax
0x1800309ca  jz      short loc_1800309E3
0x1800309cc  mov     r8, [rsp+118h+var_E0]; unsigned __int64
0x1800309d1  mov     rdx, [rsp+118h+var_E8]; unsigned __int64
0x1800309d6  mov     rcx, rax; this
0x1800309d9  call    ??0CapiHash@cryptography@fs@microsoft@@QEAA@_K0_N1@Z; microsoft::fs::cryptography::CapiHash::CapiHash(unsigned __int64,unsigned __int64,bool,bool)
0x1800309de  mov     rbx, rax
0x1800309e1  jmp     short loc_1800309E5
0x1800309e3  xor     ebx, ebx
0x1800309e5  mov     [rsp+118h+var_D8], rbx
0x1800309ea  test    rbx, rbx
0x1800309ed  jnz     short loc_180030A2C
0x1800309ef  mov     [rsp+118h+var_F8], 8007000Eh; int
0x1800309f7  lea     r9, aPhash; "pHash"
0x1800309fe  mov     r8d, 9Ah; unsigned int
0x180030a04  lea     rdx, aOnecoreDsSecur_7; "onecore\\ds\\security\\services\\ca\\fs"...
0x180030a0b  lea     rcx, [rsp+118h+var_40]; this
0x180030a13  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180030a18  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x180030a1f  lea     rcx, [rsp+118h+var_40]; pExceptionObject
0x180030a27  call    _CxxThrowException_0
0x180030a2c  mov     [rsp+118h+var_E8], 0
0x180030a35  lea     rcx, [rsp+118h+var_E8]
0x180030a3a  call    ?close@?$auto_handle_t@_K$0A@VCloseCapiProviderFunctor@cryptography@fs@microsoft@@@common@fs@microsoft@@AEAAXXZ; microsoft::fs::common::auto_handle_t<unsigned __int64,0,microsoft::fs::cryptography::CloseCapiProviderFunctor>::close(void)
0x180030a3f  nop
0x180030a40  mov     rax, rbx
0x180030a43  mov     rbx, [rsp+118h+arg_0]
0x180030a4b  add     rsp, 110h
0x180030a52  pop     rdi
0x180030a53  retn
```
