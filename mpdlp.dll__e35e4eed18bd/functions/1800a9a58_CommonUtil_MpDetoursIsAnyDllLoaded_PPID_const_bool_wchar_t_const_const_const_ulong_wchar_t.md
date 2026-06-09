# CommonUtil::MpDetoursIsAnyDllLoaded(PPID const &,bool &,wchar_t const * const * const,ulong,wchar_t * *)

- ea: `0x1800a9a58`
- end: `0x1800a9ca2`
- name: `?MpDetoursIsAnyDllLoaded@CommonUtil@@YAJAEBUPPID@@AEA_NQEBQEB_WKPEAPEA_W@Z`
- size: `586`
- prototype: `int(CommonUtil *__hidden this, const struct PPID *, bool *, const wchar_t *const *const, unsigned int, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a99d4`

## callees

- `0x1800809d0`
- `0x180089510`
- `0x1800a9a58`
- `0x1800c0174`
- `0x180105f50`
- `0x18010cb40`
- `0x18013eb4c`
- `0x18023a310`

## import_xrefs

- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800a9ac8`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1800a9ac8`
- `KERNEL32!GetLastError` at `0x1800a9ad6`
- `KERNEL32!GetLastError` at `0x1800a9bd5`
- `KERNEL32!GetLastError` at `0x1800a9ad6`
- `KERNEL32!GetLastError` at `0x1800a9bd5`
- `KERNEL32!CloseHandle` at `0x1800a9c31`
- `KERNEL32!CloseHandle` at `0x1800a9c73`
- `KERNEL32!CloseHandle` at `0x1800a9c31`
- `KERNEL32!CloseHandle` at `0x1800a9c73`
- `KERNEL32!Module32FirstW` at `0x1800a9b80`
- `KERNEL32!Module32FirstW` at `0x1800a9b80`
- `KERNEL32!Module32NextW` at `0x1800a9bc4`
- `KERNEL32!Module32NextW` at `0x1800a9bc4`

## pseudocode

```c

```
