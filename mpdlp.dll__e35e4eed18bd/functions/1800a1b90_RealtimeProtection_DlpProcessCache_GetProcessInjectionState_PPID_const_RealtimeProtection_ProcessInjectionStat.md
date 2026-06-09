# RealtimeProtection::DlpProcessCache::GetProcessInjectionState(PPID const &,RealtimeProtection::ProcessInjectionState &)

- ea: `0x1800a1b90`
- end: `0x1800a1ce6`
- name: `?GetProcessInjectionState@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@AEAUProcessInjectionState@2@@Z`
- size: `342`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime1, const struct PPID *, struct RealtimeProtection::ProcessInjectionState *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180069cb8`
- `0x1800af07c`
- `0x18019fc84`

## callees

- `0x180028d80`
- `0x1800a1b90`
- `0x180107874`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x1800a1bf9`
- `KERNEL32!AcquireSRWLockShared` at `0x1800a1bf9`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800a1c87`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800a1cc6`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800a1c87`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800a1cc6`
- `KERNEL32!CompareFileTime` at `0x1800a1c62`
- `KERNEL32!CompareFileTime` at `0x1800a1c62`

## pseudocode

```c

```
