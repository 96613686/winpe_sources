# GetDefaultSortFileMapping

- ea: `0x18001b9bc`
- end: `0x18001ba7d`
- name: `GetDefaultSortFileMapping`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001b5e0`

## callees

- `0x18001b9bc`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001ba1d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001ba1d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ba40`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001ba40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba73`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b9f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001b9f1`

## pseudocode

```c
__int64 __fastcall GetDefaultSortFileMapping(const WCHAR *a1, _QWORD *a2)
{
  unsigned int v3; // edi
  HANDLE FileW; // rax
  void *v5; // rbx
  HANDLE FileMappingW; // rax
  void *v7; // rsi
  LPVOID v8; // rax

  v3 = 1;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  v7 = FileMappingW;
  if ( !FileMappingW )
  {
    CloseHandle(v5);
    return 0;
  }
  v8 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  if ( v8 )
    *a2 = v8;
  else
    v3 = 0;
  CloseHandle(v7);
  CloseHandle(v5);
  return v3;
}

```

## disassembly

```asm
0x18001b9bc  push    rbx
0x18001b9be  push    rsi
0x18001b9bf  push    rdi
0x18001b9c0  push    r14
0x18001b9c2  sub     rsp, 48h
0x18001b9c6  xor     r9d, r9d; lpSecurityAttributes
0x18001b9c9  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001b9d2  mov     r14, rdx
0x18001b9d5  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001b9dd  mov     edx, 80000000h; dwDesiredAccess
0x18001b9e2  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18001b9ea  lea     edi, [r9+1]
0x18001b9ee  mov     r8d, edi; dwShareMode
0x18001b9f1  call    cs:__imp_CreateFileW
0x18001b9f7  mov     rbx, rax
0x18001b9fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b9fe  jz      short loc_18001BA79
0x18001ba00  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18001ba09  lea     r8d, [rdi+1]; flProtect
0x18001ba0d  xor     r9d, r9d; dwMaximumSizeHigh
0x18001ba10  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18001ba18  xor     edx, edx; lpFileMappingAttributes
0x18001ba1a  mov     rcx, rax; hFile
0x18001ba1d  call    cs:__imp_CreateFileMappingW
0x18001ba23  mov     rsi, rax
0x18001ba26  test    rax, rax
0x18001ba29  jz      short loc_18001BA70
0x18001ba2b  xor     r9d, r9d; dwFileOffsetLow
0x18001ba2e  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18001ba37  xor     r8d, r8d; dwFileOffsetHigh
0x18001ba3a  lea     edx, [rdi+3]; dwDesiredAccess
0x18001ba3d  mov     rcx, rax; hFileMappingObject
0x18001ba40  call    cs:__imp_MapViewOfFile
0x18001ba46  test    rax, rax
0x18001ba49  jz      short loc_18001BA6C
0x18001ba4b  mov     [r14], rax
0x18001ba4e  mov     rcx, rsi; hObject
0x18001ba51  call    cs:__imp_CloseHandle
0x18001ba57  mov     rcx, rbx; hObject
0x18001ba5a  call    cs:__imp_CloseHandle
0x18001ba60  mov     eax, edi
0x18001ba62  add     rsp, 48h
0x18001ba66  pop     r14
0x18001ba68  pop     rdi
0x18001ba69  pop     rsi
0x18001ba6a  pop     rbx
0x18001ba6b  retn
0x18001ba6c  xor     edi, edi
0x18001ba6e  jmp     short loc_18001BA4E
0x18001ba70  mov     rcx, rbx; hObject
0x18001ba73  call    cs:__imp_CloseHandle
0x18001ba79  xor     eax, eax
0x18001ba7b  jmp     short loc_18001BA62
```
