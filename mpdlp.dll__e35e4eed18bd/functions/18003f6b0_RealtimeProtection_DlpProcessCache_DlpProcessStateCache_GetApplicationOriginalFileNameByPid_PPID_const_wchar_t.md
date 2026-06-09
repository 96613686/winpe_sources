# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::GetApplicationOriginalFileNameByPid(PPID const &,wchar_t * *)

- ea: `0x18003f6b0`
- end: `0x18003f870`
- name: `?GetApplicationOriginalFileNameByPid@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEBAJAEBUPPID@@PEAPEA_W@Z`
- size: `448`
- prototype: `int(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003f3f8`

## callees

- `0x18003f6b0`
- `0x1800809d0`
- `0x180100c34`
- `0x180107874`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18003f6e4`
- `KERNEL32!AcquireSRWLockShared` at `0x18003f6e4`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f770`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f7bb`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f7d2`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f817`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f770`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f7bb`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f7d2`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003f817`
- `KERNEL32!CompareFileTime` at `0x18003f744`
- `KERNEL32!CompareFileTime` at `0x18003f744`

## pseudocode

```c

```
