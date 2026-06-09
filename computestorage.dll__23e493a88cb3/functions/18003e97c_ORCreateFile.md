# ORCreateFile

- ea: `0x18003e97c`
- end: `0x18003e9cf`
- name: `ORCreateFile`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003b6f4`
- `0x18003d768`

## callees

- `0x18003e97c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e99b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003e99b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e9b8`

## pseudocode

```c
__int64 __fastcall ORCreateFile(const WCHAR *a1, DWORD a2, __int64 a3, DWORD a4, _QWORD *a5)
{
  unsigned int v5; // ebx
  HANDLE FileW; // rcx

  v5 = 0;
  FileW = CreateFileW(a1, a2, a4, 0, 3u, 0, 0);
  *a5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v5;
}

```

## disassembly

```asm
0x18003e97c  push    rbx
0x18003e97e  sub     rsp, 40h
0x18003e982  xor     ebx, ebx
0x18003e984  mov     r8d, r9d; dwShareMode
0x18003e987  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18003e98c  xor     r9d, r9d; lpSecurityAttributes
0x18003e98f  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18003e993  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18003e99b  call    cs:__imp_CreateFileW
0x18003e9a2  nop     dword ptr [rax+rax+00h]
0x18003e9a7  mov     rcx, rax
0x18003e9aa  mov     rax, [rsp+48h+arg_20]
0x18003e9af  mov     [rax], rcx
0x18003e9b2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003e9b6  jnz     short loc_18003E9C6
0x18003e9b8  call    cs:__imp_GetLastError
0x18003e9bf  nop     dword ptr [rax+rax+00h]
0x18003e9c4  mov     ebx, eax
0x18003e9c6  mov     eax, ebx
0x18003e9c8  add     rsp, 40h
0x18003e9cc  pop     rbx
0x18003e9cd  retn
```
