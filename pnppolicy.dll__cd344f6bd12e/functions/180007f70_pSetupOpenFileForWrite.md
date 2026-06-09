# pSetupOpenFileForWrite

- ea: `0x180007f70`
- end: `0x180007fe7`
- name: `pSetupOpenFileForWrite`
- size: `119`
- prototype: `__int64 __fastcall(const WCHAR *, int, __int64, __int64, HANDLE *, LONG *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x1800052c4`
- `0x180007ff0`

## callees

- `0x180007968`
- `0x180007f70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fcd`
- `KERNEL32!SetFilePointer` at `0x180007fb7`
- `KERNEL32!SetFilePointer` at `0x180007fb7`
- `KERNEL32!GetFileSize` at `0x180007f9f`
- `KERNEL32!GetFileSize` at `0x180007f9f`

## pseudocode

```c
__int64 __fastcall pSetupOpenFileForWrite(const WCHAR *a1, int a2, __int64 a3, __int64 a4, HANDLE *a5, LONG *a6)
{
  DWORD File; // edi
  LONG FileSize; // eax
  int v9; // [rsp+20h] [rbp-28h]

  File = pSpUtilsCreateFile(a1, a2 | 0xC0000000, a3, a4, v9, a4, a5);
  if ( !File )
  {
    FileSize = GetFileSize(*a5, 0);
    *a6 = FileSize;
    if ( SetFilePointer(*a5, FileSize, 0, 0) == -1 )
    {
      File = GetLastError();
      CloseHandle(*a5);
      *a5 = (HANDLE)-1LL;
    }
  }
  return File;
}

```

## disassembly

```asm
0x180007f70  mov     [rsp+arg_0], rbx
0x180007f75  push    rdi
0x180007f76  sub     rsp, 40h
0x180007f7a  mov     rbx, [rsp+48h+arg_20]
0x180007f7f  or      edx, 0C0000000h; dwDesiredAccess
0x180007f85  mov     [rsp+48h+var_18], rbx; __int64
0x180007f8a  mov     [rsp+48h+var_20], r9d; int
0x180007f8f  call    _pSpUtilsCreateFile
0x180007f94  mov     edi, eax
0x180007f96  test    eax, eax
0x180007f98  jnz     short loc_180007FDA
0x180007f9a  mov     rcx, [rbx]; hFile
0x180007f9d  xor     edx, edx; lpFileSizeHigh
0x180007f9f  call    cs:__imp_GetFileSize
0x180007fa5  mov     rcx, [rsp+48h+arg_28]
0x180007faa  xor     r9d, r9d; dwMoveMethod
0x180007fad  xor     r8d, r8d; lpDistanceToMoveHigh
0x180007fb0  mov     edx, eax; lDistanceToMove
0x180007fb2  mov     [rcx], eax
0x180007fb4  mov     rcx, [rbx]; hFile
0x180007fb7  call    cs:__imp_SetFilePointer
0x180007fbd  cmp     eax, 0FFFFFFFFh
0x180007fc0  jnz     short loc_180007FDA
0x180007fc2  call    cs:__imp_GetLastError
0x180007fc8  mov     rcx, [rbx]; hObject
0x180007fcb  mov     edi, eax
0x180007fcd  call    cs:__imp_CloseHandle
0x180007fd3  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180007fda  mov     rbx, [rsp+48h+arg_0]
0x180007fdf  mov     eax, edi
0x180007fe1  add     rsp, 40h
0x180007fe5  pop     rdi
0x180007fe6  retn
```
