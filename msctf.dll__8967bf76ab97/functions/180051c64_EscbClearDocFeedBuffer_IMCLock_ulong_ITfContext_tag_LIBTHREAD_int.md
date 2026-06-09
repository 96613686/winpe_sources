# EscbClearDocFeedBuffer(IMCLock &,ulong,ITfContext *,tag_LIBTHREAD *,int)

- ea: `0x180051c64`
- end: `0x180051dfb`
- name: `?EscbClearDocFeedBuffer@@YAJAEAVIMCLock@@KPEAUITfContext@@PEAUtag_LIBTHREAD@@H@Z`
- size: `407`
- prototype: `int(struct IMCLock *, unsigned int, struct ITfContext *, struct tag_LIBTHREAD *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180017730`
- `0x180051b14`
- `0x180096e70`
- `0x1800e6738`

## callees

- `0x1800185f0`
- `0x180051c64`
- `0x180051e04`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051dac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051d03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051d03`
- `IMM32!ImmLockIMCC` at `0x180051cb0`
- `IMM32!ImmLockIMCC` at `0x180051cb0`
- `IMM32!ImmUnlockIMCC` at `0x180051da2`
- `IMM32!ImmUnlockIMCC` at `0x180051da2`

## pseudocode

```c

```
