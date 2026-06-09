# CheckCommonDriverFoundInDirectory(PLATFORM,ushort const *,ushort *)

- ea: `0x1800095b0`
- end: `0x18000971b`
- name: `?CheckCommonDriverFoundInDirectory@@YAJW4PLATFORM@@PEBGPEAG@Z`
- size: `363`
- prototype: `int __high(enum PLATFORM, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cc8c`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x1800095b0`
- `0x18000b200`
- `0x180012b28`
- `0x180026df0`
- `0x180026ed4`
- `0x1800271a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800096d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800096d6`
- `KERNEL32!lstrcmpiW` at `0x18000966d`
- `KERNEL32!lstrcmpiW` at `0x18000966d`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18000965b`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18000965b`

## pseudocode

```c

```
