# ProvideComponentFromDescriptor(char const *,ulong,char *,ulong *,ulong *,bool,bool)

- ea: `0x18015298c`
- end: `0x180152e59`
- name: `?ProvideComponentFromDescriptor@@YAIPEBDKPEADPEAK2_N3@Z`
- size: `1229`
- prototype: `unsigned int(const char *, unsigned int, char *, unsigned int *, unsigned int *, bool, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800546a0`
- `0x1801991c0`
- `0x1801999e0`

## callees

- `0x18000a150`
- `0x18001cab0`
- `0x18001d960`
- `0x18004cb30`
- `0x18004ceb0`
- `0x18004cee4`
- `0x180051d20`
- `0x180055030`
- `0x180055ee4`
- `0x18006e53c`
- `0x18012ef34`
- `0x18015298c`
- `0x18018ec50`
- `0x18025ab12`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180152b3b`
- `KERNEL32!lstrlenA` at `0x180152c74`
- `KERNEL32!lstrlenA` at `0x180152b3b`
- `KERNEL32!lstrlenA` at `0x180152c74`
- `KERNEL32!GlobalFree` at `0x180152cd5`
- `KERNEL32!GlobalFree` at `0x180152d03`
- `KERNEL32!GlobalFree` at `0x180152d6d`
- `KERNEL32!GlobalFree` at `0x180152d87`
- `KERNEL32!GlobalFree` at `0x180152da1`
- `KERNEL32!GlobalFree` at `0x180152ddd`
- `KERNEL32!GlobalFree` at `0x180152df9`
- `KERNEL32!GlobalFree` at `0x180152e15`
- `KERNEL32!GlobalFree` at `0x180152cd5`
- `KERNEL32!GlobalFree` at `0x180152d03`
- `KERNEL32!GlobalFree` at `0x180152d6d`
- `KERNEL32!GlobalFree` at `0x180152d87`
- `KERNEL32!GlobalFree` at `0x180152da1`
- `KERNEL32!GlobalFree` at `0x180152ddd`
- `KERNEL32!GlobalFree` at `0x180152df9`
- `KERNEL32!GlobalFree` at `0x180152e15`

## string_xrefs

- `0x180152b03`: `MsiProvideComponentFromDescriptor called for component %s: returning harcoded oleaut32.dll value`
- `0x180152b34`: `oleaut32.dll`
- `0x180152b73`: `oleaut32.dll`

## pseudocode

```c

```
