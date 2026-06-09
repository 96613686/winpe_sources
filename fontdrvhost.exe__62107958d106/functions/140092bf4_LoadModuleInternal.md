# LoadModuleInternal

- ea: `0x140092bf4`
- end: `0x140092d71`
- name: `LoadModuleInternal`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14007e568`

## callees

- `0x140075de0`
- `0x1400927b8`
- `0x140092bac`
- `0x140092bf4`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x140092d0d`
- `KERNEL32!MapViewOfFile` at `0x140092d0d`
- `KERNEL32!CreateFileMappingW` at `0x140092cd8`
- `KERNEL32!CreateFileMappingW` at `0x140092cd8`
- `KERNEL32!SetFileInformationByHandle` at `0x140092c8e`
- `KERNEL32!SetFileInformationByHandle` at `0x140092c8e`
- `KERNEL32!GetFileInformationByHandle` at `0x140092c64`
- `KERNEL32!GetFileInformationByHandle` at `0x140092c64`
- `KERNEL32!GetProcessHeap` at `0x140092d1c`
- `KERNEL32!GetProcessHeap` at `0x140092d1c`
- `KERNEL32!HeapAlloc` at `0x140092d2b`
- `KERNEL32!HeapAlloc` at `0x140092d2b`

## pseudocode

```c
_OWORD *__fastcall LoadModuleInternal(__int64 a1, unsigned int a2, int a3)
{
  void *v5; // rsi
  DWORD nFileSizeLow; // ebx
  HANDLE FileMappingW; // rax
  HANDLE ProcessHeap; // rax
  _OWORD *result; // rax
  __int128 v10; // xmm1
  __int64 v11; // [rsp+30h] [rbp-29h] BYREF
  __int128 v12; // [rsp+38h] [rbp-21h] BYREF
  __int128 v13; // [rsp+48h] [rbp-11h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+58h] [rbp-1h] BYREF

  v11 = 0;
  v12 = 0;
  v13 = 0;
  *(_QWORD *)&v12 = EngCreateFile(a1, 7);
  v5 = (void *)v12;
  if ( (_QWORD)v12 == -1 )
    return 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle((HANDLE)v12, &FileInformation) )
  {
    if ( a3 || !a2 )
    {
      nFileSizeLow = FileInformation.nFileSizeLow;
      goto LABEL_8;
    }
    v11 = a2;
    if ( SetFileInformationByHandle((HANDLE)v12, FileEndOfFileInfo, &v11, 8u) )
    {
      nFileSizeLow = v11;
      FileInformation.nFileSizeLow = v11;
      FileInformation.nFileSizeHigh = 0;
LABEL_8:
      DWORD2(v13) = nFileSizeLow;
      FileMappingW = CreateFileMappingW(v5, 0, a3 != 0 ? 134217730 : 134217732, 0, 0, 0);
      *((_QWORD *)&v12 + 1) = FileMappingW;
      if ( FileMappingW )
      {
        if ( !FileInformation.nFileSizeHigh )
        {
          if ( nFileSizeLow )
          {
            *(_QWORD *)&v13 = MapViewOfFile(FileMappingW, a3 != 0 ? 4 : 2, 0, 0, 0);
            if ( (_QWORD)v13 )
            {
              ProcessHeap = GetProcessHeap();
              result = HeapAlloc(ProcessHeap, 0, 0x20u);
              if ( result )
              {
                v10 = v13;
                *result = v12;
                result[1] = v10;
                return result;
              }
            }
          }
        }
      }
    }
  }
  FileViewCleanupInternal(&v12);
  return 0;
}

```

## disassembly

