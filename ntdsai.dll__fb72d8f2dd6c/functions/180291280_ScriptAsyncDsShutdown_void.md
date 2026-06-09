# ScriptAsyncDsShutdown(void *)

- ea: `0x180291280`
- end: `0x18029155a`
- name: `?ScriptAsyncDsShutdown@@YAIPEAX@Z`
- size: `730`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001133c`
- `0x18001135c`
- `0x18001e090`
- `0x1800aae40`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x180291280`
- `0x18038fb8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802913f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802913f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180291535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180291535`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1802912ee`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1802912ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1802912bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1802912bc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802912f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802912f7`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x1802913e8`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x1802913e8`
- `ntdll!RtlAdjustPrivilege` at `0x1802913c5`
- `ntdll!RtlAdjustPrivilege` at `0x1802913c5`
- `ntdll!NtShutdownSystem` at `0x180291525`
- `ntdll!NtShutdownSystem` at `0x180291525`

## string_xrefs

- `0x1802912a9`: `ntdll.dll`

## pseudocode

```c

```
