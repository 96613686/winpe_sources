# NtfsQueryStatLxInfo

- ea: `0x140180dc0`
- end: `0x140181580`
- name: `NtfsQueryStatLxInfo`
- size: `1984`
- prototype: `__int64 __fastcall(__int64, struct _SECURITY_SUBJECT_CONTEXT *, __int64, __int64, int *, _DWORD *, __int64 GrantedAccess)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017ba20`
- `0x1401822c0`
- `0x140182c30`

## callees

- `0x140025a40`
- `0x1400596c0`
- `0x14017ee68`
- `0x14017f870`
- `0x140180dc0`
- `0x140181588`
- `0x14018a850`
- `0x1401ba624`

## import_xrefs

- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140181082`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x140181082`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401814f2`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x1401814f2`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018110f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14018110f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140181150`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140181150`
- `ntoskrnl!SeAccessCheck` at `0x14018119f`
- `ntoskrnl!SeAccessCheck` at `0x14018119f`
- `ntoskrnl!ExReleasePushLockEx` at `0x140181144`
- `ntoskrnl!ExReleasePushLockEx` at `0x140181144`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140180e59`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140180e59`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018132f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401813e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140181541`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aa64e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018132f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401813e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140181541`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aa64e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401812f3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401813ad`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401812f3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401813ad`

## pseudocode

```c

```
