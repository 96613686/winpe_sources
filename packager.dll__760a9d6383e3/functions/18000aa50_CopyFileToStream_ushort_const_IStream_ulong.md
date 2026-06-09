# CopyFileToStream(ushort const *,IStream *,ulong *)

- ea: `0x18000aa50`
- end: `0x18000abe8`
- name: `?CopyFileToStream@@YAJPEBGPEAUIStream@@PEAK@Z`
- size: `408`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct IStream *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800080a8`
- `0x18000882c`

## callees

- `0x18000aa50`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000abba`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000ab1e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000ab1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aae4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aae4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000ab32`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000aba4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000ab32`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000aba4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000ab5d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000ab5d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000aaa5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000aaa5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000abc3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000abc3`

## pseudocode

```c
__int64 __fastcall CopyFileToStream(LPCWSTR lpFileName, struct IStream *a2, unsigned int *a3)
{
  HGLOBAL v6; // rsi
  signed int v7; // ebx
  HANDLE FileW; // rax
  void *v9; // rdi
  signed int LastError; // eax
  DWORD FileSize; // r15d
  int v12; // ecx
  LONG DistanceToMoveHigh[4]; // [rsp+40h] [rbp-10h] BYREF
  int v15; // [rsp+98h] [rbp+48h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+50h] BYREF
  DWORD FileSizeHigh; // [rsp+A8h] [rbp+58h] BYREF

  FileSizeHigh = 0;
  DistanceToMoveHigh[0] = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !lpFileName )
    return 2147500035LL;
  v6 = GlobalAlloc(0x40u, 0x1000u);
  if ( !v6 )
    return (unsigned int)-2147024882;
  FileW = CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2147467259;
    goto LABEL_22;
  }
  FileSize = GetFileSize(FileW, &FileSizeHigh);
  SetFilePointer(v9, 0, 0, 0);
  v12 = 4096;
  NumberOfBytesRead = 4096;
  v15 = 4096;
  while ( 1 )
  {
    if ( v12 != 4096 )
    {
LABEL_20:
      v7 = FileSize != SetFilePointer(v9, 0, DistanceToMoveHigh, 1u) ? 0x80004005 : 0;
      goto LABEL_21;
    }
    if ( !ReadFile(v9, v6, 0x1000u, &NumberOfBytesRead, 0) )
    {
      v12 = v15;
      goto LABEL_19;
    }
    if ( ((int (__fastcall *)(struct IStream *, HGLOBAL, _QWORD, int *))a2->lpVtbl->Write)(
           a2,
           v6,
           NumberOfBytesRead,
           &v15) < 0 )
      break;
    v12 = v15;
    *a3 += v15;
LABEL_19:
    if ( NumberOfBytesRead != 4096 )
      goto LABEL_20;
  }
  v7 = -2147467259;
LABEL_21:
  CloseHandle(v9);
