# PathCchCombineEx

- ea: `0x1803453e8`
- end: `0x18034568b`
- name: `PathCchCombineEx`
- size: `675`
- prototype: `HRESULT __stdcall(PWSTR pszPathOut, size_t cchPathOut, PCWSTR pszPathIn, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180256820`

## callees

- `0x1801a2af4`
- `0x1803447d0`
- `0x180345318`
- `0x1803453e8`
- `0x180345924`
- `0x1803481f0`

## import_xrefs

- `msvcrt!iswalpha` at `0x18034551b`
- `msvcrt!iswalpha` at `0x18034551b`
- `KERNEL32!LocalAlloc` at `0x1803454c9`
- `KERNEL32!LocalAlloc` at `0x1803454c9`
- `KERNEL32!LocalFree` at `0x180345652`
- `KERNEL32!LocalFree` at `0x180345652`

## pseudocode

```c

```
