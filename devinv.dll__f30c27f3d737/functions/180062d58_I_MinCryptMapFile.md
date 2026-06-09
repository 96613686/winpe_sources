# I_MinCryptMapFile

- ea: `0x180062d58`
- end: `0x180062ecc`
- name: `I_MinCryptMapFile`
- size: `372`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180061e10`
- `0x180062384`
- `0x180062478`
- `0x180062d58`

## callees

- `0x180062d58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062e6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062e24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062eb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062e24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180062eb1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180062db7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180062db7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062e5b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180062e5b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180062e17`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180062e17`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180062df7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180062df7`

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
0x180062d58  mov     [rsp+arg_8], rbx
0x180062d5d  mov     [rsp+arg_10], rbp
0x180062d62  push    rsi
0x180062d63  push    rdi
0x180062d64  push    r14
0x180062d66  sub     rsp, 40h
0x180062d6a  xor     ebx, ebx
0x180062d6c  mov     r14, r9
0x180062d6f  mov     rdi, r8
0x180062d72  mov     rsi, rdx
0x180062d75  test    r9, r9
0x180062d78  jz      short loc_180062D81
0x180062d7a  mov     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x180062d81  sub     ecx, 1
0x180062d84  jz      loc_180062E37
0x180062d8a  sub     ecx, 1
0x180062d8d  jz      short loc_180062DAB
0x180062d8f  cmp     ecx, 1
0x180062d92  jz      short loc_180062D9E
0x180062d94  mov     ebx, 57h ; 'W'
0x180062d99  jmp     loc_180062E7C
0x180062d9e  movups  xmm0, xmmword ptr [rdx]
0x180062da1  movdqu  xmmword ptr [r8], xmm0
0x180062da6  jmp     loc_180062EB7
0x180062dab  lea     rdx, [rsp+58h+FileSizeHigh]; lpFileSizeHigh
0x180062db0  mov     [rsp+58h+FileSizeHigh], ebx
0x180062db4  mov     rcx, rsi; hFile
0x180062db7  call    cs:__imp_GetFileSize
0x180062dbd  mov     ebp, eax
0x180062dbf  cmp     eax, 0FFFFFFFFh
0x180062dc2  jnz     short loc_180062DD2
0x180062dc4  call    cs:__imp_GetLastError
0x180062dca  test    eax, eax
0x180062dcc  jnz     loc_180062E6A
0x180062dd2  cmp     [rsp+58h+FileSizeHigh], ebx
0x180062dd6  jz      short loc_180062DE2
0x180062dd8  mov     ebx, 3EEh
0x180062ddd  jmp     loc_180062E7C
0x180062de2  xor     r9d, r9d; dwMaximumSizeHigh
0x180062de5  mov     [rsp+58h+lpName], rbx; lpName
0x180062dea  xor     edx, edx; lpFileMappingAttributes
0x180062dec  mov     [rsp+58h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x180062df0  mov     rcx, rsi; hFile
0x180062df3  lea     r8d, [r9+2]; flProtect
0x180062df7  call    cs:__imp_CreateFileMappingW
0x180062dfd  mov     rsi, rax
0x180062e00  test    rax, rax
0x180062e03  jz      short loc_180062E6A
0x180062e05  xor     r9d, r9d; dwFileOffsetLow
0x180062e08  mov     qword ptr [rsp+58h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x180062e0d  xor     r8d, r8d; dwFileOffsetHigh
0x180062e10  mov     rcx, rax; hFileMappingObject
0x180062e13  lea     edx, [r9+4]; dwDesiredAccess
0x180062e17  call    cs:__imp_MapViewOfFile
0x180062e1d  mov     rcx, rsi; hObject
0x180062e20  mov     [rdi+8], rax
0x180062e24  call    cs:__imp_CloseHandle
0x180062e2a  cmp     [rdi+8], rbx
0x180062e2e  jz      short loc_180062E6A
0x180062e30  mov     [rdi], ebp
0x180062e32  jmp     loc_180062EB7
0x180062e37  xor     r9d, r9d; lpSecurityAttributes
0x180062e3a  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x180062e3f  mov     dword ptr [rsp+58h+lpName], 80h; dwFlagsAndAttributes
0x180062e47  mov     edx, 80000000h; dwDesiredAccess
0x180062e4c  mov     rcx, rsi; lpFileName
0x180062e4f  mov     [rsp+58h+dwMaximumSizeLow], 3; dwCreationDisposition
0x180062e57  lea     r8d, [r9+1]; dwShareMode
0x180062e5b  call    cs:__imp_CreateFileW
0x180062e61  mov     rsi, rax
0x180062e64  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180062e68  jnz     short loc_180062E8C
0x180062e6a  call    cs:__imp_GetLastError
0x180062e70  mov     ebx, eax
0x180062e72  mov     eax, 6Eh ; 'n'
0x180062e77  test    ebx, ebx
0x180062e79  cmovz   ebx, eax
0x180062e7c  mov     qword ptr [rdi+8], 0
0x180062e84  mov     dword ptr [rdi], 0
0x180062e8a  jmp     short loc_180062EB7
0x180062e8c  xor     r9d, r9d
0x180062e8f  mov     r8, rdi
0x180062e92  mov     rdx, rsi
0x180062e95  lea     ecx, [r9+2]
0x180062e99  call    I_MinCryptMapFile
0x180062e9e  mov     ebx, eax
0x180062ea0  test    eax, eax
0x180062ea2  jnz     short loc_180062EAE
0x180062ea4  test    r14, r14
0x180062ea7  jz      short loc_180062EAE
0x180062ea9  mov     [r14], rsi
0x180062eac  jmp     short loc_180062EB7
0x180062eae  mov     rcx, rsi; hObject
0x180062eb1  call    cs:__imp_CloseHandle
0x180062eb7  mov     rbp, [rsp+58h+arg_10]
0x180062ebc  mov     eax, ebx
0x180062ebe  mov     rbx, [rsp+58h+arg_8]
0x180062ec3  add     rsp, 40h
0x180062ec7  pop     r14
0x180062ec9  pop     rdi
0x180062eca  pop     rsi
0x180062ecb  retn
```
