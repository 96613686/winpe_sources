# RealtimeProtection::DlpEngineUtils::IsExcludedProcess(ulong,PPID const &,wchar_t const *)

- ea: `0x18002a020`
- end: `0x18002a392`
- name: `?IsExcludedProcess@DlpEngineUtils@RealtimeProtection@@YA_NKAEBUPPID@@PEB_W@Z`
- size: `882`
- prototype: `bool(RealtimeProtection::DlpEngineUtils *__hidden this, unsigned int, const struct PPID *, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800538c4`

## callees

- `0x180028a10`
- `0x180028d80`
- `0x18002a020`
- `0x18002a3a0`
- `0x18002abb0`
- `0x18002b050`
- `0x18002b8a0`
- `0x1800809d0`
- `0x180107874`
- `0x18010b558`
- `0x18010b568`
- `0x18010cb40`
- `0x180211e60`
- `0x18023a290`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x18002a084`
- `KERNEL32!AcquireSRWLockShared` at `0x18002a084`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002a10f`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002a188`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002a10f`
- `KERNEL32!ReleaseSRWLockShared` at `0x18002a188`
- `KERNEL32!CompareFileTime` at `0x18002a0f0`
- `KERNEL32!CompareFileTime` at `0x18002a0f0`

## pseudocode

```c

```
