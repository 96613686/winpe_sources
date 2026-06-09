# NtfsQueryStatInfo

- ea: `0x140183a20`
- end: `0x1401841bc`
- name: `NtfsQueryStatInfo`
- size: `1948`
- prototype: `void __fastcall(__int64, struct _SECURITY_SUBJECT_CONTEXT *, __int64, __int64, _QWORD *, _DWORD *, __int64, char)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017ba20`
- `0x1401822c0`
- `0x140182c30`

## callees

- `0x140025a40`
- `0x1400596c0`
- `0x14017e4c0`
- `0x140183a20`
- `0x14018a850`
- `0x1401ba624`

## import_xrefs

- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140183e11`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140183e11`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140184149`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x140184149`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140183d0e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140183d0e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140183d50`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140183d50`
- `ntoskrnl!SeAccessCheck` at `0x140183d9e`
- `ntoskrnl!SeAccessCheck` at `0x140183d9e`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140183e35`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140183e35`
- `ntoskrnl!ExReleasePushLockEx` at `0x140183d44`
- `ntoskrnl!ExReleasePushLockEx` at `0x140183d44`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140183aaa`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140183aaa`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183e7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183f86`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183ff9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140184188`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aaa5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183e7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183f86`
- `ntoskrnl!ExReleaseResourceLite` at `0x140183ff9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140184188`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aaa5b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183e56`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183f44`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183fbd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183e56`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183f44`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140183fbd`

## pseudocode

```c

```
