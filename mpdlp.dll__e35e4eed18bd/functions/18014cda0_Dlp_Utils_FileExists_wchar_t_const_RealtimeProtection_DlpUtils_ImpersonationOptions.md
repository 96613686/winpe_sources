# Dlp::Utils::FileExists(wchar_t const *,RealtimeProtection::DlpUtils::ImpersonationOptions)

- ea: `0x18014cda0`
- end: `0x18014cee5`
- name: `?FileExists@Utils@Dlp@@YA_NPEB_WUImpersonationOptions@DlpUtils@RealtimeProtection@@@Z`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001f1f8`
- `0x1800ba270`

## callees

- `0x1800809d0`
- `0x180089510`
- `0x1800b7f88`
- `0x18010cb40`
- `0x18014cda0`
- `0x18014e888`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x18014ce4c`
- `KERNEL32!GetFileAttributesExW` at `0x18014ce4c`
- `KERNEL32!CloseHandle` at `0x18014ce6f`
- `KERNEL32!CloseHandle` at `0x18014ce90`
- `KERNEL32!CloseHandle` at `0x18014ce6f`
- `KERNEL32!CloseHandle` at `0x18014ce90`
- `ADVAPI32!RevertToSelf` at `0x18014ce5d`
- `ADVAPI32!RevertToSelf` at `0x18014ce7e`
- `ADVAPI32!RevertToSelf` at `0x18014ce5d`
- `ADVAPI32!RevertToSelf` at `0x18014ce7e`

## pseudocode

```c

```
