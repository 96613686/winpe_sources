# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetProcessInjectionInProgressStateExclusive(PPID const &,bool,bool &)

- ea: `0x18001b838`
- end: `0x18001b996`
- name: `?SetProcessInjectionInProgressStateExclusive@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@_NAEA_N@Z`
- size: `350`
- prototype: `int(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, bool, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b7bc`

## callees

- `0x18001b838`
- `0x1800809d0`
- `0x180107874`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b874`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001b874`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b904`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b93a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b948`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b904`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b93a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001b948`
- `KERNEL32!CompareFileTime` at `0x18001b8d3`
- `KERNEL32!CompareFileTime` at `0x18001b8d3`

## pseudocode

```c

```
