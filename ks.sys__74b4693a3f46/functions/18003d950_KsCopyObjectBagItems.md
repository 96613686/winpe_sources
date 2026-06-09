# KsCopyObjectBagItems

- ea: `0x18003d950`
- end: `0x18003daac`
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
- `0x18003d950`
- `0x18004ee10`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18003da7d`
- `ntoskrnl!KeReleaseMutex` at `0x18003da8e`
- `ntoskrnl!KeReleaseMutex` at `0x18003da7d`
- `ntoskrnl!KeReleaseMutex` at `0x18003da8e`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003da09`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003da2a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003da09`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003da2a`

## pseudocode

```c

```
