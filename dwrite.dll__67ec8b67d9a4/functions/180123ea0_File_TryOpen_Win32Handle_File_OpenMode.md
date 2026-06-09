# File::TryOpen(Win32Handle &&,File::OpenMode)

- ea: `0x180123ea0`
- end: `0x180123fda`
- name: `?TryOpen@File@@QEAAJ$$QEAVWin32Handle@@W4OpenMode@1@@Z`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180123b68`
- `0x1801f4bc8`

## callees

- `0x180123ea0`
- `0x180123fe0`
- `0x180212490`

## import_xrefs

- `kernel32!GetLastError` at `0x180123f90`
- `kernel32!GetLastError` at `0x180123f90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123fcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180123fcf`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180123fc4`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180123fc4`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180123eeb`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180123eeb`

## pseudocode

```c
__int64 __fastcall File::TryOpen(__int64 a1, void **a2, char a3)
{
  void *v6; // rcx
  int v7; // ecx
  unsigned __int64 v8; // rbx
  void *v9; // rax
  __int64 result; // rax
  DWORD LastError; // eax
  void *v12; // rcx
  FILETIME LastAccessTime; // [rsp+20h] [rbp-50h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+28h] [rbp-48h] BYREF

  if ( (a3 & 0x10) != 0 )
  {
    v12 = *a2;
    LastAccessTime.dwLowDateTime = -1;
    LastAccessTime.dwHighDateTime = -1;
    SetFileTime(v12, 0, &LastAccessTime, &LastAccessTime);
  }
  v6 = *a2;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle(v6, &FileInformation) )
  {
    v7 = FileInformation.dwFileAttributes & 0x10;
    *(_BYTE *)(a1 + 32) = v7 != 0;
    if ( ((a3 & 1) != 0 || v7)
      && (LastAccessTime = (FILETIME)__PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow),
          v8 = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow),
          __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow) <= 0x7FFFFFFFFFFFFFFFLL) )
    {
      if ( *(_QWORD *)a1 )
        CloseHandle(*(HANDLE *)a1);
      *(FILETIME *)(a1 + 16) = FileInformation.ftLastWriteTime;
      LastAccessTime = FileInformation.ftCreationTime;
      *(FILETIME *)(a1 + 24) = FileInformation.ftCreationTime;
      v9 = *a2;
      *a2 = 0;
      *(_QWORD *)a1 = v9;
      result = 0;
      *(_QWORD *)(a1 + 8) = v8;
    }
    else
    {
      return 2291683328LL;
    }
  }
  else
  {
    LastError = GetLastError();
    return IOException::MapFileOpenError(LastError);
  }
  return result;
}

