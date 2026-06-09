# MapMUIFile

- ea: `0x180022b10`
- end: `0x180022bf4`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180022c3c`
- `0x180022d54`

## callees

- `0x180022b10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022bdf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022bbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022bbc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180022b83`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180022b83`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022bb0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022bb0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022b53`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180022b53`

## pseudocode

```c
HMODULE __fastcall MapMUIFile(const WCHAR *a1, int a2, int a3)
{
  HANDLE FileW; // rax
  void *v4; // rbx
  HANDLE FileMappingW; // rdi
  unsigned __int64 v6; // rbx

  if ( a1 )
  {
    if ( !a2 )
      return LoadLibraryExW(a1, 0, a3 != 0);
    FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 8u, 0, 0, 0);
      CloseHandle(v4);
      if ( FileMappingW )
      {
        v6 = (unsigned __int64)MapViewOfFile(FileMappingW, 1u, 0, 0, 0);
        CloseHandle(FileMappingW);
        return (HMODULE)((v6 | 1) & -(__int64)(v6 != 0));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180022b10  mov     [rsp+arg_0], rbx
0x180022b15  push    rdi
0x180022b16  sub     rsp, 40h
0x180022b1a  mov     eax, r8d
0x180022b1d  test    rcx, rcx
0x180022b20  jz      loc_180022BE7
0x180022b26  test    edx, edx
0x180022b28  jz      loc_180022BD4
0x180022b2e  xor     r9d, r9d; lpSecurityAttributes
0x180022b31  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180022b3a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180022b42  mov     edx, 80000000h; dwDesiredAccess
0x180022b47  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180022b4f  lea     r8d, [r9+5]; dwShareMode
0x180022b53  call    cs:__imp_CreateFileW
0x180022b59  mov     rbx, rax
0x180022b5c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022b60  jz      loc_180022BE7
0x180022b66  xor     r9d, r9d; dwMaximumSizeHigh
0x180022b69  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180022b72  xor     edx, edx; lpFileMappingAttributes
0x180022b74  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180022b7c  mov     rcx, rax; hFile
0x180022b7f  lea     r8d, [r9+8]; flProtect
0x180022b83  call    cs:__imp_CreateFileMappingW
0x180022b89  mov     rcx, rbx; hObject
0x180022b8c  mov     rdi, rax
0x180022b8f  call    cs:__imp_CloseHandle
0x180022b95  test    rdi, rdi
0x180022b98  jz      short loc_180022BE7
0x180022b9a  xor     r9d, r9d; dwFileOffsetLow
0x180022b9d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180022ba6  xor     r8d, r8d; dwFileOffsetHigh
0x180022ba9  mov     rcx, rdi; hFileMappingObject
0x180022bac  lea     edx, [r9+1]; dwDesiredAccess
0x180022bb0  call    cs:__imp_MapViewOfFile
0x180022bb6  mov     rcx, rdi; hObject
0x180022bb9  mov     rbx, rax
0x180022bbc  call    cs:__imp_CloseHandle
0x180022bc2  mov     rcx, rbx
0x180022bc5  or      rcx, 1; lpLibFileName
0x180022bc9  neg     rbx
0x180022bcc  sbb     rax, rax
0x180022bcf  and     rax, rcx
0x180022bd2  jmp     short loc_180022BE9
0x180022bd4  xor     r8d, r8d
0x180022bd7  test    eax, eax
0x180022bd9  setnz   r8b; dwFlags
0x180022bdd  xor     edx, edx; hFile
0x180022bdf  call    cs:__imp_LoadLibraryExW
0x180022be5  jmp     short loc_180022BE9
0x180022be7  xor     eax, eax
0x180022be9  mov     rbx, [rsp+48h+arg_0]
0x180022bee  add     rsp, 40h
0x180022bf2  pop     rdi
0x180022bf3  retn
```