```asm
0x140092bf4  mov     [rsp-8+arg_0], rbx
0x140092bf9  push    rbp
0x140092bfa  push    rsi
0x140092bfb  push    rdi
0x140092bfc  lea     rbp, [rsp-47h]
0x140092c01  sub     rsp, 0A0h
0x140092c08  mov     rax, cs:__security_cookie
0x140092c0f  xor     rax, rsp
0x140092c12  mov     [rbp+57h+var_20], rax
0x140092c16  xorps   xmm0, xmm0
0x140092c19  mov     [rbp+57h+var_80], 0
0x140092c21  mov     ebx, edx
0x140092c23  mov     edi, r8d
0x140092c26  mov     edx, 7
0x140092c2b  movups  [rbp+57h+var_78], xmm0
0x140092c2f  movups  [rbp+57h+var_68], xmm0
0x140092c33  call    EngCreateFile
0x140092c38  mov     qword ptr [rbp+57h+var_78], rax
0x140092c3c  mov     rsi, rax
0x140092c3f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140092c43  jz      loc_140092D50
0x140092c49  xorps   xmm0, xmm0
0x140092c4c  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x140092c50  xor     eax, eax
0x140092c52  mov     rcx, rsi; hFile
0x140092c55  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x140092c59  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x140092c5c  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x140092c60  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x140092c64  call    cs:__imp_GetFileInformationByHandle
0x140092c6a  test    eax, eax
0x140092c6c  jz      loc_140092D47
0x140092c72  test    edi, edi
0x140092c74  jnz     short loc_140092CA7
0x140092c76  test    ebx, ebx
0x140092c78  jz      short loc_140092CA7
0x140092c7a  lea     r9d, [rdi+8]; dwBufferSize
0x140092c7e  mov     dword ptr [rbp+57h+var_80], ebx
0x140092c81  lea     r8, [rbp+57h+var_80]; lpFileInformation
0x140092c85  mov     dword ptr [rbp+57h+var_80+4], edi
0x140092c88  lea     edx, [rdi+6]; FileInformationClass
0x140092c8b  mov     rcx, rsi; hFile
0x140092c8e  call    cs:__imp_SetFileInformationByHandle
0x140092c94  test    eax, eax
0x140092c96  jz      loc_140092D47
0x140092c9c  mov     ebx, dword ptr [rbp+57h+var_80]
0x140092c9f  mov     [rbp+57h+FileInformation.nFileSizeLow], ebx
0x140092ca2  mov     [rbp+57h+FileInformation.nFileSizeHigh], edi
0x140092ca5  jmp     short loc_140092CAA
0x140092ca7  mov     ebx, [rbp+57h+FileInformation.nFileSizeLow]
0x140092caa  mov     eax, edi
0x140092cac  mov     [rsp+0B0h+lpName], 0; lpName
0x140092cb5  neg     eax
0x140092cb7  mov     dword ptr [rbp+57h+var_68+8], ebx
0x140092cba  mov     rcx, rsi; hFile
0x140092cbd  mov     [rsp+0B0h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x140092cc5  sbb     r8d, r8d
0x140092cc8  xor     r9d, r9d; dwMaximumSizeHigh
0x140092ccb  and     r8d, 0FFFFFFFEh
0x140092ccf  xor     edx, edx; lpFileMappingAttributes
0x140092cd1  add     r8d, 8000004h; flProtect
0x140092cd8  call    cs:__imp_CreateFileMappingW
0x140092cde  mov     qword ptr [rbp+57h+var_78+8], rax
0x140092ce2  test    rax, rax
0x140092ce5  jz      short loc_140092D47
0x140092ce7  cmp     [rbp+57h+FileInformation.nFileSizeHigh], 0
0x140092ceb  jnz     short loc_140092D47
0x140092ced  test    ebx, ebx
0x140092cef  jz      short loc_140092D47
0x140092cf1  neg     edi
0x140092cf3  mov     qword ptr [rsp+0B0h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x140092cfc  mov     rcx, rax; hFileMappingObject
0x140092cff  sbb     edx, edx
0x140092d01  xor     r9d, r9d; dwFileOffsetLow
0x140092d04  and     edx, 2
0x140092d07  xor     r8d, r8d; dwFileOffsetHigh
0x140092d0a  add     edx, 2; dwDesiredAccess
0x140092d0d  call    cs:__imp_MapViewOfFile
0x140092d13  mov     qword ptr [rbp+57h+var_68], rax
0x140092d17  test    rax, rax
0x140092d1a  jz      short loc_140092D47
0x140092d1c  call    cs:__imp_GetProcessHeap
0x140092d22  xor     edx, edx; dwFlags
0x140092d24  mov     rcx, rax; hHeap
0x140092d27  lea     r8d, [rdx+20h]; dwBytes
0x140092d2b  call    cs:__imp_HeapAlloc
0x140092d31  test    rax, rax
0x140092d34  jz      short loc_140092D47
0x140092d36  movups  xmm0, [rbp+57h+var_78]
0x140092d3a  movups  xmm1, [rbp+57h+var_68]
0x140092d3e  movups  xmmword ptr [rax], xmm0
0x140092d41  movups  xmmword ptr [rax+10h], xmm1
0x140092d45  jmp     short loc_140092D52
0x140092d47  lea     rcx, [rbp+57h+var_78]
0x140092d4b  call    FileViewCleanupInternal
0x140092d50  xor     eax, eax
0x140092d52  mov     rcx, [rbp+57h+var_20]
0x140092d56  xor     rcx, rsp; StackCookie
0x140092d59  call    __security_check_cookie
0x140092d5e  mov     rbx, [rsp+0B0h+arg_0]
0x140092d66  add     rsp, 0A0h
0x140092d6d  pop     rdi
0x140092d6e  pop     rsi
0x140092d6f  pop     rbp
0x140092d70  retn
```
