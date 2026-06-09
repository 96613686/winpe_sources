# TraceVerifyFolderIsNotALink

- ea: `0x1800abd04`
- end: `0x1800abe1e`
- name: `TraceVerifyFolderIsNotALink`
- size: `282`
- prototype: `__int64 __fastcall(HANDLE hFile, wchar_t *String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1800ab0ac`

## callees

- `0x1800abd04`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800abde4`
- `msvcrt!_wcsnicmp` at `0x1800abde4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abd96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abd96`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800abd86`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800abd86`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800abd4f`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800abd4f`

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
  return _wcsnicmp(String1, v7, v5) != 0 ? 0xA1 : 0;
}

```

## disassembly

```asm
0x1800abd04  mov     [rsp-8+arg_10], rbx
0x1800abd09  push    rbp
0x1800abd0a  push    rsi
0x1800abd0b  push    rdi
0x1800abd0c  lea     rbp, [rsp-180h]
0x1800abd14  sub     rsp, 280h
0x1800abd1b  mov     rax, cs:__security_cookie
0x1800abd22  xor     rax, rsp
0x1800abd25  mov     [rbp+190h+var_20], rax
0x1800abd2c  xorps   xmm0, xmm0
0x1800abd2f  mov     rsi, rdx
0x1800abd32  xor     eax, eax
0x1800abd34  lea     rdx, [rsp+290h+FileInformation]; lpFileInformation
0x1800abd39  movups  xmmword ptr [rsp+290h+FileInformation.dwFileAttributes], xmm0
0x1800abd3e  mov     [rsp+290h+FileInformation.nFileIndexLow], eax
0x1800abd42  mov     rdi, rcx
0x1800abd45  movups  xmmword ptr [rsp+290h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800abd4a  movups  xmmword ptr [rsp+290h+FileInformation.nFileSizeHigh], xmm0
0x1800abd4f  call    cs:__imp_GetFileInformationByHandle
0x1800abd56  nop     dword ptr [rax+rax+00h]
0x1800abd5b  test    eax, eax
0x1800abd5d  jnz     short loc_1800ABD69
0x1800abd5f  mov     eax, 0A1h
0x1800abd64  jmp     loc_1800ABDFB
0x1800abd69  test    [rsp+290h+FileInformation.dwFileAttributes], 400h
0x1800abd71  jnz     short loc_1800ABD5F
0x1800abd73  mov     ebx, 104h
0x1800abd78  lea     rdx, [rsp+290h+szFilePath]; lpszFilePath
0x1800abd7d  mov     r8d, ebx; cchFilePath
0x1800abd80  xor     r9d, r9d; dwFlags
0x1800abd83  mov     rcx, rdi; hFile
0x1800abd86  call    cs:__imp_GetFinalPathNameByHandleW
0x1800abd8d  nop     dword ptr [rax+rax+00h]
0x1800abd92  test    eax, eax
0x1800abd94  jnz     short loc_1800ABDA4
0x1800abd96  call    cs:__imp_GetLastError
0x1800abd9d  nop     dword ptr [rax+rax+00h]
0x1800abda2  jmp     short loc_1800ABDFB
0x1800abda4  cmp     eax, ebx
0x1800abda6  ja      short loc_1800ABD5F
0x1800abda8  cmp     eax, 4
0x1800abdab  jb      short loc_1800ABDD9
0x1800abdad  cmp     [rsp+290h+szFilePath], 5Ch ; '\'
0x1800abdb3  jnz     short loc_1800ABDD9
0x1800abdb5  cmp     [rsp+290h+var_22E], 5Ch ; '\'
0x1800abdbb  jnz     short loc_1800ABDD9
0x1800abdbd  cmp     [rsp+290h+var_22C], 3Fh ; '?'
0x1800abdc3  jnz     short loc_1800ABDD9
0x1800abdc5  cmp     [rsp+290h+var_22A], 5Ch ; '\'
0x1800abdcb  jnz     short loc_1800ABDD9
0x1800abdcd  mov     ebx, 100h
0x1800abdd2  lea     rdx, [rsp+290h+var_228]
0x1800abdd7  jmp     short loc_1800ABDDE
0x1800abdd9  lea     rdx, [rsp+290h+szFilePath]; String2
0x1800abdde  mov     r8, rbx; MaxCount
0x1800abde1  mov     rcx, rsi; String1
0x1800abde4  call    cs:__imp__wcsnicmp
0x1800abdeb  nop     dword ptr [rax+rax+00h]
0x1800abdf0  neg     eax
0x1800abdf2  mov     eax, 0A1h
0x1800abdf7  sbb     ecx, ecx
0x1800abdf9  and     eax, ecx
0x1800abdfb  mov     rcx, [rbp+190h+var_20]
0x1800abe02  xor     rcx, rsp; StackCookie
0x1800abe05  call    __security_check_cookie
0x1800abe0a  mov     rbx, [rsp+290h+arg_10]
0x1800abe12  add     rsp, 280h
0x1800abe19  pop     rdi
0x1800abe1a  pop     rsi
0x1800abe1b  pop     rbp
0x1800abe1c  retn
```
