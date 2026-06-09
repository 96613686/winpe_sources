# ReportUnsafeExtensionViolation

- ea: `0x180b3c4b4`
- end: `0x180b3c6ee`
- name: `ReportUnsafeExtensionViolation`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180b3c3dc`

## callees

- `0x18080df34`
- `0x180b3c24c`
- `0x180b3c4b4`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180b3c611`
- `KERNEL32!LoadLibraryExW` at `0x180b3c611`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180b3c553`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180b3c553`
- `KERNEL32!WerSetFlags` at `0x180b3c6aa`
- `KERNEL32!WerSetFlags` at `0x180b3c6c7`
- `KERNEL32!WerSetFlags` at `0x180b3c6aa`
- `KERNEL32!WerSetFlags` at `0x180b3c6c7`
- `KERNEL32!GetProcAddress` at `0x180b3c62d`
- `KERNEL32!GetProcAddress` at `0x180b3c62d`
- `KERNEL32!FreeLibrary` at `0x180b3c6d0`
- `KERNEL32!FreeLibrary` at `0x180b3c6d0`
- `KERNEL32!GetCurrentProcess` at `0x180b3c688`
- `KERNEL32!GetCurrentProcess` at `0x180b3c688`
- `KERNEL32!WerGetFlags` at `0x180b3c696`
- `KERNEL32!WerGetFlags` at `0x180b3c696`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3c597`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b3c597`

## string_xrefs

- `0x180b3c57d`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180b3c568`: `LastUnsafeExtensionReportTime`
- `0x180b3c604`: `FAULTREP.DLL`

## pseudocode

```c

```
