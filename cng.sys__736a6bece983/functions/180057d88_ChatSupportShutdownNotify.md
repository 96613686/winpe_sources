# ChatSupportShutdownNotify

- ea: `0x180057d88`
- end: `0x180057e63`
- name: `ChatSupportShutdownNotify`
- size: `219`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18005e010`

## callees

- `0x1800574a0`
- `0x1800575f0`
- `0x180057d88`
- `0x18006ce40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180057e0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x180057e0d`
- `ntoskrnl!ZwSetValueKey` at `0x180057e3b`
- `ntoskrnl!ZwSetValueKey` at `0x180057e3b`
- `ntoskrnl!ZwClose` at `0x180057e50`
- `ntoskrnl!ZwClose` at `0x180057e50`

## string_xrefs

- `0x180057dac`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\CngHwAssist`

## pseudocode

```c

```
