# __dcrt_write_console

- ea: `0x18001d414`
- end: `0x18001d4c8`
- name: `__dcrt_write_console`
- size: `180`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001d33c`

## callees

- `0x18001d414`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d44a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d44a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d462`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x18001d43e`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x18001d4b5`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x18001d43e`
- `api-ms-win-core-console-l1-1-0!WriteConsoleW` at `0x18001d4b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d493`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001d493`

## pseudocode

```c
__int64 __fastcall _dcrt_write_console(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  unsigned int v6; // ebx

  v6 = WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v6 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hObject <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    hObject = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    return WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x18001d414  push    rbx
0x18001d416  push    rbp
0x18001d417  push    rsi
0x18001d418  push    rdi
0x18001d419  sub     rsp, 48h
0x18001d41d  mov     rdi, r8
0x18001d420  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18001d429  mov     r9, r8; lpNumberOfCharsWritten
0x18001d42c  mov     esi, edx
0x18001d42e  mov     r8d, edx; nNumberOfCharsToWrite
0x18001d431  mov     rbp, rcx
0x18001d434  mov     rdx, rcx; lpBuffer
0x18001d437  mov     rcx, cs:hObject; hConsoleOutput
0x18001d43e  call    cs:__imp_WriteConsoleW
0x18001d444  mov     ebx, eax
0x18001d446  test    eax, eax
0x18001d448  jnz     short loc_18001D4BD
0x18001d44a  call    cs:__imp_GetLastError
0x18001d450  cmp     eax, 6
0x18001d453  jnz     short loc_18001D4BD
0x18001d455  mov     rcx, cs:hObject; hObject
0x18001d45c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001d460  ja      short loc_18001D468
0x18001d462  call    cs:__imp_CloseHandle
0x18001d468  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001d471  lea     rcx, FileName; "CONOUT$"
0x18001d478  mov     r8d, 3; dwShareMode
0x18001d47e  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001d486  xor     r9d, r9d; lpSecurityAttributes
0x18001d489  mov     dword ptr [rsp+68h+lpReserved], r8d; dwCreationDisposition
0x18001d48e  mov     edx, 40000000h; dwDesiredAccess
0x18001d493  call    cs:__imp_CreateFileW
0x18001d499  mov     r9, rdi; lpNumberOfCharsWritten
0x18001d49c  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18001d4a5  mov     rcx, rax; hConsoleOutput
0x18001d4a8  mov     cs:hObject, rax
0x18001d4af  mov     r8d, esi; nNumberOfCharsToWrite
0x18001d4b2  mov     rdx, rbp; lpBuffer
0x18001d4b5  call    cs:__imp_WriteConsoleW
0x18001d4bb  mov     ebx, eax
0x18001d4bd  mov     eax, ebx
0x18001d4bf  add     rsp, 48h
0x18001d4c3  pop     rdi
0x18001d4c4  pop     rsi
0x18001d4c5  pop     rbp
0x18001d4c6  pop     rbx
0x18001d4c7  retn
```
