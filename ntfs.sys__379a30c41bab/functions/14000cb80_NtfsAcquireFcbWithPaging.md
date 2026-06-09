# NtfsAcquireFcbWithPaging

- ea: `0x14000cb80`
- end: `0x14000d1d5`
- name: `NtfsAcquireFcbWithPaging`
- size: `1621`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400e72b8`
- `0x1400e7fc8`
- `0x1400e9dc0`
- `0x1400ead90`
- `0x140128190`
- `0x14013b8c0`
- `0x140179c70`
- `0x14018b100`
- `0x14019f350`
- `0x1401b9310`
- `0x1401eb110`
- `0x1402022d8`
- `0x14020b204`
- `0x14020d880`
- `0x140210e20`
- `0x140235574`
- `0x140235a20`
- `0x1402376fc`
- `0x1402475a4`
- `0x14024fbf4`
- `0x1402527d8`
- `0x140255040`
- `0x140263b10`
- `0x140278ac0`
- `0x14028371c`
- `0x14028a2ec`
- `0x140298eac`

## callees

- `0x14000c290`
- `0x14000cb80`
- `0x14000d1e0`
- `0x14000e220`
- `0x140021590`

## import_xrefs

- `ntoskrnl!FsRtlReleaseEofLock` at `0x14000cbfc`
- `ntoskrnl!FsRtlReleaseEofLock` at `0x14000cbfc`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000cf8e`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14000cf8e`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000cf64`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14000cf64`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cfd1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cfd1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cea6`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000cea6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000cebe`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000cebe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cd48`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ce74`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d011`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cd48`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000ce74`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d011`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000ce5b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14000ce5b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000cdae`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000cdae`

## pseudocode

```c

```
