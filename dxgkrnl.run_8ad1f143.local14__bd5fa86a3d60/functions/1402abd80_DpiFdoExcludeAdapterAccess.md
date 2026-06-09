# DpiFdoExcludeAdapterAccess

- ea: `0x1402abd80`
- end: `0x1402ac286`
- name: `DpiFdoExcludeAdapterAccess`
- size: `1286`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x140022434`
- `0x140035f90`
- `0x140041db4`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x140243230`
- `0x14024330c`
- `0x1402abd80`
- `0x140365a4c`
- `0x140367720`
- `0x1403de550`
- `0x1403fe3f0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402abee5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402abee5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402ac034`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402ac034`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac224`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ac224`
- `ntoskrnl!IoFreeWorkItem` at `0x1402ac235`
- `ntoskrnl!IoFreeWorkItem` at `0x1402ac235`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402abf0b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402abf0b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ac028`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ac028`
- `ntoskrnl!KeSetEvent` at `0x1402ac213`
- `ntoskrnl!KeSetEvent` at `0x1402ac213`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402abf2b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402abf2b`
- `ntoskrnl!KeReleaseMutex` at `0x1402ac003`
- `ntoskrnl!KeReleaseMutex` at `0x1402ac003`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402ac250`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402ac250`
- `watchdog!SMgrGdiCallout` at `0x1402abe8c`
- `watchdog!SMgrGdiCallout` at `0x1402ac0e7`
- `watchdog!SMgrGdiCallout` at `0x1402abe8c`
- `watchdog!SMgrGdiCallout` at `0x1402ac0e7`
- `watchdog!WdLogSingleEntry1` at `0x1402abdf7`
- `watchdog!WdLogSingleEntry1` at `0x1402abebc`
- `watchdog!WdLogSingleEntry1` at `0x1402abf63`
- `watchdog!WdLogSingleEntry1` at `0x1402ac11b`
- `watchdog!WdLogSingleEntry1` at `0x1402ac1d8`
- `watchdog!WdLogSingleEntry1` at `0x1402abdf7`
- `watchdog!WdLogSingleEntry1` at `0x1402abebc`
- `watchdog!WdLogSingleEntry1` at `0x1402abf63`
- `watchdog!WdLogSingleEntry1` at `0x1402ac11b`
- `watchdog!WdLogSingleEntry1` at `0x1402ac1d8`

## pseudocode

```c

```
