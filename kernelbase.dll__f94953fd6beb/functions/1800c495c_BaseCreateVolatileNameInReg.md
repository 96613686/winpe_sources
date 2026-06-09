# BaseCreateVolatileNameInReg

- ea: `0x1800c495c`
- end: `0x1800c4ab2`
- name: `BaseCreateVolatileNameInReg`
- size: `342`
- prototype: `__int64 __fastcall(PVOID Data)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c4be0`

## callees

- `0x1800c495c`
- `0x1800c512c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800c49a9`
- `ntdll!RtlInitUnicodeString` at `0x1800c49ba`
- `ntdll!RtlInitUnicodeString` at `0x1800c4a78`
- `ntdll!RtlInitUnicodeString` at `0x1800c49a9`
- `ntdll!RtlInitUnicodeString` at `0x1800c49ba`
- `ntdll!RtlInitUnicodeString` at `0x1800c4a78`
- `ntdll!wcslen` at `0x1800c4a81`
- `ntdll!wcslen` at `0x1800c4a81`
- `ntdll!NtCreateKey` at `0x1800c4a10`
- `ntdll!NtCreateKey` at `0x1800c4a10`
- `ntdll!NtSetValueKey` at `0x1800c4aa8`
- `ntdll!NtSetValueKey` at `0x1800c4aa8`
- `ntdll!NtClose` at `0x1800c4a52`
- `ntdll!NtClose` at `0x1800c4a52`

## string_xrefs

- `0x1800c49af`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x1800c4a33`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x1800c4982`: `Network ComputerName`
- `0x1800c4a2a`: `ComputerName`
- `0x1800c4a6d`: `ComputerName`

## pseudocode

```c

```
