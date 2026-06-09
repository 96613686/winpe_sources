# MapImageFile(ushort const *,ulong,ulong,ulong,bool,void * *,ulong *,void * *)

- ea: `0x180091d40`
- end: `0x180091fa4`
- name: `?MapImageFile@@YAJPEBGKKK_NPEAPEAXPEAK2@Z`
- size: `612`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, bool, void **, unsigned int *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800a4044`
- `0x180264a80`
- `0x180264e30`

## callees

- `0x180091d40`
- `0x180195fcc`
- `0x180197584`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091eb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091eb5`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180091d8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180091dd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180091d8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180091dd2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091e13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091f76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091e13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091e8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180091f76`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180091df5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180091df5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091db8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180091db8`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180091f67`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180091f67`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180091e4f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180091e4f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180091e7a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180091e7a`
- `dbghelp!ImageNtHeader` at `0x180091ed8`
- `dbghelp!ImageNtHeader` at `0x180091ed8`

## pseudocode

```c
signed int __fastcall MapImageFile(
        LPCWSTR lpFileName,
        int a2,
        int a3,
        int a4,
        bool a5,
        void **a6,
        unsigned int *a7,
        void **a8)
{
  void *v8; // rsi
  UINT v12; // edi
  int v13; // ebp
  char *FileW; // rbx
  DWORD FileSize; // eax
  void *v16; // rcx
  signed int result; // eax
  HANDLE FileMappingW; // rax
  void *v19; // rdi
  bool v20; // zf
  PIMAGE_NT_HEADERS v21; // rcx

  v8 = 0;
  v20 = (g_SymOptions & 0x200) == 0;
  v12 = 0;
  *a8 = 0;
  v13 = 1;
  if ( !v20 )
    v12 = SetErrorMode(1u);
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0, 0);
  if ( (g_SymOptions & 0x200) != 0 )
    SetErrorMode(v12);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_8;
  FileSize = GetFileSize(FileW, 0);
  *a7 = FileSize;
  v16 = FileW;
  if ( FileSize == -1 )
  {
LABEL_7:
    CloseHandle(v16);
    goto LABEL_8;
  }
  FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  v19 = FileMappingW;
  if ( !FileMappingW )
  {
    v16 = FileW;
    goto LABEL_7;
  }
  v8 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  CloseHandle(v19);
  if ( !v8 )
  {
LABEL_8:
    if ( !GetLastError() )
      return -2147467259;
    result = GetLastError();
    v20 = result == 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v20 = result == 0;
    }
    if ( !v20 )
      return result;
    goto LABEL_17;
  }
  *a6 = v8;
  v8 = 0;
  *a8 = FileW;
LABEL_17:
  v21 = ImageNtHeader(*a6);
  if ( !v21 )
  {
    v13 = -2147024703;
LABEL_29:
    UnmapViewOfFile(*a6);
    CloseHandle(*a8);
    result = v13;
    *a8 = v8;
    return result;
  }
  if ( (unsigned int)(a3 - 1) <= 0xFFFFFFFD
    && v21->OptionalHeader.CheckSum != (_DWORD)v8
    && v21->OptionalHeader.CheckSum != a3
    || a2 && v21->OptionalHeader.SizeOfImage != a2
    || ((a4 + 2) & 0xFFFFFFFD) != 0 && v21->FileHeader.TimeDateStamp != a4 )
  {
    if ( a5 == (_BYTE)v8 && (g_SymOptions & 0x80000000) != 0 )
    {
      CompletePartialLine(0x200u);
      MaskOut(0x200u, L"DBGENG:  %s image header does not match memory image header.\n", lpFileName);
    }
    goto LABEL_29;
  }
  return 0;
}

