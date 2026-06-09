# NdisSetJobObjectCompartmentId(_EJOB *,uint)

- ea: `0x14014e8dc`
- end: `0x14014ea2b`
- name: `?NdisSetJobObjectCompartmentId@@YAJPEAU_EJOB@@I@Z`
- size: `335`
- prototype: `int(struct _EJOB *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400ce840`

## callees

- `0x1400483a0`
- `0x140048440`
- `0x1400484a0`
- `0x1400489b0`
- `0x1400ce708`
- `0x1400d355c`
- `0x14014e8dc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14014e9f5`
- `ntoskrnl!ObfDereferenceObject` at `0x14014ea09`
- `ntoskrnl!ObfDereferenceObject` at `0x14014e9f5`
- `ntoskrnl!ObfDereferenceObject` at `0x14014ea09`
- `ntoskrnl!PsGetJobProperty` at `0x14014e95b`
- `ntoskrnl!PsGetJobProperty` at `0x14014e95b`
- `ntoskrnl!PsSetJobProperty` at `0x14014e975`
- `ntoskrnl!PsSetJobProperty` at `0x14014e993`
- `ntoskrnl!PsSetJobProperty` at `0x14014e975`
- `ntoskrnl!PsSetJobProperty` at `0x14014e993`

## pseudocode

```c

```
