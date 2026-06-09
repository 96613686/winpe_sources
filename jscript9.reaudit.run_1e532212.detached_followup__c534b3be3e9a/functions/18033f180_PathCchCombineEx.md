# PathCchCombineEx

- ea: `0x18033f180`
- end: `0x18033f410`
- name: `PathCchCombineEx`
- size: `656`
- prototype: `HRESULT __stdcall(PWSTR pszPathOut, size_t cchPathOut, PCWSTR pszPathIn, PCWSTR pszMore, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180252304`

## callees

- `0x1801a0780`
- `0x18033e5bc`
- `0x18033f0b0`
- `0x18033f180`
- `0x18033f688`
- `0x180341dd0`

## import_xrefs

- `msvcrt!iswalpha` at `0x18033f2ad`
- `msvcrt!iswalpha` at `0x18033f2ad`
- `KERNEL32!LocalAlloc` at `0x18033f261`
- `KERNEL32!LocalAlloc` at `0x18033f261`
- `KERNEL32!LocalFree` at `0x18033f3de`
- `KERNEL32!LocalFree` at `0x18033f3de`

## pseudocode

```c

```
