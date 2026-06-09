# ClassDisableMediaChangeDetection

- ea: `0x140054350`
- end: `0x1400543da`
- name: `ClassDisableMediaChangeDetection`
- size: `138`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400553f4`

## callees

- `0x14001fbf4`
- `0x140054350`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400543c7`
- `ntoskrnl!KeReleaseMutex` at `0x1400543c7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054378`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054378`

## pseudocode

```c

```
