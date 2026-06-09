# GetModuleInfo(ushort *,uint,unsigned __int64 *)

- ea: `0x1802d8944`
- end: `0x1802d8a1d`
- name: `?GetModuleInfo@@YA_NPEAGIPEA_K@Z`
- size: `217`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1802d84d8`

## callees

- `0x18020b19c`
- `0x18025b100`
- `0x1802d8944`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1802d897b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1802d897b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d89d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802d89d7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1802d89c8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1802d89c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802d89af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1802d89af`

## pseudocode

```c
bool __fastcall GetModuleInfo(unsigned __int16 *a1, __int64 a2, unsigned __int64 *a3)
{
  HANDLE FileW; // rax
  void *v6; // rbx
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( !GetModuleFileNameW(0, Filename, 0x105u) )
    return 0;
  FileW = CreateFileW(Filename, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  if ( a3 )
    *a3 = GetFileSize(FileW, 0);
  CloseHandle(v6);
  return StringCchCopyW(a1, 0x105u, Filename) >= 0;
}

```

## disassembly

```asm
0x1802d8944  mov     [rsp+arg_8], rbx
0x1802d8949  mov     [rsp+arg_18], rsi
0x1802d894e  push    rdi
0x1802d894f  sub     rsp, 260h
0x1802d8956  mov     rax, cs:__security_cookie
0x1802d895d  xor     rax, rsp
0x1802d8960  mov     [rsp+268h+var_18], rax
0x1802d8968  mov     rdi, r8
0x1802d896b  lea     rdx, [rsp+268h+Filename]; lpFilename
0x1802d8970  mov     rsi, rcx
0x1802d8973  mov     r8d, 105h; nSize
0x1802d8979  xor     ecx, ecx; hModule
0x1802d897b  call    cs:__imp_GetModuleFileNameW
0x1802d8981  test    eax, eax
0x1802d8983  jz      short loc_1802D89F6
0x1802d8985  xor     r9d, r9d; lpSecurityAttributes
0x1802d8988  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x1802d8991  mov     [rsp+268h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1802d8999  lea     rcx, [rsp+268h+Filename]; lpFileName
0x1802d899e  mov     edx, 80000000h; dwDesiredAccess
0x1802d89a3  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x1802d89ab  lea     r8d, [r9+7]; dwShareMode
0x1802d89af  call    cs:__imp_CreateFileW
0x1802d89b5  mov     rbx, rax
0x1802d89b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1802d89bc  jz      short loc_1802D89F6
0x1802d89be  test    rdi, rdi
0x1802d89c1  jz      short loc_1802D89D4
0x1802d89c3  xor     edx, edx; lpFileSizeHigh
0x1802d89c5  mov     rcx, rax; hFile
0x1802d89c8  call    cs:__imp_GetFileSize
0x1802d89ce  mov     r8d, eax
0x1802d89d1  mov     [rdi], r8
0x1802d89d4  mov     rcx, rbx; hObject
0x1802d89d7  call    cs:__imp_CloseHandle
0x1802d89dd  lea     r8, [rsp+268h+Filename]; unsigned __int16 *
0x1802d89e2  mov     edx, 105h; unsigned __int64
0x1802d89e7  mov     rcx, rsi; unsigned __int16 *
0x1802d89ea  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802d89ef  test    eax, eax
0x1802d89f1  setns   al
0x1802d89f4  jmp     short loc_1802D89F8
0x1802d89f6  xor     al, al
0x1802d89f8  mov     rcx, [rsp+268h+var_18]
0x1802d8a00  xor     rcx, rsp; StackCookie
0x1802d8a03  call    __security_check_cookie
0x1802d8a08  lea     r11, [rsp+268h+var_8]
0x1802d8a10  mov     rbx, [r11+18h]
0x1802d8a14  mov     rsi, [r11+28h]
0x1802d8a18  mov     rsp, r11
0x1802d8a1b  pop     rdi
0x1802d8a1c  retn
```
