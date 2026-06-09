# _ClientRegisterConfigChangeNotify

- ea: `0x180022104`
- end: `0x180022185`
- name: `_ClientRegisterConfigChangeNotify`
- size: `129`
- prototype: `NTSTATUS __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180022788`

## callees

- `0x180022104`
- `0x18002218c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18002216b`
- `ntoskrnl!ObfDereferenceObject` at `0x18002216b`
- `ntoskrnl!PsGetCurrentProcess` at `0x18002214f`
- `ntoskrnl!PsGetCurrentProcess` at `0x18002214f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18002213a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x18002213a`
- `ntoskrnl!ExEventObjectType` at `0x180022110`

## pseudocode

```c

```
