# pSetupMapFileForWrite

- ea: `0x180020c1c`
- end: `0x180020caf`
- name: `pSetupMapFileForWrite`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x180006360`

## callees

- `0x180020c1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c86`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180020c48`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180020c48`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180020c69`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180020c69`

## pseudocode

```c
__int64 __fastcall pSetupMapFileForWrite(void *a1, DWORD a2, HANDLE *a3, _QWORD *a4)
{
  SIZE_T dwNumberOfBytesToMap; // rbx
  HANDLE FileMappingW; // rax
  LPVOID v8; // rax
  DWORD LastError; // ebx

  dwNumberOfBytesToMap = a2;
  FileMappingW = CreateFileMappingW(a1, 0, 4u, 0, a2, 0);
  *a3 = FileMappingW;
  if ( FileMappingW )
  {
    v8 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, dwNumberOfBytesToMap);
    *a4 = v8;
    if ( v8 )
      return 0;
    LastError = GetLastError();
    CloseHandle(*a3);
    *a3 = 0;
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180020c1c  mov     rax, rsp
0x180020c1f  mov     [rax+8], rbx
0x180020c23  mov     [rax+10h], rsi
0x180020c27  push    rdi
0x180020c28  sub     rsp, 30h
0x180020c2c  mov     ebx, edx
0x180020c2e  mov     rsi, r9
0x180020c31  xor     r9d, r9d; dwMaximumSizeHigh
0x180020c34  mov     qword ptr [rax-10h], 0
0x180020c3c  mov     rdi, r8
0x180020c3f  mov     [rax-18h], ebx
0x180020c42  xor     edx, edx; lpFileMappingAttributes
0x180020c44  lea     r8d, [r9+4]; flProtect
0x180020c48  call    cs:__imp_CreateFileMappingW
0x180020c4e  mov     [rdi], rax
0x180020c51  test    rax, rax
0x180020c54  jz      short loc_180020C95
0x180020c56  xor     r9d, r9d; dwFileOffsetLow
0x180020c59  mov     [rsp+38h+dwNumberOfBytesToMap], rbx; dwNumberOfBytesToMap
0x180020c5e  xor     r8d, r8d; dwFileOffsetHigh
0x180020c61  mov     edx, 0F001Fh; dwDesiredAccess
0x180020c66  mov     rcx, rax; hFileMappingObject
0x180020c69  call    cs:__imp_MapViewOfFile
0x180020c6f  mov     [rsi], rax
0x180020c72  test    rax, rax
0x180020c75  jz      short loc_180020C7B
0x180020c77  xor     eax, eax
0x180020c79  jmp     short loc_180020C9F
0x180020c7b  call    cs:__imp_GetLastError
0x180020c81  mov     rcx, [rdi]; hObject
0x180020c84  mov     ebx, eax
0x180020c86  call    cs:__imp_CloseHandle
0x180020c8c  mov     qword ptr [rdi], 0
0x180020c93  jmp     short loc_180020C9D
0x180020c95  call    cs:__imp_GetLastError
0x180020c9b  mov     ebx, eax
0x180020c9d  mov     eax, ebx
0x180020c9f  mov     rbx, [rsp+38h+arg_0]
0x180020ca4  mov     rsi, [rsp+38h+arg_8]
0x180020ca9  add     rsp, 30h
0x180020cad  pop     rdi
0x180020cae  retn
```
