# QatSetupDevice

- ea: `0x14018ac6c`
- end: `0x14018af54`
- name: `QatSetupDevice`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1401723d0`

## callees

- `0x14018ab94`
- `0x14018ac6c`
- `0x1401f4090`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14018ad96`
- `ntoskrnl!IofCallDriver` at `0x14018ae79`
- `ntoskrnl!IofCallDriver` at `0x14018ad96`
- `ntoskrnl!IofCallDriver` at `0x14018ae79`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14018ad7a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14018ae5d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14018ad7a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14018ae5d`
- `ntoskrnl!ExAllocatePool2` at `0x14018ade8`
- `ntoskrnl!ExAllocatePool2` at `0x14018ade8`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018ad02`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x14018ad02`
- `ntoskrnl!ZwLoadDriver` at `0x14018acc7`
- `ntoskrnl!ZwLoadDriver` at `0x14018acc7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018adbe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018aea1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018adbe`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018aea1`
- `ntoskrnl!KeInitializeEvent` at `0x14018ad33`
- `ntoskrnl!KeInitializeEvent` at `0x14018ae11`
- `ntoskrnl!KeInitializeEvent` at `0x14018ad33`
- `ntoskrnl!KeInitializeEvent` at `0x14018ae11`

## string_xrefs

- `0x14018ac80`: `\Registry\Machine\System\CurrentControlSet\Services\CfQat`

## pseudocode

```c

```
