# _wsplitpath_s

- ea: `0x180002188`
- end: `0x18000218e`
- name: `_wsplitpath_s`
- size: `6`
- prototype: `errno_t __cdecl(const wchar_t *FullPath, wchar_t *Drive, size_t DriveCount, wchar_t *Dir, size_t DirCount, wchar_t *Filename, size_t FilenameCount, wchar_t *Ext, size_t ExtCount)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800272a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180002188`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl wsplitpath_s(
        const wchar_t *FullPath,
        wchar_t *Drive,
        size_t DriveCount,
        wchar_t *Dir,
        size_t DirCount,
        wchar_t *Filename,
        size_t FilenameCount,
        wchar_t *Ext,
        size_t ExtCount)
{
  return _wsplitpath_s(FullPath, Drive, DriveCount, Dir, DirCount, Filename, FilenameCount, Ext, ExtCount);
}

```

## disassembly

```asm
0x180002188  jmp     cs:__imp__wsplitpath_s
```
