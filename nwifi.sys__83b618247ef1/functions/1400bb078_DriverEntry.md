# DriverEntry

- ea: `0x1400bb078`
- end: `0x1400bb326`
- name: `DriverEntry`
- size: `686`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400bb010`

## callees

- `0x140036420`
- `0x1400366f8`
- `0x140036750`
- `0x14009a7c0`
- `0x1400b931c`
- `0x1400bb078`
- `0x1400bb32c`
- `0x1400bb4d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb13d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb155`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb16d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb13d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb155`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bb16d`
- `ntoskrnl!EtwRegister` at `0x1400bb2e5`
- `ntoskrnl!EtwRegister` at `0x1400bb2e5`
- `NDIS!NdisFRegisterFilterDriver` at `0x1400bb2b1`
- `NDIS!NdisFRegisterFilterDriver` at `0x1400bb2b1`

## pseudocode

```c

```
