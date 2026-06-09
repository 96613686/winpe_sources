# MsvPaswdInitializeLog

- ea: `0x180034d84`
- end: `0x180034ec6`
- name: `MsvPaswdInitializeLog`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180032230`

## callees

- `0x18002fb50`
- `0x180030844`
- `0x180034d84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180034e0d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180034e25`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180034e0d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180034e25`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180034df8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180034df8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034e55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180034e55`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180034e80`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180034e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034ddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e9a`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180034dd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180034dd1`

## pseudocode

```c
__int64 MsvPaswdInitializeLog()
{
  DWORD LastError; // ebx
  HANDLE FileW; // rax
  WCHAR Buffer[264]; // [rsp+40h] [rbp-438h] BYREF
  _BYTE v4[528]; // [rsp+250h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  memset_0(v4, 0, 0x20Au);
  if ( GetWindowsDirectoryW(Buffer, 0x105u) )
  {
    _o_wcscpy_s(v4, 261, Buffer);
    _o_wcscat_s(Buffer, 261, L"\\debug\\PASSWD.LOG");
    _o_wcscat_s(v4, 261, L"\\debug\\PASSWD.BAK");
    FileW = CreateFileW(Buffer, 0x40000000u, 3u, 0, 2u, 0x80u, 0);
    MsvPaswdLogFile = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      LastError = 0;
      if ( SetFilePointer(FileW, 0, 0, 2u) != -1 )
        return LastError;
      LastError = GetLastError();
      CloseHandle(MsvPaswdLogFile);
    }
    MsvPaswdLogFile = 0;
    return LastError;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180034d84  push    rbx
0x180034d86  sub     rsp, 470h
0x180034d8d  mov     rax, cs:__security_cookie
0x180034d94  xor     rax, rsp
0x180034d97  mov     [rsp+478h+var_18], rax
0x180034d9f  mov     ebx, 20Ah
0x180034da4  lea     rcx, [rsp+478h+Buffer]; void *
0x180034da9  mov     r8d, ebx; Size
0x180034dac  xor     edx, edx; Val
0x180034dae  call    memset_0
0x180034db3  mov     r8d, ebx; Size
0x180034db6  lea     rcx, [rsp+478h+var_228]; void *
0x180034dbe  xor     edx, edx; Val
0x180034dc0  call    memset_0
0x180034dc5  mov     ebx, 105h
0x180034dca  lea     rcx, [rsp+478h+Buffer]; lpBuffer
0x180034dcf  mov     edx, ebx; uSize
0x180034dd1  call    cs:__imp_GetWindowsDirectoryW
0x180034dd7  test    eax, eax
0x180034dd9  jnz     short loc_180034DE8
0x180034ddb  call    cs:__imp_GetLastError
0x180034de1  mov     ebx, eax
0x180034de3  jmp     loc_180034EAB
0x180034de8  lea     r8, [rsp+478h+Buffer]
0x180034ded  mov     rdx, rbx
0x180034df0  lea     rcx, [rsp+478h+var_228]
0x180034df8  call    cs:__imp__o_wcscpy_s
0x180034dfe  lea     r8, aDebugPasswdLog; "\\debug\\PASSWD.LOG"
0x180034e05  mov     rdx, rbx
0x180034e08  lea     rcx, [rsp+478h+Buffer]
0x180034e0d  call    cs:__imp__o_wcscat_s
0x180034e13  lea     r8, aDebugPasswdBak; "\\debug\\PASSWD.BAK"
0x180034e1a  mov     rdx, rbx
0x180034e1d  lea     rcx, [rsp+478h+var_228]
0x180034e25  call    cs:__imp__o_wcscat_s
0x180034e2b  xor     r9d, r9d; lpSecurityAttributes
0x180034e2e  mov     [rsp+478h+hTemplateFile], 0; hTemplateFile
0x180034e37  mov     [rsp+478h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180034e3f  lea     rcx, [rsp+478h+Buffer]; lpFileName
0x180034e44  mov     edx, 40000000h; dwDesiredAccess
0x180034e49  mov     [rsp+478h+dwCreationDisposition], 2; dwCreationDisposition
0x180034e51  lea     r8d, [r9+3]; dwShareMode
0x180034e55  call    cs:__imp_CreateFileW
0x180034e5b  mov     cs:MsvPaswdLogFile, rax
0x180034e62  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034e66  jnz     short loc_180034E72
0x180034e68  call    cs:__imp_GetLastError
0x180034e6e  mov     ebx, eax
0x180034e70  jmp     short loc_180034EA0
0x180034e72  xor     ebx, ebx
0x180034e74  xor     r8d, r8d; lpDistanceToMoveHigh
0x180034e77  xor     edx, edx; lDistanceToMove
0x180034e79  mov     rcx, rax; hFile
0x180034e7c  lea     r9d, [rbx+2]; dwMoveMethod
0x180034e80  call    cs:__imp_SetFilePointer
0x180034e86  cmp     eax, 0FFFFFFFFh
0x180034e89  jnz     short loc_180034EAB
0x180034e8b  call    cs:__imp_GetLastError
0x180034e91  mov     rcx, cs:MsvPaswdLogFile; hObject
0x180034e98  mov     ebx, eax
0x180034e9a  call    cs:__imp_CloseHandle
0x180034ea0  mov     cs:MsvPaswdLogFile, 0
0x180034eab  mov     eax, ebx
0x180034ead  mov     rcx, [rsp+478h+var_18]
0x180034eb5  xor     rcx, rsp; StackCookie
0x180034eb8  call    __security_check_cookie
0x180034ebd  add     rsp, 470h
0x180034ec4  pop     rbx
0x180034ec5  retn
```
