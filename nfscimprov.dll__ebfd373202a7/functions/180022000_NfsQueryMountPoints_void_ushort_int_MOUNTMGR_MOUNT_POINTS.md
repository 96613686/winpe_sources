# NfsQueryMountPoints(void *,ushort *,int,_MOUNTMGR_MOUNT_POINTS * *)

- ea: `0x180022000`
- end: `0x1800221c9`
- name: `?NfsQueryMountPoints@@YAKPEAXPEAGHPEAPEAU_MOUNTMGR_MOUNT_POINTS@@@Z`
- size: `457`
- prototype: `unsigned int __fastcall(HANDLE hDevice, unsigned __int16 *Src, int, struct _MOUNTMGR_MOUNT_POINTS **)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180018c3c`

## callees

- `0x180001da6`
- `0x180022000`
- `0x180035b40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180022188`
- `KERNEL32!HeapFree` at `0x18002219c`
- `KERNEL32!HeapFree` at `0x180022188`
- `KERNEL32!HeapFree` at `0x18002219c`
- `KERNEL32!GetLastError` at `0x1800220f6`
- `KERNEL32!GetLastError` at `0x180022167`
- `KERNEL32!GetLastError` at `0x1800220f6`
- `KERNEL32!GetLastError` at `0x180022167`
- `KERNEL32!HeapAlloc` at `0x18002206a`
- `KERNEL32!HeapAlloc` at `0x180022126`
- `KERNEL32!HeapAlloc` at `0x18002206a`
- `KERNEL32!HeapAlloc` at `0x180022126`
- `KERNEL32!GetProcessHeap` at `0x180022057`
- `KERNEL32!GetProcessHeap` at `0x180022113`
- `KERNEL32!GetProcessHeap` at `0x18002217a`
- `KERNEL32!GetProcessHeap` at `0x18002218e`
- `KERNEL32!GetProcessHeap` at `0x180022057`
- `KERNEL32!GetProcessHeap` at `0x180022113`
- `KERNEL32!GetProcessHeap` at `0x18002217a`
- `KERNEL32!GetProcessHeap` at `0x18002218e`
- `KERNEL32!DeviceIoControl` at `0x1800220ec`
- `KERNEL32!DeviceIoControl` at `0x18002215d`
- `KERNEL32!DeviceIoControl` at `0x1800220ec`
- `KERNEL32!DeviceIoControl` at `0x18002215d`

## pseudocode

```c

```
