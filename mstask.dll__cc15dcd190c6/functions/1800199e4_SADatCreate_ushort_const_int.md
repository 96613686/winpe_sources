# SADatCreate(ushort const *,int)

- ea: `0x1800199e4`
- end: `0x180019ba7`
- name: `?SADatCreate@@YAJPEBGH@Z`
- size: `451`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a7e0`

## callees

- `0x180019950`
- `0x1800199e4`
- `0x180019d4c`
- `0x180019dac`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b50`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180019a3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180019a3a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180019b46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180019b46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019aed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019aed`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180019abb`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180019abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019b7b`

## pseudocode

```c
signed int __fastcall SADatCreate(const unsigned __int16 *a1, int a2)
{
  signed int result; // eax
  bool v5; // bl
  int v6; // eax
  char v7; // r8
  unsigned __int64 v8; // r8
  HANDLE FileW; // rax
  void *v10; // rdi
  signed int v11; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  int Buffer; // [rsp+170h] [rbp+70h] BYREF
  char v16; // [rsp+174h] [rbp+74h]
  char v17; // [rsp+175h] [rbp+75h]
  WCHAR FileName[264]; // [rsp+180h] [rbp+80h] BYREF

  Buffer = 6;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( !GetVersionExW(&VersionInformation) )
    goto LABEL_2;
  v16 = (VersionInformation.dwPlatformId == 2) + 1;
  v5 = a2 != 0;
  v6 = ResumeTimersSupported();
  v7 = v5 | 2;
  if ( !v6 )
    v7 = v5;
  v17 = v7;
  memset_0(FileName, 0, 0x20Au);
  SADatPath(a1, FileName, v8);
  SetFileAttributesW(FileName, 2u);
  FileW = CreateFileW(FileName, 0xC0040000, 3u, 0, 2u, 2u, 0);
  v10 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v11 = SADatSetSecurity(FileW);
    if ( v11 )
    {
      CloseHandle(v10);
      if ( v11 > 0 )
        return (unsigned __int16)v11 | 0x80070000;
    }
    else
    {
      NumberOfBytesWritten = 0;
      if ( WriteFile(v10, &Buffer, 6u, &NumberOfBytesWritten, 0) )
      {
        v11 = NumberOfBytesWritten != 6 ? 0x8000FFFF : 0;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseHandle(v10);
    }
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x1800199e4  mov     [rsp-8+arg_8], rbx
0x1800199e9  mov     [rsp-8+arg_10], rdi
0x1800199ee  push    rbp
0x1800199ef  lea     rbp, [rsp-2A0h]
0x1800199f7  sub     rsp, 3A0h
0x1800199fe  mov     rax, cs:__security_cookie
0x180019a05  xor     rax, rsp
0x180019a08  mov     [rbp+2A0h+var_10], rax
0x180019a0f  mov     ebx, edx
0x180019a11  mov     [rbp+2A0h+Buffer], 6
0x180019a18  mov     rdi, rcx
0x180019a1b  xor     edx, edx; Val
0x180019a1d  lea     rcx, [rsp+3A0h+VersionInformation.dwMajorVersion]; void *
0x180019a22  mov     r8d, 110h; Size
0x180019a28  call    memset_0
0x180019a2d  lea     rcx, [rsp+3A0h+VersionInformation]; lpVersionInformation
0x180019a32  mov     [rsp+3A0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180019a3a  call    cs:__imp_GetVersionExW
0x180019a40  test    eax, eax
0x180019a42  jnz     short loc_180019A5F
0x180019a44  call    cs:__imp_GetLastError
0x180019a4a  test    eax, eax
0x180019a4c  jle     loc_180019B83
0x180019a52  movzx   eax, ax
0x180019a55  or      eax, 80070000h
0x180019a5a  jmp     loc_180019B83
0x180019a5f  cmp     [rsp+3A0h+VersionInformation.dwPlatformId], 2
0x180019a64  setz    al
0x180019a67  inc     al
0x180019a69  test    ebx, ebx
0x180019a6b  mov     [rbp+2A0h+var_22C], al
0x180019a6e  setnz   bl
0x180019a71  call    ?ResumeTimersSupported@@YAHXZ; ResumeTimersSupported(void)
0x180019a76  mov     dl, bl
0x180019a78  lea     rcx, [rbp+2A0h+FileName]; void *
0x180019a7f  or      dl, 2
0x180019a82  movzx   r8d, dl
0x180019a86  test    eax, eax
0x180019a88  movzx   edx, bl
0x180019a8b  cmovz   r8d, edx
0x180019a8f  xor     edx, edx; Val
0x180019a91  mov     [rbp+2A0h+var_22B], r8b
0x180019a95  mov     r8d, 20Ah; Size
0x180019a9b  call    memset_0
0x180019aa0  lea     rdx, [rbp+2A0h+FileName]; unsigned __int16 *
0x180019aa7  mov     rcx, rdi; unsigned __int16 *
0x180019aaa  call    ?SADatPath@@YAXPEBGPEAG_K@Z; SADatPath(ushort const *,ushort *,unsigned __int64)
0x180019aaf  mov     edx, 2; dwFileAttributes
0x180019ab4  lea     rcx, [rbp+2A0h+FileName]; lpFileName
0x180019abb  call    cs:__imp_SetFileAttributesW
0x180019ac1  xor     r9d, r9d; lpSecurityAttributes
0x180019ac4  mov     [rsp+3A0h+hTemplateFile], 0; hTemplateFile
0x180019acd  mov     [rsp+3A0h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x180019ad5  lea     rcx, [rbp+2A0h+FileName]; lpFileName
0x180019adc  mov     edx, 0C0040000h; dwDesiredAccess
0x180019ae1  mov     [rsp+3A0h+dwCreationDisposition], 2; dwCreationDisposition
0x180019ae9  lea     r8d, [r9+3]; dwShareMode
0x180019aed  call    cs:__imp_CreateFileW
0x180019af3  mov     rdi, rax
0x180019af6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180019afa  jz      loc_180019A44
0x180019b00  mov     rcx, rax; handle
0x180019b03  call    ?SADatSetSecurity@@YAKPEAX@Z; SADatSetSecurity(void *)
0x180019b08  mov     ebx, eax
0x180019b0a  mov     rcx, rdi; hFile
0x180019b0d  test    eax, eax
0x180019b0f  jz      short loc_180019B26
0x180019b11  call    cs:__imp_CloseHandle
0x180019b17  test    ebx, ebx
0x180019b19  jle     short loc_180019B81
0x180019b1b  movzx   ebx, bx
0x180019b1e  or      ebx, 80070000h
0x180019b24  jmp     short loc_180019B81
0x180019b26  lea     r9, [rsp+3A0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180019b2b  mov     [rsp+3A0h+NumberOfBytesWritten], 0
0x180019b33  mov     r8d, 6; nNumberOfBytesToWrite
0x180019b39  mov     qword ptr [rsp+3A0h+dwCreationDisposition], 0; lpOverlapped
0x180019b42  lea     rdx, [rbp+2A0h+Buffer]; lpBuffer
0x180019b46  call    cs:__imp_WriteFile
0x180019b4c  test    eax, eax
0x180019b4e  jnz     short loc_180019B67
0x180019b50  call    cs:__imp_GetLastError
0x180019b56  mov     ebx, eax
0x180019b58  test    eax, eax
0x180019b5a  jle     short loc_180019B78
0x180019b5c  movzx   ebx, ax
0x180019b5f  or      ebx, 80070000h
0x180019b65  jmp     short loc_180019B78
0x180019b67  mov     eax, [rsp+3A0h+NumberOfBytesWritten]
0x180019b6b  sub     eax, 6
0x180019b6e  neg     eax
0x180019b70  sbb     ebx, ebx
0x180019b72  and     ebx, 8000FFFFh
0x180019b78  mov     rcx, rdi; hObject
0x180019b7b  call    cs:__imp_CloseHandle
0x180019b81  mov     eax, ebx
0x180019b83  mov     rcx, [rbp+2A0h+var_10]
0x180019b8a  xor     rcx, rsp; StackCookie
0x180019b8d  call    __security_check_cookie
0x180019b92  lea     r11, [rsp+3A0h+var_s0]
0x180019b9a  mov     rbx, [r11+18h]
0x180019b9e  mov     rdi, [r11+20h]
0x180019ba2  mov     rsp, r11
0x180019ba5  pop     rbp
0x180019ba6  retn
```
