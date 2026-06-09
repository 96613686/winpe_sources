# RemoveDirectoryW_0

- ea: `0x180011f17`
- end: `0x180011f1d`
- name: `RemoveDirectoryW_0`
- size: `6`
- prototype: `BOOL __stdcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800068c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180011f17`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall RemoveDirectoryW_0(LPCWSTR lpPathName)
{
  return RemoveDirectoryW(lpPathName);
}

```

## disassembly

```asm
0x180011f17  jmp     cs:__imp_RemoveDirectoryW
```
