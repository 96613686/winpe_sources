# NtdspClearDirectory

- ea: `0x180018134`
- end: `0x18001834f`
- name: `NtdspClearDirectory`
- size: `539`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180016e94`
- `0x180017c98`

## callees

- `0x180008f24`
- `0x180008fd4`
- `0x180018134`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800182e3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800182e3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018207`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018207`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018317`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018317`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018294`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180018294`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800182af`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800182af`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018283`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800182c6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180018283`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800182c6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018324`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180018324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800182f1`

## pseudocode

```c
__int64 __fastcall NtdspClearDirectory(LPCWSTR lpPathName)
{
  unsigned __int64 v2; // rax
  HANDLE FirstFileW; // rsi
  DWORD LastError; // eax
  DWORD FileAttributesW; // eax
  DWORD v7; // ebx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t FileName[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t pszDest[264]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !lpPathName || !*lpPathName )
    return 0;
  v2 = -1;
  do
    ++v2;
  while ( lpPathName[v2] );
  if ( v2 > 0x100 )
    return 87;
  memset_0(pszDest, 0, 0x20Au);
  StringCchCopyW(pszDest, 0x105u, lpPathName);
  StringCchCatW(pszDest, 0x105u, L"\\*.*");
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(pszDest, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_19;
  }
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      memset_0(FileName, 0, 0x20Au);
      StringCchCopyW(FileName, 0x105u, lpPathName);
      StringCchCatW(FileName, 0x105u, L"\\");
      StringCchCatW(FileName, 0x105u, FindFileData.cFileName);
      if ( DeleteFileW(FileName) )
      {
        FileAttributesW = GetFileAttributesW(FileName);
        if ( FileAttributesW == -1
          || (FileAttributesW & 1) != 0 && !SetFileAttributesW(FileName, FileAttributesW & 0xFFFFFFFE) )
        {
          GetLastError();
        }
        DeleteFileW(FileName);
      }
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  LastError = GetLastError();
  if ( LastError != 18 && LastError )
  {
LABEL_19:
    v7 = 0;
    if ( LastError != 18 )
      v7 = LastError;
    if ( FirstFileW == (HANDLE)-1LL )
      goto LABEL_25;
    goto LABEL_24;
  }
  v7 = 0;
LABEL_24:
  FindClose(FirstFileW);
LABEL_25:
  if ( !v7 )
    RemoveDirectoryW(lpPathName);
  return v7;
}

