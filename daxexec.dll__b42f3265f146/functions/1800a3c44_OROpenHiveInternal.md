# OROpenHiveInternal

- ea: `0x1800a3c44`
- end: `0x1800a3e3e`
- name: `OROpenHiveInternal`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005cfec`

## callees

- `0x180005886`
- `0x180005892`
- `0x1800a3bb0`
- `0x1800a3c44`
- `0x1800a570c`
- `0x1800a6a08`
- `0x1800a7bd8`
- `0x1800a7c18`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a3d94`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a3d94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3dc3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a3dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3cdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3da5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a3ccb`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800a3ccb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a3d41`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800a3d41`

## string_xrefs

- `0x1800a3d88`: `ntdll.dll`
- `0x1800a3db9`: `RtlValidRelativeSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall OROpenHiveInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HANDLE v4; // rsi
  char v5; // r14
  HANDLE v6; // rdi
  DWORD LastError; // ebx
  DWORD LowPart; // ebx
  void *v11; // rax
  HMODULE ModuleHandleW; // rax
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp+40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+50h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+58h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  hFile = 0;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  *(_QWORD *)a4 = 0;
  if ( !a2 )
  {
    LastError = 87;
    goto LABEL_22;
  }
  LastError = ORStart();
  if ( !LastError )
  {
    LastError = ORCreateFile(a2, 1, 3, 1, &hFile);
    if ( LastError )
    {
      v4 = hFile;
      goto LABEL_22;
    }
    v5 = 1;
    v4 = hFile;
    if ( GetFileSizeEx(hFile, &FileSize) || (LastError = GetLastError()) == 0 )
    {
      LowPart = FileSize.LowPart;
      if ( FileSize.LowPart <= 0x1000 || FileSize.HighPart )
      {
        LastError = 1009;
        goto LABEL_22;
      }
      v11 = o__aligned_malloc_0(FileSize.LowPart, 0x10u);
      hFile = v11;
      v6 = v11;
      if ( !v11 )
      {
        LastError = 8;
        goto LABEL_22;
      }
      if ( ReadFile(v4, v11, LowPart, &NumberOfBytesRead, 0) || (LastError = GetLastError()) == 0 )
      {
        LastError = ValidateHiveAndRecoverFromLog(&hFile, &FileSize, a2, v4);
        if ( !LastError )
        {
          ORCloseFile(v4);
          v4 = 0;
          v5 = 0;
          ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
          if ( ModuleHandleW )
          {
            ORValidRelativeSecurityDescriptor = (__int64)GetProcAddress(
                                                           ModuleHandleW,
                                                           "RtlValidRelativeSecurityDescriptor");
            if ( ORValidRelativeSecurityDescriptor )
            {
              v6 = 0;
              LastError = OROpenHiveFromMemoryInternal(hFile);
              if ( !LastError )
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a4 + 16LL) + 128LL) = 0;
              goto LABEL_22;
            }
          }
          LastError = GetLastError();
        }
        v6 = hFile;
      }
    }
  }
LABEL_22:
  if ( v6 )
    aligned_free(v6);
  if ( v5 )
    ORCloseFile(v4);
  return LastError;
}

