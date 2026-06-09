# SlowLinkp_LogTimeToText(_FILETIME const &,ushort *,ulong)

- ea: `0x180060548`
- end: `0x1800605e0`
- name: `?SlowLinkp_LogTimeToText@@YAJAEBU_FILETIME@@PEAGK@Z`
- size: `152`
- prototype: `int(const struct _FILETIME *, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180060160`
- `0x180060354`
- `0x1800606d4`
- `0x180060888`

## callees

- `0x180039610`
- `0x180060548`

## import_xrefs

- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800605b9`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatW` at `0x1800605b9`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180060577`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x180060577`
- `KERNEL32!FileTimeToSystemTime` at `0x180060593`
- `KERNEL32!FileTimeToSystemTime` at `0x180060593`

## pseudocode

```c

```
