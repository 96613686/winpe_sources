# CleanUpDeletedUserFonts(void)

- ea: `0x18001317c`
- end: `0x1800132db`
- name: `?CleanUpDeletedUserFonts@@YAXXZ`
- size: `351`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d490`

## callees

- `0x180006598`
- `0x180006624`
- `0x18001317c`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x1800131bb`
- `SHELL32!SHGetFolderPathW` at `0x1800131bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001329d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001329d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800132ab`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800132ab`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001326c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001326c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800132b8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800132b8`

## string_xrefs

- `0x1800131ee`: `\Deleted`

## pseudocode

```c
void CleanUpDeletedUserFonts(void)
{
  __int64 v0; // rax
  __int64 v1; // rax
  unsigned __int64 v2; // rbx
  unsigned __int16 *v3; // rsi
  HANDLE FirstFileW; // rdi
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF

  if ( SHGetFolderPathW(0, 28, 0, 0, FileName) >= 0
    && StringCchCatW(FileName, 0x104u, L"\\Microsoft\\Windows\\Fonts") >= 0
    && StringCchCatW(FileName, 0x104u, L"\\Deleted") >= 0
    && StringCchCatW(FileName, 0x104u, L"\\*") >= 0 )
  {
    v0 = -1;
    do
      ++v0;
    while ( FileName[v0] );
    v1 = v0 - 1;
    v2 = 260 - v1;
    v3 = &FileName[v1];
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 && StringCchCopyW(v3, v2, FindFileData.cFileName) >= 0 )
          DeleteFileW(FileName);
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
    }
  }
}

```

## disassembly

```asm
0x18001317c  push    rbp
0x18001317e  push    rbx
0x18001317f  push    rsi
0x180013180  push    rdi
0x180013181  push    r14
0x180013183  lea     rbp, [rsp-3A0h]
0x18001318b  sub     rsp, 4A0h
0x180013192  mov     rax, cs:__security_cookie
0x180013199  xor     rax, rsp
0x18001319c  mov     [rbp+3C0h+var_30], rax
0x1800131a3  xor     r9d, r9d; dwFlags
0x1800131a6  lea     rax, [rbp+3C0h+FileName]
0x1800131ad  xor     r8d, r8d; hToken
0x1800131b0  mov     [rsp+4C0h+pszPath], rax; pszPath
0x1800131b5  xor     ecx, ecx; hwnd
0x1800131b7  lea     edx, [r9+1Ch]; csidl
0x1800131bb  call    cs:__imp_SHGetFolderPathW
0x1800131c1  xor     r14d, r14d
0x1800131c4  test    eax, eax
0x1800131c6  js      loc_1800132BE
0x1800131cc  mov     ebx, 104h
0x1800131d1  lea     r8, aMicrosoftWindo; "\\Microsoft\\Windows\\Fonts"
0x1800131d8  mov     edx, ebx; unsigned __int64
0x1800131da  lea     rcx, [rbp+3C0h+FileName]; unsigned __int16 *
0x1800131e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800131e6  test    eax, eax
0x1800131e8  js      loc_1800132BE
0x1800131ee  lea     r8, aDeleted; "\\Deleted"
0x1800131f5  mov     edx, ebx; unsigned __int64
0x1800131f7  lea     rcx, [rbp+3C0h+FileName]; unsigned __int16 *
0x1800131fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013203  test    eax, eax
0x180013205  js      loc_1800132BE
0x18001320b  lea     r8, asc_180037E68; "\\*"
0x180013212  mov     edx, ebx; unsigned __int64
0x180013214  lea     rcx, [rbp+3C0h+FileName]; unsigned __int16 *
0x18001321b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013220  test    eax, eax
0x180013222  js      loc_1800132BE
0x180013228  lea     rcx, [rbp+3C0h+FileName]
0x18001322f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013233  inc     rax
0x180013236  cmp     [rcx+rax*2], r14w
0x18001323b  jnz     short loc_180013233
0x18001323d  dec     rax
0x180013240  lea     rsi, [rbp+3C0h+FileName]
0x180013247  xor     edx, edx; Val
0x180013249  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x18001324e  mov     r8d, 250h; Size
0x180013254  sub     rbx, rax
0x180013257  lea     rsi, [rsi+rax*2]
0x18001325b  call    memset_0
0x180013260  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x180013265  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x18001326c  call    cs:__imp_FindFirstFileW
0x180013272  mov     rdi, rax
0x180013275  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013279  jz      short loc_1800132BE
0x18001327b  test    byte ptr [rsp+4C0h+FindFileData.dwFileAttributes], 10h
0x180013280  jnz     short loc_1800132A3
0x180013282  lea     r8, [rsp+4C0h+FindFileData.cFileName]; unsigned __int16 *
0x180013287  mov     rdx, rbx; unsigned __int64
0x18001328a  mov     rcx, rsi; unsigned __int16 *
0x18001328d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013292  test    eax, eax
0x180013294  js      short loc_1800132A3
0x180013296  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x18001329d  call    cs:__imp_DeleteFileW
0x1800132a3  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x1800132a8  mov     rcx, rdi; hFindFile
0x1800132ab  call    cs:__imp_FindNextFileW
0x1800132b1  test    eax, eax
0x1800132b3  jnz     short loc_18001327B
0x1800132b5  mov     rcx, rdi; hFindFile
0x1800132b8  call    cs:__imp_FindClose
0x1800132be  mov     rcx, [rbp+3C0h+var_30]
0x1800132c5  xor     rcx, rsp; StackCookie
0x1800132c8  call    __security_check_cookie
0x1800132cd  add     rsp, 4A0h
0x1800132d4  pop     r14
0x1800132d6  pop     rdi
0x1800132d7  pop     rsi
0x1800132d8  pop     rbx
0x1800132d9  pop     rbp
0x1800132da  retn
```
