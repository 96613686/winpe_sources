# GetDefaultSortFileMapping

- ea: `0x180019588`
- end: `0x180019672`
- name: `GetDefaultSortFileMapping`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180019170`

## callees

- `0x180019588`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800195f3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800195f3`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001961c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001961c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019662`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019633`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019662`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800195bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800195bd`

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
0x180019588  push    rbx
0x18001958a  push    rsi
0x18001958b  push    rdi
0x18001958c  push    r14
0x18001958e  sub     rsp, 48h
0x180019592  xor     r9d, r9d; lpSecurityAttributes
0x180019595  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001959e  mov     r14, rdx
0x1800195a1  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800195a9  mov     edx, 80000000h; dwDesiredAccess
0x1800195ae  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800195b6  lea     edi, [r9+1]
0x1800195ba  mov     r8d, edi; dwShareMode
0x1800195bd  call    cs:__imp_CreateFileW
0x1800195c4  nop     dword ptr [rax+rax+00h]
0x1800195c9  mov     rbx, rax
0x1800195cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800195d0  jz      loc_18001966E
0x1800195d6  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x1800195df  lea     r8d, [rdi+1]; flProtect
0x1800195e3  xor     r9d, r9d; dwMaximumSizeHigh
0x1800195e6  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800195ee  xor     edx, edx; lpFileMappingAttributes
0x1800195f0  mov     rcx, rax; hFile
0x1800195f3  call    cs:__imp_CreateFileMappingW
0x1800195fa  nop     dword ptr [rax+rax+00h]
0x1800195ff  mov     rsi, rax
0x180019602  test    rax, rax
0x180019605  jz      short loc_18001965F
0x180019607  xor     r9d, r9d; dwFileOffsetLow
0x18001960a  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180019613  xor     r8d, r8d; dwFileOffsetHigh
0x180019616  lea     edx, [rdi+3]; dwDesiredAccess
0x180019619  mov     rcx, rax; hFileMappingObject
0x18001961c  call    cs:__imp_MapViewOfFile
0x180019623  nop     dword ptr [rax+rax+00h]
0x180019628  test    rax, rax
0x18001962b  jz      short loc_18001965B
0x18001962d  mov     [r14], rax
0x180019630  mov     rcx, rsi; hObject
0x180019633  call    cs:__imp_CloseHandle
0x18001963a  nop     dword ptr [rax+rax+00h]
0x18001963f  mov     rcx, rbx; hObject
0x180019642  call    cs:__imp_CloseHandle
0x180019649  nop     dword ptr [rax+rax+00h]
0x18001964e  mov     eax, edi
0x180019650  add     rsp, 48h
0x180019654  pop     r14
0x180019656  pop     rdi
0x180019657  pop     rsi
0x180019658  pop     rbx
0x180019659  retn
0x18001965b  xor     edi, edi
0x18001965d  jmp     short loc_180019630
0x18001965f  mov     rcx, rbx; hObject
0x180019662  call    cs:__imp_CloseHandle
0x180019669  nop     dword ptr [rax+rax+00h]
0x18001966e  xor     eax, eax
0x180019670  jmp     short loc_180019650
```
