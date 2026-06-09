# CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)

- ea: `0x180067270`
- end: `0x1800672e4`
- name: `?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `116`
- prototype: `HRESULT __fastcall(void *hProcess, void **ppPackageSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800671fc`
- `0x1800675dc`

## callees

- `0x180066b14`
- `0x180067270`
- `0x1800672ec`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800672d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800672d1`

## pseudocode

```c

```
