# ChangeJournal::QueryWithDelete(VolumeId const &,USN_JOURNAL_DATA_V1 &)

- ea: `0x14008c3a4`
- end: `0x14008c613`
- name: `?QueryWithDelete@ChangeJournal@@AEAAPEAVFrsStatus@@AEBVVolumeId@@AEAUUSN_JOURNAL_DATA_V1@@@Z`
- size: `623`
- prototype: `struct FrsStatus *(ChangeJournal *__hidden this, const struct VolumeId *, struct USN_JOURNAL_DATA_V1 *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14008a754`
- `0x14008c050`
- `0x14008c834`

## callees

- `0x1400036a0`
- `0x14000cdc0`
- `0x140089c5c`
- `0x14008c3a4`
- `0x1400bf79c`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x14008c423`
- `KERNEL32!DeviceIoControl` at `0x14008c491`
- `KERNEL32!DeviceIoControl` at `0x14008c423`
- `KERNEL32!DeviceIoControl` at `0x14008c491`
- `KERNEL32!GetLastError` at `0x14008c437`
- `KERNEL32!GetLastError` at `0x14008c4b3`
- `KERNEL32!GetLastError` at `0x14008c437`
- `KERNEL32!GetLastError` at `0x14008c4b3`
- `KERNEL32!GetCurrentThreadId` at `0x14008c4a5`
- `KERNEL32!GetCurrentThreadId` at `0x14008c4ec`
- `KERNEL32!GetCurrentThreadId` at `0x14008c59c`
- `KERNEL32!GetCurrentThreadId` at `0x14008c4a5`
- `KERNEL32!GetCurrentThreadId` at `0x14008c4ec`
- `KERNEL32!GetCurrentThreadId` at `0x14008c59c`

## string_xrefs

- `0x14008c4d0`: `ChangeJournal::QueryWithDelete`
- `0x14008c509`: `ChangeJournal::QueryWithDelete`
- `0x14008c5b9`: `ChangeJournal::QueryWithDelete`
- `0x14008c55e`: `ChangeJournal::QueryWithDelete`

## pseudocode

```c

```
