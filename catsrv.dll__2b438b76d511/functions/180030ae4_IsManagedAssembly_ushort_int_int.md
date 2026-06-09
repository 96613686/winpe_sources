# IsManagedAssembly(ushort *,int *,int *)

- ea: `0x180030ae4`
- end: `0x180030e22`
- name: `?IsManagedAssembly@@YAJPEAGPEAH1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180029584`
- `0x18002967c`
- `0x180030e28`

## callees

- `0x180030ae4`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `ntdll!RtlImageRvaToVa` at `0x180030d4b`
- `ntdll!RtlImageRvaToVa` at `0x180030d4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030df7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030d28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d72`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180030d18`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180030d18`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180030dac`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180030dac`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180030cf4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180030cf4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030bb4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030c72`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030bb4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180030c72`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180030b8c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180030b8c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180030c3c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180030c3c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030b72`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030b72`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180030be5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180030be5`

## pseudocode

```c
__int64 __fastcall IsManagedAssembly(LPCWSTR lpFileName, int *a2, int *a3)
{
  signed int v6; // ebx
  HANDLE FileW; // rax
  __int64 v8; // rdi
  signed int v9; // eax
  void *v10; // rsp
  HANDLE FileMappingW; // rax
  void *v12; // r12
  char *v13; // r15
  _WORD *v14; // rax
  signed int LastError; // eax
  _DWORD v17[6]; // [rsp+20h] [rbp-110h] BYREF
  __int16 v18; // [rsp+38h] [rbp-F8h]
  ULONG v19; // [rsp+108h] [rbp-28h]
  unsigned int v20; // [rsp+10Ch] [rbp-24h]
  DWORD dwFlagsAndAttributes; // [rsp+118h] [rbp-18h]
  int v22; // [rsp+11Ch] [rbp-14h]
  DWORD NumberOfBytesRead; // [rsp+130h] [rbp+0h] BYREF
  signed int v24; // [rsp+134h] [rbp+4h]
  union _LARGE_INTEGER FileSize; // [rsp+138h] [rbp+8h] BYREF
  HANDLE v26; // [rsp+140h] [rbp+10h]
  char *v27; // [rsp+148h] [rbp+18h]
  _WORD Buffer[30]; // [rsp+150h] [rbp+20h] BYREF
  unsigned int v29; // [rsp+18Ch] [rbp+5Ch]

  NumberOfBytesRead = 0;
  memset_0(Buffer, 0, 0x40u);
  if ( !lpFileName || !a2 )
  {
    v8 = -1;
    v6 = -2147024809;
    goto LABEL_44;
  }
  v6 = 0;
  *a2 = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v8 = (__int64)FileW;
  v26 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_44;
  if ( GetFileType(FileW) != 1 )
  {
    v6 = -2146368471;
    goto LABEL_44;
  }
  if ( ReadFile((HANDLE)v8, Buffer, 0x40u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 64 && Buffer[0] == 23117 )
  {
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx((HANDLE)v8, &FileSize) )
      goto LABEL_10;
    if ( v29 > 0x10000000 || FileSize.QuadPart < 0 || (int)v29 >= FileSize.QuadPart )
    {
      v6 = -2147418113;
      goto LABEL_44;
    }
    if ( SetFilePointer((HANDLE)v8, v29, 0, 0) == -1 )
      goto LABEL_10;
    NumberOfBytesRead = 0;
    v10 = alloca(272);
    if ( !ReadFile((HANDLE)v8, v17, 0x108u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 264 || v17[0] != 17744 )
      goto LABEL_44;
    if ( v18 == 267 )
    {
      if ( !v19 )
        goto LABEL_44;
      if ( !v20 )
        goto LABEL_44;
      *a2 = 1;
      if ( !a3 )
        goto LABEL_44;
      if ( v20 >= 0x48 )
      {
        *a3 = 1;
        FileMappingW = CreateFileMappingW((HANDLE)v8, 0, 2u, 0, 0, 0);
        v12 = FileMappingW;
        if ( FileMappingW )
        {
          v13 = (char *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
          v27 = v13;
          CloseHandle(v12);
          if ( v13 )
          {
            v14 = RtlImageRvaToVa((PIMAGE_NT_HEADERS)&v13[v29], v13, v19, 0);
            if ( v14 )
            {
              if ( v14[2] < 2u || v14[3] < 5u || (v14[8] & 2) != 0 )
                *a3 = 0;
            }
            else
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
              v24 = v6;
              if ( v6 >= 0 )
                v6 = -2147467259;
              v24 = v6;
            }
            UnmapViewOfFile(v13);
            goto LABEL_44;
          }
        }
LABEL_10:
        v9 = GetLastError();
        v6 = v9;
        if ( v9 > 0 )
          v6 = (unsigned __int16)v9 | 0x80070000;
        goto LABEL_44;
      }
    }
    else
    {
      if ( v18 != 523 )
        goto LABEL_44;
      if ( !dwFlagsAndAttributes )
        goto LABEL_44;
      if ( !v22 )
        goto LABEL_44;
      *a2 = 1;
      if ( !a3 )
        goto LABEL_44;
    }
    *a3 = 0;
  }
LABEL_44:
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030ae4  push    rbp
0x180030ae6  push    rsi
0x180030ae7  push    rdi
0x180030ae8  push    r12
0x180030aea  push    r13
0x180030aec  push    r14
0x180030aee  push    r15
0x180030af0  sub     rsp, 0B0h
0x180030af7  lea     rbp, [rsp+40h]
0x180030afc  mov     [rbp+0A0h+arg_18], rbx
0x180030b03  mov     rax, cs:__security_cookie
0x180030b0a  xor     rax, rbp
0x180030b0d  mov     [rbp+0A0h+var_40], rax
0x180030b11  mov     r14, r8
0x180030b14  mov     r15, rdx
0x180030b17  mov     rdi, rcx
0x180030b1a  xor     r13d, r13d
0x180030b1d  mov     [rbp+0A0h+NumberOfBytesRead], r13d
0x180030b21  lea     esi, [r13+40h]
0x180030b25  mov     r8d, esi; Size
0x180030b28  xor     edx, edx; Val
0x180030b2a  lea     rcx, [rbp+0A0h+Buffer]; void *
0x180030b2e  call    memset_0
0x180030b33  test    rdi, rdi
0x180030b36  jz      loc_180030DE5
0x180030b3c  test    r15, r15
0x180030b3f  jz      loc_180030DE5
0x180030b45  mov     ebx, r13d
0x180030b48  mov     [r15], r13d
0x180030b4b  mov     [rsp+0E0h+hTemplateFile], r13; hTemplateFile
0x180030b50  mov     [rsp+0E0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180030b58  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180030b60  xor     r9d, r9d; lpSecurityAttributes
0x180030b63  lea     r12d, [r13+1]
0x180030b67  mov     r8d, r12d; dwShareMode
0x180030b6a  mov     edx, 80000000h; dwDesiredAccess
0x180030b6f  mov     rcx, rdi; lpFileName
0x180030b72  call    cs:__imp_CreateFileW
0x180030b78  mov     rdi, rax
0x180030b7b  mov     [rbp+0A0h+var_90], rax
0x180030b7f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030b83  jz      loc_180030DEE
0x180030b89  mov     rcx, rax; hFile
0x180030b8c  call    cs:__imp_GetFileType
0x180030b92  cmp     eax, r12d
0x180030b95  jz      short loc_180030BA1
0x180030b97  mov     ebx, 80110429h
0x180030b9c  jmp     loc_180030DEE
0x180030ba1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpOverlapped
0x180030ba6  lea     r9, [rbp+0A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180030baa  mov     r8d, esi; nNumberOfBytesToRead
0x180030bad  lea     rdx, [rbp+0A0h+Buffer]; lpBuffer
0x180030bb1  mov     rcx, rdi; hFile
0x180030bb4  call    cs:__imp_ReadFile
0x180030bba  test    eax, eax
0x180030bbc  jz      loc_180030DEE
0x180030bc2  cmp     [rbp+0A0h+NumberOfBytesRead], esi
0x180030bc5  jnz     loc_180030DEE
0x180030bcb  mov     eax, 5A4Dh
0x180030bd0  cmp     [rbp+0A0h+Buffer], ax
0x180030bd4  jnz     loc_180030DEE
0x180030bda  mov     qword ptr [rbp+0A0h+FileSize], r13
0x180030bde  lea     rdx, [rbp+0A0h+FileSize]; lpFileSize
0x180030be2  mov     rcx, rdi; hFile
0x180030be5  call    cs:__imp_GetFileSizeEx
0x180030beb  test    eax, eax
0x180030bed  jnz     short loc_180030C0D
0x180030bef  call    cs:__imp_GetLastError
0x180030bf5  mov     ebx, eax
0x180030bf7  test    eax, eax
0x180030bf9  jle     loc_180030DEE
0x180030bff  movzx   ebx, ax
0x180030c02  or      ebx, 80070000h
0x180030c08  jmp     loc_180030DEE
0x180030c0d  movsxd  rdx, [rbp+0A0h+var_44]; lDistanceToMove
0x180030c11  cmp     edx, 10000000h
0x180030c17  ja      loc_180030DDE
0x180030c1d  mov     rax, qword ptr [rbp+0A0h+FileSize]
0x180030c21  test    rax, rax
0x180030c24  js      loc_180030DDE
0x180030c2a  cmp     rdx, rax
0x180030c2d  jge     loc_180030DDE
0x180030c33  xor     r9d, r9d; dwMoveMethod
0x180030c36  xor     r8d, r8d; lpDistanceToMoveHigh
0x180030c39  mov     rcx, rdi; hFile
0x180030c3c  call    cs:__imp_SetFilePointer
0x180030c42  cmp     eax, 0FFFFFFFFh
0x180030c45  jz      short loc_180030BEF
0x180030c47  mov     [rbp+0A0h+NumberOfBytesRead], r13d
0x180030c4b  mov     eax, [rsp+0E0h+var_E0]
0x180030c4e  mov     eax, 110h
0x180030c53  sub     rsp, rax
0x180030c56  lea     rsi, [rsp+1F0h+var_1B0]
0x180030c5b  mov     eax, [rsi]
0x180030c5d  mov     [rsp+1F0h+lpOverlapped], r13; lpOverlapped
0x180030c62  lea     r9, [rbp+0A0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180030c66  mov     r8d, 108h; nNumberOfBytesToRead
0x180030c6c  mov     rdx, rsi; lpBuffer
0x180030c6f  mov     rcx, rdi; hFile
0x180030c72  call    cs:__imp_ReadFile
0x180030c78  test    eax, eax
0x180030c7a  jz      loc_180030DEE
0x180030c80  cmp     [rbp+0A0h+NumberOfBytesRead], 108h
0x180030c87  jnz     loc_180030DEE
0x180030c8d  cmp     dword ptr [rsi], 4550h
0x180030c93  jnz     loc_180030DEE
0x180030c99  mov     eax, 10Bh
0x180030c9e  cmp     [rsi+18h], ax
0x180030ca2  jnz     loc_180030DB4
0x180030ca8  cmp     [rsi+0E8h], r13d
0x180030caf  jz      loc_180030DEE
0x180030cb5  cmp     [rsi+0ECh], r13d
0x180030cbc  jz      loc_180030DEE
0x180030cc2  mov     [r15], r12d
0x180030cc5  test    r14, r14
0x180030cc8  jz      loc_180030DEE
0x180030cce  cmp     dword ptr [rsi+0ECh], 48h ; 'H'
0x180030cd5  jb      loc_180030DD9
0x180030cdb  mov     [r14], r12d
0x180030cde  mov     [rsp+1F0h+lpName], r13; lpName
0x180030ce3  mov     dword ptr [rsp+1F0h+lpOverlapped], r13d; dwMaximumSizeLow
0x180030ce8  xor     r9d, r9d; dwMaximumSizeHigh
0x180030ceb  xor     edx, edx; lpFileMappingAttributes
0x180030ced  lea     r8d, [r9+2]; flProtect
0x180030cf1  mov     rcx, rdi; hFile
0x180030cf4  call    cs:__imp_CreateFileMappingW
0x180030cfa  mov     r12, rax
0x180030cfd  test    rax, rax
0x180030d00  jz      loc_180030BEF
0x180030d06  mov     [rsp+1F0h+lpOverlapped], r13; dwNumberOfBytesToMap
0x180030d0b  xor     r9d, r9d; dwFileOffsetLow
0x180030d0e  xor     r8d, r8d; dwFileOffsetHigh
0x180030d11  lea     edx, [r9+4]; dwDesiredAccess
0x180030d15  mov     rcx, rax; hFileMappingObject
0x180030d18  call    cs:__imp_MapViewOfFile
0x180030d1e  mov     r15, rax
0x180030d21  mov     [rbp+0A0h+var_88], rax
0x180030d25  mov     rcx, r12; hObject
0x180030d28  call    cs:__imp_CloseHandle
0x180030d2e  test    r15, r15
0x180030d31  jz      loc_180030BEF
0x180030d37  movsxd  rcx, [rbp+0A0h+var_44]
0x180030d3b  add     rcx, r15; NtHeader
0x180030d3e  xor     r9d, r9d; SectionHeader
0x180030d41  mov     r8d, [rsi+0E8h]; Rva
0x180030d48  mov     rdx, r15; BaseAddress
0x180030d4b  call    cs:__imp_RtlImageRvaToVa
0x180030d51  test    rax, rax
0x180030d54  jz      short loc_180030D72
0x180030d56  mov     ecx, 2
0x180030d5b  cmp     [rax+4], cx
0x180030d5f  jb      short loc_180030D6D
0x180030d61  cmp     word ptr [rax+6], 5
0x180030d66  jb      short loc_180030D6D
0x180030d68  test    [rax+10h], cl
0x180030d6b  jz      short loc_180030D97
0x180030d6d  mov     [r14], r13d
0x180030d70  jmp     short loc_180030D97
0x180030d72  call    cs:__imp_GetLastError
0x180030d78  mov     ebx, eax
0x180030d7a  test    eax, eax
0x180030d7c  jle     short loc_180030D87
0x180030d7e  movzx   ebx, ax
0x180030d81  or      ebx, 80070000h
0x180030d87  mov     [rbp+0A0h+var_9C], ebx
0x180030d8a  mov     eax, 80004005h
0x180030d8f  test    ebx, ebx
0x180030d91  cmovns  ebx, eax
0x180030d94  mov     [rbp+0A0h+var_9C], ebx
0x180030d97  jmp     short loc_180030DA9
0x180030d99  mov     ebx, 80070002h
0x180030d9e  mov     [rbp+0A0h+var_9C], ebx
0x180030da1  mov     rdi, [rbp+0A0h+var_90]
0x180030da5  mov     r15, [rbp+0A0h+var_88]
0x180030da9  mov     rcx, r15; lpBaseAddress
0x180030dac  call    cs:__imp_UnmapViewOfFile
0x180030db2  jmp     short loc_180030DEE
0x180030db4  mov     eax, 20Bh
0x180030db9  cmp     [rsi+18h], ax
0x180030dbd  jnz     short loc_180030DEE
0x180030dbf  cmp     [rsi+0F8h], r13d
0x180030dc6  jz      short loc_180030DEE
0x180030dc8  cmp     [rsi+0FCh], r13d
0x180030dcf  jz      short loc_180030DEE
0x180030dd1  mov     [r15], r12d
0x180030dd4  test    r14, r14
0x180030dd7  jz      short loc_180030DEE
0x180030dd9  mov     [r14], r13d
0x180030ddc  jmp     short loc_180030DEE
0x180030dde  mov     ebx, 8000FFFFh
0x180030de3  jmp     short loc_180030DEE
0x180030de5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180030de9  mov     ebx, 80070057h
0x180030dee  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180030df2  jz      short loc_180030DFD
0x180030df4  mov     rcx, rdi; hObject
0x180030df7  call    cs:__imp_CloseHandle
0x180030dfd  mov     eax, ebx
0x180030dff  mov     rcx, [rbp+0A0h+var_40]
0x180030e03  xor     rcx, rbp; StackCookie
0x180030e06  call    __security_check_cookie
0x180030e0b  mov     rbx, [rbp+0A0h+arg_18]
0x180030e12  lea     rsp, [rbp+70h]
0x180030e16  pop     r15
0x180030e18  pop     r14
0x180030e1a  pop     r13
0x180030e1c  pop     r12
0x180030e1e  pop     rdi
0x180030e1f  pop     rsi
0x180030e20  pop     rbp
0x180030e21  retn
0x180056baf  push    rbp
0x180056bb1  sub     rsp, 40h
0x180056bb5  lea     rbp, [rdx+40h]
0x180056bb9  mov     rax, [rcx]
0x180056bbc  xor     ecx, ecx
0x180056bbe  cmp     dword ptr [rax], 0C0000006h
0x180056bc4  setz    cl
0x180056bc7  mov     eax, ecx
0x180056bc9  add     rsp, 40h
0x180056bcd  pop     rbp
0x180056bce  retn
```
