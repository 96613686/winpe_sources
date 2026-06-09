# WriteByteArrayToFile(ushort const *,uchar const *,ulong)

- ea: `0x180045194`
- end: `0x18004524e`
- name: `?WriteByteArrayToFile@@YAJPEBGPEBEK@Z`
- size: `186`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18004493c`

## callees

- `0x18000ac48`
- `0x180045164`
- `0x180045194`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004522b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004522b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800451d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800451d1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045211`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180045211`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004523d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004523d`

## pseudocode

```c
__int64 __fastcall WriteByteArrayToFile(LPCWSTR lpFileName, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  HANDLE FileW; // rax
  int Error; // ebx
  HANDLE hFile; // [rsp+40h] [rbp-38h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+98h] [rbp+20h] BYREF

  hFile = 0;
  FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  Error = ResultFromWin32Handle(FileW, &hFile);
  if ( Error >= 0 )
  {
    NumberOfBytesWritten = 0;
    if ( WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    CloseHandle(hFile);
    if ( Error < 0 )
      DeleteFileW(lpFileName);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180045194  mov     rax, rsp
0x180045197  push    rbx
0x180045198  push    rbp
0x180045199  push    rsi
0x18004519a  push    rdi
0x18004519b  sub     rsp, 58h
0x18004519f  mov     qword ptr [rax-48h], 0
0x1800451a7  mov     esi, r8d
0x1800451aa  mov     rbp, rdx
0x1800451ad  mov     dword ptr [rax-50h], 80h
0x1800451b4  xor     r8d, r8d; dwShareMode
0x1800451b7  mov     dword ptr [rax-58h], 2
0x1800451be  mov     edx, 40000000h; dwDesiredAccess
0x1800451c3  mov     qword ptr [rax-38h], 0
0x1800451cb  xor     r9d, r9d; lpSecurityAttributes
0x1800451ce  mov     rdi, rcx
0x1800451d1  call    cs:__imp_CreateFileW
0x1800451d7  mov     rcx, rax; void *
0x1800451da  lea     rdx, [rsp+78h+hFile]; void **
0x1800451df  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x1800451e4  mov     ebx, eax
0x1800451e6  test    eax, eax
0x1800451e8  js      short loc_180045243
0x1800451ea  mov     rcx, [rsp+78h+hFile]; hFile
0x1800451ef  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800451f7  mov     r8d, esi; nNumberOfBytesToWrite
0x1800451fa  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180045205  mov     rdx, rbp; lpBuffer
0x180045208  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180045211  call    cs:__imp_WriteFile
0x180045217  test    eax, eax
0x180045219  jz      short loc_18004521F
0x18004521b  xor     ebx, ebx
0x18004521d  jmp     short loc_180045226
0x18004521f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045224  mov     ebx, eax
0x180045226  mov     rcx, [rsp+78h+hFile]; hObject
0x18004522b  call    cs:__imp_CloseHandle
0x180045231  mov     eax, ebx
0x180045233  shr     eax, 1Fh
0x180045236  test    al, al
0x180045238  jz      short loc_180045243
0x18004523a  mov     rcx, rdi; lpFileName
0x18004523d  call    cs:__imp_DeleteFileW
0x180045243  mov     eax, ebx
0x180045245  add     rsp, 58h
0x180045249  pop     rdi
0x18004524a  pop     rsi
0x18004524b  pop     rbp
0x18004524c  pop     rbx
0x18004524d  retn
```
