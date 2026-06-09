# ElCleanLog

- ea: `0x18001d6d4`
- end: `0x18001d878`
- name: `ElCleanLog`
- size: `420`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001e074`

## callees

- `0x18000f1b4`
- `0x18001d6d4`
- `0x18001e944`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d84f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d84f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001d847`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001d847`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001d7ef`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001d7ef`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d78c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d78c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d7e1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001d7e1`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001d737`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001d737`

## pseudocode

```c
__int64 ElCleanLog()
{
  unsigned int TempPath2W; // eax
  STRSAFE_LPWSTR *v1; // r9
  __int64 v2; // rbx
  unsigned int v3; // ebx
  HANDLE FirstFileW; // rdi
  size_t v5; // rsi
  wchar_t *v6; // r14
  STRSAFE_LPWSTR *v7; // r9
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  size_t *pcchRemaininga; // [rsp+20h] [rbp-E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszSrc[16]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR pszDest[576]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  wcscpy(pszSrc, L"ratmp.htm");
  TempPath2W = GetTempPath2W(260, pszDest);
  v2 = TempPath2W;
  if ( TempPath2W - 1 > 0x103 )
    return GetLastError();
  if ( StringCchCatExW(pszDest, 0x23Au, pszSrc, v1, pcchRemaining, 0x100u) < 0 )
    return 1003;
  FirstFileW = FindFirstFileW(pszDest, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return GetLastError();
  v5 = 570 - v2;
  v6 = &pszDest[v2];
  if ( StringCchCopyExW(v6, 570 - v2, FindFileData.cFileName, 0, 0, 0x100u) < 0 )
    return 1003;
  v3 = 0;
  while ( 1 )
  {
    DeleteFileW(pszDest);
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      break;
    if ( StringCchCopyExW(v6, v5, &word_18005536C, 0, 0, 0x100u) < 0
      || StringCchCatExW(pszDest, 0x23Au, FindFileData.cFileName, v7, pcchRemaininga, 0x100u) < 0 )
    {
      v3 = 1003;
      break;
    }
  }
  FindClose(FirstFileW);
  return v3;
}

```

## disassembly

