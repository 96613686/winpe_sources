# MprInfoBlockAdd

- ea: `0x180031f80`
- end: `0x180032210`
- name: `MprInfoBlockAdd`
- size: `656`
- prototype: `DWORD __stdcall(LPVOID lpHeader, DWORD dwInfoType, DWORD dwItemSize, DWORD dwItemCount, LPBYTE lpItemData, LPVOID *lplpNewHeader)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800181b8`

## callees

- `0x180031f80`
- `0x180032220`
- `0x180032a08`
- `0x180051112`
- `0x18005112a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800320d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800320d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800320df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800320df`

## pseudocode

```c

```
