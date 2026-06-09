# RefsSetupWatchForRegistryChanges(ushort const *,void (*)(void *),uchar)

- ea: `0x1402c9528`
- end: `0x1402c97c0`
- name: `?RefsSetupWatchForRegistryChanges@@YAXPEBGP6AXPEAX@ZE@Z`
- size: `664`
- prototype: `void __fastcall(PCWSTR SourceString, void (*)(void *), unsigned __int8)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1402cc6f0`
- `0x14034cc48`

## callees

- `0x14008dbd0`
- `0x1400ca788`
- `0x1401ea140`
- `0x1402c93f8`
- `0x1402c9528`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1402c97b2`
- `ntoskrnl!ExQueueWorkItem` at `0x140345be2`
- `ntoskrnl!ExQueueWorkItem` at `0x1402c97b2`
- `ntoskrnl!ExQueueWorkItem` at `0x140345be2`
- `ntoskrnl!DbgPrintEx` at `0x1402c96d3`
- `ntoskrnl!DbgPrintEx` at `0x1402c96fe`
- `ntoskrnl!DbgPrintEx` at `0x1402c974d`
- `ntoskrnl!DbgPrintEx` at `0x1402c979a`
- `ntoskrnl!DbgPrintEx` at `0x140345b80`
- `ntoskrnl!DbgPrintEx` at `0x140345bca`
- `ntoskrnl!DbgPrintEx` at `0x1402c96d3`
- `ntoskrnl!DbgPrintEx` at `0x1402c96fe`
- `ntoskrnl!DbgPrintEx` at `0x1402c974d`
- `ntoskrnl!DbgPrintEx` at `0x1402c979a`
- `ntoskrnl!DbgPrintEx` at `0x140345b80`
- `ntoskrnl!DbgPrintEx` at `0x140345bca`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c960a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402c960a`
- `ntoskrnl!ZwClose` at `0x1402c9724`
- `ntoskrnl!ZwClose` at `0x140345b57`
- `ntoskrnl!ZwClose` at `0x1402c9724`
- `ntoskrnl!ZwClose` at `0x140345b57`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1402c96a8`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1402c96a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c975e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402c975e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140345b91`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402c956d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402c956d`

## string_xrefs

- `0x1402c9651`: `ReFS: SetupRegWatch: Failed Deepst Key open, status=0x%08x "%wZ"\n`
- `0x1402c9789`: `ReFS: SetupRegWatch: Queing private worker thread, status=0x%08x "%wZ"\n`
- `0x140345bb9`: `ReFS: SetupRegWatch: Queing private worker thread, status=0x%08x "%wZ"\n`

## pseudocode

```c

```
