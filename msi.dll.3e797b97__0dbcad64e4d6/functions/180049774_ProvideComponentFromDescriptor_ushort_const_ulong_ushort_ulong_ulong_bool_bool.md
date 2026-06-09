# ProvideComponentFromDescriptor(ushort const *,ulong,ushort *,ulong *,ulong *,bool,bool)

- ea: `0x180049774`
- end: `0x180049c7e`
- name: `?ProvideComponentFromDescriptor@@YAIPEBGKPEAGPEAK2_N3@Z`
- size: `1290`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *, unsigned int *, bool, bool)`
- caller_count: `3`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180042b60`
- `0x18004bb30`
- `0x1801a0980`

## callees

- `0x18000c4bc`
- `0x180014160`
- `0x180044960`
- `0x1800459c0`
- `0x180049774`
- `0x180049c84`
- `0x18004a014`
- `0x18004a050`
- `0x18004a07c`
- `0x18004a530`
- `0x18009443c`
- `0x1802651d2`
- `0x180265240`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180049b2d`
- `KERNEL32!lstrlenW` at `0x180049bd7`
- `KERNEL32!lstrlenW` at `0x180049b2d`
- `KERNEL32!lstrlenW` at `0x180049bd7`
- `KERNEL32!GlobalFree` at `0x180049933`
- `KERNEL32!GlobalFree` at `0x180049953`
- `KERNEL32!GlobalFree` at `0x180049973`
- `KERNEL32!GlobalFree` at `0x1800499ed`
- `KERNEL32!GlobalFree` at `0x180049a0f`
- `KERNEL32!GlobalFree` at `0x180049a31`
- `KERNEL32!GlobalFree` at `0x180049a74`
- `KERNEL32!GlobalFree` at `0x180049933`
- `KERNEL32!GlobalFree` at `0x180049953`
- `KERNEL32!GlobalFree` at `0x180049973`
- `KERNEL32!GlobalFree` at `0x1800499ed`
- `KERNEL32!GlobalFree` at `0x180049a0f`
- `KERNEL32!GlobalFree` at `0x180049a31`
- `KERNEL32!GlobalFree` at `0x180049a74`

## string_xrefs

- `0x180049aed`: `MsiProvideComponentFromDescriptor called for component %s: returning harcoded oleaut32.dll value`
- `0x180049b26`: `oleaut32.dll`
- `0x180049b6a`: `oleaut32.dll`

## pseudocode

```c

```
