# GenInvokeEnumStackProviders(ulong,_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ushort const *,_LIST_ENTRY *)

- ea: `0x180407f44`
- end: `0x18040809d`
- name: `?GenInvokeEnumStackProviders@@YAJKPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEBGPEAU_LIST_ENTRY@@@Z`
- size: `345`
- prototype: `int(unsigned int, struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, const unsigned __int16 *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180407ccc`

## callees

- `0x180402f34`
- `0x180403158`
- `0x1804032e0`
- `0x180407f44`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180408021`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180408080`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180408021`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180408080`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180407f67`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180407f67`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180407fc0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180407fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180407f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180407f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180407f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180407f8b`

## pseudocode

```c

```
