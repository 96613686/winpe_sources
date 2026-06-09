# UxpSslInitializeIpConfigurationByRegistryIndex

- ea: `0x14008e9a0`
- end: `0x14008ebc5`
- name: `UxpSslInitializeIpConfigurationByRegistryIndex`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x14008e9a0`
- `0x14008ebcc`
- `0x14008ee7c`
- `0x14008ef04`
- `0x140090790`
- `0x1401677e0`
- `0x1401c3f58`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14008eb82`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008eb82`
- `ntoskrnl!ZwClose` at `0x14008ea75`
- `ntoskrnl!ZwClose` at `0x14008ea75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ea5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008eacb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ea5d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008eacb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ea8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ea8f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14008e9e3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14008e9e3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008ea51`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008eabf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008ea51`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008eabf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008e9c5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008e9c5`

## string_xrefs

- `0x14008ea00`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\SslBindingInfo`

## pseudocode

```c

```
