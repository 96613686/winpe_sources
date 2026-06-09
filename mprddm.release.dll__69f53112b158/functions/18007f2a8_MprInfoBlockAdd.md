# MprInfoBlockAdd

- ea: `0x18007f2a8`
- end: `0x18007f563`
- name: `MprInfoBlockAdd`
- size: `699`
- prototype: `DWORD __stdcall(LPVOID lpHeader, DWORD dwInfoType, DWORD dwItemSize, DWORD dwItemCount, LPBYTE lpItemData, LPVOID *lplpNewHeader)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800271f0`

## callees

- `0x180002be6`
- `0x18007f2a8`
- `0x18007f83c`
- `0x180092a92`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18007f40b`
- `KERNEL32!GetProcessHeap` at `0x18007f40b`
- `KERNEL32!HeapAlloc` at `0x18007f41f`
- `KERNEL32!HeapAlloc` at `0x18007f41f`

## pseudocode

```c

```
