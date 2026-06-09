# KsStreamIo

- ea: `0x180038430`
- end: `0x18003868b`
- name: `KsStreamIo`
- size: `603`
- prototype: `NTSTATUS __stdcall(PFILE_OBJECT FileObject, PKEVENT Event, PVOID PortContext, PIO_COMPLETION_ROUTINE CompletionRoutine, PVOID CompletionContext, KSCOMPLETION_INVOCATION CompletionInvocationFlags, PIO_STATUS_BLOCK IoStatusBlock, PVOID StreamHeaders, ULONG Length, ULONG Flags, KPROCESSOR_MODE RequestorMode)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180019cb0`
- `0x180038430`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1800385fd`
- `ntoskrnl!ObfReferenceObject` at `0x18003860c`
- `ntoskrnl!ObfReferenceObject` at `0x1800385fd`
- `ntoskrnl!ObfReferenceObject` at `0x18003860c`
- `ntoskrnl!IofCallDriver` at `0x180038665`
- `ntoskrnl!IofCallDriver` at `0x180038665`
- `ntoskrnl!ExGetPreviousMode` at `0x18003848f`
- `ntoskrnl!ExGetPreviousMode` at `0x18003848f`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038545`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x180038545`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003846b`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x18003846b`
- `ntoskrnl!KeClearEvent` at `0x18003845c`
- `ntoskrnl!KeClearEvent` at `0x180038519`
- `ntoskrnl!KeClearEvent` at `0x18003845c`
- `ntoskrnl!KeClearEvent` at `0x180038519`
- `ntoskrnl!ExRaiseStatus` at `0x18003856b`
- `ntoskrnl!ExRaiseStatus` at `0x18003856b`

## pseudocode

```c

```
