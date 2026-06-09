# HrOpenUrlViaCache(ushort const *,IStream * *)

- ea: `0x180052178`
- end: `0x180052236`
- name: `?HrOpenUrlViaCache@@YAJPEBGPEAPEAUIStream@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IStream **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180051dc0`
- `0x180075fa8`
- `0x18007d36c`

## callees

- `0x180052178`
- `0x1800cca00`
- `0x1800cca90`

## import_xrefs

- `MSOERT2!OpenFileStreamW` at `0x1800521e8`
- `MSOERT2!OpenFileStreamW` at `0x1800521e8`
- `urlmon!URLOpenBlockingStreamW` at `0x180052206`
- `urlmon!URLOpenBlockingStreamW` at `0x180052206`
- `WININET!RetrieveUrlCacheEntryFileW` at `0x1800521c0`
- `WININET!RetrieveUrlCacheEntryFileW` at `0x1800521c0`
- `WININET!UnlockUrlCacheEntryFileW` at `0x1800521cf`
- `WININET!UnlockUrlCacheEntryFileW` at `0x1800521cf`

## pseudocode

```c
__int64 __fastcall HrOpenUrlViaCache(const unsigned __int16 *a1, struct IStream **a2)
{
  __int64 result; // rax
  DWORD cbCacheEntryInfo[4]; // [rsp+30h] [rbp-1028h] BYREF
  _INTERNET_CACHE_ENTRY_INFOW CacheEntryInfo; // [rsp+40h] [rbp-1018h] BYREF

  cbCacheEntryInfo[0] = 4096;
  CacheEntryInfo.dwStructSize = 112;
  if ( !RetrieveUrlCacheEntryFileW(a1, &CacheEntryInfo, cbCacheEntryInfo, 0) )
    return URLOpenBlockingStreamW(0, a1, a2, 0, 0) != 0 ? 0x800CCE3E : 0;
  UnlockUrlCacheEntryFileW(a1, 0);
  result = OpenFileStreamW(CacheEntryInfo.lpszLocalFileName, 3, 0x80000000LL, a2);
  if ( (_DWORD)result )
    return URLOpenBlockingStreamW(0, a1, a2, 0, 0) != 0 ? 0x800CCE3E : 0;
  return result;
}

```

## disassembly

```asm
0x180052178  mov     [rsp+arg_10], rbx
0x18005217d  push    rdi
0x18005217e  mov     eax, 1050h
0x180052183  call    _alloca_probe
0x180052188  sub     rsp, rax
0x18005218b  mov     rax, cs:__security_cookie
0x180052192  xor     rax, rsp
0x180052195  mov     [rsp+1058h+var_18], rax
0x18005219d  mov     rdi, rdx
0x1800521a0  mov     [rsp+1058h+cbCacheEntryInfo], 1000h
0x1800521a8  lea     rdx, [rsp+1058h+CacheEntryInfo]; lpCacheEntryInfo
0x1800521ad  mov     [rsp+1058h+CacheEntryInfo.dwStructSize], 70h ; 'p'
0x1800521b5  xor     r9d, r9d; dwReserved
0x1800521b8  lea     r8, [rsp+1058h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x1800521bd  mov     rbx, rcx
0x1800521c0  call    cs:__imp_RetrieveUrlCacheEntryFileW
0x1800521c6  test    eax, eax
0x1800521c8  jz      short loc_1800521F2
0x1800521ca  xor     edx, edx; dwReserved
0x1800521cc  mov     rcx, rbx; lpszUrlName
0x1800521cf  call    cs:__imp_UnlockUrlCacheEntryFileW
0x1800521d5  mov     rcx, [rsp+1058h+CacheEntryInfo.lpszLocalFileName]
0x1800521da  mov     r9, rdi
0x1800521dd  mov     edx, 3
0x1800521e2  mov     r8d, 80000000h
0x1800521e8  call    cs:__imp_OpenFileStreamW
0x1800521ee  test    eax, eax
0x1800521f0  jz      short loc_180052215
0x1800521f2  xor     r9d, r9d; DWORD
0x1800521f5  mov     [rsp+1058h+var_1038], 0; LPBINDSTATUSCALLBACK
0x1800521fe  mov     r8, rdi; LPSTREAM *
0x180052201  mov     rdx, rbx; LPCWSTR
0x180052204  xor     ecx, ecx; LPUNKNOWN
0x180052206  call    cs:__imp_URLOpenBlockingStreamW
0x18005220c  neg     eax
0x18005220e  sbb     eax, eax
0x180052210  and     eax, 800CCE3Eh
0x180052215  mov     rcx, [rsp+1058h+var_18]
0x18005221d  xor     rcx, rsp; StackCookie
0x180052220  call    __security_check_cookie
0x180052225  mov     rbx, [rsp+1058h+arg_10]
0x18005222d  add     rsp, 1050h
0x180052234  pop     rdi
0x180052235  retn
```
