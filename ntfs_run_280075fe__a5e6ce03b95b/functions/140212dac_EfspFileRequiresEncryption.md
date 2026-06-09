# EfspFileRequiresEncryption

- ea: `0x140212dac`
- end: `0x140213481`
- name: `EfspFileRequiresEncryption`
- size: `1749`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140116180`
- `0x140212b40`

## callees

- `0x140030b70`
- `0x1400313ec`
- `0x140031b38`
- `0x140036464`
- `0x140037f80`
- `0x14003c94c`
- `0x1400586fc`
- `0x140059250`
- `0x140117b40`
- `0x140117db0`
- `0x140117e88`
- `0x140117ed4`
- `0x140118200`
- `0x140119b7c`
- `0x140119ba4`
- `0x140119c94`
- `0x14011c8cc`
- `0x140147658`
- `0x140212dac`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140212e85`
- `ntoskrnl!KeGetCurrentIrql` at `0x140212e85`
- `ntoskrnl!RtlInitUnicodeString` at `0x140212ff1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14021301a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402130d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140212ff1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14021301a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402130d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402133fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213427`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213442`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402133fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213427`
- `ntoskrnl!ExFreePoolWithTag` at `0x140213442`
- `ntoskrnl!ExAcquireFastMutex` at `0x140213072`
- `ntoskrnl!ExAcquireFastMutex` at `0x14021312b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140213072`
- `ntoskrnl!ExAcquireFastMutex` at `0x14021312b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402130aa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140213163`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402130aa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140213163`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x140212f1f`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x140212f1f`
- `ntoskrnl!wcsrchr` at `0x1402131f9`
- `ntoskrnl!wcsrchr` at `0x1402131f9`

## string_xrefs

- `0x140212fe2`: `\Registry\Machine\System\CurrentControlSet\Services\NTFS\EFS\Parameters`
- `0x14021300b`: `EdpExcludedExtensions`
- `0x1402130c4`: `EdpExcludedPaths`

## pseudocode

```c

```
