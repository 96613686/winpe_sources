# MyUnmapCreatedMappedFile

- ea: `0x180006fd0`
- end: `0x18000702c`
- name: `MyUnmapCreatedMappedFile`
- size: `92`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBaseAddress, LONG lDistanceToMove)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180003580`
- `0x1800036e0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006ffc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006ffc`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180007025`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180007005`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180007005`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006feb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006feb`

## pseudocode

```c
BOOL __fastcall MyUnmapCreatedMappedFile(HANDLE hFile, LPCVOID lpBaseAddress, LONG lDistanceToMove, const FILETIME *a4)
{
  UnmapViewOfFile(lpBaseAddress);
  SetFilePointer(hFile, lDistanceToMove, 0, 0);
  SetEndOfFile(hFile);
  return SetFileTime(hFile, 0, 0, a4);
}

```

## disassembly

```asm
0x180006fd0  mov     [rsp+arg_0], rbx
0x180006fd5  mov     [rsp+arg_8], rsi
0x180006fda  push    rdi
0x180006fdb  sub     rsp, 20h
0x180006fdf  mov     rsi, rcx
0x180006fe2  mov     rdi, r9
0x180006fe5  mov     rcx, rdx; lpBaseAddress
0x180006fe8  mov     ebx, r8d
0x180006feb  call    cs:__imp_UnmapViewOfFile
0x180006ff1  xor     r9d, r9d; dwMoveMethod
0x180006ff4  xor     r8d, r8d; lpDistanceToMoveHigh
0x180006ff7  mov     edx, ebx; lDistanceToMove
0x180006ff9  mov     rcx, rsi; hFile
0x180006ffc  call    cs:__imp_SetFilePointer
0x180007002  mov     rcx, rsi; hFile
0x180007005  call    cs:__imp_SetEndOfFile
0x18000700b  mov     r9, rdi
0x18000700e  xor     r8d, r8d
0x180007011  xor     edx, edx
0x180007013  mov     rcx, rsi
0x180007016  mov     rbx, [rsp+28h+arg_0]
0x18000701b  mov     rsi, [rsp+28h+arg_8]
0x180007020  add     rsp, 20h
0x180007024  pop     rdi
0x180007025  jmp     cs:__imp_SetFileTime
```
