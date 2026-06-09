# IsFileNotASymlink

- ea: `0x1800806f0`
- end: `0x18008081d`
- name: `IsFileNotASymlink`
- size: `301`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180080430`

## callees

- `0x1800806f0`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800807ce`
- `msvcrt!_wcsnicmp` at `0x1800807ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807e7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008077b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18008077b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18008073b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18008073b`

## pseudocode

```c
DWORD __fastcall IsFileNotASymlink(HANDLE hFile, wchar_t *String1)
{
  size_t v4; // rbx
  DWORD FinalPathNameByHandleW; // eax
  WCHAR *v6; // rdx
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR szFilePath[4]; // [rsp+60h] [rbp-A0h] BYREF
  char v10; // [rsp+68h] [rbp-98h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hFile, &FileInformation)
    || (FileInformation.dwFileAttributes & 0x400) != 0
    || FileInformation.nNumberOfLinks > 1 )
  {
    return 161;
  }
  v4 = 260;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 0);
  if ( FinalPathNameByHandleW - 1 > 0x103 )
    return GetLastError();
  if ( FinalPathNameByHandleW >= 4
    && szFilePath[0] == 92
    && szFilePath[1] == 92
    && szFilePath[2] == 63
    && szFilePath[3] == 92 )
  {
    v4 = 256;
    v6 = (WCHAR *)&v10;
  }
  else
  {
    v6 = szFilePath;
  }
  return _wcsnicmp(String1, v6, v4) != 0 ? 0xA1 : 0;
}

```

## disassembly

```asm
0x1800806f0  mov     [rsp-8+arg_10], rbx
0x1800806f5  push    rbp
0x1800806f6  push    rsi
0x1800806f7  push    rdi
0x1800806f8  lea     rbp, [rsp-180h]
0x180080700  sub     rsp, 280h
0x180080707  mov     rax, cs:__security_cookie
0x18008070e  xor     rax, rsp
0x180080711  mov     [rbp+190h+var_20], rax
0x180080718  xorps   xmm0, xmm0
0x18008071b  mov     rsi, rdx
0x18008071e  xor     eax, eax
0x180080720  lea     rdx, [rsp+290h+FileInformation]; lpFileInformation
0x180080725  movups  xmmword ptr [rsp+290h+FileInformation.dwFileAttributes], xmm0
0x18008072a  mov     [rsp+290h+FileInformation.nFileIndexLow], eax
0x18008072e  mov     rdi, rcx
0x180080731  movups  xmmword ptr [rsp+290h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180080736  movups  xmmword ptr [rsp+290h+FileInformation.nFileSizeHigh], xmm0
0x18008073b  call    cs:__imp_GetFileInformationByHandle
0x180080742  nop     dword ptr [rax+rax+00h]
0x180080747  test    eax, eax
0x180080749  jz      loc_1800807F5
0x18008074f  test    [rsp+290h+FileInformation.dwFileAttributes], 400h
0x180080757  jnz     loc_1800807F5
0x18008075d  cmp     [rsp+290h+FileInformation.nNumberOfLinks], 1
0x180080762  ja      loc_1800807F5
0x180080768  mov     ebx, 104h
0x18008076d  lea     rdx, [rsp+290h+szFilePath]; lpszFilePath
0x180080772  mov     r8d, ebx; cchFilePath
0x180080775  xor     r9d, r9d; dwFlags
0x180080778  mov     rcx, rdi; hFile
0x18008077b  call    cs:__imp_GetFinalPathNameByHandleW
0x180080782  nop     dword ptr [rax+rax+00h]
0x180080787  lea     ecx, [rax-1]
0x18008078a  cmp     ecx, 103h
0x180080790  ja      short loc_1800807E7
0x180080792  cmp     eax, 4
0x180080795  jb      short loc_1800807C3
0x180080797  cmp     [rsp+290h+szFilePath], 5Ch ; '\'
0x18008079d  jnz     short loc_1800807C3
0x18008079f  cmp     [rsp+290h+var_22E], 5Ch ; '\'
0x1800807a5  jnz     short loc_1800807C3
0x1800807a7  cmp     [rsp+290h+var_22C], 3Fh ; '?'
0x1800807ad  jnz     short loc_1800807C3
0x1800807af  cmp     [rsp+290h+var_22A], 5Ch ; '\'
0x1800807b5  jnz     short loc_1800807C3
0x1800807b7  mov     ebx, 100h
0x1800807bc  lea     rdx, [rsp+290h+var_228]
0x1800807c1  jmp     short loc_1800807C8
0x1800807c3  lea     rdx, [rsp+290h+szFilePath]; String2
0x1800807c8  mov     r8, rbx; MaxCount
0x1800807cb  mov     rcx, rsi; String1
0x1800807ce  call    cs:__imp__wcsnicmp
0x1800807d5  nop     dword ptr [rax+rax+00h]
0x1800807da  neg     eax
0x1800807dc  mov     eax, 0A1h
0x1800807e1  sbb     ecx, ecx
0x1800807e3  and     eax, ecx
0x1800807e5  jmp     short loc_1800807FA
0x1800807e7  call    cs:__imp_GetLastError
0x1800807ee  nop     dword ptr [rax+rax+00h]
0x1800807f3  jmp     short loc_1800807FA
0x1800807f5  mov     eax, 0A1h
0x1800807fa  mov     rcx, [rbp+190h+var_20]
0x180080801  xor     rcx, rsp; StackCookie
0x180080804  call    __security_check_cookie
0x180080809  mov     rbx, [rsp+290h+arg_10]
0x180080811  add     rsp, 280h
0x180080818  pop     rdi
0x180080819  pop     rsi
0x18008081a  pop     rbp
0x18008081b  retn
```
