# ShutdownProgressThreadProc(void *)

- ea: `0x1800f9e90`
- end: `0x1800fa232`
- name: `?ShutdownProgressThreadProc@@YAKPEAX@Z`
- size: `930`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180013250`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800ae508`
- `0x1800b1a24`
- `0x1800cd854`
- `0x1800eb920`
- `0x1800f1eb4`
- `0x1800f9e90`
- `0x1801235d8`
- `0x180123f40`
- `0x1801240f8`
- `0x180124b48`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800fa1a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800fa1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa1c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fa1c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800f9eba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800fa042`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800fa0ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800fa121`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800f9eba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800fa042`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800fa0ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800fa121`

## string_xrefs

- `0x1800fa066`: `Unable to make service wait.`
- `0x1800fa110`: `Unable to make service wait.`
- `0x1800f9ee7`: `ShutdownProgressThread started without ITrustedInstallerService`
- `0x1800fa1fa`: `Shtd: progress thread terminating.`
- `0x1800f9f85`: `Shtd: Failed loading WmsgApi.dll, continuing without posting messages during shutdown`
- `0x1800f9f49`: `Shtd: progress thread started`
- `0x1800fa149`: `Shtd: Timed out waiting for shutdown processing to complete - no progress detected in last {} milliseconds`
- `0x1800fa1e0`: `Shtd: Failed waiting for shutdown processing to complete.`

## pseudocode

```c

```
