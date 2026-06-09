# OROpenHiveInternal

- ea: `0x18003b6f4`
- end: `0x18003b912`
- name: `OROpenHiveInternal`
- size: `542`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002c09c`
- `0x18002d9b0`

## callees

- `0x180003166`
- `0x180003172`
- `0x180039028`
- `0x18003b660`
- `0x18003b6f4`
- `0x18003d768`
- `0x18003e93c`
- `0x18003e97c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003b794`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18003b794`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003b80a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003b80a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b862`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b862`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b891`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b873`

## string_xrefs

- `0x18003b85b`: `ntdll.dll`
- `0x18003b887`: `RtlValidRelativeSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall OROpenHiveInternal(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  char v5; // r14
  HANDLE v7; // rsi
  char v8; // r15
  HANDLE v9; // rdi
  DWORD LastError; // ebx
  __int64 v11; // r8
  unsigned int v12; // r14d
  DWORD v13; // eax
  DWORD LowPart; // ebx
  void *v15; // rax
  HMODULE ModuleHandleW; // rax
  HANDLE hFile[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp+40h] BYREF
  int v20; // [rsp+84h] [rbp+44h]
  union _LARGE_INTEGER FileSize; // [rsp+98h] [rbp+58h] BYREF

  v20 = HIDWORD(a1);
  hFile[0] = 0;
  v5 = a3;
  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  v7 = 0;
  *(_QWORD *)a4 = 0;
  v8 = 0;
  v9 = 0;
  if ( !a2 || (a3 & 0xFFFFFFFE) != 0 )
  {
    LastError = 87;
    goto LABEL_24;
  }
  LastError = ORStart();
  if ( !LastError )
  {
    v12 = v5 & 1;
    v13 = ORCreateFile(a2, 2 * (v12 ^ 1) + 1, v11, v12, hFile);
    v7 = hFile[0];
    LastError = v13;
    if ( !v13 )
    {
      v8 = 1;
      if ( GetFileSizeEx(hFile[0], &FileSize) || (LastError = GetLastError()) == 0 )
      {
        LowPart = FileSize.LowPart;
        if ( FileSize.LowPart <= 0x1000 || FileSize.HighPart )
        {
          LastError = 1009;
          goto LABEL_24;
        }
        v15 = o__aligned_malloc_0(FileSize.LowPart, 0x10u);
        hFile[0] = v15;
        v9 = v15;
        if ( !v15 )
        {
          LastError = 8;
          goto LABEL_24;
        }
        if ( ReadFile(v7, v15, LowPart, &NumberOfBytesRead, 0) || (LastError = GetLastError()) == 0 )
        {
          LastError = ValidateHiveAndRecoverFromLog(hFile, &FileSize, a2, v7);
          if ( !LastError )
          {
            if ( v12 )
            {
              ORCloseFile(v7);
              v7 = 0;
              v8 = 0;
            }
            ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
            if ( ModuleHandleW )
            {
              ORValidRelativeSecurityDescriptor = (__int64)GetProcAddress(
                                                             ModuleHandleW,
                                                             "RtlValidRelativeSecurityDescriptor");
              if ( ORValidRelativeSecurityDescriptor )
              {
                v9 = 0;
                LastError = OROpenHiveFromMemoryInternal(hFile[0]);
                if ( !LastError )
                {
                  v8 = 0;
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a4 + 16LL) + 128LL) = v7;
                }
                goto LABEL_24;
              }
            }
            LastError = GetLastError();
          }
          v9 = hFile[0];
        }
      }
    }
  }
LABEL_24:
  if ( v9 )
    aligned_free(v9);
  if ( v8 )
    ORCloseFile(v7);
  return LastError;
}

```

## disassembly

