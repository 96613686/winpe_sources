# LoadSetupApiDll(_SETUPAPI_INFO *)

- ea: `0x18009bd80`
- end: `0x18009be5e`
- name: `?LoadSetupApiDll@@YAHPEAU_SETUPAPI_INFO@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(struct _SETUPAPI_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18009bc10`

## callees

- `0x18003ea2c`
- `0x18009bd80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009bdc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009bddb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009bdef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009be03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009bdc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009bddb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009bdef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009be03`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009be48`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009be48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009be29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009be29`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009bd92`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009bdac`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009bd92`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18009bdac`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009bda1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009bda1`

## string_xrefs

- `0x18009be39`: `LoadSetupApiDll`
- `0x18009bde4`: `SetupDiRemoveDevice`
- `0x18009bdf8`: `SetupDiOpenDeviceInfoW`

## pseudocode

```c

```
