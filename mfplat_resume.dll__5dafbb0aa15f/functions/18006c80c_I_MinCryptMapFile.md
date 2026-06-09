# I_MinCryptMapFile

- ea: `0x18006c80c`
- end: `0x18006c980`
- name: `I_MinCryptMapFile`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18006c614`
- `0x18006c80c`

## callees

- `0x18006c80c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c91e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c91e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006c8cb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006c8cb`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006c8ab`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006c8ab`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006c86b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18006c86b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c90f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c90f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c8d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c965`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c8d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c965`

## pseudocode

```c
__int64 __fastcall I_MinCryptMapFile(int a1, WCHAR *a2, __int64 a3, _QWORD *a4)
{
  DWORD LastError; // ebx
  int v8; // ecx
  int v9; // ecx
  DWORD FileSize; // ebp
  HANDLE FileMappingW; // rax
  void *v12; // rsi
  HANDLE FileW; // rax
  void *v14; // rsi
  DWORD FileSizeHigh; // [rsp+60h] [rbp+8h] BYREF

  LastError = 0;
  if ( a4 )
    *a4 = -1;
  v8 = a1 - 1;
  if ( !v8 )
  {
    FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v14 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      LastError = I_MinCryptMapFile(2, FileW, a3);
      if ( LastError || !a4 )
        CloseHandle(v14);
      else
        *a4 = v14;
      return LastError;
    }
LABEL_16:
    LastError = GetLastError();
    if ( !LastError )
      LastError = 110;
    goto LABEL_18;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    FileSizeHigh = 0;
    FileSize = GetFileSize(a2, &FileSizeHigh);
    if ( FileSize != -1 || !GetLastError() )
    {
      if ( FileSizeHigh )
      {
        LastError = 1006;
        goto LABEL_18;
      }
      FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
      v12 = FileMappingW;
      if ( FileMappingW )
      {
        *(_QWORD *)(a3 + 8) = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        CloseHandle(v12);
        if ( *(_QWORD *)(a3 + 8) )
        {
          *(_DWORD *)a3 = FileSize;
          return LastError;
        }
      }
    }
    goto LABEL_16;
  }
  if ( v9 != 1 )
  {
    LastError = 87;
LABEL_18:
    *(_QWORD *)(a3 + 8) = 0;
    *(_DWORD *)a3 = 0;
    return LastError;
  }
  *(_OWORD *)a3 = *(_OWORD *)a2;
  return LastError;
}

