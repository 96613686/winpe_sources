# ORCreateFile

- ea: `0x140028e10`
- end: `0x140028e63`
- name: `ORCreateFile`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140023544`
- `0x140023780`
- `0x140027b04`

## callees

- `0x140028e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e4c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140028e2f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140028e2f`

## pseudocode

```c
__int64 __fastcall ORCreateFile(const WCHAR *a1, DWORD a2, DWORD dwCreationDisposition, DWORD a4, _QWORD *a5)
{
  unsigned int v5; // ebx
  HANDLE FileW; // rcx

  v5 = 0;
  FileW = CreateFileW(a1, a2, a4, 0, dwCreationDisposition, 0, 0);
  *a5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v5;
}

```

## disassembly

```asm
0x140028e10  push    rbx
0x140028e12  sub     rsp, 40h
0x140028e16  mov     eax, r9d
0x140028e19  xor     ebx, ebx
0x140028e1b  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x140028e20  xor     r9d, r9d; lpSecurityAttributes
0x140028e23  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x140028e27  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x140028e2c  mov     r8d, eax; dwShareMode
0x140028e2f  call    cs:__imp_CreateFileW
0x140028e36  nop     dword ptr [rax+rax+00h]
0x140028e3b  mov     rcx, rax
0x140028e3e  mov     rax, [rsp+48h+arg_20]
0x140028e43  mov     [rax], rcx
0x140028e46  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140028e4a  jnz     short loc_140028E5A
0x140028e4c  call    cs:__imp_GetLastError
0x140028e53  nop     dword ptr [rax+rax+00h]
0x140028e58  mov     ebx, eax
0x140028e5a  mov     eax, ebx
0x140028e5c  add     rsp, 40h
0x140028e60  pop     rbx
0x140028e61  retn
```
