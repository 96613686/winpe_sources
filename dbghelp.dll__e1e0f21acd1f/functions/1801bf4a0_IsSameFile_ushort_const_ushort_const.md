# IsSameFile(ushort const *,ushort const *)

- ea: `0x1801bf4a0`
- end: `0x1801bf656`
- name: `?IsSameFile@@YAHPEBG0@Z`
- size: `438`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x1801bf360`
- `0x1801bf408`

## callees

- `0x1801bf4a0`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801bf4e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801bf53e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801bf63e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801bf4e2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801bf53e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801bf63e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801bf5f6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801bf60f`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801bf5f6`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1801bf60f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801bf574`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801bf5a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801bf574`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801bf5a3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801bf503`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801bf51b`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801bf503`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801bf51b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bf5b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bf61a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bf623`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bf5b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bf61a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801bf623`

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
  WCHAR szFilePath[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp-238h] BYREF

  if ( !lpFileName || !a2 )
    return 0;
  if ( lpFileName != a2 && (unsigned int)_o__wcsicmp(lpFileName, a2) )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, Buffer, 0);
    v5 = GetFullPathNameW(a2, 0x104u, szFilePath, 0);
    if ( !FullPathNameW || !v5 )
      return 0;
    if ( (unsigned int)_o__wcsicmp(Buffer, szFilePath) )
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
      v10 = GetFinalPathNameByHandleW(v7, szFilePath, 0x104u, 2u);
      CloseHandle(FileW);
      CloseHandle(v7);
      if ( !FinalPathNameByHandleW || !v10 || (unsigned int)_o__wcsicmp(Buffer, szFilePath) )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1801bf4a0  mov     [rsp+arg_10], rbx