```

## disassembly

```asm
0x180091d40  mov     [rsp+arg_8], rbx
0x180091d45  mov     [rsp+arg_10], r8d
0x180091d4a  mov     [rsp+arg_0], rcx
0x180091d4f  push    rbp
0x180091d50  push    rsi
0x180091d51  push    rdi
0x180091d52  push    r12
0x180091d54  push    r13
0x180091d56  push    r14
0x180091d58  push    r15
0x180091d5a  sub     rsp, 40h
0x180091d5e  mov     r14, [rsp+78h+arg_38]
0x180091d66  xor     esi, esi
0x180091d68  mov     r15d, 200h
0x180091d6e  mov     r13d, r9d
0x180091d71  test    cs:?g_SymOptions@@3KA, r15d; ulong g_SymOptions
0x180091d78  mov     r12d, edx
0x180091d7b  mov     rbx, rcx
0x180091d7e  mov     edi, esi
0x180091d80  mov     [r14], rsi
0x180091d83  lea     ebp, [rsi+1]
0x180091d86  jz      short loc_180091D98
0x180091d88  mov     ecx, ebp; uMode
0x180091d8a  call    cs:__imp_SetErrorMode
0x180091d91  nop     dword ptr [rax+rax+00h]
0x180091d96  mov     edi, eax
0x180091d98  xor     r9d, r9d; lpSecurityAttributes
0x180091d9b  mov     [rsp+78h+hTemplateFile], rsi; hTemplateFile
0x180091da0  mov     [rsp+78h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180091da4  mov     edx, 80000000h; dwDesiredAccess
0x180091da9  mov     rcx, rbx; lpFileName
0x180091dac  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180091db4  lea     r8d, [r9+7]; dwShareMode
0x180091db8  call    cs:__imp_CreateFileW
0x180091dbf  nop     dword ptr [rax+rax+00h]
0x180091dc4  test    cs:?g_SymOptions@@3KA, r15d; ulong g_SymOptions
0x180091dcb  mov     rbx, rax
0x180091dce  jz      short loc_180091DDE
0x180091dd0  mov     ecx, edi; uMode
0x180091dd2  call    cs:__imp_SetErrorMode
0x180091dd9  nop     dword ptr [rax+rax+00h]
0x180091dde  mov     r15, [rsp+78h+arg_28]
0x180091de6  lea     rcx, [rbx-1]
0x180091dea  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180091dee  ja      short loc_180091E1F
0x180091df0  xor     edx, edx; lpFileSizeHigh
0x180091df2  mov     rcx, rbx; hFile
0x180091df5  call    cs:__imp_GetFileSize
0x180091dfc  nop     dword ptr [rax+rax+00h]
0x180091e01  mov     rcx, [rsp+78h+arg_30]
0x180091e09  mov     [rcx], eax
0x180091e0b  mov     rcx, rbx; hFile
0x180091e0e  cmp     eax, 0FFFFFFFFh
0x180091e11  jnz     short loc_180091E3D
0x180091e13  call    cs:__imp_CloseHandle
0x180091e1a  nop     dword ptr [rax+rax+00h]
0x180091e1f  call    cs:__imp_GetLastError
0x180091e26  nop     dword ptr [rax+rax+00h]
0x180091e2b  test    eax, eax
0x180091e2d  jnz     loc_180091EB5
0x180091e33  mov     eax, 80004005h
0x180091e38  jmp     loc_180091F8B
0x180091e3d  xor     r9d, r9d; dwMaximumSizeHigh
0x180091e40  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rsi; lpName
0x180091e45  xor     edx, edx; lpFileMappingAttributes
0x180091e47  mov     [rsp+78h+dwCreationDisposition], esi; dwMaximumSizeLow
0x180091e4b  lea     r8d, [r9+2]; flProtect
0x180091e4f  call    cs:__imp_CreateFileMappingW
0x180091e56  nop     dword ptr [rax+rax+00h]
0x180091e5b  mov     rdi, rax
0x180091e5e  test    rax, rax
0x180091e61  jnz     short loc_180091E68
0x180091e63  mov     rcx, rbx
0x180091e66  jmp     short loc_180091E13
0x180091e68  xor     r9d, r9d; dwFileOffsetLow
0x180091e6b  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi; dwNumberOfBytesToMap
0x180091e70  xor     r8d, r8d; dwFileOffsetHigh
0x180091e73  mov     rcx, rdi; hFileMappingObject
0x180091e76  lea     edx, [r9+4]; dwDesiredAccess
0x180091e7a  call    cs:__imp_MapViewOfFile
0x180091e81  nop     dword ptr [rax+rax+00h]
0x180091e86  mov     rcx, rdi; hObject
0x180091e89  mov     rsi, rax
0x180091e8c  call    cs:__imp_CloseHandle
0x180091e93  nop     dword ptr [rax+rax+00h]
0x180091e98  test    rsi, rsi
0x180091e9b  jnz     short loc_180091EAB
0x180091e9d  call    cs:__imp_GetLastError
0x180091ea4  nop     dword ptr [rax+rax+00h]
0x180091ea9  jmp     short loc_180091E2B
0x180091eab  mov     [r15], rsi
0x180091eae  xor     esi, esi
0x180091eb0  mov     [r14], rbx
0x180091eb3  jmp     short loc_180091ED5
0x180091eb5  call    cs:__imp_GetLastError
0x180091ebc  nop     dword ptr [rax+rax+00h]
0x180091ec1  test    eax, eax
0x180091ec3  jle     short loc_180091ECF
0x180091ec5  movzx   eax, ax
0x180091ec8  or      eax, 80070000h
0x180091ecd  test    eax, eax
0x180091ecf  jnz     loc_180091F8B
0x180091ed5  mov     rcx, [r15]; Base
0x180091ed8  call    cs:__imp_ImageNtHeader
0x180091edf  nop     dword ptr [rax+rax+00h]
0x180091ee4  mov     rcx, rax
0x180091ee7  test    rax, rax
0x180091eea  jnz     short loc_180091EF3
0x180091eec  mov     ebp, 800700C1h
0x180091ef1  jmp     short loc_180091F64
0x180091ef3  mov     edx, [rsp+78h+arg_10]
0x180091efa  mov     r8d, 0FFFFFFFDh
0x180091f00  lea     eax, [rdx-1]
0x180091f03  cmp     eax, r8d
0x180091f06  ja      short loc_180091F12
0x180091f08  cmp     [rcx+58h], esi
0x180091f0b  jz      short loc_180091F12
0x180091f0d  cmp     [rcx+58h], edx
0x180091f10  jnz     short loc_180091F2C
0x180091f12  test    r12d, r12d
0x180091f15  jz      short loc_180091F1D
0x180091f17  cmp     [rcx+50h], r12d
0x180091f1b  jnz     short loc_180091F2C
0x180091f1d  lea     eax, [r13+2]
0x180091f21  test    r8d, eax
0x180091f24  jz      short loc_180091F89
0x180091f26  cmp     [rcx+8], r13d
0x180091f2a  jz      short loc_180091F89
0x180091f2c  cmp     [rsp+78h+arg_20], sil
0x180091f34  jnz     short loc_180091F64
0x180091f36  test    cs:?g_SymOptions@@3KA, 80000000h; ulong g_SymOptions
0x180091f40  jz      short loc_180091F64
0x180091f42  mov     ebx, 200h
0x180091f47  mov     ecx, ebx; unsigned int
0x180091f49  call    ?CompletePartialLine@@YAXK@Z; CompletePartialLine(ulong)
0x180091f4e  mov     r8, [rsp+78h+arg_0]
0x180091f56  lea     rdx, aDbgengSImageHe; "DBGENG:  %s image header does not match"...
0x180091f5d  mov     ecx, ebx; unsigned int
0x180091f5f  call    ?MaskOut@@YAXKPEBGZZ; MaskOut(ulong,ushort const *,...)
0x180091f64  mov     rcx, [r15]; lpBaseAddress
0x180091f67  call    cs:__imp_UnmapViewOfFile
0x180091f6e  nop     dword ptr [rax+rax+00h]
0x180091f73  mov     rcx, [r14]; hObject
0x180091f76  call    cs:__imp_CloseHandle
0x180091f7d  nop     dword ptr [rax+rax+00h]
0x180091f82  mov     eax, ebp
0x180091f84  mov     [r14], rsi
0x180091f87  jmp     short loc_180091F8B
0x180091f89  xor     eax, eax
0x180091f8b  mov     rbx, [rsp+78h+arg_8]
0x180091f93  add     rsp, 40h
0x180091f97  pop     r15
0x180091f99  pop     r14
0x180091f9b  pop     r13
0x180091f9d  pop     r12
0x180091f9f  pop     rdi
0x180091fa0  pop     rsi
0x180091fa1  pop     rbp
0x180091fa2  retn
```
