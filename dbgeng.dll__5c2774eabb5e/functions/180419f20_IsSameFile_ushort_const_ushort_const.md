# IsSameFile(ushort const *,ushort const *)

- ea: `0x180419f20`
- end: `0x18041a127`
- name: `?IsSameFile@@YAHPEBG0@Z`
- size: `519`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x1800b1fbc`
- `0x180416c38`

## callees

- `0x1800f0f40`
- `0x180419f20`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180419f62`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180419fd0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18041a109`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180419f62`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x180419fd0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18041a109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041a059`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041a0d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041a0e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041a059`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041a0d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18041a0e0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18041a00c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18041a041`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18041a00c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18041a041`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180419f89`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180419fa7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180419f89`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180419fa7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18041a0a1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18041a0c0`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18041a0a1`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18041a0c0`

## pseudocode

```c
__int64 __fastcall IsSameFile(LPCWSTR lpFileName, LPCWSTR a2)
{
  DWORD FullPathNameW; // ebx
  DWORD v5; // eax
  HANDLE FileW; // rsi
  HANDLE v7; // rbp
  DWORD FinalPathNameByHandleW; // ebx
  DWORD v10; // edi
  WCHAR String2[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp-238h] BYREF

  if ( !lpFileName || !a2 )
    return 0;
  if ( lpFileName != a2 && _wcsicmp(lpFileName, a2) )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, Buffer, 0);
    v5 = GetFullPathNameW(a2, 0x104u, String2, 0);
    if ( !FullPathNameW || !v5 )
      return 0;
    if ( _wcsicmp(Buffer, String2) )
    {
      FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
        return 0;
      v7 = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
      if ( v7 == (HANDLE)-1LL )
      {
        CloseHandle(FileW);
        return 0;
      }
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, Buffer, 0x104u, 2u);
      v10 = GetFinalPathNameByHandleW(v7, String2, 0x104u, 2u);
      CloseHandle(FileW);
      CloseHandle(v7);
      if ( !FinalPathNameByHandleW || !v10 || _wcsicmp(Buffer, String2) )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180419f20  mov     [rsp+arg_10], rbx