LABEL_22:
  GlobalFree(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000aa50  push    rbp
0x18000aa52  push    rbx
0x18000aa53  push    rsi
0x18000aa54  push    rdi
0x18000aa55  push    r13
0x18000aa57  push    r14
0x18000aa59  push    r15
0x18000aa5b  mov     rbp, rsp
0x18000aa5e  sub     rsp, 50h
0x18000aa62  mov     [rbp+FileSizeHigh], 0
0x18000aa69  mov     rbx, r8
0x18000aa6c  mov     [rbp+DistanceToMoveHigh], 0
0x18000aa73  mov     r14, rdx
0x18000aa76  mov     rdi, rcx
0x18000aa79  test    r8, r8
0x18000aa7c  jz      short loc_18000AA85
0x18000aa7e  mov     dword ptr [r8], 0
0x18000aa85  test    r14, r14
0x18000aa88  jz      loc_18000ABD4
0x18000aa8e  test    rdi, rdi
0x18000aa91  jz      loc_18000ABD4
0x18000aa97  mov     r13d, 1000h
0x18000aa9d  mov     ecx, 40h ; '@'; uFlags
0x18000aaa2  mov     edx, r13d; dwBytes
0x18000aaa5  call    cs:__imp_GlobalAlloc
0x18000aaab  mov     rsi, rax
0x18000aaae  test    rax, rax
0x18000aab1  jnz     short loc_18000AABD
0x18000aab3  mov     ebx, 8007000Eh
0x18000aab8  jmp     loc_18000ABC9
0x18000aabd  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x18000aac6  mov     r8d, 3; dwShareMode
0x18000aacc  mov     [rsp+50h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000aad4  xor     r9d, r9d; lpSecurityAttributes
0x18000aad7  mov     edx, 80000000h; dwDesiredAccess
0x18000aadc  mov     [rsp+50h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000aae1  mov     rcx, rdi; lpFileName
0x18000aae4  call    cs:__imp_CreateFileW
0x18000aaea  mov     rdi, rax
0x18000aaed  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aaf1  jnz     short loc_18000AB17
0x18000aaf3  call    cs:__imp_GetLastError
0x18000aaf9  mov     ebx, eax
0x18000aafb  test    eax, eax
0x18000aafd  jle     short loc_18000AB08
0x18000aaff  movzx   ebx, ax
0x18000ab02  or      ebx, 80070000h
0x18000ab08  test    ebx, ebx
0x18000ab0a  mov     eax, 80004005h
0x18000ab0f  cmovns  ebx, eax
0x18000ab12  jmp     loc_18000ABC0
0x18000ab17  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x18000ab1b  mov     rcx, rdi; hFile
0x18000ab1e  call    cs:__imp_GetFileSize
0x18000ab24  xor     r9d, r9d; dwMoveMethod
0x18000ab27  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000ab2a  xor     edx, edx; lDistanceToMove
0x18000ab2c  mov     rcx, rdi; hFile
0x18000ab2f  mov     r15d, eax
0x18000ab32  call    cs:__imp_SetFilePointer
0x18000ab38  mov     ecx, r13d
0x18000ab3b  mov     [rbp+NumberOfBytesRead], r13d
0x18000ab3f  mov     [rbp+arg_8], ecx
0x18000ab42  cmp     ecx, r13d
0x18000ab45  jnz     short loc_18000AB95
0x18000ab47  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000ab4b  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x18000ab54  mov     r8d, r13d; nNumberOfBytesToRead
0x18000ab57  mov     rdx, rsi; lpBuffer
0x18000ab5a  mov     rcx, rdi; hFile
0x18000ab5d  call    cs:__imp_ReadFile
0x18000ab63  test    eax, eax
0x18000ab65  jz      short loc_18000AB8C
0x18000ab67  mov     rax, [r14]
0x18000ab6a  lea     r9, [rbp+arg_8]
0x18000ab6e  mov     r8d, [rbp+NumberOfBytesRead]
0x18000ab72  mov     rdx, rsi
0x18000ab75  mov     rcx, r14
0x18000ab78  mov     rax, [rax+20h]
0x18000ab7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab81  test    eax, eax
0x18000ab83  js      short loc_18000ABCD
0x18000ab85  mov     ecx, [rbp+arg_8]
0x18000ab88  add     [rbx], ecx
0x18000ab8a  jmp     short loc_18000AB8F
0x18000ab8c  mov     ecx, [rbp+arg_8]
0x18000ab8f  cmp     [rbp+NumberOfBytesRead], r13d
0x18000ab93  jz      short loc_18000AB42
0x18000ab95  mov     r9d, 1; dwMoveMethod
0x18000ab9b  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18000ab9f  xor     edx, edx; lDistanceToMove
0x18000aba1  mov     rcx, rdi; hFile
0x18000aba4  call    cs:__imp_SetFilePointer
0x18000abaa  sub     eax, r15d
0x18000abad  neg     eax
0x18000abaf  sbb     ebx, ebx
0x18000abb1  and     ebx, 80004005h
0x18000abb7  mov     rcx, rdi; hObject
0x18000abba  call    cs:__imp_CloseHandle
0x18000abc0  mov     rcx, rsi; hMem
0x18000abc3  call    cs:__imp_GlobalFree
0x18000abc9  mov     eax, ebx
0x18000abcb  jmp     short loc_18000ABD9
0x18000abcd  mov     ebx, 80004005h
0x18000abd2  jmp     short loc_18000ABB7
0x18000abd4  mov     eax, 80004003h
0x18000abd9  add     rsp, 50h
0x18000abdd  pop     r15
0x18000abdf  pop     r14
0x18000abe1  pop     r13
0x18000abe3  pop     rdi
0x18000abe4  pop     rsi
0x18000abe5  pop     rbx
0x18000abe6  pop     rbp
0x18000abe7  retn
```