```

## disassembly

```asm
0x180123ea0  mov     [rsp-18h+arg_10], rbx
0x180123ea5  push    rbp
0x180123ea6  push    rsi
0x180123ea7  push    rdi
0x180123ea8  mov     rbp, rsp
0x180123eab  sub     rsp, 70h
0x180123eaf  mov     rax, cs:__security_cookie
0x180123eb6  xor     rax, rsp
0x180123eb9  mov     [rbp+var_10], rax
0x180123ebd  mov     ebx, r8d
0x180123ec0  mov     rsi, rdx
0x180123ec3  mov     rdi, rcx
0x180123ec6  test    r8b, 10h
0x180123eca  jnz     loc_180123FAE
0x180123ed0  mov     rcx, [rsi]; hFile
0x180123ed3  lea     rdx, [rbp+FileInformation]; lpFileInformation
0x180123ed7  xorps   xmm0, xmm0
0x180123eda  xor     eax, eax
0x180123edc  movups  xmmword ptr [rbp+FileInformation.dwFileAttributes], xmm0
0x180123ee0  mov     [rbp+FileInformation.nFileIndexLow], eax
0x180123ee3  movups  xmmword ptr [rbp+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180123ee7  movups  xmmword ptr [rbp+FileInformation.nFileSizeHigh], xmm0
0x180123eeb  call    cs:__imp_GetFileInformationByHandle
0x180123ef1  test    eax, eax
0x180123ef3  jz      loc_180123F90
0x180123ef9  mov     ecx, [rbp+FileInformation.dwFileAttributes]
0x180123efc  and     ecx, 10h
0x180123eff  setnz   al
0x180123f02  mov     [rdi+20h], al
0x180123f05  test    bl, 1
0x180123f08  jz      loc_180123F9F
0x180123f0e  mov     eax, [rbp+FileInformation.nFileSizeHigh]
0x180123f11  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x180123f14  mov     eax, [rbp+FileInformation.nFileSizeLow]
0x180123f17  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x180123f1a  mov     rax, 7FFFFFFFFFFFFFFFh
0x180123f24  mov     rbx, qword ptr [rbp+LastAccessTime.dwLowDateTime]
0x180123f28  cmp     rbx, rax
0x180123f2b  ja      short loc_180123FA7
0x180123f2d  mov     rcx, [rdi]; hObject
0x180123f30  test    rcx, rcx
0x180123f33  jnz     loc_180123FCF
0x180123f39  mov     eax, [rbp+FileInformation.ftLastWriteTime.dwHighDateTime]
0x180123f3c  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x180123f3f  mov     eax, [rbp+FileInformation.ftLastWriteTime.dwLowDateTime]
0x180123f42  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x180123f45  mov     rax, qword ptr [rbp+LastAccessTime.dwLowDateTime]
0x180123f49  mov     [rdi+10h], rax
0x180123f4d  mov     eax, [rbp+FileInformation.ftCreationTime.dwHighDateTime]
0x180123f50  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x180123f53  mov     eax, [rbp+FileInformation.ftCreationTime.dwLowDateTime]
0x180123f56  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x180123f59  mov     rax, qword ptr [rbp+LastAccessTime.dwLowDateTime]
0x180123f5d  mov     [rdi+18h], rax
0x180123f61  mov     rax, [rsi]
0x180123f64  mov     qword ptr [rsi], 0
0x180123f6b  mov     [rdi], rax
0x180123f6e  xor     eax, eax
0x180123f70  mov     [rdi+8], rbx
0x180123f74  mov     rcx, [rbp+var_10]
0x180123f78  xor     rcx, rsp; StackCookie
0x180123f7b  call    __security_check_cookie
0x180123f80  mov     rbx, [rsp+70h+arg_10]
0x180123f88  add     rsp, 70h
0x180123f8c  pop     rdi
0x180123f8d  pop     rsi
0x180123f8e  pop     rbp
0x180123f8f  retn
0x180123f90  call    cs:__imp_GetLastError
0x180123f96  mov     ecx, eax; int
0x180123f98  call    ?MapFileOpenError@IOException@@SAHH@Z; IOException::MapFileOpenError(int)
0x180123f9d  jmp     short loc_180123F74
0x180123f9f  test    ecx, ecx
0x180123fa1  jnz     loc_180123F0E
0x180123fa7  mov     eax, 88985000h
0x180123fac  jmp     short loc_180123F74
0x180123fae  mov     rcx, [rsi]; hFile
0x180123fb1  lea     r9, [rbp+LastAccessTime]; lpLastWriteTime
0x180123fb5  or      eax, 0FFFFFFFFh
0x180123fb8  lea     r8, [rbp+LastAccessTime]; lpLastAccessTime
0x180123fbc  xor     edx, edx; lpCreationTime
0x180123fbe  mov     [rbp+LastAccessTime.dwLowDateTime], eax
0x180123fc1  mov     [rbp+LastAccessTime.dwHighDateTime], eax
0x180123fc4  call    cs:__imp_SetFileTime
0x180123fca  jmp     loc_180123ED0
0x180123fcf  call    cs:__imp_CloseHandle
0x180123fd5  jmp     loc_180123F39
```
