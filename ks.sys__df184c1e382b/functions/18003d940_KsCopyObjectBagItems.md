# KsCopyObjectBagItems

- ea: `0x18003d940`
- end: `0x18003da9c`
- name: `KsCopyObjectBagItems`
- size: `348`
- prototype: `NTSTATUS __stdcall(KSOBJECT_BAG ObjectBagDestination, KSOBJECT_BAG ObjectBagSource)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18006f630`

## callees

- `0x18000b7bc`
- `0x18000da50`
- `0x18003d940`
- `0x18004efb0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003da6d`
- `ntoskrnl!KeReleaseMutex` at `0x18003da7e`
- `ntoskrnl!KeReleaseMutex` at `0x18003da6d`
- `ntoskrnl!KeReleaseMutex` at `0x18003da7e`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003d9f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003da1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003d9f9`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003da1a`

## pseudocode

```c

```
