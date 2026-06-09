# MappedFile::Open(ushort const *)

- ea: `0x18001bdd8`
- end: `0x18001bec0`
- name: `?Open@MappedFile@@QEAAJPEBG@Z`
- size: `232`
- prototype: `int(MappedFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c01c`

## callees

- `0x18001bdd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be70`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001be10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001be10`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001bea0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18001bea0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001be61`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001be61`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001be3c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001be3c`

## pseudocode

```c
__int64 __fastcall MappedFile::Open(MappedFile *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  LPVOID v5; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  void *v8; // rcx
  __int64 FileSizeHigh; // [rsp+50h] [rbp+8h] BYREF

  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0, 0);
  *(_QWORD *)this = FileW;
  if ( FileW != (HANDLE)-1LL
    && (FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0), (*((_QWORD *)this + 1) = FileMappingW) != 0)
    && (v5 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), (*((_QWORD *)this + 2) = v5) != 0) )
  {
    v8 = *(void **)this;
    v7 = 0;
    HIDWORD(FileSizeHigh) = 0;
    FileSizeHigh = GetFileSize(v8, (LPDWORD)&FileSizeHigh + 1);
    *((_QWORD *)this + 3) = FileSizeHigh;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001bdd8  mov     [rsp+arg_8], rbx
0x18001bddd  push    rdi
0x18001bdde  sub     rsp, 40h
0x18001bde2  mov     rax, rdx
0x18001bde5  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18001bdee  xor     r9d, r9d; lpSecurityAttributes
0x18001bdf1  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001bdf9  mov     rdi, rcx
0x18001bdfc  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18001be04  mov     edx, 80000000h; dwDesiredAccess
0x18001be09  mov     rcx, rax; lpFileName
0x18001be0c  lea     r8d, [r9+1]; dwShareMode
0x18001be10  call    cs:__imp_CreateFileW
0x18001be16  mov     [rdi], rax
0x18001be19  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001be1d  jz      short loc_18001BE70
0x18001be1f  xor     r9d, r9d; dwMaximumSizeHigh
0x18001be22  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 0; lpName
0x18001be2b  xor     edx, edx; lpFileMappingAttributes
0x18001be2d  mov     [rsp+48h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18001be35  mov     rcx, rax; hFile
0x18001be38  lea     r8d, [r9+2]; flProtect
0x18001be3c  call    cs:__imp_CreateFileMappingW
0x18001be42  mov     [rdi+8], rax
0x18001be46  test    rax, rax
0x18001be49  jz      short loc_18001BE70
0x18001be4b  xor     r9d, r9d; dwFileOffsetLow
0x18001be4e  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18001be57  xor     r8d, r8d; dwFileOffsetHigh
0x18001be5a  mov     rcx, rax; hFileMappingObject
0x18001be5d  lea     edx, [r9+4]; dwDesiredAccess
0x18001be61  call    cs:__imp_MapViewOfFile
0x18001be67  mov     [rdi+10h], rax
0x18001be6b  test    rax, rax
0x18001be6e  jnz     short loc_18001BE91
0x18001be70  call    cs:__imp_GetLastError
0x18001be76  mov     ebx, eax
0x18001be78  test    eax, eax
0x18001be7a  jle     short loc_18001BE85
0x18001be7c  movzx   ebx, ax
0x18001be7f  or      ebx, 80070000h
0x18001be85  test    ebx, ebx
0x18001be87  mov     eax, 80004005h
0x18001be8c  cmovns  ebx, eax
0x18001be8f  jmp     short loc_18001BEB3
0x18001be91  mov     rcx, [rdi]; hFile
0x18001be94  lea     rdx, [rsp+48h+FileSizeHigh+4]; lpFileSizeHigh
0x18001be99  xor     ebx, ebx
0x18001be9b  mov     [rsp+50h], rbx
0x18001bea0  call    cs:__imp_GetFileSize
0x18001bea6  mov     dword ptr [rsp+48h+FileSizeHigh], eax
0x18001beaa  mov     rcx, [rsp+48h+FileSizeHigh]
0x18001beaf  mov     [rdi+18h], rcx
0x18001beb3  mov     eax, ebx
0x18001beb5  mov     rbx, [rsp+48h+arg_8]
0x18001beba  add     rsp, 40h
0x18001bebe  pop     rdi
0x18001bebf  retn
```
