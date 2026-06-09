# UpdateLastAccessTime(ushort const *)

- ea: `0x180005500`
- end: `0x180005643`
- name: `?UpdateLastAccessTime@@YAXPEBG@Z`
- size: `323`
- prototype: `void __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1800035b0`
- `0x1800051cc`
- `0x18001a5fc`

## callees

- `0x180005500`
- `0x180005650`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000562f`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000562f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800055a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800055a9`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800055f3`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800055f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005638`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000556b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000556b`
- `api-ms-win-core-sysinfo-l1-1-0!SystemTimeToFileTime` at `0x18000557b`
- `api-ms-win-core-sysinfo-l1-1-0!SystemTimeToFileTime` at `0x18000557b`

## string_xrefs

- `0x1800055ec`: `DBGHELP_DISABLEACCESSTIMEUPDATE`

## pseudocode

```c
void __fastcall UpdateLastAccessTime(LPCWSTR lpFileName)
{
  __int16 v2; // cx
  HANDLE FileW; // rax
  void *v4; // rbx
  DWORD EnvironmentVariableW; // eax
  _FILETIME FileTime; // [rsp+40h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-20h] BYREF

  if ( lpFileName && *lpFileName && !SymGetExtendedOption(SYMOPT_EX_DISABLEACCESSTIMEUPDATE) )
  {
    v2 = word_1802B2EFC;
    if ( word_1802B2EFC == -1 )
    {
      word_1802B2EFC = 0;
      FileTime.dwLowDateTime = 0;
      EnvironmentVariableW = GetEnvironmentVariableW(L"DBGHELP_DISABLEACCESSTIMEUPDATE", (LPWSTR)&FileTime, 2u);
      v2 = 1;
      if ( EnvironmentVariableW == 1 && LOWORD(FileTime.dwLowDateTime) == 49 )
        word_1802B2EFC = 1;
      else
        v2 = word_1802B2EFC;
    }
    if ( !v2 )
    {
      FileTime = 0;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        FileW = CreateFileW(lpFileName, 0x100u, 7u, 0, 3u, 0x80u, 0);
        v4 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          SetFileTime(FileW, 0, &FileTime, 0);
          CloseHandle(v4);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180005500  test    rcx, rcx
0x180005503  jz      locret_1800055D5
0x180005509  mov     [rsp+arg_8], rbx
0x18000550e  mov     [rsp+arg_10], rsi
0x180005513  push    rdi
0x180005514  sub     rsp, 60h
0x180005518  mov     rax, cs:__security_cookie
0x18000551f  xor     rax, rsp
0x180005522  mov     [rsp+68h+var_10], rax
0x180005527  xor     edi, edi
0x180005529  mov     rbx, rcx
0x18000552c  cmp     [rcx], di
0x18000552f  jz      loc_1800055B7
0x180005535  xor     ecx, ecx; option
0x180005537  call    SymGetExtendedOption
0x18000553c  test    eax, eax
0x18000553e  jnz     short loc_1800055B7
0x180005540  movzx   ecx, cs:word_1802B2EFC
0x180005547  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000554b  cmp     cx, si
0x18000554e  jz      loc_1800055D6
0x180005554  test    cx, cx
0x180005557  jnz     short loc_1800055B7
0x180005559  xorps   xmm0, xmm0
0x18000555c  mov     qword ptr [rsp+68h+FileTime.dwLowDateTime], rdi
0x180005561  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x180005566  movups  xmmword ptr [rsp+68h+SystemTime.wYear], xmm0
0x18000556b  call    cs:__imp_GetSystemTime
0x180005571  lea     rdx, [rsp+68h+FileTime]; lpFileTime
0x180005576  lea     rcx, [rsp+68h+SystemTime]; lpSystemTime
0x18000557b  call    cs:__imp_SystemTimeToFileTime
0x180005581  test    eax, eax
0x180005583  jz      short loc_1800055B7
0x180005585  xor     r9d, r9d; lpSecurityAttributes
0x180005588  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x18000558d  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180005595  mov     edx, 100h; dwDesiredAccess
0x18000559a  mov     rcx, rbx; lpFileName
0x18000559d  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800055a5  lea     r8d, [r9+7]; dwShareMode
0x1800055a9  call    cs:__imp_CreateFileW
0x1800055af  mov     rbx, rax
0x1800055b2  cmp     rax, rsi
0x1800055b5  jnz     short loc_180005622
0x1800055b7  mov     rcx, [rsp+68h+var_10]
0x1800055bc  xor     rcx, rsp; StackCookie
0x1800055bf  call    __security_check_cookie
0x1800055c4  lea     r11, [rsp+68h+var_8]
0x1800055c9  mov     rbx, [r11+18h]
0x1800055cd  mov     rsi, [r11+20h]
0x1800055d1  mov     rsp, r11
0x1800055d4  pop     rdi
0x1800055d5  retn
0x1800055d6  mov     r8d, 2; nSize
0x1800055dc  mov     cs:word_1802B2EFC, di
0x1800055e3  lea     rdx, [rsp+68h+FileTime]; lpBuffer
0x1800055e8  mov     [rsp+68h+FileTime.dwLowDateTime], edi
0x1800055ec  lea     rcx, Name; "DBGHELP_DISABLEACCESSTIMEUPDATE"
0x1800055f3  call    cs:__imp_GetEnvironmentVariableW
0x1800055f9  mov     ecx, 1
0x1800055fe  cmp     eax, ecx
0x180005600  jnz     short loc_180005616
0x180005602  cmp     word ptr [rsp+68h+FileTime.dwLowDateTime], 31h ; '1'
0x180005608  jnz     short loc_180005616
0x18000560a  mov     cs:word_1802B2EFC, cx
0x180005611  jmp     loc_180005554
0x180005616  movzx   ecx, cs:word_1802B2EFC
0x18000561d  jmp     loc_180005554
0x180005622  xor     r9d, r9d; lpLastWriteTime
0x180005625  lea     r8, [rsp+68h+FileTime]; lpLastAccessTime
0x18000562a  xor     edx, edx; lpCreationTime
0x18000562c  mov     rcx, rbx; hFile
0x18000562f  call    cs:__imp_SetFileTime
0x180005635  mov     rcx, rbx; hObject
0x180005638  call    cs:__imp_CloseHandle
0x18000563e  jmp     loc_1800055B7
```
