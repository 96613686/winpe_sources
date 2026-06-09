# MprInfoBlockAdd

- ea: `0x18007a454`
- end: `0x18007a6f3`
- name: `MprInfoBlockAdd`
- size: `671`
- prototype: `DWORD __stdcall(LPVOID lpHeader, DWORD dwInfoType, DWORD dwItemSize, DWORD dwItemCount, LPBYTE lpItemData, LPVOID *lplpNewHeader)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180025044`

## callees

- `0x180002ba6`
- `0x18007a454`
- `0x18007a998`
- `0x18008c5f2`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18007a5b4`
- `KERNEL32!GetProcessHeap` at `0x18007a5b4`
- `KERNEL32!HeapAlloc` at `0x18007a5c2`
- `KERNEL32!HeapAlloc` at `0x18007a5c2`

## pseudocode

```c

```