```asm
0x18003b6f4  mov     [rsp-38h+arg_8], rbx
0x18003b6f9  mov     qword ptr [rsp-38h+NumberOfBytesRead], rcx
0x18003b6fe  push    rbp
0x18003b6ff  push    rsi
0x18003b700  push    rdi
0x18003b701  push    r12
0x18003b703  push    r13
0x18003b705  push    r14
0x18003b707  push    r15
0x18003b709  mov     rbp, rsp
0x18003b70c  sub     rsp, 40h
0x18003b710  xor     ebx, ebx
0x18003b712  mov     r13, r9
0x18003b715  mov     [rbp+hFile], rbx
0x18003b719  mov     r14d, r8d
0x18003b71c  mov     [rbp+NumberOfBytesRead], ebx
0x18003b71f  mov     r12, rdx
0x18003b722  mov     qword ptr [rbp+FileSize], rbx
0x18003b726  mov     esi, ebx
0x18003b728  mov     [r9], rbx
0x18003b72b  mov     r15b, bl
0x18003b72e  mov     edi, ebx
0x18003b730  test    rdx, rdx
0x18003b733  jnz     short loc_18003B73F
0x18003b735  mov     ebx, 57h ; 'W'
0x18003b73a  jmp     loc_18003B8DD
0x18003b73f  test    r14d, 0FFFFFFFEh
0x18003b746  jnz     short loc_18003B735
0x18003b748  call    ORStart
0x18003b74d  mov     ebx, eax
0x18003b74f  test    eax, eax
0x18003b751  jnz     loc_18003B8DD
0x18003b757  and     r14d, 1
0x18003b75b  lea     rax, [rbp+hFile]
0x18003b75f  mov     edx, r14d
0x18003b762  mov     [rsp+40h+lpOverlapped], rax
0x18003b767  xor     edx, 1
0x18003b76a  mov     r9d, r14d
0x18003b76d  mov     rcx, r12
0x18003b770  lea     edx, ds:1[rdx*2]
0x18003b777  call    ORCreateFile
0x18003b77c  mov     rsi, [rbp+hFile]
0x18003b780  mov     ebx, eax
0x18003b782  test    eax, eax
0x18003b784  jnz     loc_18003B8DD
0x18003b78a  lea     rdx, [rbp+FileSize]; lpFileSize
0x18003b78e  mov     rcx, rsi; hFile
0x18003b791  mov     r15b, 1
0x18003b794  call    cs:__imp_GetFileSizeEx
0x18003b79b  nop     dword ptr [rax+rax+00h]
0x18003b7a0  test    eax, eax
0x18003b7a2  jnz     short loc_18003B7BA
0x18003b7a4  call    cs:__imp_GetLastError
0x18003b7ab  nop     dword ptr [rax+rax+00h]
0x18003b7b0  mov     ebx, eax
0x18003b7b2  test    eax, eax
0x18003b7b4  jnz     loc_18003B8DD
0x18003b7ba  mov     rbx, qword ptr [rbp+FileSize]
0x18003b7be  cmp     ebx, 1000h
0x18003b7c4  jbe     loc_18003B8D8
0x18003b7ca  cmp     dword ptr [rbp+FileSize+4], edi
0x18003b7cd  jnz     loc_18003B8D8
0x18003b7d3  mov     edx, 10h; Alignment
0x18003b7d8  mov     rcx, rbx; Size
0x18003b7db  call    _o__aligned_malloc_0
0x18003b7e0  mov     [rbp+hFile], rax
0x18003b7e4  mov     rdi, rax
0x18003b7e7  test    rax, rax
0x18003b7ea  jnz     short loc_18003B7F4
0x18003b7ec  lea     ebx, [rax+8]
0x18003b7ef  jmp     loc_18003B8DD
0x18003b7f4  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003b7f8  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x18003b801  mov     r8d, ebx; nNumberOfBytesToRead
0x18003b804  mov     rdx, rax; lpBuffer
0x18003b807  mov     rcx, rsi; hFile
0x18003b80a  call    cs:__imp_ReadFile
0x18003b811  nop     dword ptr [rax+rax+00h]
0x18003b816  test    eax, eax
0x18003b818  jnz     short loc_18003B830
0x18003b81a  call    cs:__imp_GetLastError
0x18003b821  nop     dword ptr [rax+rax+00h]
0x18003b826  mov     ebx, eax
0x18003b828  test    eax, eax
0x18003b82a  jnz     loc_18003B8DD
0x18003b830  mov     r9, rsi
0x18003b833  lea     rdx, [rbp+FileSize]
0x18003b837  mov     r8, r12
0x18003b83a  lea     rcx, [rbp+hFile]
0x18003b83e  call    ValidateHiveAndRecoverFromLog
0x18003b843  mov     ebx, eax
0x18003b845  test    eax, eax
0x18003b847  jnz     short loc_18003B881
0x18003b849  test    r14d, r14d
0x18003b84c  jz      short loc_18003B85B
0x18003b84e  mov     rcx, rsi
0x18003b851  call    ORCloseFile
0x18003b856  xor     esi, esi
0x18003b858  xor     r15b, r15b
0x18003b85b  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18003b862  call    cs:__imp_GetModuleHandleW
0x18003b869  nop     dword ptr [rax+rax+00h]
0x18003b86e  test    rax, rax
0x18003b871  jnz     short loc_18003B887
0x18003b873  call    cs:__imp_GetLastError
0x18003b87a  nop     dword ptr [rax+rax+00h]
0x18003b87f  mov     ebx, eax
0x18003b881  mov     rdi, [rbp+hFile]
0x18003b885  jmp     short loc_18003B8DD
0x18003b887  lea     rdx, aRtlvalidrelati; "RtlValidRelativeSecurityDescriptor"
0x18003b88e  mov     rcx, rax; hModule
0x18003b891  call    cs:__imp_GetProcAddress
0x18003b898  nop     dword ptr [rax+rax+00h]
0x18003b89d  mov     cs:ORValidRelativeSecurityDescriptor, rax
0x18003b8a4  test    rax, rax
0x18003b8a7  jz      short loc_18003B873
0x18003b8a9  mov     rdx, qword ptr [rbp+FileSize]
0x18003b8ad  mov     r9, r13
0x18003b8b0  mov     rcx, [rbp+hFile]; Block
0x18003b8b4  mov     r8, r12
0x18003b8b7  call    OROpenHiveFromMemoryInternal
0x18003b8bc  xor     edi, edi
0x18003b8be  mov     ebx, eax
0x18003b8c0  test    eax, eax
0x18003b8c2  jnz     short loc_18003B8DD
0x18003b8c4  mov     rax, [r13+0]
0x18003b8c8  xor     r15b, r15b
0x18003b8cb  mov     rcx, [rax+10h]
0x18003b8cf  mov     [rcx+80h], rsi
0x18003b8d6  jmp     short loc_18003B8DD
0x18003b8d8  mov     ebx, 3F1h
0x18003b8dd  test    rdi, rdi
0x18003b8e0  jz      short loc_18003B8EA
0x18003b8e2  mov     rcx, rdi; Block
0x18003b8e5  call    _aligned_free
0x18003b8ea  test    r15b, r15b
0x18003b8ed  jz      short loc_18003B8F7
0x18003b8ef  mov     rcx, rsi
0x18003b8f2  call    ORCloseFile
0x18003b8f7  mov     eax, ebx
0x18003b8f9  mov     rbx, [rsp+40h+arg_8]
0x18003b901  add     rsp, 40h
0x18003b905  pop     r15
0x18003b907  pop     r14
0x18003b909  pop     r13
0x18003b90b  pop     r12
0x18003b90d  pop     rdi
0x18003b90e  pop     rsi
0x18003b90f  pop     rbp
0x18003b910  retn
```
