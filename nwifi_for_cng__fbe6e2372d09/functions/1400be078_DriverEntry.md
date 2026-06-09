# DriverEntry

- ea: `0x1400be078`
- end: `0x1400be326`
- name: `DriverEntry`
- size: `686`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400be010`

## callees

- `0x140036640`
- `0x140036918`
- `0x140036970`
- `0x14009bfc0`
- `0x1400bc31c`
- `0x1400be078`
- `0x1400be32c`
- `0x1400be4d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400be13d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be155`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be16d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be13d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be155`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be16d`
- `ntoskrnl!EtwRegister` at `0x1400be2e5`
- `ntoskrnl!EtwRegister` at `0x1400be2e5`
- `NDIS!NdisFRegisterFilterDriver` at `0x1400be2b1`
- `NDIS!NdisFRegisterFilterDriver` at `0x1400be2b1`

## pseudocode

```c

```