```

## disassembly

```asm
0x180018134  push    rbp
0x180018136  push    rbx
0x180018137  push    rsi
0x180018138  push    rdi
0x180018139  push    r14
0x18001813b  push    r15
0x18001813d  lea     rbp, [rsp-5A8h]
0x180018145  sub     rsp, 6A8h
0x18001814c  mov     rax, cs:__security_cookie
0x180018153  xor     rax, rsp
0x180018156  mov     [rbp+5D0h+var_40], rax
0x18001815d  mov     rdi, rcx
0x180018160  mov     ebx, 250h
0x180018165  mov     r8d, ebx; Size
0x180018168  lea     rcx, [rsp+6D0h+FindFileData]; void *
0x18001816d  xor     edx, edx; Val
0x18001816f  call    memset_0
0x180018174  xor     r14d, r14d
0x180018177  test    rdi, rdi
0x18001817a  jz      loc_18001832E
0x180018180  cmp     [rdi], r14w
0x180018184  jz      loc_18001832E
0x18001818a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001818e  inc     rax
0x180018191  cmp     [rdi+rax*2], r14w
0x180018196  jnz     short loc_18001818E
0x180018198  cmp     rax, 100h
0x18001819e  jbe     short loc_1800181AA
0x1800181a0  mov     eax, 57h ; 'W'
0x1800181a5  jmp     loc_180018330
0x1800181aa  xor     edx, edx; Val
0x1800181ac  lea     rcx, [rbp+5D0h+pszDest]; void *
0x1800181b3  mov     r8d, 20Ah; Size
0x1800181b9  call    memset_0
0x1800181be  mov     r15d, 105h
0x1800181c4  lea     rcx, [rbp+5D0h+pszDest]; pszDest
0x1800181cb  mov     edx, r15d; cchDest
0x1800181ce  mov     r8, rdi; pszSrc
0x1800181d1  call    StringCchCopyW
0x1800181d6  lea     r8, asc_18003D370; "\\*.*"
0x1800181dd  mov     edx, r15d; cchDest
0x1800181e0  lea     rcx, [rbp+5D0h+pszDest]; pszDest
0x1800181e7  call    StringCchCatW
0x1800181ec  mov     r8, rbx; Size
0x1800181ef  lea     rcx, [rsp+6D0h+FindFileData]; void *
0x1800181f4  xor     edx, edx; Val
0x1800181f6  call    memset_0
0x1800181fb  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x180018200  lea     rcx, [rbp+5D0h+pszDest]; lpFileName
0x180018207  call    cs:__imp_FindFirstFileW
0x18001820d  mov     rsi, rax
0x180018210  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018214  jnz     short loc_180018221
0x180018216  call    cs:__imp_GetLastError
0x18001821c  jmp     loc_180018300
0x180018221  test    byte ptr [rsp+6D0h+FindFileData.dwFileAttributes], 10h
0x180018226  jnz     loc_1800182CC
0x18001822c  xor     edx, edx; Val
0x18001822e  lea     rcx, [rbp+5D0h+FileName]; void *
0x180018235  mov     r8d, 20Ah; Size
0x18001823b  call    memset_0
0x180018240  mov     r8, rdi; pszSrc
0x180018243  lea     rcx, [rbp+5D0h+FileName]; pszDest
0x18001824a  mov     rdx, r15; cchDest
0x18001824d  call    StringCchCopyW
0x180018252  lea     r8, pszSrc; "\\"
0x180018259  mov     rdx, r15; cchDest
0x18001825c  lea     rcx, [rbp+5D0h+FileName]; pszDest
0x180018263  call    StringCchCatW
0x180018268  lea     r8, [rsp+6D0h+FindFileData.cFileName]; pszSrc
0x18001826d  mov     rdx, r15; cchDest
0x180018270  lea     rcx, [rbp+5D0h+FileName]; pszDest
0x180018277  call    StringCchCatW
0x18001827c  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x180018283  call    cs:__imp_DeleteFileW
0x180018289  test    eax, eax
0x18001828b  jz      short loc_1800182CC
0x18001828d  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x180018294  call    cs:__imp_GetFileAttributesW
0x18001829a  cmp     eax, 0FFFFFFFFh
0x18001829d  jz      short loc_1800182B9
0x18001829f  test    al, 1
0x1800182a1  jz      short loc_1800182BF
0x1800182a3  and     eax, 0FFFFFFFEh
0x1800182a6  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x1800182ad  mov     edx, eax; dwFileAttributes
0x1800182af  call    cs:__imp_SetFileAttributesW
0x1800182b5  test    eax, eax
0x1800182b7  jnz     short loc_1800182BF
0x1800182b9  call    cs:__imp_GetLastError
0x1800182bf  lea     rcx, [rbp+5D0h+FileName]; lpFileName
0x1800182c6  call    cs:__imp_DeleteFileW
0x1800182cc  mov     r8, rbx; Size
0x1800182cf  lea     rcx, [rsp+6D0h+FindFileData]; void *
0x1800182d4  xor     edx, edx; Val
0x1800182d6  call    memset_0
0x1800182db  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x1800182e0  mov     rcx, rsi; hFindFile
0x1800182e3  call    cs:__imp_FindNextFileW
0x1800182e9  test    eax, eax
0x1800182eb  jnz     loc_180018221
0x1800182f1  call    cs:__imp_GetLastError
0x1800182f7  cmp     eax, 12h
0x1800182fa  jz      short loc_180018311
0x1800182fc  test    eax, eax
0x1800182fe  jz      short loc_180018311
0x180018300  cmp     eax, 12h
0x180018303  mov     ebx, r14d
0x180018306  cmovnz  ebx, eax
0x180018309  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001830d  jz      short loc_18001831D
0x18001830f  jmp     short loc_180018314
0x180018311  mov     ebx, r14d
0x180018314  mov     rcx, rsi; hFindFile
0x180018317  call    cs:__imp_FindClose
0x18001831d  test    ebx, ebx
0x18001831f  jnz     short loc_18001832A
0x180018321  mov     rcx, rdi; lpPathName
0x180018324  call    cs:__imp_RemoveDirectoryW
0x18001832a  mov     eax, ebx
0x18001832c  jmp     short loc_180018330
0x18001832e  xor     eax, eax
0x180018330  mov     rcx, [rbp+5D0h+var_40]
0x180018337  xor     rcx, rsp; StackCookie
0x18001833a  call    __security_check_cookie
0x18001833f  add     rsp, 6A8h
0x180018346  pop     r15
0x180018348  pop     r14
0x18001834a  pop     rdi
0x18001834b  pop     rsi
0x18001834c  pop     rbx
0x18001834d  pop     rbp
0x18001834e  retn
```
