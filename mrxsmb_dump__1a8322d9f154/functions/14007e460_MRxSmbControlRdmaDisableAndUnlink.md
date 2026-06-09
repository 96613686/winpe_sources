# MRxSmbControlRdmaDisableAndUnlink

- ea: `0x14007e460`
- end: `0x14007e614`
- name: `MRxSmbControlRdmaDisableAndUnlink`
- size: `436`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14007e37c`

## callees

- `0x140004938`
- `0x14003838c`
- `0x14004274c`
- `0x14007e460`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14007e565`
- `ntoskrnl!ZwClose` at `0x14007e565`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14007e534`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14007e534`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007e5a4`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14007e5a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007e4c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007e591`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007e4c8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14007e591`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007e491`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14007e491`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007e47c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14007e47c`

## pseudocode

```c

```
