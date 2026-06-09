# ChatSupportShutdownNotify

- ea: `0x180057498`
- end: `0x180057573`
- name: `ChatSupportShutdownNotify`
- size: `219`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18005d720`

## callees

- `0x180056bb0`
- `0x180056d00`
- `0x180057498`
- `0x18006c440`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005751d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005751d`
- `ntoskrnl!ZwSetValueKey` at `0x18005754b`
- `ntoskrnl!ZwSetValueKey` at `0x18005754b`
- `ntoskrnl!ZwClose` at `0x180057560`
- `ntoskrnl!ZwClose` at `0x180057560`

## string_xrefs

- `0x1800574bc`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\CngHwAssist`

## pseudocode

```c

```
