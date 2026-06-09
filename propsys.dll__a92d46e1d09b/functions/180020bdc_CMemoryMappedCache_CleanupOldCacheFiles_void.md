# CMemoryMappedCache::_CleanupOldCacheFiles(void)

- ea: `0x180020bdc`
- end: `0x180020d13`
- name: `?_CleanupOldCacheFiles@CMemoryMappedCache@@AEAAXXZ`
- size: `311`
- prototype: `void __fastcall(CMemoryMappedCache *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180020fa0`

## callees

- `0x180020bdc`
- `0x180025298`
- `0x18002568c`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180020cd1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180020cd1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180020cdf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180020cdf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020c90`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180020c90`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180020cec`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180020cec`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180020c10`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180020c10`

## pseudocode

```c
void __fastcall CMemoryMappedCache::_CleanupOldCacheFiles(const GUID *this)
{
  __int64 v2; // rdx
  char *Data4; // rdi
  HANDLE FirstFileW; // rbx
  int v5; // [rsp+28h] [rbp-6E0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-6D8h] BYREF
  OLECHAR sz[40]; // [rsp+280h] [rbp-488h] BYREF
  WCHAR FileName[264]; // [rsp+2D0h] [rbp-438h] BYREF
  WCHAR v9[264]; // [rsp+4E0h] [rbp-228h] BYREF

  if ( StringFromGUID2(this + 2, sz, 39) )
  {
    Data4 = (char *)this[5].Data4;
    if ( GetCachePath((unsigned __int16 *)this[5].Data4, v2, *(_DWORD *)&this[1].Data2, 0) )
    {
      v5 = *(_DWORD *)&this[1].Data2;
      if ( (int)StringCchPrintfW(FileName, 0x104u, L"%s\\%s.%1d.ver0x*", this[5].Data4, sz, v5) >= 0 )
      {
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        FirstFileW = FindFirstFileW(FileName, &FindFileData);
        if ( FirstFileW != (HANDLE)-1LL )
        {
          do
          {
            if ( (int)StringCchPrintfW(v9, 0x104u, L"%s\\%s", Data4, FindFileData.cFileName) >= 0 )
              DeleteFileW(v9);
          }
          while ( FindNextFileW(FirstFileW, &FindFileData) );
          FindClose(FirstFileW);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180020bdc  mov     [rsp+arg_8], rbx
0x180020be1  push    rdi
0x180020be2  sub     rsp, 700h
0x180020be9  mov     rax, cs:__security_cookie
0x180020bf0  xor     rax, rsp
0x180020bf3  mov     [rsp+708h+var_18], rax
0x180020bfb  mov     rbx, rcx
0x180020bfe  lea     rdx, [rsp+708h+sz]; lpsz
0x180020c06  add     rcx, 20h ; ' '; rguid
0x180020c0a  mov     r8d, 27h ; '''; cchMax
0x180020c10  call    cs:__imp_StringFromGUID2
0x180020c16  test    eax, eax
0x180020c18  jz      loc_180020CF2
0x180020c1e  mov     r8d, [rbx+14h]
0x180020c22  lea     rdi, [rbx+58h]
0x180020c26  mov     rcx, rdi
0x180020c29  xor     r9d, r9d
0x180020c2c  call    ?GetCachePath@@YAHPEAG_KW4CM_SCOPEFLAGS@@H@Z; GetCachePath(ushort *,unsigned __int64,CM_SCOPEFLAGS,int)
0x180020c31  test    eax, eax
0x180020c33  jz      loc_180020CF2
0x180020c39  mov     eax, [rbx+14h]
0x180020c3c  lea     r8, aSS1dVer0x; "%s\\%s.%1d.ver0x*"
0x180020c43  mov     [rsp+708h+var_6E0], eax
0x180020c47  lea     rcx, [rsp+708h+FileName]; unsigned __int16 *
0x180020c4f  lea     rax, [rsp+708h+sz]
0x180020c57  mov     r9, rdi
0x180020c5a  mov     edx, 104h; unsigned __int64
0x180020c5f  mov     [rsp+708h+var_6E8], rax
0x180020c64  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020c69  test    eax, eax
0x180020c6b  js      loc_180020CF2
0x180020c71  xor     edx, edx; Val
0x180020c73  lea     rcx, [rsp+708h+FindFileData]; void *
0x180020c78  mov     r8d, 250h; Size
0x180020c7e  call    memset_0
0x180020c83  lea     rdx, [rsp+708h+FindFileData]; lpFindFileData
0x180020c88  lea     rcx, [rsp+708h+FileName]; lpFileName
0x180020c90  call    cs:__imp_FindFirstFileW
0x180020c96  mov     rbx, rax
0x180020c99  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180020c9d  jz      short loc_180020CF2
0x180020c9f  lea     rax, [rsp+708h+FindFileData.cFileName]
0x180020ca4  mov     r9, rdi
0x180020ca7  lea     r8, aSS; "%s\\%s"
0x180020cae  mov     [rsp+708h+var_6E8], rax
0x180020cb3  mov     edx, 104h; unsigned __int64
0x180020cb8  lea     rcx, [rsp+708h+var_228]; unsigned __int16 *
0x180020cc0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020cc5  test    eax, eax
0x180020cc7  js      short loc_180020CD7
0x180020cc9  lea     rcx, [rsp+708h+var_228]; lpFileName
0x180020cd1  call    cs:__imp_DeleteFileW
0x180020cd7  lea     rdx, [rsp+708h+FindFileData]; lpFindFileData
0x180020cdc  mov     rcx, rbx; hFindFile
0x180020cdf  call    cs:__imp_FindNextFileW
0x180020ce5  test    eax, eax
0x180020ce7  jnz     short loc_180020C9F
0x180020ce9  mov     rcx, rbx; hFindFile
0x180020cec  call    cs:__imp_FindClose
0x180020cf2  mov     rcx, [rsp+708h+var_18]
0x180020cfa  xor     rcx, rsp; StackCookie
0x180020cfd  call    __security_check_cookie
0x180020d02  mov     rbx, [rsp+708h+arg_8]
0x180020d0a  add     rsp, 700h
0x180020d11  pop     rdi
0x180020d12  retn
```
