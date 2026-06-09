# NdisSetJobObjectCompartmentId(_EJOB *,uint)

- ea: `0x14014793c`
- end: `0x140147a8b`
- name: `?NdisSetJobObjectCompartmentId@@YAJPEAU_EJOB@@I@Z`
- size: `335`
- prototype: `int(struct _EJOB *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400c9690`

## callees

- `0x1400438a0`
- `0x140043940`
- `0x1400439a0`
- `0x140043eb0`
- `0x1400c9558`
- `0x1400ce3ac`
- `0x14014793c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140147a55`
- `ntoskrnl!ObfDereferenceObject` at `0x140147a69`
- `ntoskrnl!ObfDereferenceObject` at `0x140147a55`
- `ntoskrnl!ObfDereferenceObject` at `0x140147a69`
- `ntoskrnl!PsGetJobProperty` at `0x1401479bb`
- `ntoskrnl!PsGetJobProperty` at `0x1401479bb`
- `ntoskrnl!PsSetJobProperty` at `0x1401479d5`
- `ntoskrnl!PsSetJobProperty` at `0x1401479f3`
- `ntoskrnl!PsSetJobProperty` at `0x1401479d5`
- `ntoskrnl!PsSetJobProperty` at `0x1401479f3`

## pseudocode

```c

```
