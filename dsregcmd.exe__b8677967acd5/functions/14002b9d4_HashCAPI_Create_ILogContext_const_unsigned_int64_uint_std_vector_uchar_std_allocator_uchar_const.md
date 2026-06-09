# HashCAPI::Create(ILogContext const *,unsigned __int64,uint,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x14002b9d4`
- end: `0x14002ba94`
- name: `?Create@HashCAPI@@AEAAXPEBVILogContext@@_KIAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `192`
- prototype: `BOOL __fastcall(HCRYPTHASH *phHash, struct ILogContext *, HCRYPTPROV hProv, ALG_ID Algid, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002ba9c`

## callees

- `0x14000c7d8`
- `0x1400234dc`
- `0x14002b9d4`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ba3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ba70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ba3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ba70`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x14002ba19`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x14002ba19`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x14002b9fa`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x14002b9fa`

## string_xrefs

- `0x14002ba61`: `CryptCreateHash is failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
BOOL __fastcall HashCAPI::Create(
        HCRYPTHASH *phHash,
        struct ILogContext *a2,
        HCRYPTPROV hProv,
        ALG_ID Algid,
        __int64 a5)
{
  BOOL result; // eax
  DWORD v8; // eax
  DWORD LastError; // eax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-18h] BYREF

  if ( !CryptCreateHash(hProv, Algid, 0, 0, phHash) )
  {
    Log::Verbose(a2, L"CryptCreateHash is failed");
    LastError = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
    throw (Win32Exception *)pExceptionObject;
  }
  result = CryptHashData(*phHash, *(const BYTE **)a5, *(_DWORD *)(a5 + 8) - *(_DWORD *)a5, 0);
  if ( !result )
  {
    Log::Verbose(a2, L"CryptHashData is failed");
    v8 = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
    throw (Win32Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x14002b9d4  mov     [rsp+arg_0], rbx
0x14002b9d9  push    rdi
0x14002b9da  sub     rsp, 40h
0x14002b9de  mov     eax, r9d
0x14002b9e1  mov     [rsp+48h+phHash], rcx; phHash
0x14002b9e6  mov     r10, r8
0x14002b9e9  mov     rbx, rdx
0x14002b9ec  mov     rdi, rcx
0x14002b9ef  mov     edx, eax; Algid
0x14002b9f1  mov     rcx, r10; hProv
0x14002b9f4  xor     r9d, r9d; dwFlags
0x14002b9f7  xor     r8d, r8d; hKey
0x14002b9fa  call    cs:__imp_CryptCreateHash
0x14002ba00  test    eax, eax
0x14002ba02  jz      short loc_14002BA61
0x14002ba04  mov     rax, [rsp+48h+arg_20]
0x14002ba09  xor     r9d, r9d; dwFlags
0x14002ba0c  mov     rcx, [rdi]; hHash
0x14002ba0f  mov     r8d, [rax+8]
0x14002ba13  sub     r8d, [rax]; dwDataLen
0x14002ba16  mov     rdx, [rax]; pbData
0x14002ba19  call    cs:__imp_CryptHashData
0x14002ba1f  test    eax, eax
0x14002ba21  jz      short loc_14002BA2E
0x14002ba23  mov     rbx, [rsp+48h+arg_0]
0x14002ba28  add     rsp, 40h
0x14002ba2c  pop     rdi
0x14002ba2d  retn
0x14002ba2e  lea     rdx, aCrypthashdataI; "CryptHashData is failed"
0x14002ba35  mov     rcx, rbx; struct ILogContext *
0x14002ba38  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002ba3d  call    cs:__imp_GetLastError
0x14002ba43  mov     edx, eax; unsigned int
0x14002ba45  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14002ba4a  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002ba4f  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002ba56  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14002ba5b  call    _CxxThrowException_0
0x14002ba61  lea     rdx, aCryptcreatehas; "CryptCreateHash is failed"
0x14002ba68  mov     rcx, rbx; struct ILogContext *
0x14002ba6b  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002ba70  call    cs:__imp_GetLastError
0x14002ba76  mov     edx, eax; unsigned int
0x14002ba78  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14002ba7d  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002ba82  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002ba89  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14002ba8e  call    _CxxThrowException_0
```
