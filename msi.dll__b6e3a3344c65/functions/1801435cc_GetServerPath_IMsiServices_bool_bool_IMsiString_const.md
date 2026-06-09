# GetServerPath(IMsiServices &,bool,bool,IMsiString const * &)

- ea: `0x1801435cc`
- end: `0x180143d3e`
- name: `?GetServerPath@@YAPEAVIMsiRecord@@AEAVIMsiServices@@_N1AEAPEBVIMsiString@@@Z`
- size: `1906`
- prototype: `struct IMsiRecord *__fastcall(struct IMsiServices *, bool, bool, const struct IMsiString **)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006cc60`
- `0x1801ebf10`
- `0x1801fbb90`

## callees

- `0x180015950`
- `0x18002cfe0`
- `0x180035a8c`
- `0x180066074`
- `0x18006e6a8`
- `0x1801435cc`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180143716`
- `ADVAPI32!RegQueryValueExW` at `0x180143716`
- `ADVAPI32!RegCloseKey` at `0x180143671`
- `ADVAPI32!RegCloseKey` at `0x180143671`
- `KERNEL32!InitializeCriticalSection` at `0x180143657`
- `KERNEL32!InitializeCriticalSection` at `0x180143657`
- `KERNEL32!LeaveCriticalSection` at `0x18014368e`
- `KERNEL32!LeaveCriticalSection` at `0x18014368e`
- `KERNEL32!EnterCriticalSection` at `0x180143661`
- `KERNEL32!EnterCriticalSection` at `0x180143661`
- `KERNEL32!GetModuleFileNameW` at `0x18014391d`
- `KERNEL32!GetModuleFileNameW` at `0x18014391d`

## string_xrefs

- `0x1801436b5`: `Software\Microsoft\Windows\CurrentVersion\Installer`
- `0x1801436df`: `MsiExecCA32`
- `0x1801436e9`: `MsiExecCA64`
- `0x180143821`: `MsiExec.exe`
- `0x1801439f5`: `MsiExec.exe`
- `0x180143b05`: `MsiExec.exe`
- `0x180143ba8`: `MsiExec.exe`
- `0x180143c64`: `MsiExec.exe`

## pseudocode

```c

```
