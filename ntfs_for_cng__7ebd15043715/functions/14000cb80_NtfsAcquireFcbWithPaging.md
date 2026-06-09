# NtfsAcquireFcbWithPaging

- ea: `0x14000cb80`
- end: `0x14000d1d5`
- name: `NtfsAcquireFcbWithPaging`
- size: `1621`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `27`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400e7268`
- `0x1400e7f78`
- `0x1400e9d70`
- `0x1400ead40`
- `0x140128140`
- `0x14013b870`
- `0x140179c20`
- `0x14018b0b0`
- `0x14019f300`
- `0x1401b92c0`
- `0x1401eb0c0`
- `0x140202288`
- `0x14020b1b4`
- `0x14020d830`
- `0x140210dd0`
- `0x140235524`
- `0x1402359d0`
- `0x1402376ac`
- `0x140247554`
- `0x14024fba4`
- `0x140252788`
- `0x140254ff0`
- `0x140263ac0`
- `0x140278a70`
- `0x1402836cc`
- `0x14028a29c`
- `0x140298e5c`

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
