# ChangeJournal::Read(VolumeId const &,__int64 const &,unsigned __int64 const &,USN_RECORD_V2 &)

- ea: `0x14008c620`
- end: `0x14008c82b`
- name: `?Read@ChangeJournal@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEB_JAEB_KAEAUUSN_RECORD_V2@@@Z`
- size: `523`
- prototype: `struct FrsStatus *__fastcall(ChangeJournal *__hidden this, const struct VolumeId *, const __int64 *, const unsigned __int64 *, struct USN_RECORD_V2 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1400036a0`
- `0x14005c620`
- `0x14008c620`
- `0x1401af7b0`
- `0x1401af7c0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14008c687`
- `KERNEL32!CreateFileW` at `0x14008c687`
- `KERNEL32!DeviceIoControl` at `0x14008c76d`
- `KERNEL32!DeviceIoControl` at `0x14008c76d`
- `KERNEL32!GetLastError` at `0x14008c6b3`
- `KERNEL32!GetLastError` at `0x14008c78b`
- `KERNEL32!GetLastError` at `0x14008c6b3`
- `KERNEL32!GetLastError` at `0x14008c78b`
- `KERNEL32!GetCurrentThreadId` at `0x14008c6a5`
- `KERNEL32!GetCurrentThreadId` at `0x14008c77d`
- `KERNEL32!GetCurrentThreadId` at `0x14008c6a5`
- `KERNEL32!GetCurrentThreadId` at `0x14008c77d`

## string_xrefs

- `0x14008c6c4`: `ChangeJournal::Read`
- `0x14008c79d`: `ChangeJournal::Read`

## pseudocode

```c

```
