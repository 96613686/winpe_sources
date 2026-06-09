# MapMUIFile

- ea: `0x180038b10`
- end: `0x180038bf4`
- name: `MapMUIFile`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180038c3c`
- `0x180038d50`

## callees

- `0x180038b10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038bdf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180038bdf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038b53`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038b53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038b8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038bbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038b8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038bbc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180038b83`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180038b83`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180038bb0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180038bb0`

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
0x180038b10  mov     [rsp+arg_0], rbx
0x180038b15  push    rdi
0x180038b16  sub     rsp, 40h
0x180038b1a  mov     eax, r8d
0x180038b1d  test    rcx, rcx
0x180038b20  jz      loc_180038BE7
0x180038b26  test    edx, edx
0x180038b28  jz      loc_180038BD4
0x180038b2e  xor     r9d, r9d; lpSecurityAttributes
0x180038b31  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180038b3a  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180038b42  mov     edx, 80000000h; dwDesiredAccess
0x180038b47  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180038b4f  lea     r8d, [r9+5]; dwShareMode
0x180038b53  call    cs:__imp_CreateFileW
0x180038b59  mov     rbx, rax
0x180038b5c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038b60  jz      loc_180038BE7
0x180038b66  xor     r9d, r9d; dwMaximumSizeHigh
0x180038b69  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x180038b72  xor     edx, edx; lpFileMappingAttributes
0x180038b74  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180038b7c  mov     rcx, rax; hFile
0x180038b7f  lea     r8d, [r9+8]; flProtect
0x180038b83  call    cs:__imp_CreateFileMappingW
0x180038b89  mov     rcx, rbx; hObject
0x180038b8c  mov     rdi, rax
0x180038b8f  call    cs:__imp_CloseHandle
0x180038b95  test    rdi, rdi
0x180038b98  jz      short loc_180038BE7
0x180038b9a  xor     r9d, r9d; dwFileOffsetLow
0x180038b9d  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180038ba6  xor     r8d, r8d; dwFileOffsetHigh
0x180038ba9  mov     rcx, rdi; hFileMappingObject
0x180038bac  lea     edx, [r9+1]; dwDesiredAccess
0x180038bb0  call    cs:__imp_MapViewOfFile
0x180038bb6  mov     rcx, rdi; hObject
0x180038bb9  mov     rbx, rax
0x180038bbc  call    cs:__imp_CloseHandle
0x180038bc2  mov     rcx, rbx
0x180038bc5  or      rcx, 1; lpLibFileName
0x180038bc9  neg     rbx
0x180038bcc  sbb     rax, rax
0x180038bcf  and     rax, rcx
0x180038bd2  jmp     short loc_180038BE9
0x180038bd4  xor     r8d, r8d
0x180038bd7  test    eax, eax
0x180038bd9  setnz   r8b; dwFlags
0x180038bdd  xor     edx, edx; hFile
0x180038bdf  call    cs:__imp_LoadLibraryExW
0x180038be5  jmp     short loc_180038BE9
0x180038be7  xor     eax, eax
0x180038be9  mov     rbx, [rsp+48h+arg_0]
0x180038bee  add     rsp, 40h
0x180038bf2  pop     rdi
0x180038bf3  retn
```
