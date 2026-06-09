# SplUploadPrinterDriverPackage

- ea: `0x1800bb038`
- end: `0x1800bb641`
- name: `SplUploadPrinterDriverPackage`
- size: `1545`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x180077284`
- `0x1800ba490`

## callees

- `0x1800051f0`
- `0x180015e28`
- `0x18001860c`
- `0x1800187a8`
- `0x18002ff50`
- `0x18003e984`
- `0x18003ea2c`
- `0x180046650`
- `0x18004e678`
- `0x180061d80`
- `0x1800ba910`
- `0x1800bb038`
- `0x1800cd04c`
- `0x1800ce3a4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb21f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb27d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb2db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb21f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb27d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bb2db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bb1c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800bb1c3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bb4eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bb4eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb1d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb2f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb4a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb19a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb1d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb236`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb2f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb4a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800bb0af`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800bb0af`

## string_xrefs

- `0x1800bb1b6`: `setupapi.dll`
- `0x1800bb607`: `Install`
- `0x1800bb123`: `Attempting to upload %ws to %ws with environment %ws`
- `0x1800bb173`: `ValidateObjectAccess failed`
- `0x1800bb553`: `Incorrect parameters passed: pszInfPath=%ws, pszEnvironment=%ws, pszDestInfPath=%ws, pIniSpooler=%p`
- `0x1800bb273`: `DriverStoreAddDriverPackageW`
- `0x1800bb29e`: `GetProcAddress for DriverStoreAddDriverPackage failed`
- `0x1800bb1e2`: `Cannot load setupapi.dll`
- `0x1800bb4ab`: `DriverStoreAddDriverPackage failed`

## pseudocode

```c

```
