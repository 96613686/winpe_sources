# TraceVerifyFolderIsNotALink

- ea: `0x1800bd430`
- end: `0x1800bd52d`
- name: `TraceVerifyFolderIsNotALink`
- size: `253`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x1800bca58`

## callees

- `0x180063d98`
- `0x1800bd430`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd4b3`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd47b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800bd47b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bd4a9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bd4a9`

## pseudocode

```c
DWORD __fastcall TraceVerifyFolderIsNotALink(HANDLE hFile, wchar_t *String1)
{
  size_t v5; // rbx
  DWORD FinalPathNameByHandleW; // eax
  WCHAR *v7; // rdx
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR szFilePath[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v10; // [rsp+68h] [rbp-98h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hFile, &FileInformation) || (FileInformation.dwFileAttributes & 0x400) != 0 )
    return 161;
  v5 = 260;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 0);
  if ( !FinalPathNameByHandleW )
    return GetLastError();
  if ( FinalPathNameByHandleW > 0x104 )
    return 161;
  if ( FinalPathNameByHandleW >= 4
    && szFilePath[0] == 92
    && szFilePath[1] == 92
    && szFilePath[2] == 63
    && szFilePath[3] == 92 )
  {
    v5 = 256;
    v7 = (WCHAR *)&v10;
  }
  else
  {
    v7 = szFilePath;
  }
  return wcsnicmp_0(String1, v7, v5) != 0 ? 0xA1 : 0;
}

```

## disassembly

```asm
0x1800bd430  mov     [rsp-8+arg_10], rbx
0x1800bd435  push    rbp
0x1800bd436  push    rsi
0x1800bd437  push    rdi
0x1800bd438  lea     rbp, [rsp-180h]
0x1800bd440  sub     rsp, 280h
0x1800bd447  mov     rax, cs:__security_cookie
0x1800bd44e  xor     rax, rsp
0x1800bd451  mov     [rbp+190h+var_20], rax
0x1800bd458  xorps   xmm0, xmm0
0x1800bd45b  mov     rsi, rdx
0x1800bd45e  xor     eax, eax
0x1800bd460  lea     rdx, [rsp+290h+FileInformation]; lpFileInformation
0x1800bd465  movups  xmmword ptr [rsp+290h+FileInformation.dwFileAttributes], xmm0
0x1800bd46a  mov     [rsp+290h+FileInformation.nFileIndexLow], eax
0x1800bd46e  mov     rdi, rcx
0x1800bd471  movups  xmmword ptr [rsp+290h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800bd476  movups  xmmword ptr [rsp+290h+FileInformation.nFileSizeHigh], xmm0
0x1800bd47b  call    cs:__imp_GetFileInformationByHandle
0x1800bd481  test    eax, eax
0x1800bd483  jnz     short loc_1800BD48C
0x1800bd485  mov     eax, 0A1h
0x1800bd48a  jmp     short loc_1800BD50B
0x1800bd48c  test    [rsp+290h+FileInformation.dwFileAttributes], 400h
0x1800bd494  jnz     short loc_1800BD485
0x1800bd496  mov     ebx, 104h
0x1800bd49b  lea     rdx, [rsp+290h+szFilePath]; lpszFilePath
0x1800bd4a0  mov     r8d, ebx; cchFilePath
0x1800bd4a3  xor     r9d, r9d; dwFlags
0x1800bd4a6  mov     rcx, rdi; hFile
0x1800bd4a9  call    cs:__imp_GetFinalPathNameByHandleW
0x1800bd4af  test    eax, eax
0x1800bd4b1  jnz     short loc_1800BD4BB
0x1800bd4b3  call    cs:__imp_GetLastError
0x1800bd4b9  jmp     short loc_1800BD50B
0x1800bd4bb  cmp     eax, ebx
0x1800bd4bd  ja      short loc_1800BD485
0x1800bd4bf  cmp     eax, 4
0x1800bd4c2  jb      short loc_1800BD4F0
0x1800bd4c4  cmp     [rsp+290h+szFilePath], 5Ch ; '\'
0x1800bd4ca  jnz     short loc_1800BD4F0
0x1800bd4cc  cmp     [rsp+290h+var_22E], 5Ch ; '\'
0x1800bd4d2  jnz     short loc_1800BD4F0
0x1800bd4d4  cmp     [rsp+290h+var_22C], 3Fh ; '?'
0x1800bd4da  jnz     short loc_1800BD4F0
0x1800bd4dc  cmp     [rsp+290h+var_22A], 5Ch ; '\'
0x1800bd4e2  jnz     short loc_1800BD4F0
0x1800bd4e4  mov     ebx, 100h
0x1800bd4e9  lea     rdx, [rsp+290h+var_228]
0x1800bd4ee  jmp     short loc_1800BD4F5
0x1800bd4f0  lea     rdx, [rsp+290h+szFilePath]; String2
0x1800bd4f5  mov     r8, rbx; MaxCount
0x1800bd4f8  mov     rcx, rsi; String1
0x1800bd4fb  call    _wcsnicmp_0
0x1800bd500  neg     eax
0x1800bd502  mov     eax, 0A1h
0x1800bd507  sbb     ecx, ecx
0x1800bd509  and     eax, ecx
0x1800bd50b  mov     rcx, [rbp+190h+var_20]
0x1800bd512  xor     rcx, rsp; StackCookie
0x1800bd515  call    __security_check_cookie
0x1800bd51a  mov     rbx, [rsp+290h+arg_10]
0x1800bd522  add     rsp, 280h
0x1800bd529  pop     rdi
0x1800bd52a  pop     rsi
0x1800bd52b  pop     rbp
0x1800bd52c  retn
```
