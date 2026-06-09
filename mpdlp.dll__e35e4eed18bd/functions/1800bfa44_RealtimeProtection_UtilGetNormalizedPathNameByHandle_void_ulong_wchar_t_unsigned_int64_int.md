# RealtimeProtection::UtilGetNormalizedPathNameByHandle(void *,ulong,wchar_t * *,unsigned __int64 *,int *)

- ea: `0x1800bfa44`
- end: `0x1800bfc39`
- name: `?UtilGetNormalizedPathNameByHandle@RealtimeProtection@@YAJPEAXKPEAPEA_WPEA_KPEAH@Z`
- size: `501`
- prototype: `__int64 __fastcall(HANDLE hDevice, void *, unsigned int, wchar_t **, unsigned __int64 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1802366e4`

## callees

- `0x1800809d0`
- `0x18009f730`
- `0x1800bfa44`
- `0x180105f50`
- `0x18010cb40`
- `0x18023a6d0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1800bfc19`
- `MpClient!MpFreeMemory` at `0x1800bfc19`
- `MpClient!MpAllocMemory` at `0x1800bfa78`
- `MpClient!MpAllocMemory` at `0x1800bfb6f`
- `MpClient!MpAllocMemory` at `0x1800bfa78`
- `MpClient!MpAllocMemory` at `0x1800bfb6f`
- `KERNEL32!DeviceIoControl` at `0x1800bfac8`
- `KERNEL32!DeviceIoControl` at `0x1800bfac8`

## pseudocode

```c

```
