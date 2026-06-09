# FREE_PORT_ALLOCATED_SENSE_BUFFER

- ea: `0x140026640`
- end: `0x140026689`
- name: `FREE_PORT_ALLOCATED_SENSE_BUFFER`
- size: `73`
- prototype: `void __stdcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PSCSI_REQUEST_BLOCK Srb)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140016350`
- `0x140022920`
- `0x140037e10`

## callees

- `0x140012e18`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026656`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026656`

## pseudocode

```c

```
