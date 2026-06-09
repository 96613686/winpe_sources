# _ClientUnregisterConfigChangeNotify

- ea: `0x18006d364`
- end: `0x18006d3cc`
- name: `_ClientUnregisterConfigChangeNotify`
- size: `104`
- prototype: `NTSTATUS __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180022788`

## callees

- `0x18006ce00`
- `0x18006d364`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18006d3b7`
- `ntoskrnl!ObfDereferenceObject` at `0x18006d3b7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006d396`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18006d396`
- `ntoskrnl!ExEventObjectType` at `0x18006d36c`

## pseudocode

```c

```