```

## disassembly

```asm
0x18006c80c  mov     [rsp+arg_8], rbx
0x18006c811  mov     [rsp+arg_10], rbp
0x18006c816  push    rsi
0x18006c817  push    rdi
0x18006c818  push    r14
0x18006c81a  sub     rsp, 40h
0x18006c81e  xor     ebx, ebx
0x18006c820  mov     r14, r9
0x18006c823  mov     rdi, r8
0x18006c826  mov     rsi, rdx
0x18006c829  test    r9, r9
0x18006c82c  jz      short loc_18006C835
0x18006c82e  mov     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x18006c835  sub     ecx, 1
0x18006c838  jz      loc_18006C8EB
0x18006c83e  sub     ecx, 1
0x18006c841  jz      short loc_18006C85F
0x18006c843  cmp     ecx, 1
0x18006c846  jz      short loc_18006C852
0x18006c848  mov     ebx, 57h ; 'W'
0x18006c84d  jmp     loc_18006C930
0x18006c852  movups  xmm0, xmmword ptr [rdx]
0x18006c855  movdqu  xmmword ptr [r8], xmm0
0x18006c85a  jmp     loc_18006C96B
0x18006c85f  lea     rdx, [rsp+58h+FileSizeHigh]; lpFileSizeHigh
0x18006c864  mov     [rsp+58h+FileSizeHigh], ebx
0x18006c868  mov     rcx, rsi; hFile
0x18006c86b  call    cs:__imp_GetFileSize
0x18006c871  mov     ebp, eax
0x18006c873  cmp     eax, 0FFFFFFFFh
0x18006c876  jnz     short loc_18006C886
0x18006c878  call    cs:__imp_GetLastError
0x18006c87e  test    eax, eax
0x18006c880  jnz     loc_18006C91E
0x18006c886  cmp     [rsp+58h+FileSizeHigh], ebx
0x18006c88a  jz      short loc_18006C896
0x18006c88c  mov     ebx, 3EEh
0x18006c891  jmp     loc_18006C930
0x18006c896  xor     r9d, r9d; dwMaximumSizeHigh
0x18006c899  mov     [rsp+58h+lpName], rbx; lpName
0x18006c89e  xor     edx, edx; lpFileMappingAttributes
0x18006c8a0  mov     [rsp+58h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x18006c8a4  mov     rcx, rsi; hFile
0x18006c8a7  lea     r8d, [r9+2]; flProtect
0x18006c8ab  call    cs:__imp_CreateFileMappingW
0x18006c8b1  mov     rsi, rax
0x18006c8b4  test    rax, rax
0x18006c8b7  jz      short loc_18006C91E
0x18006c8b9  xor     r9d, r9d; dwFileOffsetLow
0x18006c8bc  mov     qword ptr [rsp+58h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18006c8c1  xor     r8d, r8d; dwFileOffsetHigh
0x18006c8c4  mov     rcx, rax; hFileMappingObject
0x18006c8c7  lea     edx, [r9+4]; dwDesiredAccess
0x18006c8cb  call    cs:__imp_MapViewOfFile
0x18006c8d1  mov     rcx, rsi; hObject
0x18006c8d4  mov     [rdi+8], rax
0x18006c8d8  call    cs:__imp_CloseHandle
0x18006c8de  cmp     [rdi+8], rbx
0x18006c8e2  jz      short loc_18006C91E
0x18006c8e4  mov     [rdi], ebp
0x18006c8e6  jmp     loc_18006C96B
0x18006c8eb  xor     r9d, r9d; lpSecurityAttributes
0x18006c8ee  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x18006c8f3  mov     dword ptr [rsp+58h+lpName], 80h; dwFlagsAndAttributes
0x18006c8fb  mov     edx, 80000000h; dwDesiredAccess
0x18006c900  mov     rcx, rsi; lpFileName
0x18006c903  mov     [rsp+58h+dwMaximumSizeLow], 3; dwCreationDisposition
0x18006c90b  lea     r8d, [r9+1]; dwShareMode
0x18006c90f  call    cs:__imp_CreateFileW
0x18006c915  mov     rsi, rax
0x18006c918  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006c91c  jnz     short loc_18006C940
0x18006c91e  call    cs:__imp_GetLastError
0x18006c924  mov     ebx, eax
0x18006c926  mov     eax, 6Eh ; 'n'
0x18006c92b  test    ebx, ebx
0x18006c92d  cmovz   ebx, eax
0x18006c930  mov     qword ptr [rdi+8], 0
0x18006c938  mov     dword ptr [rdi], 0
0x18006c93e  jmp     short loc_18006C96B
0x18006c940  xor     r9d, r9d
0x18006c943  mov     r8, rdi
0x18006c946  mov     rdx, rsi
0x18006c949  lea     ecx, [r9+2]
0x18006c94d  call    I_MinCryptMapFile
0x18006c952  mov     ebx, eax
0x18006c954  test    eax, eax
0x18006c956  jnz     short loc_18006C962
0x18006c958  test    r14, r14
0x18006c95b  jz      short loc_18006C962
0x18006c95d  mov     [r14], rsi
0x18006c960  jmp     short loc_18006C96B
0x18006c962  mov     rcx, rsi; hObject
0x18006c965  call    cs:__imp_CloseHandle
0x18006c96b  mov     rbp, [rsp+58h+arg_10]
0x18006c970  mov     eax, ebx
0x18006c972  mov     rbx, [rsp+58h+arg_8]
0x18006c977  add     rsp, 40h
0x18006c97b  pop     r14
0x18006c97d  pop     rdi
0x18006c97e  pop     rsi
0x18006c97f  retn
```
