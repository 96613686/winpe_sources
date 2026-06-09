# ConfigIoHandler_Safeguarded

- ea: `0x180023620`
- end: `0x1800242aa`
- name: `ConfigIoHandler_Safeguarded`
- size: `3210`
- prototype: `__int64 __fastcall(void *Src, unsigned int, struct _CRYPT_PROVIDER_REFS *, ULONG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180023280`

## callees

- `0x180022788`
- `0x180022e3c`
- `0x180023620`
- `0x1800244f0`
- `0x180024618`
- `0x180025aa0`
- `0x180025c00`
- `0x18009f780`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18002369d`
- `ntoskrnl!ExAllocatePool2` at `0x1800236d4`
- `ntoskrnl!ExAllocatePool2` at `0x18002369d`
- `ntoskrnl!ExAllocatePool2` at `0x1800236d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180023d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x180023dce`
- `ntoskrnl!ExFreePoolWithTag` at `0x180023d91`
- `ntoskrnl!ExFreePoolWithTag` at `0x180023dce`
- `ntoskrnl!SkIsSecureKernel` at `0x180023df3`
- `ntoskrnl!SkIsSecureKernel` at `0x180023e0d`
- `ntoskrnl!SkIsSecureKernel` at `0x18002408d`
- `ntoskrnl!SkIsSecureKernel` at `0x1800240aa`
- `ntoskrnl!SkIsSecureKernel` at `0x180023df3`
- `ntoskrnl!SkIsSecureKernel` at `0x180023e0d`
- `ntoskrnl!SkIsSecureKernel` at `0x18002408d`
- `ntoskrnl!SkIsSecureKernel` at `0x1800240aa`
- `ntoskrnl!SkAllocatePool` at `0x1800240cc`
- `ntoskrnl!SkAllocatePool` at `0x1800240e2`
- `ntoskrnl!SkAllocatePool` at `0x1800240cc`
- `ntoskrnl!SkAllocatePool` at `0x1800240e2`
- `ntoskrnl!SkFreePool` at `0x180023edc`
- `ntoskrnl!SkFreePool` at `0x180023ef5`
- `ntoskrnl!SkFreePool` at `0x180023edc`
- `ntoskrnl!SkFreePool` at `0x180023ef5`

## pseudocode

```c

```
