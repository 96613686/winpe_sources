# RealtimeProtection::DlpQuarantineEngine::CheckItemsAndQuarantineIfPossible(void)

- ea: `0x180092dc0`
- end: `0x18009351a`
- name: `?CheckItemsAndQuarantineIfPossible@DlpQuarantineEngine@RealtimeProtection@@AEAAJXZ`
- size: `1882`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpQuarantineEngine *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180092c4c`

## callees

- `0x180024ac0`
- `0x180046d10`
- `0x180080030`
- `0x1800809d0`
- `0x180092dc0`
- `0x18009351c`
- `0x18009358c`
- `0x1800943fc`
- `0x1800abfc8`
- `0x180105404`
- `0x18010cb40`
- `0x1801fc494`
- `0x1801fc864`
- `0x1801fd814`
- `0x180200fc0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180093359`
- `KERNEL32!CompareStringOrdinal` at `0x180093359`
- `KERNEL32!AcquireSRWLockShared` at `0x180092e25`
- `KERNEL32!AcquireSRWLockShared` at `0x180092e25`
- `KERNEL32!ReleaseSRWLockShared` at `0x18009308b`
- `KERNEL32!ReleaseSRWLockShared` at `0x18009308b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180092f2b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180092f2b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180092fb7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180092fb7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18009325d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18009325d`
- `KERNEL32!GetTickCount64` at `0x180092e49`
- `KERNEL32!GetTickCount64` at `0x180092e49`

## pseudocode

```c

```
