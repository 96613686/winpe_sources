# GpReadOnlyMemoryStream::InitFile(ushort const *)

- ea: `0x18008cec0`
- end: `0x18008cff2`
- name: `?InitFile@GpReadOnlyMemoryStream@@QEAAJPEBG@Z`
- size: `306`
- prototype: `int(GpReadOnlyMemoryStream *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18008ce00`

## callees

- `0x18008cb48`
- `0x18008cec0`
- `0x1800f784c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008cfb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008cfb2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008cf0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008cf0c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18008cf36`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18008cf36`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18008cfa0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18008cfa0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18008cf76`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18008cf76`

## pseudocode

```c
__int64 __fastcall GpReadOnlyMemoryStream::InitFile(GpReadOnlyMemoryStream *this, GpRuntime *a2)
{
  unsigned __int16 *v4; // rax
  HANDLE FileW; // rax
  DWORD FileSize; // edi
  HANDLE FileMappingA; // rax
  void *v8; // rsi
  LPVOID v9; // rbp
  __int64 result; // rax
  DWORD FileSizeHigh; // [rsp+70h] [rbp+8h] BYREF

  v4 = GpRuntime::UnicodeStringDuplicate(a2, (const unsigned __int16 *)a2);
  *((_QWORD *)this + 7) = v4;
  if ( !v4 )
    return 2147942414LL;
  FileW = CreateFileW((LPCWSTR)a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  *((_QWORD *)this + 6) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetWin32HRESULT();
  FileSizeHigh = 0;
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  if ( FileSize == -1 )
    return GetWin32HRESULT();
  if ( FileSizeHigh )
    return GetWin32HRESULT();
  FileMappingA = CreateFileMappingA(*((HANDLE *)this + 6), 0, 2u, 0, 0, 0);
  v8 = FileMappingA;
  if ( !FileMappingA )
    return GetWin32HRESULT();
  v9 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
  CloseHandle(v8);
  if ( !v9 )
    return GetWin32HRESULT();
  *((_QWORD *)this + 3) = v9;
  result = 0;
  *((_DWORD *)this + 8) = FileSize;
  *((_DWORD *)this + 9) = 0;
  *((_DWORD *)this + 10) = 4;
  return result;
}

```

## disassembly

```asm
0x18008cec0  push    rbx
0x18008cec2  push    rbp
0x18008cec3  push    rsi
0x18008cec4  push    rdi
0x18008cec5  sub     rsp, 48h
0x18008cec9  mov     rbx, rcx
0x18008cecc  mov     rdi, rdx
0x18008cecf  mov     rcx, rdx; this
0x18008ced2  call    ?UnicodeStringDuplicate@GpRuntime@@YAPEAGPEBG@Z; GpRuntime::UnicodeStringDuplicate(ushort const *)
0x18008ced7  mov     [rbx+38h], rax
0x18008cedb  test    rax, rax
0x18008cede  jz      loc_18008CFEB
0x18008cee4  xor     r9d, r9d; lpSecurityAttributes
0x18008cee7  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18008cef0  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008cef8  mov     edx, 80000000h; dwDesiredAccess
0x18008cefd  mov     rcx, rdi; lpFileName
0x18008cf00  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18008cf08  lea     r8d, [r9+1]; dwShareMode
0x18008cf0c  call    cs:__imp_CreateFileW
0x18008cf13  nop     dword ptr [rax+rax+00h]
0x18008cf18  mov     [rbx+30h], rax
0x18008cf1c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008cf20  jz      loc_18008CFE4
0x18008cf26  lea     rdx, [rsp+68h+FileSizeHigh]; lpFileSizeHigh
0x18008cf2b  mov     [rsp+68h+FileSizeHigh], 0
0x18008cf33  mov     rcx, rax; hFile
0x18008cf36  call    cs:__imp_GetFileSize
0x18008cf3d  nop     dword ptr [rax+rax+00h]
0x18008cf42  mov     edi, eax
0x18008cf44  cmp     eax, 0FFFFFFFFh
0x18008cf47  jz      loc_18008CFE4
0x18008cf4d  cmp     [rsp+68h+FileSizeHigh], 0
0x18008cf52  jnz     loc_18008CFE4
0x18008cf58  mov     rcx, [rbx+30h]; hFile
0x18008cf5c  xor     r9d, r9d; dwMaximumSizeHigh
0x18008cf5f  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x18008cf68  xor     edx, edx; lpFileMappingAttributes
0x18008cf6a  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18008cf72  lea     r8d, [r9+2]; flProtect
0x18008cf76  call    cs:__imp_CreateFileMappingA
0x18008cf7d  nop     dword ptr [rax+rax+00h]
0x18008cf82  mov     rsi, rax
0x18008cf85  test    rax, rax
0x18008cf88  jz      short loc_18008CFE4
0x18008cf8a  xor     r9d, r9d; dwFileOffsetLow
0x18008cf8d  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18008cf96  xor     r8d, r8d; dwFileOffsetHigh
0x18008cf99  mov     rcx, rax; hFileMappingObject
0x18008cf9c  lea     edx, [r9+4]; dwDesiredAccess
0x18008cfa0  call    cs:__imp_MapViewOfFile
0x18008cfa7  nop     dword ptr [rax+rax+00h]
0x18008cfac  mov     rcx, rsi; hObject
0x18008cfaf  mov     rbp, rax
0x18008cfb2  call    cs:__imp_CloseHandle
0x18008cfb9  nop     dword ptr [rax+rax+00h]
0x18008cfbe  test    rbp, rbp
0x18008cfc1  jz      short loc_18008CFE4
0x18008cfc3  mov     [rbx+18h], rbp
0x18008cfc7  xor     eax, eax
0x18008cfc9  mov     [rbx+20h], edi
0x18008cfcc  mov     dword ptr [rbx+24h], 0
0x18008cfd3  mov     dword ptr [rbx+28h], 4
0x18008cfda  add     rsp, 48h
0x18008cfde  pop     rdi
0x18008cfdf  pop     rsi
0x18008cfe0  pop     rbp
0x18008cfe1  pop     rbx
0x18008cfe2  retn
0x18008cfe4  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x18008cfe9  jmp     short loc_18008CFDA
0x18008cfeb  mov     eax, 8007000Eh
0x18008cff0  jmp     short loc_18008CFDA
```
