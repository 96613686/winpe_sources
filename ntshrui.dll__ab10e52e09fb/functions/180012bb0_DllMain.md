# DllMain

- ea: `0x180012bb0`
- end: `0x180012c92`
- name: `DllMain`
- size: `226`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025354`

## callees

- `0x180012bb0`
- `0x180012c98`
- `0x180012d20`
- `0x180012d58`
- `0x180012d88`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012c0c`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012c0c`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180012c7f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180012c7f`
- `USER32!UnregisterClassW` at `0x180012c4d`
- `USER32!UnregisterClassW` at `0x180012c4d`

## pseudocode

```c

```
