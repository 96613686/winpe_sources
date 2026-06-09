# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetProcessUserSID(PPID const &,wchar_t * *)

- ea: `0x18001d47c`
- end: `0x18001d65a`
- name: `?GetProcessUserSID@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@PEAPEA_W@Z`
- size: `478`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, wchar_t **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d3fc`
- `0x18002abb0`

## callees

- `0x18001d47c`
- `0x18001d65c`
- `0x1800809d0`
- `0x180100c34`
- `0x180107874`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18001d4be`
- `KERNEL32!AcquireSRWLockShared` at `0x18001d4be`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001d567`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001d59d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001d5b7`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001d567`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001d59d`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001d5b7`
- `KERNEL32!CompareFileTime` at `0x18001d526`
- `KERNEL32!CompareFileTime` at `0x18001d526`

## pseudocode

```c

```
