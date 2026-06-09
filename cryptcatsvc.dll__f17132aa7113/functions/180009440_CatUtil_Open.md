# CatUtil_Open

- ea: `0x180009440`
- end: `0x180009596`
- name: `CatUtil_Open`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001b8f4`
- `0x18001ef4c`

## callees

- `0x180009440`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000950f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000950f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009557`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009551`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009561`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009551`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000952f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009540`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000952f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009540`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800094ae`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800094ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009498`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009498`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800094da`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800094da`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000951f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000951f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800094fa`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800094fa`

## pseudocode

```c
__int64 __fastcall CatUtil_Open(__int64 a1, const WCHAR *a2, _QWORD *a3, _QWORD *a4, _DWORD *a5, __int64 *a6)
{
  void *v6; // rbx
  LPVOID v7; // rdi
  __int64 v8; // rsi
  HANDLE FileW; // rax
  void *v12; // r14
  DWORD FileSize; // eax
  SIZE_T v14; // rbp
  HANDLE FileMappingW; // rax
  __int64 result; // rax
  DWORD LastError; // ebp

  v6 = 0;
  v7 = 0;
  v8 = -1;
  if ( !a2 || !*a2 )
  {
    SetLastError(0x57u);
    LastError = GetLastError();
LABEL_16:
    SetLastError(LastError);
    LODWORD(v14) = 0;
    result = 0;
    goto LABEL_17;
  }
  FileW = CreateFileW(a2, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  v12 = FileW;
  if ( FileW == (HANDLE)-1LL
    || (v8 = (__int64)FileW, FileSize = GetFileSize(FileW, 0), v14 = FileSize, FileSize == -1) && GetLastError()
    || (FileMappingW = CreateFileMappingW(v12, 0, 2u, 0, 0, 0), (v6 = FileMappingW) == 0)
    || (v7 = MapViewOfFile(FileMappingW, 4u, 0, 0, v14)) == 0 )
  {
    LastError = GetLastError();
    if ( v6 )
    {
      CloseHandle(v6);
      v6 = 0;
    }
    if ( v8 != -1 )
    {
      CloseHandle((HANDLE)v8);
      v8 = -1;
    }
    goto LABEL_16;
  }
  result = 1;
LABEL_17:
  *a3 = v6;
  *a4 = v7;
  *a5 = v14;
  *a6 = v8;
  return result;
}

```

## disassembly

```asm
0x180009440  push    rbx
0x180009442  push    rbp
0x180009443  push    rsi
0x180009444  push    rdi
0x180009445  push    r12
0x180009447  push    r14
0x180009449  push    r15
0x18000944b  sub     rsp, 40h
0x18000944f  xor     ebx, ebx
0x180009451  xor     edi, edi
0x180009453  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009457  mov     r15, r9
0x18000945a  mov     r12, r8
0x18000945d  mov     r10, rdx
0x180009460  test    rdx, rdx
0x180009463  jz      loc_18000954C
0x180009469  xor     eax, eax
0x18000946b  cmp     ax, [rdx]
0x18000946e  jz      loc_18000954C
0x180009474  mov     [rsp+78h+hTemplateFile], rax; hTemplateFile
0x180009479  lea     r8d, [rbx+5]; dwShareMode
0x18000947d  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180009485  xor     r9d, r9d; lpSecurityAttributes
0x180009488  mov     edx, 80000000h; dwDesiredAccess
0x18000948d  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180009495  mov     rcx, r10; lpFileName
0x180009498  call    cs:__imp_CreateFileW
0x18000949e  mov     r14, rax
0x1800094a1  cmp     rax, rsi
0x1800094a4  jz      short loc_18000950F
0x1800094a6  xor     edx, edx; lpFileSizeHigh
0x1800094a8  mov     rcx, rax; hFile
0x1800094ab  mov     rsi, rax
0x1800094ae  call    cs:__imp_GetFileSize
0x1800094b4  mov     ebp, eax
0x1800094b6  cmp     eax, 0FFFFFFFFh
0x1800094b9  jnz     short loc_1800094C5
0x1800094bb  call    cs:__imp_GetLastError
0x1800094c1  test    eax, eax
0x1800094c3  jnz     short loc_18000950F
0x1800094c5  xor     r9d, r9d; dwMaximumSizeHigh
0x1800094c8  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rbx; lpName
0x1800094cd  xor     edx, edx; lpFileMappingAttributes
0x1800094cf  mov     [rsp+78h+dwCreationDisposition], ebx; dwMaximumSizeLow
0x1800094d3  mov     rcx, r14; hFile
0x1800094d6  lea     r8d, [r9+2]; flProtect
0x1800094da  call    cs:__imp_CreateFileMappingW
0x1800094e0  mov     rbx, rax
0x1800094e3  test    rax, rax
0x1800094e6  jz      short loc_18000950F
0x1800094e8  xor     r9d, r9d; dwFileOffsetLow
0x1800094eb  mov     qword ptr [rsp+78h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x1800094f0  xor     r8d, r8d; dwFileOffsetHigh
0x1800094f3  mov     rcx, rax; hFileMappingObject
0x1800094f6  lea     edx, [r9+4]; dwDesiredAccess
0x1800094fa  call    cs:__imp_MapViewOfFile
0x180009500  mov     rdi, rax
0x180009503  test    rax, rax
0x180009506  jz      short loc_18000950F
0x180009508  mov     eax, 1
0x18000950d  jmp     short loc_18000956B
0x18000950f  call    cs:__imp_GetLastError
0x180009515  mov     ebp, eax
0x180009517  test    rdi, rdi
0x18000951a  jz      short loc_180009527
0x18000951c  mov     rcx, rdi; lpBaseAddress
0x18000951f  call    cs:__imp_UnmapViewOfFile
0x180009525  xor     edi, edi
0x180009527  test    rbx, rbx
0x18000952a  jz      short loc_180009537
0x18000952c  mov     rcx, rbx; hObject
0x18000952f  call    cs:__imp_CloseHandle
0x180009535  xor     ebx, ebx
0x180009537  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000953b  jz      short loc_18000955F
0x18000953d  mov     rcx, rsi; hObject
0x180009540  call    cs:__imp_CloseHandle
0x180009546  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000954a  jmp     short loc_18000955F
0x18000954c  mov     ecx, 57h ; 'W'; dwErrCode
0x180009551  call    cs:__imp_SetLastError
0x180009557  call    cs:__imp_GetLastError
0x18000955d  mov     ebp, eax
0x18000955f  mov     ecx, ebp; dwErrCode
0x180009561  call    cs:__imp_SetLastError
0x180009567  xor     ebp, ebp
0x180009569  xor     eax, eax
0x18000956b  mov     rcx, [rsp+78h+arg_20]
0x180009573  mov     [r12], rbx
0x180009577  mov     [r15], rdi
0x18000957a  mov     [rcx], ebp
0x18000957c  mov     rcx, [rsp+78h+arg_28]
0x180009584  mov     [rcx], rsi
0x180009587  add     rsp, 40h
0x18000958b  pop     r15
0x18000958d  pop     r14
0x18000958f  pop     r12
0x180009591  pop     rdi
0x180009592  pop     rsi
0x180009593  pop     rbp
0x180009594  pop     rbx
0x180009595  retn
```
