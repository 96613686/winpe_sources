# RecursivelyDeleteDirectory

- ea: `0x180036470`
- end: `0x18003665e`
- name: `RecursivelyDeleteDirectory`
- size: `494`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000ed30`
- `0x18000f698`
- `0x18002a30c`
- `0x18002b2fc`
- `0x18002b960`
- `0x18002f364`
- `0x180036470`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180036470`
- `0x1800367b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180036515`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180036515`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180036619`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180036619`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036610`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180036610`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800365ff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800365ff`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800365bb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800365bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800365c8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800365c8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800365df`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003662c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800365df`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003662c`

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
  if ( a2 && a1 && !(unsigned int)StrNCatBuff(FileName, 260, a1, L"\\*", 0) )
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
          if ( v7 && !(unsigned int)StrNCatBuff(FileName, 260, a1, L"\\", FindFileData.cFileName) )
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
0x180036470  mov     [rsp-8+arg_10], rbx
0x180036475  push    rbp
0x180036476  push    rsi
0x180036477  push    rdi
0x180036478  push    r14
0x18003647a  push    r15
0x18003647c  lea     rbp, [rsp-3A0h]
0x180036484  sub     rsp, 4A0h
0x18003648b  mov     rax, cs:__security_cookie
0x180036492  xor     rax, rsp
0x180036495  mov     [rbp+3C0h+var_30], rax
0x18003649c  mov     r14d, edx
0x18003649f  mov     rdi, rcx
0x1800364a2  xor     edx, edx; Val
0x1800364a4  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x1800364a9  mov     r8d, 250h; Size
0x1800364af  call    memset_0
0x1800364b4  xor     edx, edx; Val
0x1800364b6  lea     rcx, [rbp+3C0h+FileName]; void *
0x1800364bd  mov     r8d, 208h; Size
0x1800364c3  call    memset_0
0x1800364c8  test    r14d, r14d
0x1800364cb  jz      loc_180036634
0x1800364d1  test    rdi, rdi
0x1800364d4  jz      loc_180036634
0x1800364da  lea     r9, asc_180046784; "\\*"
0x1800364e1  mov     [rsp+4C0h+var_4A0], 0
0x1800364ea  mov     r8, rdi
0x1800364ed  lea     rcx, [rbp+3C0h+FileName]
0x1800364f4  mov     edx, 104h
0x1800364f9  call    StrNCatBuff
0x1800364fe  test    eax, eax
0x180036500  jnz     loc_180036634
0x180036506  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x18003650b  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x180036512  lea     ebx, [rax+1]
0x180036515  call    cs:__imp_FindFirstFileW
0x18003651b  mov     rsi, rax
0x18003651e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036522  jz      loc_180036636
0x180036528  lea     r15d, [rbx+2Dh]
0x18003652c  movzx   edx, [rsp+4C0h+FindFileData.cFileName]
0x180036531  sub     edx, r15d
0x180036534  jnz     short loc_180036542
0x180036536  movzx   edx, [rsp+4C0h+FindFileData.cFileName+2]
0x18003653b  xor     eax, eax
0x18003653d  movzx   ecx, ax
0x180036540  sub     edx, ecx
0x180036542  test    edx, edx
0x180036544  jz      loc_1800365F7
0x18003654a  movzx   edx, [rsp+4C0h+FindFileData.cFileName]
0x18003654f  sub     edx, r15d
0x180036552  jnz     short loc_18003656A
0x180036554  movzx   edx, [rsp+4C0h+FindFileData.cFileName+2]
0x180036559  sub     edx, r15d
0x18003655c  jnz     short loc_18003656A
0x18003655e  movzx   edx, [rsp+4C0h+FindFileData.cFileName+4]
0x180036563  xor     eax, eax
0x180036565  movzx   ecx, ax
0x180036568  sub     edx, ecx
0x18003656a  test    edx, edx
0x18003656c  jz      loc_1800365F7
0x180036572  lea     rax, [rsp+4C0h+FindFileData.cFileName]
0x180036577  mov     [rsp+4C0h+var_498], 0
0x180036580  lea     r9, SubBlock; "\\"
0x180036587  mov     [rsp+4C0h+var_4A0], rax
0x18003658c  mov     r8, rdi
0x18003658f  lea     rcx, [rbp+3C0h+FileName]
0x180036596  mov     edx, 104h
0x18003659b  call    StrNCatBuff
0x1800365a0  test    eax, eax
0x1800365a2  jnz     short loc_1800365F7
0x1800365a4  mov     edx, [rsp+4C0h+FindFileData.dwFileAttributes]
0x1800365a8  test    dl, 10h
0x1800365ab  jnz     short loc_1800365E7
0x1800365ad  test    bl, dl
0x1800365af  jz      short loc_1800365C1
0x1800365b1  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800365b4  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x1800365bb  call    cs:__imp_SetFileAttributesW
0x1800365c1  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x1800365c8  call    cs:__imp_DeleteFileW
0x1800365ce  test    eax, eax
0x1800365d0  jnz     short loc_1800365F7
0x1800365d2  xor     edx, edx; lpNewFileName
0x1800365d4  lea     r8d, [rax+4]; dwFlags
0x1800365d8  lea     rcx, [rbp+3C0h+FileName]; lpExistingFileName
0x1800365df  call    cs:__imp_MoveFileExW
0x1800365e5  jmp     short loc_1800365F7
0x1800365e7  lea     edx, [r14-1]
0x1800365eb  lea     rcx, [rbp+3C0h+FileName]
0x1800365f2  call    RecursivelyDeleteDirectory
0x1800365f7  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x1800365fc  mov     rcx, rsi; hFindFile
0x1800365ff  call    cs:__imp_FindNextFileW
0x180036605  test    eax, eax
0x180036607  jnz     loc_18003652C
0x18003660d  mov     rcx, rsi; hFindFile
0x180036610  call    cs:__imp_FindClose
0x180036616  mov     rcx, rdi; lpPathName
0x180036619  call    cs:__imp_RemoveDirectoryW
0x18003661f  test    eax, eax
0x180036621  jnz     short loc_180036636
0x180036623  xor     edx, edx; lpNewFileName
0x180036625  lea     r8d, [rax+4]; dwFlags
0x180036629  mov     rcx, rdi; lpExistingFileName
0x18003662c  call    cs:__imp_MoveFileExW
0x180036632  jmp     short loc_180036636
0x180036634  xor     ebx, ebx
0x180036636  mov     eax, ebx
0x180036638  mov     rcx, [rbp+3C0h+var_30]
0x18003663f  xor     rcx, rsp; StackCookie
0x180036642  call    __security_check_cookie
0x180036647  mov     rbx, [rsp+4C0h+arg_10]
0x18003664f  add     rsp, 4A0h
0x180036656  pop     r15
0x180036658  pop     r14
0x18003665a  pop     rdi
0x18003665b  pop     rsi
0x18003665c  pop     rbp
0x18003665d  retn
```
