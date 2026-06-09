# UxpSslInitializeCcsConfigurationByRegistryIndex

- ea: `0x140135ac0`
- end: `0x140135cfd`
- name: `UxpSslInitializeCcsConfigurationByRegistryIndex`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task`

## callees

- `0x14002a0a8`
- `0x14008e76c`
- `0x14008ebcc`
- `0x14008ef04`
- `0x140090790`
- `0x140094f40`
- `0x140135ac0`
- `0x1401677e0`
- `0x1401c3f58`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140135cec`
- `ntoskrnl!RtlInitUnicodeString` at `0x140135cec`
- `ntoskrnl!ZwClose` at `0x140135b8c`
- `ntoskrnl!ZwClose` at `0x140135b8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140135b73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140135c61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140135b73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140135c61`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140135b09`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140135b09`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140135b67`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140135c55`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140135b67`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140135c55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140135aeb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140135aeb`

## string_xrefs

- `0x140135b26`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\SslCcsBindingInfo`

## pseudocode

```c

```
