# QatSetupDevice

- ea: `0x1401809a0`
- end: `0x140180c88`
- name: `QatSetupDevice`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1401681c0`

## callees

- `0x1401808c8`
- `0x1401809a0`
- `0x1401e9dc0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140180aca`
- `ntoskrnl!IofCallDriver` at `0x140180bad`
- `ntoskrnl!IofCallDriver` at `0x140180aca`
- `ntoskrnl!IofCallDriver` at `0x140180bad`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140180aae`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140180b91`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140180aae`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140180b91`
- `ntoskrnl!ExAllocatePool2` at `0x140180b1c`
- `ntoskrnl!ExAllocatePool2` at `0x140180b1c`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140180a36`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x140180a36`
- `ntoskrnl!ZwLoadDriver` at `0x1401809fb`
- `ntoskrnl!ZwLoadDriver` at `0x1401809fb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140180af2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140180bd5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140180af2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140180bd5`
- `ntoskrnl!KeInitializeEvent` at `0x140180a67`
- `ntoskrnl!KeInitializeEvent` at `0x140180b45`
- `ntoskrnl!KeInitializeEvent` at `0x140180a67`
- `ntoskrnl!KeInitializeEvent` at `0x140180b45`

## string_xrefs

- `0x1401809b4`: `\Registry\Machine\System\CurrentControlSet\Services\CfQat`

## pseudocode

```c

```
