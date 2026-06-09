# FltLoadFilter

- ea: `0x180053970`
- end: `0x1800539f8`
- name: `FltLoadFilter`
- size: `136`
- prototype: `NTSTATUS __stdcall(PCUNICODE_STRING FilterName)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18004e900`

## callees

- `0x1800247a0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800539ad`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800539ad`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800539c1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800539c1`
- `ntoskrnl!ZwLoadDriver` at `0x1800539d2`
- `ntoskrnl!ZwLoadDriver` at `0x1800539d2`

## string_xrefs

- `0x1800539a6`: `\Registry\Machine\System\ControlSet001\Services\`

## pseudocode

```c

```
