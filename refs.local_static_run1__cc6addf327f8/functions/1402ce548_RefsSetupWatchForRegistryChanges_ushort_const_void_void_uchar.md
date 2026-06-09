# RefsSetupWatchForRegistryChanges(ushort const *,void (*)(void *),uchar)

- ea: `0x1402ce548`
- end: `0x1402ce7e0`
- name: `?RefsSetupWatchForRegistryChanges@@YAXPEBGP6AXPEAX@ZE@Z`
- size: `664`
- prototype: `void __fastcall(PCWSTR SourceString, void (*)(void *), unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1402d15d0`
- `0x14034fc48`

## callees

- `0x1400862c0`
- `0x1400d0fd8`
- `0x1401f4400`
- `0x1402ce418`
- `0x1402ce548`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1402ce7d2`
- `ntoskrnl!ExQueueWorkItem` at `0x140348b01`
- `ntoskrnl!ExQueueWorkItem` at `0x1402ce7d2`
- `ntoskrnl!ExQueueWorkItem` at `0x140348b01`
- `ntoskrnl!DbgPrintEx` at `0x1402ce6f3`
- `ntoskrnl!DbgPrintEx` at `0x1402ce71e`
- `ntoskrnl!DbgPrintEx` at `0x1402ce76d`
- `ntoskrnl!DbgPrintEx` at `0x1402ce7ba`
- `ntoskrnl!DbgPrintEx` at `0x140348a9f`
- `ntoskrnl!DbgPrintEx` at `0x140348ae9`
- `ntoskrnl!DbgPrintEx` at `0x1402ce6f3`
- `ntoskrnl!DbgPrintEx` at `0x1402ce71e`
- `ntoskrnl!DbgPrintEx` at `0x1402ce76d`
- `ntoskrnl!DbgPrintEx` at `0x1402ce7ba`
- `ntoskrnl!DbgPrintEx` at `0x140348a9f`
- `ntoskrnl!DbgPrintEx` at `0x140348ae9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ce62a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ce62a`
- `ntoskrnl!ZwClose` at `0x1402ce744`
- `ntoskrnl!ZwClose` at `0x140348a76`
- `ntoskrnl!ZwClose` at `0x1402ce744`
- `ntoskrnl!ZwClose` at `0x140348a76`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1402ce6c8`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1402ce6c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ce77e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140348ab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ce77e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140348ab0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ce58d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ce58d`

## string_xrefs

- `0x1402ce671`: `ReFS: SetupRegWatch: Failed Deepst Key open, status=0x%08x "%wZ"\n`
- `0x1402ce7a9`: `ReFS: SetupRegWatch: Queing private worker thread, status=0x%08x "%wZ"\n`
- `0x140348ad8`: `ReFS: SetupRegWatch: Queing private worker thread, status=0x%08x "%wZ"\n`

## pseudocode

```c

```
