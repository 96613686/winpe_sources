# RunServerSideInstall(ireEnum,ushort const *,ushort const *,ushort const *,iioEnum,IMsiServices &,IMsiRecord const *)

- ea: `0x18000879c`
- end: `0x180008b3a`
- name: `?RunServerSideInstall@@YAHW4ireEnum@@PEBG11W4iioEnum@@AEAVIMsiServices@@PEBVIMsiRecord@@@Z`
- size: `926`
- prototype: `int __high(enum ireEnum, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum iioEnum, struct IMsiServices *, const struct IMsiRecord *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180140058`

## callees

- `0x18000879c`
- `0x180008b40`
- `0x180008d68`
- `0x18000919c`
- `0x18001f57c`
- `0x180027634`
- `0x180042810`
- `0x1800a614c`
- `0x18014d2d0`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180008a58`
- `KERNEL32!CloseHandle` at `0x180008a99`
- `KERNEL32!CloseHandle` at `0x180008b0d`
- `KERNEL32!CloseHandle` at `0x180008a58`
- `KERNEL32!CloseHandle` at `0x180008a99`
- `KERNEL32!CloseHandle` at `0x180008b0d`
- `KERNEL32!ReleaseMutex` at `0x180008a49`
- `KERNEL32!ReleaseMutex` at `0x180008a8a`
- `KERNEL32!ReleaseMutex` at `0x180008afe`
- `KERNEL32!ReleaseMutex` at `0x180008a49`
- `KERNEL32!ReleaseMutex` at `0x180008a8a`
- `KERNEL32!ReleaseMutex` at `0x180008afe`
- `KERNEL32!GlobalAlloc` at `0x18000884e`
- `KERNEL32!GlobalAlloc` at `0x18000884e`
- `USER32!IsWindowEnabled` at `0x1800088ea`
- `USER32!IsWindowEnabled` at `0x1800088ea`
- `USER32!EnableWindow` at `0x180008972`
- `USER32!EnableWindow` at `0x180008972`

## pseudocode

```c

```
