# microsoft::fs::cryptography::CryptoUtil::ExportCapiKey(unsigned __int64,microsoft::fs::cryptography::ICipher *,ushort const *,uchar *,ulong *,microsoft::fs::common::FsException *)

- ea: `0x18002e868`
- end: `0x18002e9e6`
- name: `?ExportCapiKey@CryptoUtil@cryptography@fs@microsoft@@SAX_KPEAVICipher@234@PEBGPEAEPEAKPEAVFsException@common@34@@Z`
- size: `382`
- prototype: `void __fastcall(unsigned __int64, struct microsoft::fs::cryptography::ICipher *, const unsigned __int16 *, unsigned __int8 *, unsigned int *, struct microsoft::fs::common::FsException *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035b00`

## callees

- `0x1800022ec`
- `0x18000f628`
- `0x180019448`
- `0x18002e5e4`
- `0x18002e868`
- `0x18002ecf4`
- `0x180031054`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e990`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e990`

## string_xrefs

- `0x18002e89d`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002e8e4`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002e928`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`
- `0x18002e9ae`: `onecore\ds\security\services\ca\fs\crypto\cryptoutil.cpp`

## pseudocode

```c
void __fastcall microsoft::fs::cryptography::CryptoUtil::ExportCapiKey(
        unsigned __int64 a1,
        struct microsoft::fs::cryptography::ICipher *a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        struct microsoft::fs::common::FsException *a6)
{
  int v9; // eax
  struct microsoft::fs::common::FsException *v10; // rdx
  const unsigned __int16 *v11; // r11
  unsigned int v12; // r9d
  unsigned int v13; // r14d
  unsigned __int64 v14; // rax
  DWORD LastError; // eax
  int v16; // eax
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v18[48]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v19[48]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v20[48]; // [rsp+C0h] [rbp-68h] BYREF
  const microsoft::fs::common::FsException *v21; // [rsp+F0h] [rbp-38h] BYREF

  try
  {
    if ( !a1 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)pExceptionObject,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
        398,
        L"0 != hKey",
        -2147024809);
      throw (microsoft::fs::common::FsException *)pExceptionObject;
    }
    v9 = StringCchLengthW(a3, 0x7FFFFFFFu, 0);
    if ( v9 < 0 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v18,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
        400,
        L"StringCchLength(pszBlobType, STRSAFE_MAX_CCH, 0)",
        v9);
      throw (microsoft::fs::common::FsException *)v18;
    }
    if ( !a5 )
    {
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v19,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
        402,
        L"pcbBlob",
        -2147024809);
      throw (microsoft::fs::common::FsException *)v19;
    }
    v13 = *((_DWORD *)microsoft::fs::cryptography::CryptoUtil::GetBlobLookupEntry(v11, v10) + 2);
    if ( a2 )
      v14 = (*(__int64 (__fastcall **)(struct microsoft::fs::cryptography::ICipher *))(*(_QWORD *)a2 + 80LL))(a2);
    else
      v14 = 0;
    if ( !(unsigned int)fsCryptExportKey(a1, v14, v13, v12, a4, a5) )
    {
      LastError = GetLastError();
      v16 = HR_FROM_WIN32(LastError);
      microsoft::fs::common::FsException::FsException(
        (microsoft::fs::common::FsException *)v20,
        L"onecore\\ds\\security\\services\\ca\\fs\\crypto\\cryptoutil.cpp",
        411,
        L"CryptExportKey( hKey, pEncryptionKey ? reinterpret_cast<HCRYPTKEY>(pEncryptionKey->GetHandle()) : 0, GetBlobLook"
         "upEntry(pszBlobType)->nCapiBlobType, 0, pbBlob, pcbBlob)",
        v16);
      throw (microsoft::fs::common::FsException *)v20;
    }
  }
  catch ( const microsoft::fs::common::FsException *v21 )
  {
    throw;
  }
  catch ( ... )
  {
    throw;
  }
}