0x1801bf4a5  push    rbp
0x1801bf4a6  push    rsi
0x1801bf4a7  push    rdi
0x1801bf4a8  sub     rsp, 470h
0x1801bf4af  mov     rax, cs:__security_cookie
0x1801bf4b6  xor     rax, rsp
0x1801bf4b9  mov     [rsp+488h+var_28], rax
0x1801bf4c1  mov     rdi, rdx
0x1801bf4c4  mov     rsi, rcx
0x1801bf4c7  test    rcx, rcx
0x1801bf4ca  jz      loc_1801BF5BB
0x1801bf4d0  test    rdx, rdx
0x1801bf4d3  jz      loc_1801BF5BB
0x1801bf4d9  cmp     rcx, rdx
0x1801bf4dc  jz      loc_1801BF64C
0x1801bf4e2  call    cs:__imp__o__wcsicmp
0x1801bf4e8  test    eax, eax
0x1801bf4ea  jz      loc_1801BF64C
0x1801bf4f0  xor     r9d, r9d; lpFilePart
0x1801bf4f3  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x1801bf4fb  mov     edx, 104h; nBufferLength
0x1801bf500  mov     rcx, rsi; lpFileName
0x1801bf503  call    cs:__imp_GetFullPathNameW
0x1801bf509  xor     r9d, r9d; lpFilePart
0x1801bf50c  lea     r8, [rsp+488h+szFilePath]; lpBuffer
0x1801bf511  mov     edx, 104h; nBufferLength
0x1801bf516  mov     rcx, rdi; lpFileName
0x1801bf519  mov     ebx, eax
0x1801bf51b  call    cs:__imp_GetFullPathNameW
0x1801bf521  test    ebx, ebx
0x1801bf523  jz      loc_1801BF5BB
0x1801bf529  test    eax, eax
0x1801bf52b  jz      loc_1801BF5BB
0x1801bf531  lea     rdx, [rsp+488h+szFilePath]
0x1801bf536  lea     rcx, [rsp+488h+Buffer]
0x1801bf53e  call    cs:__imp__o__wcsicmp
0x1801bf544  test    eax, eax
0x1801bf546  jz      loc_1801BF64C
0x1801bf54c  mov     ebx, 80h
0x1801bf551  mov     [rsp+488h+hTemplateFile], 0; hTemplateFile
0x1801bf55a  mov     [rsp+488h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1801bf55e  xor     r9d, r9d; lpSecurityAttributes
0x1801bf561  mov     edx, 80000000h; dwDesiredAccess
0x1801bf566  mov     rcx, rsi; lpFileName
0x1801bf569  lea     ebp, [rbx-7Dh]
0x1801bf56c  lea     r8d, [rbx-79h]; dwShareMode
0x1801bf570  mov     [rsp+488h+dwCreationDisposition], ebp; dwCreationDisposition
0x1801bf574  call    cs:__imp_CreateFileW
0x1801bf57a  mov     rsi, rax
0x1801bf57d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801bf581  jz      short loc_1801BF5BB
0x1801bf583  mov     [rsp+488h+hTemplateFile], 0; hTemplateFile
0x1801bf58c  lea     r8d, [rbx-79h]; dwShareMode
0x1801bf590  mov     [rsp+488h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1801bf594  xor     r9d, r9d; lpSecurityAttributes
0x1801bf597  mov     edx, 80000000h; dwDesiredAccess
0x1801bf59c  mov     [rsp+488h+dwCreationDisposition], ebp; dwCreationDisposition
0x1801bf5a0  mov     rcx, rdi; lpFileName
0x1801bf5a3  call    cs:__imp_CreateFileW
0x1801bf5a9  mov     rbp, rax
0x1801bf5ac  mov     rcx, rsi; hFile
0x1801bf5af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801bf5b3  jnz     short loc_1801BF5E0
0x1801bf5b5  call    cs:__imp_CloseHandle
0x1801bf5bb  xor     eax, eax
0x1801bf5bd  mov     rcx, [rsp+488h+var_28]
0x1801bf5c5  xor     rcx, rsp; StackCookie
0x1801bf5c8  call    __security_check_cookie
0x1801bf5cd  mov     rbx, [rsp+488h+arg_10]
0x1801bf5d5  add     rsp, 470h
0x1801bf5dc  pop     rdi
0x1801bf5dd  pop     rsi
0x1801bf5de  pop     rbp
0x1801bf5df  retn
0x1801bf5e0  mov     edi, 2
0x1801bf5e5  lea     rdx, [rsp+488h+Buffer]; lpszFilePath
0x1801bf5ed  mov     r9d, edi; dwFlags
0x1801bf5f0  mov     r8d, 104h; cchFilePath
0x1801bf5f6  call    cs:__imp_GetFinalPathNameByHandleW
0x1801bf5fc  mov     r9d, edi; dwFlags
0x1801bf5ff  lea     rdx, [rsp+488h+szFilePath]; lpszFilePath
0x1801bf604  mov     r8d, 104h; cchFilePath
0x1801bf60a  mov     rcx, rbp; hFile
0x1801bf60d  mov     ebx, eax
0x1801bf60f  call    cs:__imp_GetFinalPathNameByHandleW
0x1801bf615  mov     rcx, rsi; hObject
0x1801bf618  mov     edi, eax
0x1801bf61a  call    cs:__imp_CloseHandle
0x1801bf620  mov     rcx, rbp; hObject
0x1801bf623  call    cs:__imp_CloseHandle
0x1801bf629  test    ebx, ebx
0x1801bf62b  jz      short loc_1801BF5BB
0x1801bf62d  test    edi, edi
0x1801bf62f  jz      short loc_1801BF5BB
0x1801bf631  lea     rdx, [rsp+488h+szFilePath]
0x1801bf636  lea     rcx, [rsp+488h+Buffer]
0x1801bf63e  call    cs:__imp__o__wcsicmp
0x1801bf644  test    eax, eax
0x1801bf646  jnz     loc_1801BF5BB
0x1801bf64c  mov     eax, 1
0x1801bf651  jmp     loc_1801BF5BD
```
