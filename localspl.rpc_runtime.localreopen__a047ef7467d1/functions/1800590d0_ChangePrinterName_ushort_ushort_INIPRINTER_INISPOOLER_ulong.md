# ChangePrinterName(ushort *,ushort *,_INIPRINTER *,_INISPOOLER *,ulong *)

- ea: `0x1800590d0`
- end: `0x180059234`
- name: `?ChangePrinterName@@YAXPEAG0PEAU_INIPRINTER@@PEAU_INISPOOLER@@PEAK@Z`
- size: `356`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *, struct _INIPRINTER *, struct _INISPOOLER *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180057b58`

## callees

- `0x18000e890`
- `0x18003ea2c`
- `0x180040484`
- `0x180040acc`
- `0x180054b3c`
- `0x180055098`
- `0x1800590d0`
- `0x18009c0c0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059199`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180059199`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800591e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800591e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800591ee`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059181`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180059181`
- `SPOOLSS!DllFreeSplStr` at `0x18005920d`
- `SPOOLSS!DllFreeSplStr` at `0x18005920d`
- `SPOOLSS!AllocSplStr` at `0x18005910b`
- `SPOOLSS!AllocSplStr` at `0x18005910b`

## string_xrefs

- `0x18005917a`: `mscms.dll`
- `0x18005918f`: `DeviceRenameEvent`
- `0x1800591be`: `DeviceRenameEvent failed. Error %d`
- `0x1800591cd`: `Failed to find DeviceRenameEvent entry point in mscms.dll. Error %d`
- `0x1800591f7`: `Failed to load mscms.dll. Error %d`

## pseudocode

```c

```