```asm
0x18001d6d4  push    rbp
0x18001d6d6  push    rbx
0x18001d6d7  push    rsi
0x18001d6d8  push    rdi
0x18001d6d9  push    r12
0x18001d6db  push    r14
0x18001d6dd  lea     rbp, [rsp-638h]
0x18001d6e5  sub     rsp, 738h
0x18001d6ec  mov     rax, cs:__security_cookie
0x18001d6f3  xor     rax, rsp
0x18001d6f6  mov     [rbp+660h+var_40], rax
0x18001d6fd  xor     edx, edx; Val
0x18001d6ff  lea     rcx, [rsp+760h+FindFileData]; void *
0x18001d704  mov     r8d, 250h; Size
0x18001d70a  call    memset_0
0x18001d70f  movups  xmm0, xmmword ptr cs:aRasTmpHtm; "ras*.tmp.htm"
0x18001d716  lea     rdx, [rbp+660h+pszDest]
0x18001d71d  mov     ecx, 104h
0x18001d722  movups  xmm1, xmmword ptr cs:aRasTmpHtm+0Ah; "tmp.htm"
0x18001d729  movups  xmmword ptr [rbp+660h+pszSrc], xmm0
0x18001d730  movups  xmmword ptr [rbp+660h+pszSrc+0Ah], xmm1
0x18001d737  call    cs:__imp_GetTempPath2W
0x18001d73d  mov     ebx, eax
0x18001d73f  lea     ecx, [rbx-1]
0x18001d742  cmp     ecx, 103h
0x18001d748  ja      loc_18001D84F
0x18001d74e  mov     r12d, 23Ah
0x18001d754  mov     [rsp+760h+dwFlags], 100h; dwFlags
0x18001d75c  mov     edx, r12d; cchDest
0x18001d75f  lea     r8, [rbp+660h+pszSrc]; pszSrc
0x18001d766  lea     rcx, [rbp+660h+pszDest]; pszDest
0x18001d76d  call    StringCchCatExW
0x18001d772  test    eax, eax
0x18001d774  jns     short loc_18001D780
0x18001d776  mov     ebx, 3EBh
0x18001d77b  jmp     loc_18001D857
0x18001d780  lea     rdx, [rsp+760h+FindFileData]; lpFindFileData
0x18001d785  lea     rcx, [rbp+660h+pszDest]; lpFileName
0x18001d78c  call    cs:__imp_FindFirstFileW
0x18001d792  mov     rdi, rax
0x18001d795  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001d799  jz      loc_18001D84F
0x18001d79f  mov     rsi, r12
0x18001d7a2  mov     [rsp+760h+dwFlags], 100h; dwFlags
0x18001d7aa  lea     r14, [rbp+660h+pszDest]
0x18001d7b1  mov     [rsp+760h+pcchRemaining], 0; pcchRemaining
0x18001d7ba  sub     rsi, rbx
0x18001d7bd  lea     r14, [r14+rbx*2]
0x18001d7c1  mov     rdx, rsi; cchDest
0x18001d7c4  lea     r8, [rsp+760h+FindFileData.cFileName]; pszSrc
0x18001d7c9  mov     rcx, r14; pszDest
0x18001d7cc  xor     r9d, r9d; ppszDestEnd
0x18001d7cf  call    StringCchCopyExW
0x18001d7d4  test    eax, eax
0x18001d7d6  js      short loc_18001D776
0x18001d7d8  xor     ebx, ebx
0x18001d7da  lea     rcx, [rbp+660h+pszDest]; lpFileName
0x18001d7e1  call    cs:__imp_DeleteFileW
0x18001d7e7  lea     rdx, [rsp+760h+FindFileData]; lpFindFileData
0x18001d7ec  mov     rcx, rdi; hFindFile
0x18001d7ef  call    cs:__imp_FindNextFileW
0x18001d7f5  test    eax, eax
0x18001d7f7  jz      short loc_18001D844
0x18001d7f9  mov     [rsp+760h+dwFlags], 100h; dwFlags
0x18001d801  lea     r8, word_18005536C; pszSrc
0x18001d808  xor     r9d, r9d; ppszDestEnd
0x18001d80b  mov     [rsp+760h+pcchRemaining], rbx; pcchRemaining
0x18001d810  mov     rdx, rsi; cchDest
0x18001d813  mov     rcx, r14; pszDest
0x18001d816  call    StringCchCopyExW
0x18001d81b  test    eax, eax
0x18001d81d  js      short loc_18001D83F
0x18001d81f  lea     r8, [rsp+760h+FindFileData.cFileName]; pszSrc
0x18001d824  mov     [rsp+760h+dwFlags], 100h; dwFlags
0x18001d82c  mov     rdx, r12; cchDest
0x18001d82f  lea     rcx, [rbp+660h+pszDest]; pszDest
0x18001d836  call    StringCchCatExW
0x18001d83b  test    eax, eax
0x18001d83d  jns     short loc_18001D7DA
0x18001d83f  mov     ebx, 3EBh
0x18001d844  mov     rcx, rdi; hFindFile
0x18001d847  call    cs:__imp_FindClose
0x18001d84d  jmp     short loc_18001D857
0x18001d84f  call    cs:__imp_GetLastError
0x18001d855  mov     ebx, eax
0x18001d857  mov     eax, ebx
0x18001d859  mov     rcx, [rbp+660h+var_40]
0x18001d860  xor     rcx, rsp; StackCookie
0x18001d863  call    __security_check_cookie
0x18001d868  add     rsp, 738h
0x18001d86f  pop     r14
0x18001d871  pop     r12
0x18001d873  pop     rdi
0x18001d874  pop     rsi
0x18001d875  pop     rbx
0x18001d876  pop     rbp
0x18001d877  retn
```
