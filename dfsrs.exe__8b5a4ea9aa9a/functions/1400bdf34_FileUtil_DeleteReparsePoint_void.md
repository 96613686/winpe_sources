# FileUtil::DeleteReparsePoint(void *)

- ea: `0x1400bdf34`
- end: `0x1400be0b7`
- name: `?DeleteReparsePoint@FileUtil@@SAPEAVFrsStatus@@PEAX@Z`
- size: `387`
- prototype: `struct FrsStatus *__fastcall(HANDLE hDevice)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x1400bfd74`
- `0x1400c0078`

## callees

- `0x14002c548`
- `0x1400bdf34`
- `0x1401af7b0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1400bdf9a`
- `KERNEL32!DeviceIoControl` at `0x1400be039`
- `KERNEL32!DeviceIoControl` at `0x1400bdf9a`
- `KERNEL32!DeviceIoControl` at `0x1400be039`
- `KERNEL32!GetLastError` at `0x1400bdfc6`
- `KERNEL32!GetLastError` at `0x1400be057`
- `KERNEL32!GetLastError` at `0x1400bdfc6`
- `KERNEL32!GetLastError` at `0x1400be057`
- `KERNEL32!GetCurrentThreadId` at `0x1400bdfb8`
- `KERNEL32!GetCurrentThreadId` at `0x1400be049`
- `KERNEL32!GetCurrentThreadId` at `0x1400bdfb8`
- `KERNEL32!GetCurrentThreadId` at `0x1400be049`

## string_xrefs

- `0x1400bdfa6`: `FileUtil::DeleteReparsePoint`

## pseudocode

```c

```
