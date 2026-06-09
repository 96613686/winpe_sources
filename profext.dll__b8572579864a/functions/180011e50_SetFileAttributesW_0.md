# SetFileAttributesW_0

- ea: `0x180011e50`
- end: `0x180011e56`
- name: `SetFileAttributesW_0`
- size: `6`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, DWORD dwFileAttributes)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18000681c`
- `0x1800068c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180011e50`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall SetFileAttributesW_0(LPCWSTR lpFileName, DWORD dwFileAttributes)
{
  return SetFileAttributesW(lpFileName, dwFileAttributes);
}

```

## disassembly

```asm
0x180011e50  jmp     cs:__imp_SetFileAttributesW
```
