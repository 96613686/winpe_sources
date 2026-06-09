# CMemoryMappedCacheMgr::Delete(_GUID const &,CM_SCOPEFLAGS)

- ea: `0x1800632b0`
- end: `0x18006340a`
- name: `?Delete@CMemoryMappedCacheMgr@@UEAAJAEBU_GUID@@W4CM_SCOPEFLAGS@@@Z`
- size: `346`
- prototype: `int __high(const struct _GUID *, enum CM_SCOPEFLAGS)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180025298`
- `0x18002568c`
- `0x180025b70`
- `0x1800632b0`
- `0x180063410`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800633ca`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800633ca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800633d8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800633d8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180063387`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180063387`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800633e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800633e5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180063328`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180063328`

## pseudocode

```c
__int64 __fastcall CMemoryMappedCacheMgr::Delete(CMemoryMappedCacheMgr *a1, const GUID *a2, unsigned int a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  HANDLE FirstFileW; // rdi
  int v10; // [rsp+28h] [rbp-D8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v13[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR FileName[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR v15[264]; // [rsp+6F0h] [rbp+5F0h] BYREF

  v6 = CMemoryMappedCacheMgr::_EnsureVersion(a1);
  if ( v6 >= 0 )
  {
    CVersionManager::Delete(*((_QWORD *)a1 + 2), a2, a3);
    if ( GetCachePath(v13, v7, a3, 0) )
    {
      StringFromGUID2(a2, sz, 39);
      v10 = a3;
      v6 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s.%1d.ver0x*", v13, sz, v10);
      if ( v6 >= 0 )
      {
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        FirstFileW = FindFirstFileW(FileName, &FindFileData);
        if ( FirstFileW != (HANDLE)-1LL )
        {
          do
          {
            v6 = StringCchPrintfW(v15, 0x104u, L"%s\\%s", v13, FindFileData.cFileName);
            if ( v6 >= 0 )
              DeleteFileW(v15);
          }
          while ( FindNextFileW(FirstFileW, &FindFileData) );
          FindClose(FirstFileW);
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800632b0  push    rbp
0x1800632b2  push    rbx
0x1800632b3  push    rsi
0x1800632b4  push    rdi
0x1800632b5  push    r14
0x1800632b7  lea     rbp, [rsp-810h]
0x1800632bf  sub     rsp, 910h
0x1800632c6  mov     rax, cs:__security_cookie
0x1800632cd  xor     rax, rsp
0x1800632d0  mov     [rbp+830h+var_30], rax
0x1800632d7  mov     edi, r8d
0x1800632da  mov     r14, rdx
0x1800632dd  mov     rsi, rcx
0x1800632e0  call    ?_EnsureVersion@CMemoryMappedCacheMgr@@AEAAJXZ; CMemoryMappedCacheMgr::_EnsureVersion(void)
0x1800632e5  mov     ebx, eax
0x1800632e7  test    eax, eax
0x1800632e9  js      loc_1800633EB
0x1800632ef  mov     rcx, [rsi+10h]
0x1800632f3  mov     r8d, edi
0x1800632f6  mov     rdx, r14
0x1800632f9  call    ?Delete@CVersionManager@@QEAAJAEBU_GUID@@W4CM_SCOPEFLAGS@@@Z; CVersionManager::Delete(_GUID const &,CM_SCOPEFLAGS)
0x1800632fe  xor     r9d, r9d
0x180063301  lea     rcx, [rbp+830h+var_660]
0x180063308  mov     r8d, edi
0x18006330b  call    ?GetCachePath@@YAHPEAG_KW4CM_SCOPEFLAGS@@H@Z; GetCachePath(ushort *,unsigned __int64,CM_SCOPEFLAGS,int)
0x180063310  test    eax, eax
0x180063312  jz      loc_1800633EB
0x180063318  mov     r8d, 27h ; '''; cchMax
0x18006331e  lea     rdx, [rbp+830h+sz]; lpsz
0x180063325  mov     rcx, r14; rguid
0x180063328  call    cs:__imp_StringFromGUID2
0x18006332e  lea     rax, [rbp+830h+sz]
0x180063335  mov     [rsp+930h+var_908], edi
0x180063339  mov     esi, 104h
0x18006333e  mov     [rsp+930h+var_910], rax
0x180063343  mov     edx, esi; unsigned __int64
0x180063345  lea     r9, [rbp+830h+var_660]
0x18006334c  lea     r8, aSS1dVer0x; "%s\\%s.%1d.ver0x*"
0x180063353  lea     rcx, [rbp+830h+FileName]; unsigned __int16 *
0x18006335a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006335f  mov     ebx, eax
0x180063361  test    eax, eax
0x180063363  js      loc_1800633EB
0x180063369  xor     edx, edx; Val
0x18006336b  lea     rcx, [rsp+930h+FindFileData]; void *
0x180063370  mov     r8d, 250h; Size
0x180063376  call    memset_0
0x18006337b  lea     rdx, [rsp+930h+FindFileData]; lpFindFileData
0x180063380  lea     rcx, [rbp+830h+FileName]; lpFileName
0x180063387  call    cs:__imp_FindFirstFileW
0x18006338d  mov     rdi, rax
0x180063390  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180063394  jz      short loc_1800633EB
0x180063396  lea     rax, [rsp+930h+FindFileData.cFileName]
0x18006339b  mov     rdx, rsi; unsigned __int64
0x18006339e  lea     r9, [rbp+830h+var_660]
0x1800633a5  mov     [rsp+930h+var_910], rax
0x1800633aa  lea     r8, aSS; "%s\\%s"
0x1800633b1  lea     rcx, [rbp+830h+var_240]; unsigned __int16 *
0x1800633b8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800633bd  mov     ebx, eax
0x1800633bf  test    eax, eax
0x1800633c1  js      short loc_1800633D0
0x1800633c3  lea     rcx, [rbp+830h+var_240]; lpFileName
0x1800633ca  call    cs:__imp_DeleteFileW
0x1800633d0  lea     rdx, [rsp+930h+FindFileData]; lpFindFileData
0x1800633d5  mov     rcx, rdi; hFindFile
0x1800633d8  call    cs:__imp_FindNextFileW
0x1800633de  test    eax, eax
0x1800633e0  jnz     short loc_180063396
0x1800633e2  mov     rcx, rdi; hFindFile
0x1800633e5  call    cs:__imp_FindClose
0x1800633eb  mov     eax, ebx
0x1800633ed  mov     rcx, [rbp+830h+var_30]
0x1800633f4  xor     rcx, rsp; StackCookie
0x1800633f7  call    __security_check_cookie
0x1800633fc  add     rsp, 910h
0x180063403  pop     r14
0x180063405  pop     rdi
0x180063406  pop     rsi
0x180063407  pop     rbx
0x180063408  pop     rbp
0x180063409  retn
```
