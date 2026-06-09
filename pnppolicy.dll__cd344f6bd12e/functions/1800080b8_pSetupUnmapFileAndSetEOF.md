# pSetupUnmapFileAndSetEOF

- ea: `0x1800080b8`
- end: `0x180008122`
- name: `pSetupUnmapFileAndSetEOF`
- size: `106`
- prototype: `__int64 __fastcall(HANDLE hFile, HANDLE hObject, LPCVOID lpBaseAddress)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800054d4`
- `0x1800059f4`

## callees

- `0x1800080b8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800080ee`
- `KERNEL32!SetEndOfFile` at `0x18000810a`
- `KERNEL32!SetEndOfFile` at `0x18000810a`
- `KERNEL32!UnmapViewOfFile` at `0x1800080da`
- `KERNEL32!UnmapViewOfFile` at `0x1800080da`

## pseudocode

```c
__int64 __fastcall pSetupUnmapFileAndSetEOF(HANDLE hFile, HANDLE hObject, LPCVOID lpBaseAddress)
{
  unsigned int v5; // ebx

  v5 = 1;
  if ( lpBaseAddress )
    v5 = UnmapViewOfFile(lpBaseAddress);
  if ( hObject )
    v5 = v5 && CloseHandle(hObject);
  if ( hFile != (HANDLE)-1LL )
    SetEndOfFile(hFile);
  return v5;
}

```

## disassembly

```asm
0x1800080b8  mov     [rsp+arg_0], rbx
0x1800080bd  mov     [rsp+arg_8], rsi
0x1800080c2  push    rdi
0x1800080c3  sub     rsp, 20h
0x1800080c7  mov     rsi, rdx
0x1800080ca  mov     rdi, rcx
0x1800080cd  mov     ebx, 1
0x1800080d2  test    r8, r8
0x1800080d5  jz      short loc_1800080E2
0x1800080d7  mov     rcx, r8; lpBaseAddress
0x1800080da  call    cs:__imp_UnmapViewOfFile
0x1800080e0  mov     ebx, eax
0x1800080e2  test    rsi, rsi
0x1800080e5  jz      short loc_180008101
0x1800080e7  test    ebx, ebx
0x1800080e9  jz      short loc_1800080FF
0x1800080eb  mov     rcx, rsi; hObject
0x1800080ee  call    cs:__imp_CloseHandle
0x1800080f4  test    eax, eax
0x1800080f6  jz      short loc_1800080FF
0x1800080f8  mov     ebx, 1
0x1800080fd  jmp     short loc_180008101
0x1800080ff  xor     ebx, ebx
0x180008101  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180008105  jz      short loc_180008110
0x180008107  mov     rcx, rdi; hFile
0x18000810a  call    cs:__imp_SetEndOfFile
0x180008110  mov     rsi, [rsp+28h+arg_8]
0x180008115  mov     eax, ebx
0x180008117  mov     rbx, [rsp+28h+arg_0]
0x18000811c  add     rsp, 20h
0x180008120  pop     rdi
0x180008121  retn
```