```

## disassembly

```asm
0x18002e868  push    rbx
0x18002e86a  push    rsi
0x18002e86b  push    rdi
0x18002e86c  push    r14
0x18002e86e  push    r15
0x18002e870  sub     rsp, 100h
0x18002e877  mov     r15, r9
0x18002e87a  mov     r11, r8
0x18002e87d  mov     rdi, rdx
0x18002e880  mov     rsi, rcx
0x18002e883  test    rcx, rcx
0x18002e886  jnz     short loc_18002E8BF
0x18002e888  mov     dword ptr [rsp+128h+var_108], 80070057h; int
0x18002e890  lea     r9, a0Hkey; "0 != hKey"
0x18002e897  mov     r8d, 18Eh; unsigned int
0x18002e89d  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002e8a4  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18002e8a9  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002e8ae  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002e8b5  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18002e8ba  call    _CxxThrowException_0
0x18002e8bf  xor     r8d, r8d; unsigned __int64 *
0x18002e8c2  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002e8c7  mov     rcx, r11; unsigned __int16 *
0x18002e8ca  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002e8cf  test    eax, eax
0x18002e8d1  jns     short loc_18002E906
0x18002e8d3  mov     dword ptr [rsp+128h+var_108], eax; int
0x18002e8d7  lea     r9, aStringcchlengt_1; "StringCchLength(pszBlobType, STRSAFE_MA"...
0x18002e8de  mov     r8d, 190h; unsigned int
0x18002e8e4  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002e8eb  lea     rcx, [rsp+128h+var_C8]; this
0x18002e8f0  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002e8f5  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002e8fc  lea     rcx, [rsp+128h+var_C8]; pExceptionObject
0x18002e901  call    _CxxThrowException_0
0x18002e906  mov     rbx, [rsp+128h+arg_20]
0x18002e90e  test    rbx, rbx
0x18002e911  jnz     short loc_18002E950
0x18002e913  mov     dword ptr [rsp+128h+var_108], 80070057h; int
0x18002e91b  lea     r9, aPcbblob; "pcbBlob"
0x18002e922  mov     r8d, 192h; unsigned int
0x18002e928  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002e92f  lea     rcx, [rsp+128h+var_98]; this
0x18002e937  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002e93c  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002e943  lea     rcx, [rsp+128h+var_98]; pExceptionObject
0x18002e94b  call    _CxxThrowException_0
0x18002e950  mov     rcx, r11; unsigned __int16 *
0x18002e953  call    ?GetBlobLookupEntry@CryptoUtil@cryptography@fs@microsoft@@SAPEBUBlobLookupEntry@1234@PEBGPEAVFsException@common@34@@Z; microsoft::fs::cryptography::CryptoUtil::GetBlobLookupEntry(ushort const *,microsoft::fs::common::FsException *)
0x18002e958  mov     r14d, [rax+8]
0x18002e95c  test    rdi, rdi
0x18002e95f  jz      short loc_18002E972
0x18002e961  mov     rax, [rdi]
0x18002e964  mov     rcx, rdi
0x18002e967  mov     rax, [rax+50h]
0x18002e96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e970  jmp     short loc_18002E974
0x18002e972  xor     eax, eax
0x18002e974  mov     [rsp+128h+var_100], rbx; DWORD *
0x18002e979  mov     [rsp+128h+var_108], r15; BYTE *
0x18002e97e  mov     r8d, r14d; unsigned int
0x18002e981  mov     rdx, rax; unsigned __int64
0x18002e984  mov     rcx, rsi; unsigned __int64
0x18002e987  call    ?fsCryptExportKey@@YAH_K0KKPEAEPEAK@Z; fsCryptExportKey(unsigned __int64,unsigned __int64,ulong,ulong,uchar *,ulong *)
0x18002e98c  test    eax, eax
0x18002e98e  jnz     short loc_18002E9D7
0x18002e990  call    cs:__imp_GetLastError
0x18002e996  mov     ecx, eax; unsigned int
0x18002e998  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x18002e99d  mov     dword ptr [rsp+128h+var_108], eax; int
0x18002e9a1  lea     r9, aCryptexportkey_0; "CryptExportKey( hKey, pEncryptionKey ? "...
0x18002e9a8  mov     r8d, 19Bh; unsigned int
0x18002e9ae  lea     rdx, aOnecoreDsSecur_11; "onecore\\ds\\security\\services\\ca\\fs"...
0x18002e9b5  lea     rcx, [rsp+128h+var_68]; this
0x18002e9bd  call    ??0FsException@common@fs@microsoft@@QEAA@PEBGK0J@Z; microsoft::fs::common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x18002e9c2  lea     rdx, _TI1?AVFsException@common@fs@microsoft@@; pThrowInfo
0x18002e9c9  lea     rcx, [rsp+128h+var_68]; pExceptionObject
0x18002e9d1  call    _CxxThrowException_0
0x18002e9d7  add     rsp, 100h
0x18002e9de  pop     r15
0x18002e9e0  pop     r14
0x18002e9e2  pop     rdi
0x18002e9e3  pop     rsi
0x18002e9e4  pop     rbx
0x18002e9e5  retn
```
