# PutObjectDataProc(IMsiData const *,uint *)

- ea: `0x180003778`
- end: `0x180003901`
- name: `?PutObjectDataProc@@YA?AW4Bool@@PEBVIMsiData@@PEAI@Z`
- size: `393`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180003570`
- `0x18000365c`
- `0x1800040e4`
- `0x180007cb0`
- `0x18003da80`
- `0x18022f420`

## callees

- `0x180003778`
- `0x18025c010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180003857`
- `KERNEL32!GlobalLock` at `0x180003857`
- `KERNEL32!GlobalReAlloc` at `0x1800038d6`
- `KERNEL32!GlobalReAlloc` at `0x1800038d6`
- `KERNEL32!GlobalUnlock` at `0x1800038bc`
- `KERNEL32!GlobalUnlock` at `0x1800038bc`
- `KERNEL32!LeaveCriticalSection` at `0x1800037f9`
- `KERNEL32!LeaveCriticalSection` at `0x1800038f4`
- `KERNEL32!LeaveCriticalSection` at `0x1800037f9`
- `KERNEL32!LeaveCriticalSection` at `0x1800038f4`
- `KERNEL32!EnterCriticalSection` at `0x180003798`
- `KERNEL32!EnterCriticalSection` at `0x180003798`
- `KERNEL32!GlobalAlloc` at `0x180003839`
- `KERNEL32!GlobalAlloc` at `0x180003839`

## pseudocode

```c

```
