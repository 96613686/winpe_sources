# OpenFileForRead

- ea: `0x180144b74`
- end: `0x180144bdf`
- name: `OpenFileForRead`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180144cb0`

## callees

- `0x180144b74`
- `0x1801595f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180144ba2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180144ba2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144bae`

## pseudocode

```c
__int64 __fastcall OpenFileForRead(const WCHAR *a1, _QWORD *a2)
{
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 v5; // rcx
  unsigned int v6; // r10d
  unsigned int v7; // r10d

  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    LogErrorFxn(v5, v6);
  }
  else
  {
    *a2 = FileW;
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180144b74  push    rbx
0x180144b76  sub     rsp, 40h
0x180144b7a  xor     r9d, r9d; lpSecurityAttributes
0x180144b7d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180144b86  mov     rbx, rdx
0x180144b89  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180144b91  mov     edx, 80000000h; dwDesiredAccess
0x180144b96  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180144b9e  lea     r8d, [r9+7]; dwShareMode
0x180144ba2  call    cs:__imp_CreateFileW
0x180144ba8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180144bac  jnz     short loc_180144BD0
0x180144bae  call    cs:__imp_GetLastError
0x180144bb4  mov     r10d, eax
0x180144bb7  test    eax, eax
0x180144bb9  jle     short loc_180144BC6
0x180144bbb  movzx   r10d, ax
0x180144bbf  or      r10d, 80070000h
0x180144bc6  mov     edx, r10d
0x180144bc9  call    LogErrorFxn
0x180144bce  jmp     short loc_180144BD6
0x180144bd0  mov     [rbx], rax
0x180144bd3  xor     r10d, r10d
0x180144bd6  mov     eax, r10d
0x180144bd9  add     rsp, 40h
0x180144bdd  pop     rbx
0x180144bde  retn
```
