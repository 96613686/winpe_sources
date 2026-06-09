# UxpSslInitializeIpConfigurationByRegistryIndex

- ea: `0x14008e980`
- end: `0x14008eba5`
- name: `UxpSslInitializeIpConfigurationByRegistryIndex`
- size: `549`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x14008e980`
- `0x14008ebac`
- `0x14008ee5c`
- `0x14008eee4`
- `0x140090770`
- `0x1401678f0`
- `0x1401c3f58`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14008eb62`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008eb62`
- `ntoskrnl!ZwClose` at `0x14008ea55`
- `ntoskrnl!ZwClose` at `0x14008ea55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ea3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008eaab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008ea3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14008eaab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ea6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008ea6f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14008e9c3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14008e9c3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008ea31`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008ea9f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008ea31`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14008ea9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008e9a5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008e9a5`

## string_xrefs

- `0x14008e9e0`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\SslBindingInfo`

## pseudocode

```c

```
