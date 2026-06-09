# GetRegistryValue(void *,ushort *,ulong,void *,ulong)

- ea: `0x18003b25c`
- end: `0x18003b361`
- name: `?GetRegistryValue@@YAJPEAXPEAGK0K@Z`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, unsigned __int16 *, __int64, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005d03c`

## callees

- `0x180019d00`
- `0x18001a000`
- `0x18003b25c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003b28f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b28f`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b310`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b310`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003b349`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003b349`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b2b6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b2b6`

## pseudocode

```c

```
