# Dlp::BrowserCache::DLPBrowserCache::UpdateBrowserSessionHeartBeat(wchar_t const *,ulong,unsigned __int64,std::optional<std::basic_string_view<char,std::char_traits<char>>> const &)

- ea: `0x1800aa748`
- end: `0x1800aaccf`
- name: `?UpdateBrowserSessionHeartBeat@DLPBrowserCache@BrowserCache@Dlp@@QEAAJPEB_WK_KAEBV?$optional@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@std@@@Z`
- size: `1415`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, __int64, int, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x1800b6650`

## callees

- `0x180004120`
- `0x180005c28`
- `0x180034420`
- `0x180038450`
- `0x180079dc0`
- `0x1800809d0`
- `0x1800aa748`
- `0x1800aacd0`
- `0x1800aada8`
- `0x1800ae33c`
- `0x1800b3710`
- `0x1800b8fcc`
- `0x1800bb228`
- `0x1800bff48`
- `0x18010cb40`
- `0x18014f1dc`
- `0x1801507cc`
- `0x180150afc`
- `0x180151268`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa796`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800aa796`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aaab8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aab2d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aabc0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aaab8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aab2d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800aabc0`

## string_xrefs

- `0x1800aab5b`: `DLP::UpdateBrowserSessionHeartBeat cleaned up evaluated entry filename=%ls, cleanupInterval=%llu`
- `0x1800aabea`: `DLP::UpdateBrowserSessionHeartBeat cleaned up unevaluated entry filename=%ls, cleanupInterval=%llu`

## pseudocode

```c

```
