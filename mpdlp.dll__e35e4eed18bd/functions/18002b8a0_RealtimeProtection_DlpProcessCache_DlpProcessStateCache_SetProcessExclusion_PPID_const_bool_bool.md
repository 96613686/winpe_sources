# RealtimeProtection::DlpProcessCache::DlpProcessStateCache::SetProcessExclusion(PPID const &,bool,bool)

- ea: `0x18002b8a0`
- end: `0x18002ba47`
- name: `?SetProcessExclusion@DlpProcessStateCache@DlpProcessCache@RealtimeProtection@@QEAAJAEBUPPID@@_N1@Z`
- size: `423`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpProcessCache::DlpProcessStateCache *__hidden this, const struct PPID *, bool, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002a020`
- `0x18002c2b0`

## callees

- `0x180028a10`
- `0x18002b8a0`
- `0x18002ba50`
- `0x1800809d0`
- `0x180107874`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b8eb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002b8eb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b98b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b9f7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b98b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002b9f7`
- `KERNEL32!CompareFileTime` at `0x18002b951`
- `KERNEL32!CompareFileTime` at `0x18002b951`

## pseudocode

```c

```
