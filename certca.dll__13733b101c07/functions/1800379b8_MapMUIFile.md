# MapMUIFile

- ea: `0x1800379b8`
- end: `0x180037a9c`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180037ae4`
- `0x180037bf8`

## callees

- `0x1800379b8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037a87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037a87`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800379fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800379fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037a64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037a64`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180037a58`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180037a58`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180037a2b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180037a2b`

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
0x1800379b8  mov     [rsp+arg_0], rbx
0x1800379bd  push    rdi
0x1800379be  sub     rsp, 40h
0x1800379c2  mov     eax, r8d
0x1800379c5  test    rcx, rcx
0x1800379c8  jz      loc_180037A8F
0x1800379ce  test    edx, edx
0x1800379d0  jz      loc_180037A7C
0x1800379d6  xor     r9d, r9d; lpSecurityAttributes
0x1800379d9  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800379e2  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800379ea  mov     edx, 80000000h; dwDesiredAccess
0x1800379ef  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800379f7  lea     r8d, [r9+5]; dwShareMode
0x1800379fb  call    cs:__imp_CreateFileW
0x180037a01  mov     rbx, rax
0x180037a04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037a08  jz      loc_180037A8F
0x180037a0e  xor     r9d, r9d; dwMaximumSizeHigh
0x180037a11  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180037a1a  xor     edx, edx; lpFileMappingAttributes
0x180037a1c  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180037a24  mov     rcx, rax; hFile
0x180037a27  lea     r8d, [r9+8]; flProtect
0x180037a2b  call    cs:__imp_CreateFileMappingW
0x180037a31  mov     rcx, rbx; hObject
0x180037a34  mov     rdi, rax
0x180037a37  call    cs:__imp_CloseHandle
0x180037a3d  test    rdi, rdi
0x180037a40  jz      short loc_180037A8F
0x180037a42  xor     r9d, r9d; dwFileOffsetLow
0x180037a45  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180037a4e  xor     r8d, r8d; dwFileOffsetHigh
0x180037a51  mov     rcx, rdi; hFileMappingObject
0x180037a54  lea     edx, [r9+1]; dwDesiredAccess
0x180037a58  call    cs:__imp_MapViewOfFile
0x180037a5e  mov     rcx, rdi; hObject
0x180037a61  mov     rbx, rax
0x180037a64  call    cs:__imp_CloseHandle
0x180037a6a  mov     rcx, rbx
0x180037a6d  or      rcx, 1; lpLibFileName
0x180037a71  neg     rbx
0x180037a74  sbb     rax, rax
0x180037a77  and     rax, rcx
0x180037a7a  jmp     short loc_180037A91
0x180037a7c  xor     r8d, r8d
0x180037a7f  test    eax, eax
0x180037a81  setnz   r8b; dwFlags
0x180037a85  xor     edx, edx; hFile
0x180037a87  call    cs:__imp_LoadLibraryExW
0x180037a8d  jmp     short loc_180037A91
0x180037a8f  xor     eax, eax
0x180037a91  mov     rbx, [rsp+48h+arg_0]
0x180037a96  add     rsp, 40h
0x180037a9a  pop     rdi
0x180037a9b  retn
```
