# RecursivelyDeleteDirectory

- ea: `0x1800ca284`
- end: `0x1800ca472`
- name: `RecursivelyDeleteDirectory`
- size: `494`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800ac384`
- `0x1800c1b18`
- `0x1800ca284`

## callees

- `0x18000bb60`
- `0x180046650`
- `0x180047330`
- `0x1800ca284`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca3cf`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800ca3cf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca3dc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ca3dc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800ca413`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800ca413`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800ca329`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800ca329`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800ca424`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800ca424`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800ca42d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800ca42d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca3f3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca440`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca3f3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800ca440`

## pseudocode

```c
__int64 __fastcall RecursivelyDeleteDirectory(const WCHAR *a1, int a2)
{
  unsigned int v4; // ebx
  HANDLE FirstFileW; // rsi
  int v6; // edx
  int v7; // edx
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(FileName, 0, 0x208u);
  if ( a2 && a1 && !(unsigned int)StrNCatBuff(FileName, 260, a1, L"\\*") )
  {
    v4 = 1;
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
      {
        v6 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v6 = FindFileData.cFileName[1];
        if ( v6 )
        {
          v7 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v7 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v7 = FindFileData.cFileName[2];
          }
          if ( v7 && !(unsigned int)StrNCatBuff(FileName, 260, a1, L"\\") )
          {
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              RecursivelyDeleteDirectory(FileName, (unsigned int)(a2 - 1));
            }
            else
            {
              if ( (FindFileData.dwFileAttributes & 1) != 0 )
                SetFileAttributesW(FileName, FindFileData.dwFileAttributes & 0xFFFFFFFE);
              if ( !DeleteFileW(FileName) )
                MoveFileExW(FileName, 0, 4u);
            }
          }
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
      if ( !RemoveDirectoryW(a1) )
        MoveFileExW(a1, 0, 4u);
    }
  }
  else
  {
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800ca284  mov     [rsp-8+arg_10], rbx
0x1800ca289  push    rbp
0x1800ca28a  push    rsi
0x1800ca28b  push    rdi
0x1800ca28c  push    r14
0x1800ca28e  push    r15
0x1800ca290  lea     rbp, [rsp-3A0h]
0x1800ca298  sub     rsp, 4A0h
0x1800ca29f  mov     rax, cs:__security_cookie
0x1800ca2a6  xor     rax, rsp
0x1800ca2a9  mov     [rbp+3C0h+var_30], rax
0x1800ca2b0  mov     r14d, edx
0x1800ca2b3  mov     rdi, rcx
0x1800ca2b6  xor     edx, edx; Val
0x1800ca2b8  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x1800ca2bd  mov     r8d, 250h; Size
0x1800ca2c3  call    memset_0
0x1800ca2c8  xor     edx, edx; Val
0x1800ca2ca  lea     rcx, [rbp+3C0h+FileName]; void *
0x1800ca2d1  mov     r8d, 208h; Size
0x1800ca2d7  call    memset_0
0x1800ca2dc  test    r14d, r14d
0x1800ca2df  jz      loc_1800CA448
0x1800ca2e5  test    rdi, rdi
0x1800ca2e8  jz      loc_1800CA448
0x1800ca2ee  lea     r9, asc_1800FF25C; "\\*"
0x1800ca2f5  mov     [rsp+4C0h+var_4A0], 0
0x1800ca2fe  mov     r8, rdi
0x1800ca301  lea     rcx, [rbp+3C0h+FileName]
0x1800ca308  mov     edx, 104h
0x1800ca30d  call    StrNCatBuff
0x1800ca312  test    eax, eax
0x1800ca314  jnz     loc_1800CA448
0x1800ca31a  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x1800ca31f  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x1800ca326  lea     ebx, [rax+1]
0x1800ca329  call    cs:__imp_FindFirstFileW
0x1800ca32f  mov     rsi, rax
0x1800ca332  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ca336  jz      loc_1800CA44A
0x1800ca33c  lea     r15d, [rbx+2Dh]
0x1800ca340  movzx   edx, [rsp+4C0h+FindFileData.cFileName]
0x1800ca345  sub     edx, r15d
0x1800ca348  jnz     short loc_1800CA356
0x1800ca34a  movzx   edx, [rsp+4C0h+FindFileData.cFileName+2]
0x1800ca34f  xor     eax, eax
0x1800ca351  movzx   ecx, ax
0x1800ca354  sub     edx, ecx
0x1800ca356  test    edx, edx
0x1800ca358  jz      loc_1800CA40B
0x1800ca35e  movzx   edx, [rsp+4C0h+FindFileData.cFileName]
0x1800ca363  sub     edx, r15d
0x1800ca366  jnz     short loc_1800CA37E
0x1800ca368  movzx   edx, [rsp+4C0h+FindFileData.cFileName+2]
0x1800ca36d  sub     edx, r15d
0x1800ca370  jnz     short loc_1800CA37E
0x1800ca372  movzx   edx, [rsp+4C0h+FindFileData.cFileName+4]
0x1800ca377  xor     eax, eax
0x1800ca379  movzx   ecx, ax
0x1800ca37c  sub     edx, ecx
0x1800ca37e  test    edx, edx
0x1800ca380  jz      loc_1800CA40B
0x1800ca386  lea     rax, [rsp+4C0h+FindFileData.cFileName]
0x1800ca38b  mov     [rsp+4C0h+var_498], 0
0x1800ca394  lea     r9, SubBlock; "\\"
0x1800ca39b  mov     [rsp+4C0h+var_4A0], rax
0x1800ca3a0  mov     r8, rdi
0x1800ca3a3  lea     rcx, [rbp+3C0h+FileName]
0x1800ca3aa  mov     edx, 104h
0x1800ca3af  call    StrNCatBuff
0x1800ca3b4  test    eax, eax
0x1800ca3b6  jnz     short loc_1800CA40B
0x1800ca3b8  mov     edx, [rsp+4C0h+FindFileData.dwFileAttributes]
0x1800ca3bc  test    dl, 10h
0x1800ca3bf  jnz     short loc_1800CA3FB
0x1800ca3c1  test    bl, dl
0x1800ca3c3  jz      short loc_1800CA3D5
0x1800ca3c5  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800ca3c8  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x1800ca3cf  call    cs:__imp_SetFileAttributesW
0x1800ca3d5  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x1800ca3dc  call    cs:__imp_DeleteFileW
0x1800ca3e2  test    eax, eax
0x1800ca3e4  jnz     short loc_1800CA40B
0x1800ca3e6  xor     edx, edx; lpNewFileName
0x1800ca3e8  lea     r8d, [rax+4]; dwFlags
0x1800ca3ec  lea     rcx, [rbp+3C0h+FileName]; lpExistingFileName
0x1800ca3f3  call    cs:__imp_MoveFileExW
0x1800ca3f9  jmp     short loc_1800CA40B
0x1800ca3fb  lea     edx, [r14-1]
0x1800ca3ff  lea     rcx, [rbp+3C0h+FileName]
0x1800ca406  call    RecursivelyDeleteDirectory
0x1800ca40b  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x1800ca410  mov     rcx, rsi; hFindFile
0x1800ca413  call    cs:__imp_FindNextFileW
0x1800ca419  test    eax, eax
0x1800ca41b  jnz     loc_1800CA340
0x1800ca421  mov     rcx, rsi; hFindFile
0x1800ca424  call    cs:__imp_FindClose
0x1800ca42a  mov     rcx, rdi; lpPathName
0x1800ca42d  call    cs:__imp_RemoveDirectoryW
0x1800ca433  test    eax, eax
0x1800ca435  jnz     short loc_1800CA44A
0x1800ca437  xor     edx, edx; lpNewFileName
0x1800ca439  lea     r8d, [rax+4]; dwFlags
0x1800ca43d  mov     rcx, rdi; lpExistingFileName
0x1800ca440  call    cs:__imp_MoveFileExW
0x1800ca446  jmp     short loc_1800CA44A
0x1800ca448  xor     ebx, ebx
0x1800ca44a  mov     eax, ebx
0x1800ca44c  mov     rcx, [rbp+3C0h+var_30]
0x1800ca453  xor     rcx, rsp; StackCookie
0x1800ca456  call    __security_check_cookie
0x1800ca45b  mov     rbx, [rsp+4C0h+arg_10]
0x1800ca463  add     rsp, 4A0h
0x1800ca46a  pop     r15
0x1800ca46c  pop     r14
0x1800ca46e  pop     rdi
0x1800ca46f  pop     rsi
0x1800ca470  pop     rbp
0x1800ca471  retn
```
