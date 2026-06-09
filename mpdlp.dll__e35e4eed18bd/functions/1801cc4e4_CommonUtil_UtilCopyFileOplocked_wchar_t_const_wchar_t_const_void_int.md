# CommonUtil::UtilCopyFileOplocked(wchar_t const *,wchar_t const *,void *,int)

- ea: `0x1801cc4e4`
- end: `0x1801cc631`
- name: `?UtilCopyFileOplocked@CommonUtil@@YAJPEB_W0PEAXH@Z`
- size: `333`
- prototype: `__int64 __fastcall(void **this, LPCWSTR lpNewFileName, const wchar_t *, void *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1801ac564`

## callees

- `0x180028530`
- `0x1800809d0`
- `0x1800b7f88`
- `0x1801cc4e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801cc5ba`
- `KERNEL32!GetLastError` at `0x1801cc5ba`
- `KERNEL32!CloseHandle` at `0x1801cc590`
- `KERNEL32!CloseHandle` at `0x1801cc605`
- `KERNEL32!CloseHandle` at `0x1801cc590`
- `KERNEL32!CloseHandle` at `0x1801cc605`
- `KERNEL32!CopyFileW` at `0x1801cc5b0`
- `KERNEL32!CopyFileW` at `0x1801cc5b0`
- `ADVAPI32!RevertToSelf` at `0x1801cc59d`
- `ADVAPI32!RevertToSelf` at `0x1801cc612`
- `ADVAPI32!RevertToSelf` at `0x1801cc59d`
- `ADVAPI32!RevertToSelf` at `0x1801cc612`

## pseudocode

```c

```
