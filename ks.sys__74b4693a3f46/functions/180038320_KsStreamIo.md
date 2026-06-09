# KsStreamIo

- ea: `0x180038320`
- end: `0x18003857b`
- name: `KsStreamIo`
- size: `603`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, PKEVENT Event, PVOID PortContext, PIO_COMPLETION_ROUTINE CompletionRoutine, PVOID CompletionContext, KSCOMPLETION_INVOCATION CompletionInvocationFlags, PIO_STATUS_BLOCK IoStatusBlock, PVOID StreamHeaders, ULONG Length, ULONG Flags, KPROCESSOR_MODE RequestorMode)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019c60`
- `0x180038320`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1800384ed`
- `ntoskrnl!ObfReferenceObject` at `0x1800384fc`
- `ntoskrnl!ObfReferenceObject` at `0x1800384ed`
- `ntoskrnl!ObfReferenceObject` at `0x1800384fc`
- `ntoskrnl!IofCallDriver` at `0x180038555`
- `ntoskrnl!IofCallDriver` at `0x180038555`
- `ntoskrnl!ExGetPreviousMode` at `0x18003837f`
- `ntoskrnl!ExGetPreviousMode` at `0x18003837f`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038435`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038435`
- `ntoskrnl!ExRaiseStatus` at `0x18003845b`
- `ntoskrnl!ExRaiseStatus` at `0x18003845b`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003835b`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003835b`
- `ntoskrnl!KeClearEvent` at `0x18003834c`
- `ntoskrnl!KeClearEvent` at `0x180038409`
- `ntoskrnl!KeClearEvent` at `0x18003834c`
- `ntoskrnl!KeClearEvent` at `0x180038409`

## pseudocode

```c

```
