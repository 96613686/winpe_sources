# PersistXmlStore::InitializePersistXml(void)

- ea: `0x180036dc0`
- end: `0x180036f27`
- name: `?InitializePersistXml@PersistXmlStore@@AEAAJXZ`
- size: `359`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800371c8`

## callees

- `0x1800039f0`
- `0x180036dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036f04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036f04`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180036e9d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180036edc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180036e9d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180036edc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036e55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180036e55`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180036e16`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180036e16`

## pseudocode

```c
__int64 __fastcall PersistXmlStore::InitializePersistXml(PersistXmlStore *this)
{
  char *v1; // rdi
  bool v2; // cc
  const WCHAR *v3; // rcx
  signed int v4; // ebx
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v7; // eax
  signed int v8; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-38h] BYREF
  int Buffer; // [rsp+44h] [rbp-34h] BYREF
  char v12[24]; // [rsp+48h] [rbp-30h] BYREF

  v1 = (char *)this + 8;
  NumberOfBytesWritten = 0;
  v2 = *((_QWORD *)this + 4) <= 7u;
  strcpy(v12, "<list count=\"0\"></list>");
  Buffer = 12565487;
  if ( v2 )
    v3 = (const WCHAR *)((char *)this + 8);
  else
    v3 = *(const WCHAR **)v1;
  v4 = 0;
  if ( GetFileAttributesW(v3) == -1 )
  {
    if ( *((_QWORD *)v1 + 3) > 7u )
      v1 = *(char **)v1;
    FileW = CreateFileW((LPCWSTR)v1, 0xC0000000, 1u, 0, 4u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
      goto LABEL_14;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_14:
      if ( WriteFile(FileW, &Buffer, 3u, &NumberOfBytesWritten, 0) )
        goto LABEL_23;
      v7 = GetLastError();
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_23:
        if ( !WriteFile(FileW, v12, 0x17u, &NumberOfBytesWritten, 0) )
        {
          v8 = GetLastError();
          v4 = v8;
          if ( v8 > 0 )
            v4 = (unsigned __int16)v8 | 0x80070000;
        }
      }
      if ( FileW != (HANDLE)-1LL )
        CloseHandle(FileW);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180036dc0  mov     [rsp+arg_8], rbx
0x180036dc5  push    rdi
0x180036dc6  sub     rsp, 70h
0x180036dca  mov     rax, cs:__security_cookie
0x180036dd1  xor     rax, rsp
0x180036dd4  mov     [rsp+78h+var_18], rax
0x180036dd9  movups  xmm0, xmmword ptr cs:aListCount0List; "<list count=\"0\"></list>"
0x180036de0  lea     rdi, [rcx+8]
0x180036de4  mov     [rsp+78h+NumberOfBytesWritten], 0
0x180036dec  movsd   xmm1, qword ptr cs:aListCount0List+10h; "</list>"
0x180036df4  cmp     qword ptr [rdi+18h], 7
0x180036df9  movups  xmmword ptr [rsp+78h+var_30], xmm0
0x180036dfe  mov     [rsp+78h+Buffer], 0BFBBEFh
0x180036e06  movsd   qword ptr [rsp+78h+var_30+10h], xmm1
0x180036e0c  jbe     short loc_180036E13
0x180036e0e  mov     rcx, [rdi]
0x180036e11  jmp     short loc_180036E16
0x180036e13  mov     rcx, rdi; lpFileName
0x180036e16  call    cs:__imp_GetFileAttributesW
0x180036e1c  xor     ebx, ebx
0x180036e1e  cmp     eax, 0FFFFFFFFh
0x180036e21  jnz     loc_180036F0A
0x180036e27  cmp     qword ptr [rdi+18h], 7
0x180036e2c  jbe     short loc_180036E31
0x180036e2e  mov     rdi, [rdi]
0x180036e31  xor     r9d, r9d; lpSecurityAttributes
0x180036e34  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x180036e39  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180036e41  mov     edx, 0C0000000h; dwDesiredAccess
0x180036e46  mov     rcx, rdi; lpFileName
0x180036e49  mov     [rsp+78h+dwCreationDisposition], 4; dwCreationDisposition
0x180036e51  lea     r8d, [r9+1]; dwShareMode
0x180036e55  call    cs:__imp_CreateFileW
0x180036e5b  mov     rdi, rax
0x180036e5e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180036e62  jnz     short loc_180036E81
0x180036e64  call    cs:__imp_GetLastError
0x180036e6a  mov     ebx, eax
0x180036e6c  test    eax, eax
0x180036e6e  jle     short loc_180036E79
0x180036e70  movzx   ebx, ax
0x180036e73  or      ebx, 80070000h
0x180036e79  test    ebx, ebx
0x180036e7b  js      loc_180036F0A
0x180036e81  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180036e86  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x180036e8f  mov     r8d, 3; nNumberOfBytesToWrite
0x180036e95  lea     rdx, [rsp+78h+Buffer]; lpBuffer
0x180036e9a  mov     rcx, rdi; hFile
0x180036e9d  call    cs:__imp_WriteFile
0x180036ea3  test    eax, eax
0x180036ea5  jnz     short loc_180036EC0
0x180036ea7  call    cs:__imp_GetLastError
0x180036ead  mov     ebx, eax
0x180036eaf  test    eax, eax
0x180036eb1  jle     short loc_180036EBC
0x180036eb3  movzx   ebx, ax
0x180036eb6  or      ebx, 80070000h
0x180036ebc  test    ebx, ebx
0x180036ebe  js      short loc_180036EFB
0x180036ec0  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180036ec5  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOverlapped
0x180036ece  mov     r8d, 17h; nNumberOfBytesToWrite
0x180036ed4  lea     rdx, [rsp+78h+var_30]; lpBuffer
0x180036ed9  mov     rcx, rdi; hFile
0x180036edc  call    cs:__imp_WriteFile
0x180036ee2  test    eax, eax
0x180036ee4  jnz     short loc_180036EFB
0x180036ee6  call    cs:__imp_GetLastError
0x180036eec  mov     ebx, eax
0x180036eee  test    eax, eax
0x180036ef0  jle     short loc_180036EFB
0x180036ef2  movzx   ebx, ax
0x180036ef5  or      ebx, 80070000h
0x180036efb  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180036eff  jz      short loc_180036F0A
0x180036f01  mov     rcx, rdi; hObject
0x180036f04  call    cs:__imp_CloseHandle
0x180036f0a  mov     eax, ebx
0x180036f0c  mov     rcx, [rsp+78h+var_18]
0x180036f11  xor     rcx, rsp; StackCookie
0x180036f14  call    __security_check_cookie
0x180036f19  mov     rbx, [rsp+78h+arg_8]
0x180036f21  add     rsp, 70h
0x180036f25  pop     rdi
0x180036f26  retn
```
