# I_UrlCacheUpdateMetaData

- ea: `0x180002ca8`
- end: `0x180002d1e`
- name: `I_UrlCacheUpdateMetaData`
- size: `118`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180001154`
- `0x180001460`
- `0x180002460`

## callees

- `0x180002ca8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002cf2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002cf2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002cd0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180002cd0`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180002cff`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180002cff`

## pseudocode

```c
__int64 __fastcall I_UrlCacheUpdateMetaData(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite)
{
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  if ( SetFilePointer(hFile, 0, 0, 0) == -1
    || !WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    return 0;
  }
  SetEndOfFile(hFile);
  return 1;
}

```

## disassembly

```asm
0x180002ca8  mov     [rsp+arg_0], rbx
0x180002cad  mov     [rsp+arg_8], rsi
0x180002cb2  push    rdi
0x180002cb3  sub     rsp, 30h
0x180002cb7  mov     edi, r8d
0x180002cba  mov     [rsp+38h+NumberOfBytesWritten], 0
0x180002cc2  mov     rsi, rdx
0x180002cc5  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002cc8  xor     edx, edx; lDistanceToMove
0x180002cca  xor     r9d, r9d; dwMoveMethod
0x180002ccd  mov     rbx, rcx
0x180002cd0  call    cs:__imp_SetFilePointer
0x180002cd6  cmp     eax, 0FFFFFFFFh
0x180002cd9  jz      short loc_180002D1A
0x180002cdb  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002ce0  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180002ce9  mov     r8d, edi; nNumberOfBytesToWrite
0x180002cec  mov     rdx, rsi; lpBuffer
0x180002cef  mov     rcx, rbx; hFile
0x180002cf2  call    cs:__imp_WriteFile
0x180002cf8  test    eax, eax
0x180002cfa  jz      short loc_180002D1A
0x180002cfc  mov     rcx, rbx; hFile
0x180002cff  call    cs:__imp_SetEndOfFile
0x180002d05  mov     eax, 1
0x180002d0a  mov     rbx, [rsp+38h+arg_0]
0x180002d0f  mov     rsi, [rsp+38h+arg_8]
0x180002d14  add     rsp, 30h
0x180002d18  pop     rdi
0x180002d19  retn
0x180002d1a  xor     eax, eax
0x180002d1c  jmp     short loc_180002D0A
```
