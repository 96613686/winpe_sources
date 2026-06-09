# io_OpenFile

- ea: `0x18002d84c`
- end: `0x18002d986`
- name: `io_OpenFile`
- size: `314`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002d1e0`

## callees

- `0x18002d728`
- `0x18002d84c`
- `0x180031070`

## import_xrefs

- `msvcrt!malloc` at `0x18002d876`
- `msvcrt!malloc` at `0x18002d876`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d8eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d8eb`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18002d8d2`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18002d8d2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002d955`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002d955`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002d929`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002d929`
- `KERNEL32!CreateFileMappingA` at `0x18002d908`
- `KERNEL32!CreateFileMappingA` at `0x18002d908`

## pseudocode

```c
void **__fastcall io_OpenFile(LPCSTR lpFileName)
{
  void **v2; // rax
  void **v3; // rbx
  HANDLE v4; // rax
  HANDLE FileMappingA; // rax
  char *v6; // rax
  void *v7; // rcx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-28h] BYREF

  *(&SecurityAttributes.nLength + 1) = 0;
  v2 = (void **)malloc(0x30u);
  v3 = v2;
  if ( v2 )
  {
    *v2 = 0;
    v2[1] = 0;
    v2[2] = 0;
    v2[3] = 0;
    *((_DWORD *)v2 + 10) = 0;
    *((_BYTE *)v2 + 44) = 0;
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = 0;
    SecurityAttributes.bInheritHandle = 0;
    v4 = CreateFileA(lpFileName, 0x80000000, 1u, &SecurityAttributes, 3u, 1u, 0);
    *v3 = v4;
    if ( v4 == (HANDLE)-1LL )
    {
      io_CloseFile(v3);
      SetLastError(0);
    }
    else
    {
      FileMappingA = CreateFileMappingA(v4, 0, 2u, 0, 0, 0);
      v3[1] = FileMappingA;
      if ( FileMappingA )
      {
        v6 = (char *)MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
        v3[2] = v6;
        if ( v6 )
        {
          v7 = *v3;
          v3[3] = v6;
          v3[4] = v6;
          v3[4] = &v6[GetFileSize(v7, 0)];
          return v3;
        }
      }
      io_CloseFile(v3);
    }
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18002d84c  mov     [rsp+arg_8], rbx
0x18002d851  mov     [rsp+arg_10], rsi
0x18002d856  push    rdi
0x18002d857  sub     rsp, 60h
0x18002d85b  mov     rax, cs:__security_cookie
0x18002d862  xor     rax, rsp
0x18002d865  mov     [rsp+68h+var_10], rax
0x18002d86a  xor     esi, esi
0x18002d86c  mov     rdi, rcx
0x18002d86f  mov     dword ptr [rsp+68h+SecurityAttributes+4], esi
0x18002d873  lea     ecx, [rsi+30h]; Size
0x18002d876  call    cs:__imp_malloc
0x18002d87c  mov     rbx, rax
0x18002d87f  test    rax, rax
0x18002d882  jz      loc_18002D964
0x18002d888  mov     [rax], rsi
0x18002d88b  lea     r8d, [rsi+1]; dwShareMode
0x18002d88f  mov     [rax+8], rsi
0x18002d893  lea     r9, [rsp+68h+SecurityAttributes]; lpSecurityAttributes
0x18002d898  mov     [rax+10h], rsi
0x18002d89c  mov     edx, 80000000h; dwDesiredAccess
0x18002d8a1  mov     [rax+18h], rsi
0x18002d8a5  mov     rcx, rdi; lpFileName
0x18002d8a8  mov     [rax+28h], esi
0x18002d8ab  mov     [rax+2Ch], sil
0x18002d8af  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x18002d8b4  mov     [rsp+68h+dwFlagsAndAttributes], r8d; dwFlagsAndAttributes
0x18002d8b9  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d8c1  mov     [rsp+68h+SecurityAttributes.nLength], 18h
0x18002d8c9  mov     [rsp+68h+SecurityAttributes.lpSecurityDescriptor], rsi
0x18002d8ce  mov     [rsp+68h+SecurityAttributes.bInheritHandle], esi
0x18002d8d2  call    cs:__imp_CreateFileA
0x18002d8d8  mov     [rbx], rax
0x18002d8db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d8df  jnz     short loc_18002D8F3
0x18002d8e1  mov     rcx, rbx; Block
0x18002d8e4  call    io_CloseFile
0x18002d8e9  xor     ecx, ecx; dwErrCode
0x18002d8eb  call    cs:__imp_SetLastError
0x18002d8f1  jmp     short loc_18002D943
0x18002d8f3  xor     r9d, r9d; dwMaximumSizeHigh
0x18002d8f6  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi; lpName
0x18002d8fb  xor     edx, edx; lpFileMappingAttributes
0x18002d8fd  mov     [rsp+68h+dwCreationDisposition], esi; dwMaximumSizeLow
0x18002d901  mov     rcx, rax; hFile
0x18002d904  lea     r8d, [r9+2]; flProtect
0x18002d908  call    cs:__imp_CreateFileMappingA
0x18002d90e  mov     [rbx+8], rax
0x18002d912  test    rax, rax
0x18002d915  jz      short loc_18002D93B
0x18002d917  xor     r9d, r9d; dwFileOffsetLow
0x18002d91a  mov     qword ptr [rsp+68h+dwCreationDisposition], rsi; dwNumberOfBytesToMap
0x18002d91f  xor     r8d, r8d; dwFileOffsetHigh
0x18002d922  mov     rcx, rax; hFileMappingObject
0x18002d925  lea     edx, [r9+4]; dwDesiredAccess
0x18002d929  call    cs:__imp_MapViewOfFile
0x18002d92f  mov     [rbx+10h], rax
0x18002d933  mov     rdi, rax
0x18002d936  test    rax, rax
0x18002d939  jnz     short loc_18002D948
0x18002d93b  mov     rcx, rbx; Block
0x18002d93e  call    io_CloseFile
0x18002d943  mov     rbx, rsi
0x18002d946  jmp     short loc_18002D964
0x18002d948  mov     rcx, [rbx]; hFile
0x18002d94b  xor     edx, edx; lpFileSizeHigh
0x18002d94d  mov     [rbx+18h], rdi
0x18002d951  mov     [rbx+20h], rdi
0x18002d955  call    cs:__imp_GetFileSize
0x18002d95b  mov     eax, eax
0x18002d95d  add     rax, rdi
0x18002d960  mov     [rbx+20h], rax
0x18002d964  mov     rax, rbx
0x18002d967  mov     rcx, [rsp+68h+var_10]
0x18002d96c  xor     rcx, rsp; StackCookie
0x18002d96f  call    __security_check_cookie
0x18002d974  lea     r11, [rsp+68h+var_8]
0x18002d979  mov     rbx, [r11+18h]
0x18002d97d  mov     rsi, [r11+20h]
0x18002d981  mov     rsp, r11
0x18002d984  pop     rdi
0x18002d985  retn
```
