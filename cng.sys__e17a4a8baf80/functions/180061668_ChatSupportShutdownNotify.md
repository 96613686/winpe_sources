# ChatSupportShutdownNotify

- ea: `0x180061668`
- end: `0x180061743`
- name: `ChatSupportShutdownNotify`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800678f0`

## callees

- `0x180060d80`
- `0x180060ed0`
- `0x180061668`
- `0x1800765e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800616ed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800616ed`
- `ntoskrnl!ZwSetValueKey` at `0x18006171b`
- `ntoskrnl!ZwSetValueKey` at `0x18006171b`
- `ntoskrnl!ZwClose` at `0x180061730`
- `ntoskrnl!ZwClose` at `0x180061730`

## string_xrefs

- `0x18006168c`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\CngHwAssist`

## pseudocode

```c

```
