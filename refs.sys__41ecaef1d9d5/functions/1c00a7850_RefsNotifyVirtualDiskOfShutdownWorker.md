# RefsNotifyVirtualDiskOfShutdownWorker

- ea: `0x1c00a7850`
- end: `0x1c00a7973`
- name: `RefsNotifyVirtualDiskOfShutdownWorker`
- size: `291`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1c000f920`
- `0x1c00a7850`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c00a78a3`
- `ntoskrnl!KeInitializeEvent` at `0x1c00a78a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00a7941`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c00a7941`
- `ntoskrnl!KeClearEvent` at `0x1c00a7951`
- `ntoskrnl!KeClearEvent` at `0x1c00a7951`
- `ntoskrnl!IofCompleteRequest` at `0x1c00a791d`
- `ntoskrnl!IofCompleteRequest` at `0x1c00a791d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1c00a78e7`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1c00a78e7`

## pseudocode

```c

```
