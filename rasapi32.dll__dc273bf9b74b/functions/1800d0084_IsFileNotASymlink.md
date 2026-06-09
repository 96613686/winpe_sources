# IsFileNotASymlink

- ea: `0x1800d0084`
- end: `0x1800d0193`
- name: `IsFileNotASymlink`
- size: `271`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *String1)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18000b960`

## callees

- `0x180063d98`
- `0x1800d0084`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0164`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800d00cf`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800d00cf`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d0105`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800d0105`

## pseudocode

```c
DWORD __fastcall IsFileNotASymlink(HANDLE hFile, wchar_t *String1)
{
  size_t v4; // rbx
  DWORD FinalPathNameByHandleW; // eax
  WCHAR *v6; // rdx
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-E0h] BYREF
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
  return wcsnicmp_0(String1, v6, v4) != 0 ? 0xA1 : 0;
}

```

## disassembly

```asm
0x1800d0084  mov     [rsp-8+arg_10], rbx
0x1800d0089  push    rbp
0x1800d008a  push    rsi
0x1800d008b  push    rdi
0x1800d008c  lea     rbp, [rsp-180h]
0x1800d0094  sub     rsp, 280h
0x1800d009b  mov     rax, cs:__security_cookie
0x1800d00a2  xor     rax, rsp
0x1800d00a5  mov     [rbp+190h+var_20], rax
0x1800d00ac  xorps   xmm0, xmm0
0x1800d00af  mov     rsi, rdx
0x1800d00b2  xor     eax, eax
0x1800d00b4  lea     rdx, [rsp+290h+FileInformation]; lpFileInformation
0x1800d00b9  movups  xmmword ptr [rsp+290h+FileInformation.dwFileAttributes], xmm0
0x1800d00be  mov     [rsp+290h+FileInformation.nFileIndexLow], eax
0x1800d00c2  mov     rdi, rcx
0x1800d00c5  movups  xmmword ptr [rsp+290h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800d00ca  movups  xmmword ptr [rsp+290h+FileInformation.nFileSizeHigh], xmm0
0x1800d00cf  call    cs:__imp_GetFileInformationByHandle
0x1800d00d5  test    eax, eax
0x1800d00d7  jz      loc_1800D016C
0x1800d00dd  test    [rsp+290h+FileInformation.dwFileAttributes], 400h
0x1800d00e5  jnz     loc_1800D016C
0x1800d00eb  cmp     [rsp+290h+FileInformation.nNumberOfLinks], 1
0x1800d00f0  ja      short loc_1800D016C
0x1800d00f2  mov     ebx, 104h
0x1800d00f7  lea     rdx, [rsp+290h+szFilePath]; lpszFilePath
0x1800d00fc  mov     r8d, ebx; cchFilePath
0x1800d00ff  xor     r9d, r9d; dwFlags
0x1800d0102  mov     rcx, rdi; hFile
0x1800d0105  call    cs:__imp_GetFinalPathNameByHandleW
0x1800d010b  lea     ecx, [rax-1]
0x1800d010e  cmp     ecx, 103h
0x1800d0114  ja      short loc_1800D0164
0x1800d0116  cmp     eax, 4
0x1800d0119  jb      short loc_1800D0147
0x1800d011b  cmp     [rsp+290h+szFilePath], 5Ch ; '\'
0x1800d0121  jnz     short loc_1800D0147
0x1800d0123  cmp     [rsp+290h+var_22E], 5Ch ; '\'
0x1800d0129  jnz     short loc_1800D0147
0x1800d012b  cmp     [rsp+290h+var_22C], 3Fh ; '?'
0x1800d0131  jnz     short loc_1800D0147
0x1800d0133  cmp     [rsp+290h+var_22A], 5Ch ; '\'
0x1800d0139  jnz     short loc_1800D0147
0x1800d013b  mov     ebx, 100h
0x1800d0140  lea     rdx, [rsp+290h+var_228]
0x1800d0145  jmp     short loc_1800D014C
0x1800d0147  lea     rdx, [rsp+290h+szFilePath]; String2
0x1800d014c  mov     r8, rbx; MaxCount
0x1800d014f  mov     rcx, rsi; String1
0x1800d0152  call    _wcsnicmp_0
0x1800d0157  neg     eax
0x1800d0159  mov     eax, 0A1h
0x1800d015e  sbb     ecx, ecx
0x1800d0160  and     eax, ecx
0x1800d0162  jmp     short loc_1800D0171
0x1800d0164  call    cs:__imp_GetLastError
0x1800d016a  jmp     short loc_1800D0171
0x1800d016c  mov     eax, 0A1h
0x1800d0171  mov     rcx, [rbp+190h+var_20]
0x1800d0178  xor     rcx, rsp; StackCookie
0x1800d017b  call    __security_check_cookie
0x1800d0180  mov     rbx, [rsp+290h+arg_10]
0x1800d0188  add     rsp, 280h
0x1800d018f  pop     rdi
0x1800d0190  pop     rsi
0x1800d0191  pop     rbp
0x1800d0192  retn
```
