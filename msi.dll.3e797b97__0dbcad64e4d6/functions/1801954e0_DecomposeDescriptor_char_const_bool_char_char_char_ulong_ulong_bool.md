# DecomposeDescriptor(char const *,bool,char *,char *,char *,ulong *,ulong *,bool *)

- ea: `0x1801954e0`
- end: `0x1801959b2`
- name: `?DecomposeDescriptor@@YAHPEBD_NPEAD22PEAK3PEA_N@Z`
- size: `1234`
- prototype: `int(const char *, bool, char *, char *, char *, unsigned int *, unsigned int *, bool *)`
- caller_count: `10`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b74c0`
- `0x180154d60`
- `0x18015850c`
- `0x180163570`
- `0x18019bb00`
- `0x18019c680`
- `0x18019c920`
- `0x1801a0e30`
- `0x1801a11a0`
- `0x1801a1500`

## callees

- `0x18000c4bc`
- `0x180048e68`
- `0x1801954e0`
- `0x18019d110`
- `0x180265240`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18019554a`
- `KERNEL32!lstrlenA` at `0x18019554a`
- `KERNEL32!GlobalFree` at `0x18019578b`
- `KERNEL32!GlobalFree` at `0x1801957ad`
- `KERNEL32!GlobalFree` at `0x1801957d0`
- `KERNEL32!GlobalFree` at `0x1801958c9`
- `KERNEL32!GlobalFree` at `0x1801958eb`
- `KERNEL32!GlobalFree` at `0x180195957`
- `KERNEL32!GlobalFree` at `0x18019597c`
- `KERNEL32!GlobalFree` at `0x18019578b`
- `KERNEL32!GlobalFree` at `0x1801957ad`
- `KERNEL32!GlobalFree` at `0x1801957d0`
- `KERNEL32!GlobalFree` at `0x1801958c9`
- `KERNEL32!GlobalFree` at `0x1801958eb`
- `KERNEL32!GlobalFree` at `0x180195957`
- `KERNEL32!GlobalFree` at `0x18019597c`

## string_xrefs

- `0x18019557b`: `MSI_DBG: Provided descriptor less than minimum size`
- `0x18019564c`: `MSI_DBG: Invalid descriptor format - unable to decode ProductCode in descriptor`
- `0x1801956a4`: `MSI_DBG: Invalid feature name provided in descriptor (exceeds max feature length)`
- `0x180195914`: `MSI_DBG: Invalid descriptor format`
- `0x1801956f6`: `MSI_DBG: Descriptor feature validation failed`
- `0x18019574d`: `MSI_DBG: Descriptor feature validation failed`
- `0x180195808`: `MSI_DBG: Invalid descriptor format - missing component specification`
- `0x180195888`: `MSI_DBG: Invalid descriptor format - unable to decode component`

## pseudocode

```c

```
