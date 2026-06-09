# CDpUrlAccessor::GetLastModified(_FILETIME *)

- ea: `0x180006c80`
- end: `0x180006db9`
- name: `?GetLastModified@CDpUrlAccessor@@UEAAJPEAU_FILETIME@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(CDpUrlAccessor *this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006c80`
- `0x18000ab60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180006d79`
- `KERNEL32!CloseHandle` at `0x180006d90`
- `KERNEL32!CloseHandle` at `0x180006d79`
- `KERNEL32!CloseHandle` at `0x180006d90`
- `KERNEL32!SystemTimeToFileTime` at `0x180006d4d`
- `KERNEL32!SystemTimeToFileTime` at `0x180006d4d`
- `KERNEL32!GetSystemTime` at `0x180006d3f`
- `KERNEL32!GetSystemTime` at `0x180006d3f`
- `KERNEL32!GetLastError` at `0x180006d57`
- `KERNEL32!GetLastError` at `0x180006d57`
- `KERNEL32!GetFileInformationByHandle` at `0x180006d19`
- `KERNEL32!GetFileInformationByHandle` at `0x180006d19`
- `KERNEL32!CreateFileW` at `0x180006ce7`
- `KERNEL32!CreateFileW` at `0x180006ce7`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::GetLastModified(CDpUrlAccessor *this, struct _FILETIME *a2)
{
  char *v4; // rcx
  char *FileW; // rbx
  signed int LastError; // eax
  unsigned int v7; // edi
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-58h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+50h] [rbp-48h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = (char *)this + 184;
  if ( *((_QWORD *)v4 + 3) >= 8u )
    v4 = *(char **)v4;
  FileW = (char *)CreateFileW((LPCWSTR)v4, 0x80100000, 7u, 0, 3u, 0x200080u, 0);
  if ( FileW != (char *)-1LL )
  {
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( GetFileInformationByHandle(FileW, &FileInformation) )
    {
      *a2 = FileInformation.ftLastWriteTime;
      if ( FileW )
        goto LABEL_16;
      return 0;
    }
  }
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( SystemTimeToFileTime(&SystemTime, a2) )
  {
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_16:
      CloseHandle(FileW);
    return 0;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return v7;
}

```

## disassembly

```asm
0x180006c80  mov     [rsp+arg_10], rbx
0x180006c85  push    rdi
0x180006c86  sub     rsp, 90h
0x180006c8d  mov     rax, cs:__security_cookie
0x180006c94  xor     rax, rsp
0x180006c97  mov     [rsp+98h+var_10], rax
0x180006c9f  mov     rdi, rdx
0x180006ca2  test    rdx, rdx
0x180006ca5  jnz     short loc_180006CB1
0x180006ca7  mov     eax, 80004003h
0x180006cac  jmp     loc_180006D98
0x180006cb1  add     rcx, 0B8h
0x180006cb8  cmp     qword ptr [rcx+18h], 8
0x180006cbd  jb      short loc_180006CC2
0x180006cbf  mov     rcx, [rcx]; lpFileName
0x180006cc2  xor     r9d, r9d; lpSecurityAttributes
0x180006cc5  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180006cce  mov     [rsp+98h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x180006cd6  mov     edx, 80100000h; dwDesiredAccess
0x180006cdb  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x180006ce3  lea     r8d, [r9+7]; dwShareMode
0x180006ce7  call    cs:__imp_CreateFileW
0x180006ced  mov     rbx, rax
0x180006cf0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006cf4  jz      short loc_180006D32
0x180006cf6  xorps   xmm0, xmm0
0x180006cf9  lea     rdx, [rsp+98h+FileInformation]; lpFileInformation
0x180006cfe  xor     eax, eax
0x180006d00  mov     rcx, rbx; hFile
0x180006d03  movups  xmmword ptr [rsp+98h+FileInformation.dwFileAttributes], xmm0
0x180006d08  mov     [rsp+98h+FileInformation.nFileIndexLow], eax
0x180006d0f  movups  xmmword ptr [rsp+98h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180006d14  movups  xmmword ptr [rsp+98h+FileInformation.nFileSizeHigh], xmm0
0x180006d19  call    cs:__imp_GetFileInformationByHandle
0x180006d1f  test    eax, eax
0x180006d21  jz      short loc_180006D32
0x180006d23  mov     rax, qword ptr [rsp+98h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x180006d28  mov     [rdi], rax
0x180006d2b  test    rbx, rbx
0x180006d2e  jz      short loc_180006D96
0x180006d30  jmp     short loc_180006D8D
0x180006d32  xorps   xmm0, xmm0
0x180006d35  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x180006d3a  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x180006d3f  call    cs:__imp_GetSystemTime
0x180006d45  mov     rdx, rdi; lpFileTime
0x180006d48  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x180006d4d  call    cs:__imp_SystemTimeToFileTime
0x180006d53  test    eax, eax
0x180006d55  jnz     short loc_180006D83
0x180006d57  call    cs:__imp_GetLastError
0x180006d5d  mov     edi, eax
0x180006d5f  test    eax, eax
0x180006d61  jle     short loc_180006D6C
0x180006d63  movzx   edi, ax
0x180006d66  or      edi, 80070000h
0x180006d6c  lea     rcx, [rbx-1]
0x180006d70  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180006d74  ja      short loc_180006D7F
0x180006d76  mov     rcx, rbx; hObject
0x180006d79  call    cs:__imp_CloseHandle
0x180006d7f  mov     eax, edi
0x180006d81  jmp     short loc_180006D98
0x180006d83  lea     rax, [rbx-1]
0x180006d87  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006d8b  ja      short loc_180006D96
0x180006d8d  mov     rcx, rbx; hObject
0x180006d90  call    cs:__imp_CloseHandle
0x180006d96  xor     eax, eax
0x180006d98  mov     rcx, [rsp+98h+var_10]
0x180006da0  xor     rcx, rsp; StackCookie
0x180006da3  call    __security_check_cookie
0x180006da8  mov     rbx, [rsp+98h+arg_10]
0x180006db0  add     rsp, 90h
0x180006db7  pop     rdi
0x180006db8  retn
```
