# ProvideComponentFromDescriptor(char const *,ulong,char *,ulong *,ulong *,bool,bool)

- ea: `0x18015850c`
- end: `0x180158a19`
- name: `?ProvideComponentFromDescriptor@@YAIPEBDKPEADPEAK2_N3@Z`
- size: `1293`
- prototype: `unsigned int(const char *, unsigned int, char *, unsigned int *, unsigned int *, bool, bool)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b74c0`
- `0x1801a0010`
- `0x1801a0880`

## callees

- `0x180027634`
- `0x180041c54`
- `0x180044960`
- `0x1800459c0`
- `0x180049c84`
- `0x18004a014`
- `0x18004a050`
- `0x18009443c`
- `0x1800b6f2c`
- `0x1800b7d84`
- `0x180134ce0`
- `0x18015850c`
- `0x1801954e0`
- `0x1802651d2`
- `0x180265240`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1801586bb`
- `KERNEL32!lstrlenA` at `0x1801587fa`
- `KERNEL32!lstrlenA` at `0x1801586bb`
- `KERNEL32!lstrlenA` at `0x1801587fa`
- `KERNEL32!GlobalFree` at `0x180158861`
- `KERNEL32!GlobalFree` at `0x180158895`
- `KERNEL32!GlobalFree` at `0x180158905`
- `KERNEL32!GlobalFree` at `0x180158925`
- `KERNEL32!GlobalFree` at `0x180158945`
- `KERNEL32!GlobalFree` at `0x18015898a`
- `KERNEL32!GlobalFree` at `0x1801589ac`
- `KERNEL32!GlobalFree` at `0x1801589ce`
- `KERNEL32!GlobalFree` at `0x180158861`
- `KERNEL32!GlobalFree` at `0x180158895`
- `KERNEL32!GlobalFree` at `0x180158905`
- `KERNEL32!GlobalFree` at `0x180158925`
- `KERNEL32!GlobalFree` at `0x180158945`
- `KERNEL32!GlobalFree` at `0x18015898a`
- `KERNEL32!GlobalFree` at `0x1801589ac`
- `KERNEL32!GlobalFree` at `0x1801589ce`

## string_xrefs

- `0x180158683`: `MsiProvideComponentFromDescriptor called for component %s: returning harcoded oleaut32.dll value`
- `0x1801586b4`: `oleaut32.dll`
- `0x1801586f9`: `oleaut32.dll`

## pseudocode

```c

```
