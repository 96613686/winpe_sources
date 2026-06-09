# EfspFileRequiresEncryption

- ea: `0x1402f1420`
- end: `0x1402f1af8`
- name: `EfspFileRequiresEncryption`
- size: `1752`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1402efc80`
- `0x1402f0420`

## callees

- `0x140001008`
- `0x1400081a4`
- `0x1400081e4`
- `0x140049050`
- `0x14011001c`
- `0x1401100a0`
- `0x140110b94`
- `0x1401f3fb0`
- `0x1402f1420`
- `0x1402f327c`
- `0x1402f36d0`
- `0x1402f37a8`
- `0x1402f37f4`
- `0x1402f3b20`
- `0x1402f5df8`
- `0x1402f5e84`
- `0x1402f605c`
- `0x1402f6d44`
- `0x1402f9d18`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1402f14f9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1402f14f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402f1665`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402f168e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402f1747`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402f1665`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402f168e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402f1747`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402f16e6`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402f179f`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402f16e6`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402f179f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402f171e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402f17d7`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402f171e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402f17d7`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x1402f1593`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x1402f1593`
- `ntoskrnl!wcsrchr` at `0x1402f186d`
- `ntoskrnl!wcsrchr` at `0x1402f186d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f1a73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f1a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f1ab9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f1a73`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f1a9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402f1ab9`

## string_xrefs

- `0x1402f1656`: `\Registry\Machine\System\CurrentControlSet\Services\NTFS\EFS\Parameters`
- `0x1402f167f`: `EdpExcludedExtensions`
- `0x1402f1738`: `EdpExcludedPaths`

## pseudocode

```c

```
