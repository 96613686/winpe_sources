# DpiFdoExcludeAdapterAccess

- ea: `0x1402a53d0`
- end: `0x1402a58d6`
- name: `DpiFdoExcludeAdapterAccess`
- size: `1286`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x140022264`
- `0x140035dc0`
- `0x140041b54`
- `0x1400a0100`
- `0x1400a0540`
- `0x1402406d0`
- `0x1402407ac`
- `0x1402a53d0`
- `0x140365a0c`
- `0x1403676e0`
- `0x1403de130`
- `0x140400990`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a5535`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a5535`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a5684`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a5684`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5874`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a5874`
- `ntoskrnl!IoFreeWorkItem` at `0x1402a5885`
- `ntoskrnl!IoFreeWorkItem` at `0x1402a5885`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402a555b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402a555b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a5678`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a5678`
- `ntoskrnl!KeSetEvent` at `0x1402a5863`
- `ntoskrnl!KeSetEvent` at `0x1402a5863`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a557b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a557b`
- `ntoskrnl!KeReleaseMutex` at `0x1402a5653`
- `ntoskrnl!KeReleaseMutex` at `0x1402a5653`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402a58a0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402a58a0`
- `watchdog!SMgrGdiCallout` at `0x1402a54dc`
- `watchdog!SMgrGdiCallout` at `0x1402a5737`
- `watchdog!SMgrGdiCallout` at `0x1402a54dc`
- `watchdog!SMgrGdiCallout` at `0x1402a5737`
- `watchdog!WdLogSingleEntry1` at `0x1402a5447`
- `watchdog!WdLogSingleEntry1` at `0x1402a550c`
- `watchdog!WdLogSingleEntry1` at `0x1402a55b3`
- `watchdog!WdLogSingleEntry1` at `0x1402a576b`
- `watchdog!WdLogSingleEntry1` at `0x1402a5828`
- `watchdog!WdLogSingleEntry1` at `0x1402a5447`
- `watchdog!WdLogSingleEntry1` at `0x1402a550c`
- `watchdog!WdLogSingleEntry1` at `0x1402a55b3`
- `watchdog!WdLogSingleEntry1` at `0x1402a576b`
- `watchdog!WdLogSingleEntry1` at `0x1402a5828`

## pseudocode

```c

```
