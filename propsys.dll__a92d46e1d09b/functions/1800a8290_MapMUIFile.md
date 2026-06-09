# MapMUIFile

- ea: `0x1800a8290`
- end: `0x1800a8374`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18005a1cc`
- `0x1800a83bc`

## callees

- `0x1800a8290`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a835f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a835f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a830f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a833c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a830f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a833c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a82d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a82d3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a8330`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800a8330`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a8303`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800a8303`

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
0x1800a8290  mov     [rsp+arg_0], rbx
0x1800a8295  push    rdi
0x1800a8296  sub     rsp, 40h
0x1800a829a  mov     eax, r8d
0x1800a829d  test    rcx, rcx
0x1800a82a0  jz      loc_1800A8367
0x1800a82a6  test    edx, edx
0x1800a82a8  jz      loc_1800A8354
0x1800a82ae  xor     r9d, r9d; lpSecurityAttributes
0x1800a82b1  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800a82ba  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800a82c2  mov     edx, 80000000h; dwDesiredAccess
0x1800a82c7  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a82cf  lea     r8d, [r9+5]; dwShareMode
0x1800a82d3  call    cs:__imp_CreateFileW
0x1800a82d9  mov     rbx, rax
0x1800a82dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a82e0  jz      loc_1800A8367
0x1800a82e6  xor     r9d, r9d; dwMaximumSizeHigh
0x1800a82e9  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x1800a82f2  xor     edx, edx; lpFileMappingAttributes
0x1800a82f4  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800a82fc  mov     rcx, rax; hFile
0x1800a82ff  lea     r8d, [r9+8]; flProtect
0x1800a8303  call    cs:__imp_CreateFileMappingW
0x1800a8309  mov     rcx, rbx; hObject
0x1800a830c  mov     rdi, rax
0x1800a830f  call    cs:__imp_CloseHandle
0x1800a8315  test    rdi, rdi
0x1800a8318  jz      short loc_1800A8367
0x1800a831a  xor     r9d, r9d; dwFileOffsetLow
0x1800a831d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800a8326  xor     r8d, r8d; dwFileOffsetHigh
0x1800a8329  mov     rcx, rdi; hFileMappingObject
0x1800a832c  lea     edx, [r9+1]; dwDesiredAccess
0x1800a8330  call    cs:__imp_MapViewOfFile
0x1800a8336  mov     rcx, rdi; hObject
0x1800a8339  mov     rbx, rax
0x1800a833c  call    cs:__imp_CloseHandle
0x1800a8342  mov     rcx, rbx
0x1800a8345  or      rcx, 1; lpLibFileName
0x1800a8349  neg     rbx
0x1800a834c  sbb     rax, rax
0x1800a834f  and     rax, rcx
0x1800a8352  jmp     short loc_1800A8369
0x1800a8354  xor     r8d, r8d
0x1800a8357  test    eax, eax
0x1800a8359  setnz   r8b; dwFlags
0x1800a835d  xor     edx, edx; hFile
0x1800a835f  call    cs:__imp_LoadLibraryExW
0x1800a8365  jmp     short loc_1800A8369
0x1800a8367  xor     eax, eax
0x1800a8369  mov     rbx, [rsp+48h+arg_0]
0x1800a836e  add     rsp, 40h
0x1800a8372  pop     rdi
0x1800a8373  retn
```