```

## disassembly

```asm
0x1800a3c44  mov     [rsp-38h+NumberOfBytesRead], r8d
0x1800a3c49  mov     qword ptr [rsp-38h+FileSize], rcx
0x1800a3c4e  push    rbp
0x1800a3c4f  push    rbx
0x1800a3c50  push    rsi
0x1800a3c51  push    rdi
0x1800a3c52  push    r12
0x1800a3c54  push    r14
0x1800a3c56  push    r15
0x1800a3c58  mov     rbp, rsp
0x1800a3c5b  sub     rsp, 30h
0x1800a3c5f  xor     esi, esi
0x1800a3c61  xor     r14b, r14b
0x1800a3c64  xor     edi, edi
0x1800a3c66  mov     [rbp+hFile], rsi
0x1800a3c6a  mov     [rbp+NumberOfBytesRead], esi
0x1800a3c6d  mov     r12, r9
0x1800a3c70  mov     qword ptr [rbp+FileSize], rsi
0x1800a3c74  mov     r15, rdx
0x1800a3c77  mov     [r9], rsi
0x1800a3c7a  test    rdx, rdx
0x1800a3c7d  jnz     short loc_1800A3C87
0x1800a3c7f  lea     ebx, [rdx+57h]
0x1800a3c82  jmp     loc_1800A3E12
0x1800a3c87  call    ORStart
0x1800a3c8c  mov     ebx, eax
0x1800a3c8e  test    eax, eax
0x1800a3c90  jnz     loc_1800A3E12
0x1800a3c96  lea     esi, [rbx+1]
0x1800a3c99  mov     rcx, r15
0x1800a3c9c  lea     rax, [rbp+hFile]
0x1800a3ca0  mov     r9d, esi
0x1800a3ca3  mov     edx, esi
0x1800a3ca5  mov     [rsp+30h+lpOverlapped], rax
0x1800a3caa  lea     r8d, [rbx+3]
0x1800a3cae  call    ORCreateFile
0x1800a3cb3  mov     ebx, eax
0x1800a3cb5  test    eax, eax
0x1800a3cb7  jnz     loc_1800A3E0E
0x1800a3cbd  mov     r14b, sil
0x1800a3cc0  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800a3cc4  mov     rsi, [rbp+hFile]
0x1800a3cc8  mov     rcx, rsi; hFile
0x1800a3ccb  call    cs:__imp_GetFileSizeEx
0x1800a3cd2  nop     dword ptr [rax+rax+00h]
0x1800a3cd7  test    eax, eax
0x1800a3cd9  jnz     short loc_1800A3CF1
0x1800a3cdb  call    cs:__imp_GetLastError
0x1800a3ce2  nop     dword ptr [rax+rax+00h]
0x1800a3ce7  mov     ebx, eax
0x1800a3ce9  test    eax, eax
0x1800a3ceb  jnz     loc_1800A3E12
0x1800a3cf1  mov     rbx, qword ptr [rbp+FileSize]
0x1800a3cf5  cmp     ebx, 1000h
0x1800a3cfb  jbe     loc_1800A3E07
0x1800a3d01  cmp     dword ptr [rbp+FileSize+4], edi
0x1800a3d04  jnz     loc_1800A3E07
0x1800a3d0a  mov     edx, 10h; Alignment
0x1800a3d0f  mov     rcx, rbx; Size
0x1800a3d12  call    _o__aligned_malloc_0
0x1800a3d17  mov     [rbp+hFile], rax
0x1800a3d1b  mov     rdi, rax
0x1800a3d1e  test    rax, rax
0x1800a3d21  jnz     short loc_1800A3D2B
0x1800a3d23  lea     ebx, [rax+8]
0x1800a3d26  jmp     loc_1800A3E12
0x1800a3d2b  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800a3d2f  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x1800a3d38  mov     r8d, ebx; nNumberOfBytesToRead
0x1800a3d3b  mov     rdx, rax; lpBuffer
0x1800a3d3e  mov     rcx, rsi; hFile
0x1800a3d41  call    cs:__imp_ReadFile
0x1800a3d48  nop     dword ptr [rax+rax+00h]
0x1800a3d4d  test    eax, eax
0x1800a3d4f  jnz     short loc_1800A3D67
0x1800a3d51  call    cs:__imp_GetLastError
0x1800a3d58  nop     dword ptr [rax+rax+00h]
0x1800a3d5d  mov     ebx, eax
0x1800a3d5f  test    eax, eax
0x1800a3d61  jnz     loc_1800A3E12
0x1800a3d67  mov     r9, rsi
0x1800a3d6a  lea     rdx, [rbp+FileSize]
0x1800a3d6e  mov     r8, r15
0x1800a3d71  lea     rcx, [rbp+hFile]
0x1800a3d75  call    ValidateHiveAndRecoverFromLog
0x1800a3d7a  mov     ebx, eax
0x1800a3d7c  test    eax, eax
0x1800a3d7e  jnz     short loc_1800A3DB3
0x1800a3d80  mov     rcx, rsi
0x1800a3d83  call    ORCloseFile
0x1800a3d88  lea     rcx, ModuleName; "ntdll.dll"
0x1800a3d8f  xor     esi, esi
0x1800a3d91  xor     r14b, r14b
0x1800a3d94  call    cs:__imp_GetModuleHandleW
0x1800a3d9b  nop     dword ptr [rax+rax+00h]
0x1800a3da0  test    rax, rax
0x1800a3da3  jnz     short loc_1800A3DB9
0x1800a3da5  call    cs:__imp_GetLastError
0x1800a3dac  nop     dword ptr [rax+rax+00h]
0x1800a3db1  mov     ebx, eax
0x1800a3db3  mov     rdi, [rbp+hFile]
0x1800a3db7  jmp     short loc_1800A3E12
0x1800a3db9  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x1800a3dc0  mov     rcx, rax; hModule
0x1800a3dc3  call    cs:__imp_GetProcAddress
0x1800a3dca  nop     dword ptr [rax+rax+00h]
0x1800a3dcf  mov     cs:ORValidRelativeSecurityDescriptor, rax
0x1800a3dd6  test    rax, rax
0x1800a3dd9  jz      short loc_1800A3DA5
0x1800a3ddb  mov     rdx, qword ptr [rbp+FileSize]
0x1800a3ddf  mov     r9, r12
0x1800a3de2  mov     rcx, [rbp+hFile]; Block
0x1800a3de6  mov     r8, r15
0x1800a3de9  call    OROpenHiveFromMemoryInternal
0x1800a3dee  xor     edi, edi
0x1800a3df0  mov     ebx, eax
0x1800a3df2  test    eax, eax
0x1800a3df4  jnz     short loc_1800A3E12
0x1800a3df6  mov     rax, [r12]
0x1800a3dfa  mov     rcx, [rax+10h]
0x1800a3dfe  mov     [rcx+80h], rsi
0x1800a3e05  jmp     short loc_1800A3E12
0x1800a3e07  mov     ebx, 3F1h
0x1800a3e0c  jmp     short loc_1800A3E12
0x1800a3e0e  mov     rsi, [rbp+hFile]
0x1800a3e12  test    rdi, rdi
0x1800a3e15  jz      short loc_1800A3E1F
0x1800a3e17  mov     rcx, rdi; Block
0x1800a3e1a  call    _aligned_free
0x1800a3e1f  test    r14b, r14b
0x1800a3e22  jz      short loc_1800A3E2C
0x1800a3e24  mov     rcx, rsi
0x1800a3e27  call    ORCloseFile
0x1800a3e2c  mov     eax, ebx
0x1800a3e2e  add     rsp, 30h
0x1800a3e32  pop     r15
0x1800a3e34  pop     r14
0x1800a3e36  pop     r12
0x1800a3e38  pop     rdi
0x1800a3e39  pop     rsi
0x1800a3e3a  pop     rbx
0x1800a3e3b  pop     rbp
0x1800a3e3c  retn
```
