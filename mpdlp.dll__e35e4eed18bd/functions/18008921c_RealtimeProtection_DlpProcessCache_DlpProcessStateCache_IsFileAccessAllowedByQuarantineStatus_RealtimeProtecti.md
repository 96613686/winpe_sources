# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::IsFileAccessAllowedByQuarantineStatus(RealtimeProtection::FileUniqueId const &)

- ea: `0x18008921c`
- end: `0x1800893ec`
- name: `?IsFileAccessAllowedByQuarantineStatus@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEBA_NAEBVFileUniqueId@3@@Z`
- size: `464`
- prototype: `bool __fastcall(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct RealtimeProtection::FileUniqueId *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18008916c`

## callees

- `0x1800809d0`
- `0x18008921c`
- `0x1800893f0`
- `0x180089498`
- `0x180089510`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x180089247`
- `KERNEL32!AcquireSRWLockShared` at `0x180089267`
- `KERNEL32!AcquireSRWLockShared` at `0x180089247`
- `KERNEL32!AcquireSRWLockShared` at `0x180089267`
- `KERNEL32!ReleaseSRWLockShared` at `0x180089293`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800892c3`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800892ec`
- `KERNEL32!ReleaseSRWLockShared` at `0x180089293`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800892c3`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800892ec`

## pseudocode

```c

```
