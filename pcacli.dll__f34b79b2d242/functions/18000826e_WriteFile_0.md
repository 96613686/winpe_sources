# WriteFile_0

- ea: `0x18000826e`
- end: `0x180008274`
- name: `WriteFile_0`
- size: `6`
- prototype: `BOOL __stdcall(HANDLE hFile, LPCVOID lpBuffer, DWORD nNumberOfBytesToWrite, LPDWORD lpNumberOfBytesWritten, LPOVERLAPPED lpOverlapped)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180007200`
- `0x180008d4c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000826e`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall WriteFile_0(
        HANDLE hFile,
        LPCVOID lpBuffer,
        DWORD nNumberOfBytesToWrite,
        LPDWORD lpNumberOfBytesWritten,
        LPOVERLAPPED lpOverlapped)
{
  return WriteFile(hFile, lpBuffer, nNumberOfBytesToWrite, lpNumberOfBytesWritten, lpOverlapped);
}

```

## disassembly

```asm
0x18000826e  jmp     cs:__imp_WriteFile
```
