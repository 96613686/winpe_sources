# FindAndRemove

- ea: `0x18000e2fc`
- end: `0x18000e4ca`
- name: `FindAndRemove`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000c120`

## callees

- `0x18000d304`
- `0x18000e2fc`
- `0x18000e4d0`
- `0x180020dbc`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000e390`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000e390`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e3d4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e3d4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000e463`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000e463`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e470`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e39f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e39f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e47a`

## string_xrefs

- `0x18000e3c5`: `	Error searching Path %ws:%lu\n`
- `0x18000e36b`: `	Error constructing search path %lu\n`
- `0x18000e405`: `	Error constructing path %lu\n`
- `0x18000e489`: `DeleteFileW on %ws failed with %lu\n`

## pseudocode

```c
__int64 __fastcall FindAndRemove(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  DWORD LastError; // ebx
  HANDLE FirstFileW; // rax
  unsigned __int64 v7; // rdi
  unsigned int v8; // eax
  DWORD v9; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszDest[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = StringCchPrintfW(pszDest, 0x105u, L"%ws\\%ws", a1, a2);
  LastError = v4;
  if ( v4 )
  {
    DsRolepLogPrintRoutine(1, "\tError constructing search path %lu\n", v4);
    return LastError;
  }
  FirstFileW = FindFirstFileW(pszDest, &FindFileData);
  v7 = -1;
  if ( FirstFileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( ((LastError - 2) & 0xFFFFFFEE) == 0 && LastError != 19 )
      return 0;
    if ( LastError )
    {
      DsRolepLogPrintRoutine(1, "\tError searching Path %ws:%lu\n", pszDest, LastError);
      return LastError;
    }
  }
  else
  {
    FindClose(FirstFileW);
  }
  v8 = StringCchPrintfW(pszDest, 0x105u, L"%ws\\%ws", a1, FindFileData.cFileName);
  LastError = v8;
  if ( v8 )
  {
    DsRolepLogPrintRoutine(1, "\tError constructing path %lu\n", v8);
  }
  else
  {
    DsRolepLogPrintRoutine(4, "\tRemoving %ws\n", pszDest);
    if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      do
        ++v7;
      while ( pszDest[v7] );
      return (unsigned int)DsRolepDelnodePath(pszDest, v7, 1);
    }
    else
    {
      SetFileAttributesW(pszDest, 0x80u);
      if ( !DeleteFileW(pszDest) )
      {
        v9 = GetLastError();
        LastError = v9;
        if ( v9 )
          DsRolepLogPrintRoutine(1, "DeleteFileW on %ws failed with %lu\n", pszDest, v9);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000e2fc  mov     [rsp-8+arg_10], rbx
0x18000e301  mov     [rsp-8+arg_18], rsi
0x18000e306  push    rbp
0x18000e307  push    rdi
0x18000e308  push    r14
0x18000e30a  lea     rbp, [rsp-3A0h]
0x18000e312  sub     rsp, 4A0h
0x18000e319  mov     rax, cs:__security_cookie
0x18000e320  xor     rax, rsp
0x18000e323  mov     [rbp+3B0h+var_20], rax
0x18000e32a  mov     rbx, rdx
0x18000e32d  mov     rsi, rcx
0x18000e330  xor     edx, edx; Val
0x18000e332  lea     rcx, [rsp+4B0h+FindFileData]; void *
0x18000e337  mov     r8d, 250h; Size
0x18000e33d  call    memset_0
0x18000e342  mov     r9, rsi
0x18000e345  mov     [rsp+4B0h+var_490], rbx
0x18000e34a  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000e351  mov     edx, 105h; cchDest
0x18000e356  lea     rcx, [rbp+3B0h+pszDest]; pszDest
0x18000e35d  call    StringCchPrintfW
0x18000e362  xor     r14d, r14d
0x18000e365  mov     ebx, eax
0x18000e367  test    eax, eax
0x18000e369  jz      short loc_18000E384
0x18000e36b  lea     rdx, aErrorConstruct; "\tError constructing search path %lu\n"
0x18000e372  mov     r8d, eax
0x18000e375  mov     ecx, 1
0x18000e37a  call    DsRolepLogPrintRoutine
0x18000e37f  jmp     loc_18000E4A1
0x18000e384  lea     rdx, [rsp+4B0h+FindFileData]; lpFindFileData
0x18000e389  lea     rcx, [rbp+3B0h+pszDest]; lpFileName
0x18000e390  call    cs:__imp_FindFirstFileW
0x18000e396  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e39a  cmp     rax, rdi
0x18000e39d  jnz     short loc_18000E3D1
0x18000e39f  call    cs:__imp_GetLastError
0x18000e3a5  mov     ebx, eax
0x18000e3a7  add     eax, 0FFFFFFFEh
0x18000e3aa  test    eax, 0FFFFFFEEh
0x18000e3af  jnz     short loc_18000E3BE
0x18000e3b1  cmp     ebx, 13h
0x18000e3b4  jz      short loc_18000E3BE
0x18000e3b6  mov     ebx, r14d
0x18000e3b9  jmp     loc_18000E4A1
0x18000e3be  test    ebx, ebx
0x18000e3c0  jz      short loc_18000E3DA
0x18000e3c2  mov     r9d, ebx
0x18000e3c5  lea     rdx, aErrorSearching; "\tError searching Path %ws:%lu\n"
0x18000e3cc  jmp     loc_18000E490
0x18000e3d1  mov     rcx, rax; hFindFile
0x18000e3d4  call    cs:__imp_FindClose
0x18000e3da  lea     rax, [rsp+4B0h+FindFileData.cFileName]
0x18000e3df  mov     r9, rsi
0x18000e3e2  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000e3e9  mov     [rsp+4B0h+var_490], rax
0x18000e3ee  mov     edx, 105h; cchDest
0x18000e3f3  lea     rcx, [rbp+3B0h+pszDest]; pszDest
0x18000e3fa  call    StringCchPrintfW
0x18000e3ff  mov     ebx, eax
0x18000e401  test    eax, eax
0x18000e403  jz      short loc_18000E411
0x18000e405  lea     rdx, aErrorConstruct_0; "\tError constructing path %lu\n"
0x18000e40c  jmp     loc_18000E372
0x18000e411  lea     r8, [rbp+3B0h+pszDest]
0x18000e418  mov     ecx, 4
0x18000e41d  lea     rdx, aRemovingWs; "\tRemoving %ws\n"
0x18000e424  call    DsRolepLogPrintRoutine
0x18000e429  test    byte ptr [rsp+4B0h+FindFileData.dwFileAttributes], 10h
0x18000e42e  jz      short loc_18000E457
0x18000e430  lea     rax, [rbp+3B0h+pszDest]
0x18000e437  inc     rdi
0x18000e43a  cmp     [rax+rdi*2], r14w
0x18000e43f  jnz     short loc_18000E437
0x18000e441  mov     r8b, 1
0x18000e444  lea     rcx, [rbp+3B0h+pszDest]
0x18000e44b  mov     rdx, rdi
0x18000e44e  call    DsRolepDelnodePath
0x18000e453  mov     ebx, eax
0x18000e455  jmp     short loc_18000E4A1
0x18000e457  mov     edx, 80h; dwFileAttributes
0x18000e45c  lea     rcx, [rbp+3B0h+pszDest]; lpFileName
0x18000e463  call    cs:__imp_SetFileAttributesW
0x18000e469  lea     rcx, [rbp+3B0h+pszDest]; lpFileName
0x18000e470  call    cs:__imp_DeleteFileW
0x18000e476  test    eax, eax
0x18000e478  jnz     short loc_18000E4A1
0x18000e47a  call    cs:__imp_GetLastError
0x18000e480  mov     ebx, eax
0x18000e482  test    eax, eax
0x18000e484  jz      short loc_18000E4A1
0x18000e486  mov     r9d, eax
0x18000e489  lea     rdx, aDeletefilewOnW; "DeleteFileW on %ws failed with %lu\n"
0x18000e490  lea     r8, [rbp+3B0h+pszDest]
0x18000e497  mov     ecx, 1
0x18000e49c  call    DsRolepLogPrintRoutine
0x18000e4a1  mov     eax, ebx
0x18000e4a3  mov     rcx, [rbp+3B0h+var_20]
0x18000e4aa  xor     rcx, rsp; StackCookie
0x18000e4ad  call    __security_check_cookie
0x18000e4b2  lea     r11, [rsp+4B0h+var_10]
0x18000e4ba  mov     rbx, [r11+30h]
0x18000e4be  mov     rsi, [r11+38h]
0x18000e4c2  mov     rsp, r11
0x18000e4c5  pop     r14
0x18000e4c7  pop     rdi
0x18000e4c8  pop     rbp
0x18000e4c9  retn
```