0x180419f25  push    rbp
0x180419f26  push    rsi
0x180419f27  push    rdi
0x180419f28  sub     rsp, 470h
0x180419f2f  mov     rax, cs:__security_cookie
0x180419f36  xor     rax, rsp
0x180419f39  mov     [rsp+488h+var_28], rax
0x180419f41  mov     rdi, rdx
0x180419f44  mov     rsi, rcx
0x180419f47  test    rcx, rcx
0x180419f4a  jz      loc_18041A065
0x180419f50  test    rdx, rdx
0x180419f53  jz      loc_18041A065
0x180419f59  cmp     rcx, rdx
0x180419f5c  jz      loc_18041A11D
0x180419f62  call    cs:__imp__wcsicmp
0x180419f69  nop     dword ptr [rax+rax+00h]
0x180419f6e  test    eax, eax
0x180419f70  jz      loc_18041A11D
0x180419f76  xor     r9d, r9d; lpFilePart
0x180419f79  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x180419f81  mov     edx, 104h; nBufferLength
0x180419f86  mov     rcx, rsi; lpFileName
0x180419f89  call    cs:__imp_GetFullPathNameW
0x180419f90  nop     dword ptr [rax+rax+00h]
0x180419f95  xor     r9d, r9d; lpFilePart
0x180419f98  lea     r8, [rsp+488h+String2]; lpBuffer
0x180419f9d  mov     edx, 104h; nBufferLength
0x180419fa2  mov     rcx, rdi; lpFileName
0x180419fa5  mov     ebx, eax
0x180419fa7  call    cs:__imp_GetFullPathNameW
0x180419fae  nop     dword ptr [rax+rax+00h]
0x180419fb3  test    ebx, ebx
0x180419fb5  jz      loc_18041A065
0x180419fbb  test    eax, eax
0x180419fbd  jz      loc_18041A065
0x180419fc3  lea     rdx, [rsp+488h+String2]; String2
0x180419fc8  lea     rcx, [rsp+488h+Buffer]; String1
0x180419fd0  call    cs:__imp__wcsicmp
0x180419fd7  nop     dword ptr [rax+rax+00h]
0x180419fdc  test    eax, eax
0x180419fde  jz      loc_18041A11D
0x180419fe4  mov     ebx, 80h
0x180419fe9  mov     [rsp+488h+hTemplateFile], 0; hTemplateFile
0x180419ff2  mov     [rsp+488h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180419ff6  xor     r9d, r9d; lpSecurityAttributes
0x180419ff9  mov     edx, 80000000h; dwDesiredAccess
0x180419ffe  mov     rcx, rsi; lpFileName
0x18041a001  lea     ebp, [rbx-7Dh]
0x18041a004  lea     r8d, [rbx-79h]; dwShareMode
0x18041a008  mov     [rsp+488h+dwCreationDisposition], ebp; dwCreationDisposition
0x18041a00c  call    cs:__imp_CreateFileW
0x18041a013  nop     dword ptr [rax+rax+00h]
0x18041a018  mov     rsi, rax
0x18041a01b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18041a01f  jz      short loc_18041A065
0x18041a021  mov     [rsp+488h+hTemplateFile], 0; hTemplateFile
0x18041a02a  lea     r8d, [rbx-79h]; dwShareMode
0x18041a02e  mov     [rsp+488h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18041a032  xor     r9d, r9d; lpSecurityAttributes
0x18041a035  mov     edx, 80000000h; dwDesiredAccess
0x18041a03a  mov     [rsp+488h+dwCreationDisposition], ebp; dwCreationDisposition
0x18041a03e  mov     rcx, rdi; lpFileName
0x18041a041  call    cs:__imp_CreateFileW
0x18041a048  nop     dword ptr [rax+rax+00h]
0x18041a04d  mov     rbp, rax
0x18041a050  mov     rcx, rsi; hFile
0x18041a053  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18041a057  jnz     short loc_18041A08B
0x18041a059  call    cs:__imp_CloseHandle
0x18041a060  nop     dword ptr [rax+rax+00h]
0x18041a065  xor     eax, eax
0x18041a067  mov     rcx, [rsp+488h+var_28]
0x18041a06f  xor     rcx, rsp; StackCookie
0x18041a072  call    __security_check_cookie
0x18041a077  mov     rbx, [rsp+488h+arg_10]
0x18041a07f  add     rsp, 470h
0x18041a086  pop     rdi
0x18041a087  pop     rsi
0x18041a088  pop     rbp
0x18041a089  retn
0x18041a08b  mov     edi, 2
0x18041a090  lea     rdx, [rsp+488h+Buffer]; lpszFilePath
0x18041a098  mov     r9d, edi; dwFlags
0x18041a09b  mov     r8d, 104h; cchFilePath
0x18041a0a1  call    cs:__imp_GetFinalPathNameByHandleW
0x18041a0a8  nop     dword ptr [rax+rax+00h]
0x18041a0ad  mov     r9d, edi; dwFlags
0x18041a0b0  lea     rdx, [rsp+488h+String2]; lpszFilePath
0x18041a0b5  mov     r8d, 104h; cchFilePath
0x18041a0bb  mov     rcx, rbp; hFile
0x18041a0be  mov     ebx, eax
0x18041a0c0  call    cs:__imp_GetFinalPathNameByHandleW
0x18041a0c7  nop     dword ptr [rax+rax+00h]
0x18041a0cc  mov     rcx, rsi; hObject
0x18041a0cf  mov     edi, eax
0x18041a0d1  call    cs:__imp_CloseHandle
0x18041a0d8  nop     dword ptr [rax+rax+00h]
0x18041a0dd  mov     rcx, rbp; hObject
0x18041a0e0  call    cs:__imp_CloseHandle
0x18041a0e7  nop     dword ptr [rax+rax+00h]
0x18041a0ec  test    ebx, ebx
0x18041a0ee  jz      loc_18041A065
0x18041a0f4  test    edi, edi
0x18041a0f6  jz      loc_18041A065
0x18041a0fc  lea     rdx, [rsp+488h+String2]; String2
0x18041a101  lea     rcx, [rsp+488h+Buffer]; String1
0x18041a109  call    cs:__imp__wcsicmp
0x18041a110  nop     dword ptr [rax+rax+00h]
0x18041a115  test    eax, eax
0x18041a117  jnz     loc_18041A065
0x18041a11d  mov     eax, 1
0x18041a122  jmp     loc_18041A067
```
