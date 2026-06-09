# ReportUnsafeExtensionViolation

- ea: `0x180b54230`
- end: `0x180b544a1`
- name: `ReportUnsafeExtensionViolation`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180b54150`

## callees

- `0x180817094`
- `0x180b53fb0`
- `0x180b54230`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180b54399`
- `KERNEL32!LoadLibraryExW` at `0x180b54399`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180b542cf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180b542cf`
- `KERNEL32!WerSetFlags` at `0x180b5444a`
- `KERNEL32!WerSetFlags` at `0x180b5446d`
- `KERNEL32!WerSetFlags` at `0x180b5444a`
- `KERNEL32!WerSetFlags` at `0x180b5446d`
- `KERNEL32!GetProcAddress` at `0x180b543bb`
- `KERNEL32!GetProcAddress` at `0x180b543bb`
- `KERNEL32!FreeLibrary` at `0x180b5447c`
- `KERNEL32!FreeLibrary` at `0x180b5447c`
- `KERNEL32!GetCurrentProcess` at `0x180b5441c`
- `KERNEL32!GetCurrentProcess` at `0x180b5441c`
- `KERNEL32!WerGetFlags` at `0x180b54430`
- `KERNEL32!WerGetFlags` at `0x180b54430`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b54319`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x180b54319`

## string_xrefs

- `0x180b542ff`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180b542ea`: `LastUnsafeExtensionReportTime`
- `0x180b5438c`: `FAULTREP.DLL`

## pseudocode

```c

```
