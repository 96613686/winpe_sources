# GetRegistryValue(void *,ushort *,ulong,void *,ulong)

- ea: `0x18003b26c`
- end: `0x18003b371`
- name: `?GetRegistryValue@@YAJPEAXPEAGK0K@Z`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, unsigned __int16 *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005ce9c`

## callees

- `0x180019cc0`
- `0x180019fc0`
- `0x18003b26c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003b29f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003b29f`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b320`
- `ntoskrnl!ZwQueryValueKey` at `0x18003b320`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003b359`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003b359`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b2c6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003b2c6`

## pseudocode

```c

```
