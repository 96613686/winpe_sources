# RunServerSideInstall(ireEnum,ushort const *,ushort const *,ushort const *,iioEnum,IMsiServices &,IMsiRecord const *)

- ea: `0x18009a89c`
- end: `0x18009ac03`
- name: `?RunServerSideInstall@@YAHW4ireEnum@@PEBG11W4iioEnum@@AEAVIMsiServices@@PEBVIMsiRecord@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(unsigned int, const WCHAR *, __int64, __int64, int, __int64, struct IMsiRecord *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18013ae34`

## callees

- `0x18000a150`
- `0x18001db00`
- `0x18003bccc`
- `0x18009a89c`
- `0x18009ac10`
- `0x18009ae30`
- `0x18009b23c`
- `0x18009de10`
- `0x180147d88`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009ab40`
- `KERNEL32!CloseHandle` at `0x18009ab75`
- `KERNEL32!CloseHandle` at `0x18009abdd`
- `KERNEL32!CloseHandle` at `0x18009ab40`
- `KERNEL32!CloseHandle` at `0x18009ab75`
- `KERNEL32!CloseHandle` at `0x18009abdd`
- `KERNEL32!ReleaseMutex` at `0x18009ab37`
- `KERNEL32!ReleaseMutex` at `0x18009ab6c`
- `KERNEL32!ReleaseMutex` at `0x18009abd4`
- `KERNEL32!ReleaseMutex` at `0x18009ab37`
- `KERNEL32!ReleaseMutex` at `0x18009ab6c`
- `KERNEL32!ReleaseMutex` at `0x18009abd4`
- `KERNEL32!GlobalAlloc` at `0x18009a94e`
- `KERNEL32!GlobalAlloc` at `0x18009a94e`
- `USER32!IsWindowEnabled` at `0x18009a9e4`
- `USER32!IsWindowEnabled` at `0x18009a9e4`
- `USER32!EnableWindow` at `0x18009aa66`
- `USER32!EnableWindow` at `0x18009aa66`

## pseudocode

```c

```
