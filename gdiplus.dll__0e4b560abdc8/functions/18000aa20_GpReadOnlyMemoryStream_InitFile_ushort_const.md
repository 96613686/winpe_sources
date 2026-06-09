# GpReadOnlyMemoryStream::InitFile(ushort const *)

- ea: `0x18000aa20`
- end: `0x18000ab4b`
- name: `?InitFile@GpReadOnlyMemoryStream@@QEAAJPEBG@Z`
- size: `299`
- prototype: `int(GpReadOnlyMemoryStream *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a430`

## callees

- `0x18000aa20`
- `0x18000b20c`
- `0x1800e7040`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab09`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aa74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aa74`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000aa97`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000aa97`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000aaf7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000aaf7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18000aac9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18000aac9`

## pseudocode

```c
__int64 __fastcall GpReadOnlyMemoryStream::InitFile(GpReadOnlyMemoryStream *this, GpRuntime *a2)
{
  unsigned __int16 *v4; // rax
  HANDLE FileW; // rax
  DWORD FileSize; // edi
  HANDLE FileMappingA; // rax
  void *v8; // rsi
  __int64 result; // rax
  LPVOID v10; // rbp
  DWORD FileSizeHigh; // [rsp+50h] [rbp+8h] BYREF

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
  v10 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
  CloseHandle(v8);
  if ( !v10 )
    return GetWin32HRESULT();
  *((_DWORD *)this + 9) = 0;
  result = 0;
  *((_QWORD *)this + 3) = v10;
  *((_DWORD *)this + 8) = FileSize;
  *((_DWORD *)this + 10) = 4;
  return result;
}

```

## disassembly

```asm
0x18000aa20  mov     [rsp+arg_8], rbx
0x18000aa25  mov     [rsp+arg_10], rbp
0x18000aa2a  mov     [rsp+arg_18], rsi
0x18000aa2f  push    rdi
0x18000aa30  sub     rsp, 40h
0x18000aa34  mov     rbx, rcx
0x18000aa37  mov     rdi, rdx
0x18000aa3a  mov     rcx, rdx; this
0x18000aa3d  call    ?UnicodeStringDuplicate@GpRuntime@@YAPEAGPEBG@Z; GpRuntime::UnicodeStringDuplicate(ushort const *)
0x18000aa42  mov     [rbx+38h], rax
0x18000aa46  test    rax, rax
0x18000aa49  jz      loc_18000AB44
0x18000aa4f  and     [rsp+48h+var_18], 0
0x18000aa55  xor     r9d, r9d; lpSecurityAttributes
0x18000aa58  mov     [rsp+48h+dwFlagsAndAttributes], 80h; lpName
0x18000aa60  mov     edx, 80000000h; dwDesiredAccess
0x18000aa65  mov     rcx, rdi; lpFileName
0x18000aa68  mov     [rsp+48h+dwCreationDisposition], 3; dwNumberOfBytesToMap
0x18000aa70  lea     r8d, [r9+1]; dwShareMode
0x18000aa74  call    cs:__imp_CreateFileW
0x18000aa7b  nop     dword ptr [rax+rax+00h]
0x18000aa80  mov     [rbx+30h], rax
0x18000aa84  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aa88  jz      short loc_18000AADD
0x18000aa8a  and     [rsp+48h+FileSizeHigh], 0
0x18000aa8f  lea     rdx, [rsp+48h+FileSizeHigh]; lpFileSizeHigh
0x18000aa94  mov     rcx, rax; hFile
0x18000aa97  call    cs:__imp_GetFileSize
0x18000aa9e  nop     dword ptr [rax+rax+00h]
0x18000aaa3  mov     edi, eax
0x18000aaa5  cmp     eax, 0FFFFFFFFh
0x18000aaa8  jz      short loc_18000AADD
0x18000aaaa  cmp     [rsp+48h+FileSizeHigh], 0
0x18000aaaf  jnz     short loc_18000AADD
0x18000aab1  and     qword ptr [rsp+48h+dwFlagsAndAttributes], 0
0x18000aab7  xor     r9d, r9d; dwMaximumSizeHigh
0x18000aaba  mov     rcx, [rbx+30h]; hFile
0x18000aabe  xor     edx, edx; lpFileMappingAttributes
0x18000aac0  and     [rsp+48h+dwCreationDisposition], 0
0x18000aac5  lea     r8d, [r9+2]; flProtect
0x18000aac9  call    cs:__imp_CreateFileMappingA
0x18000aad0  nop     dword ptr [rax+rax+00h]
0x18000aad5  mov     rsi, rax
0x18000aad8  test    rax, rax
0x18000aadb  jnz     short loc_18000AAE4
0x18000aadd  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x18000aae2  jmp     short loc_18000AB2E
0x18000aae4  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x18000aaea  xor     r9d, r9d; dwFileOffsetLow
0x18000aaed  xor     r8d, r8d; dwFileOffsetHigh
0x18000aaf0  mov     rcx, rsi; hFileMappingObject
0x18000aaf3  lea     edx, [r9+4]; dwDesiredAccess
0x18000aaf7  call    cs:__imp_MapViewOfFile
0x18000aafe  nop     dword ptr [rax+rax+00h]
0x18000ab03  mov     rcx, rsi; hObject
0x18000ab06  mov     rbp, rax
0x18000ab09  call    cs:__imp_CloseHandle
0x18000ab10  nop     dword ptr [rax+rax+00h]
0x18000ab15  test    rbp, rbp
0x18000ab18  jz      short loc_18000AADD
0x18000ab1a  and     dword ptr [rbx+24h], 0
0x18000ab1e  xor     eax, eax
0x18000ab20  mov     [rbx+18h], rbp
0x18000ab24  mov     [rbx+20h], edi
0x18000ab27  mov     dword ptr [rbx+28h], 4
0x18000ab2e  mov     rbx, [rsp+48h+arg_8]
0x18000ab33  mov     rbp, [rsp+48h+arg_10]
0x18000ab38  mov     rsi, [rsp+48h+arg_18]
0x18000ab3d  add     rsp, 40h
0x18000ab41  pop     rdi
0x18000ab42  retn
0x18000ab44  mov     eax, 8007000Eh
0x18000ab49  jmp     short loc_18000AB2E
```
