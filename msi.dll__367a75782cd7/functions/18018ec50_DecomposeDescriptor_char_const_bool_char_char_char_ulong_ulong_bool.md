# DecomposeDescriptor(char const *,bool,char *,char *,char *,ulong *,ulong *,bool *)

- ea: `0x18018ec50`
- end: `0x18018f0ee`
- name: `?DecomposeDescriptor@@YAHPEBD_NPEAD22PEAK3PEA_N@Z`
- size: `1182`
- prototype: `int(const char *, bool, char *, char *, char *, unsigned int *, unsigned int *, bool *)`
- caller_count: `10`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800546a0`
- `0x18014f4b0`
- `0x18015298c`
- `0x18015d800`
- `0x180194e90`
- `0x1801959e0`
- `0x180195c80`
- `0x180199f70`
- `0x18019a2d0`
- `0x18019a600`

## callees

- `0x180025a18`
- `0x1800504bc`
- `0x18018ec50`
- `0x180196420`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18018ecba`
- `KERNEL32!lstrlenA` at `0x18018ecba`
- `KERNEL32!GlobalFree` at `0x18018eef5`
- `KERNEL32!GlobalFree` at `0x18018ef11`
- `KERNEL32!GlobalFree` at `0x18018ef2e`
- `KERNEL32!GlobalFree` at `0x18018f021`
- `KERNEL32!GlobalFree` at `0x18018f03d`
- `KERNEL32!GlobalFree` at `0x18018f0a0`
- `KERNEL32!GlobalFree` at `0x18018f0bf`
- `KERNEL32!GlobalFree` at `0x18018eef5`
- `KERNEL32!GlobalFree` at `0x18018ef11`
- `KERNEL32!GlobalFree` at `0x18018ef2e`
- `KERNEL32!GlobalFree` at `0x18018f021`
- `KERNEL32!GlobalFree` at `0x18018f03d`
- `KERNEL32!GlobalFree` at `0x18018f0a0`
- `KERNEL32!GlobalFree` at `0x18018f0bf`

## string_xrefs

- `0x18018ece5`: `MSI_DBG: Provided descriptor less than minimum size`
- `0x18018edb6`: `MSI_DBG: Invalid descriptor format - unable to decode ProductCode in descriptor`
- `0x18018ee0e`: `MSI_DBG: Invalid feature name provided in descriptor (exceeds max feature length)`
- `0x18018f05d`: `MSI_DBG: Invalid descriptor format`
- `0x18018ee60`: `MSI_DBG: Descriptor feature validation failed`
- `0x18018eeb7`: `MSI_DBG: Descriptor feature validation failed`
- `0x18018ef60`: `MSI_DBG: Invalid descriptor format - missing component specification`
- `0x18018efe0`: `MSI_DBG: Invalid descriptor format - unable to decode component`

## pseudocode

```c

```
