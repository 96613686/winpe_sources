# CFveApiBase::WriteBytesToFile(ushort const *,void *,ulong)

- ea: `0x18007b0f8`
- end: `0x18007b1ef`
- name: `?WriteBytesToFile@CFveApiBase@@SAJPEBGPEAXK@Z`
- size: `247`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800779a0`

## callees

- `0x180005410`
- `0x18007b0f8`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b1c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123b1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b1c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123b1a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007b19c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007b19c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007b140`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007b140`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18007b131`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18007b131`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b16f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b16f`

## pseudocode

```c
__int64 __fastcall CFveApiBase::WriteBytesToFile(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  unsigned int LastHresultError; // ebx
  HANDLE FileW; // rax
  void *v8; // rdi
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-30h] BYREF

  LastHresultError = 0;
  NumberOfBytesWritten = 0;
  SetFileAttributesW(lpFileName, 0x80u);
  DeleteFileW(lpFileName);
  FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x80000007, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL
    || !WriteFile(FileW, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0)
    || nNumberOfBytesToWrite != NumberOfBytesWritten )
  {
    LastHresultError = GetLastHresultError();
  }
  if ( v8 != (void *)-1LL )
    CloseHandle(v8);
  return LastHresultError;
}

```

## disassembly

```asm
0x18007b0f8  mov     [rsp+arg_18], rbx
0x18007b0fd  push    rsi
0x18007b0fe  push    rdi
0x18007b0ff  push    r14
0x18007b101  sub     rsp, 60h
0x18007b105  mov     rax, cs:__security_cookie
0x18007b10c  xor     rax, rsp
0x18007b10f  mov     [rsp+78h+var_28], rax
0x18007b114  mov     esi, r8d
0x18007b117  mov     r14, rdx
0x18007b11a  mov     rdi, rcx
0x18007b11d  xor     ebx, ebx
0x18007b11f  mov     [rsp+78h+var_38], 0FFFFFFFFFFFFFFFFh
0x18007b128  mov     [rsp+78h+NumberOfBytesWritten], ebx
0x18007b12c  mov     edx, 80h; dwFileAttributes
0x18007b131  call    cs:__imp_SetFileAttributesW
0x18007b138  nop     dword ptr [rax+rax+00h]
0x18007b13d  mov     rcx, rdi; lpFileName
0x18007b140  call    cs:__imp_DeleteFileW
0x18007b147  nop     dword ptr [rax+rax+00h]
0x18007b14c  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18007b151  mov     [rsp+78h+dwFlagsAndAttributes], 80000007h; dwFlagsAndAttributes
0x18007b159  mov     [rsp+78h+dwCreationDisposition], 2; dwCreationDisposition
0x18007b161  xor     r9d, r9d; lpSecurityAttributes
0x18007b164  xor     r8d, r8d; dwShareMode
0x18007b167  mov     edx, 0C0000000h; dwDesiredAccess
0x18007b16c  mov     rcx, rdi; lpFileName
0x18007b16f  call    cs:__imp_CreateFileW
0x18007b176  nop     dword ptr [rax+rax+00h]
0x18007b17b  mov     rdi, rax
0x18007b17e  mov     [rsp+78h+var_38], rax
0x18007b183  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007b187  jz      short loc_18007B1B2
0x18007b189  mov     qword ptr [rsp+78h+dwCreationDisposition], rbx; lpOverlapped
0x18007b18e  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007b193  mov     r8d, esi; nNumberOfBytesToWrite
0x18007b196  mov     rdx, r14; lpBuffer
0x18007b199  mov     rcx, rax; hFile
0x18007b19c  call    cs:__imp_WriteFile
0x18007b1a3  nop     dword ptr [rax+rax+00h]
0x18007b1a8  test    eax, eax
0x18007b1aa  jz      short loc_18007B1B2
0x18007b1ac  cmp     esi, [rsp+78h+NumberOfBytesWritten]
0x18007b1b0  jz      short loc_18007B1B9
0x18007b1b2  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18007b1b7  mov     ebx, eax
0x18007b1b9  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18007b1bd  jz      short loc_18007B1CE
0x18007b1bf  mov     rcx, rdi; hObject
0x18007b1c2  call    cs:__imp_CloseHandle
0x18007b1c9  nop     dword ptr [rax+rax+00h]
0x18007b1ce  mov     eax, ebx
0x18007b1d0  mov     rcx, [rsp+78h+var_28]
0x18007b1d5  xor     rcx, rsp; StackCookie
0x18007b1d8  call    __security_check_cookie
0x18007b1dd  mov     rbx, [rsp+78h+arg_18]
0x18007b1e5  add     rsp, 60h
0x18007b1e9  pop     r14
0x18007b1eb  pop     rdi
0x18007b1ec  pop     rsi
0x18007b1ed  retn
0x180123b07  push    rbp
0x180123b09  sub     rsp, 40h
0x180123b0d  mov     rbp, rdx
0x180123b10  mov     rcx, [rbp+40h]; hObject
0x180123b14  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180123b18  jz      short loc_180123B27
0x180123b1a  call    cs:__imp_CloseHandle
0x180123b21  nop     dword ptr [rax+rax+00h]
0x180123b26  nop
0x180123b27  add     rsp, 40h
0x180123b2b  pop     rbp
0x180123b2c  retn
```
