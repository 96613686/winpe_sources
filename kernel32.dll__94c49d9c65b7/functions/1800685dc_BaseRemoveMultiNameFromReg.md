# BaseRemoveMultiNameFromReg

- ea: `0x1800685dc`
- end: `0x18006870e`
- name: `BaseRemoveMultiNameFromReg`
- size: `306`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, void *Buf2)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180068c30`

## callees

- `0x1800378d4`
- `0x18006828c`
- `0x1800685dc`
- `0x180068714`
- `0x180068870`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18006867f`
- `ntdll!RtlNtStatusToDosError` at `0x18006867f`
- `ntdll!RtlFreeHeap` at `0x1800686f3`
- `ntdll!RtlFreeHeap` at `0x1800686f3`
- `ntdll!RtlAllocateHeap` at `0x180068649`
- `ntdll!RtlAllocateHeap` at `0x180068649`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006862c`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18006862c`

## pseudocode

```c

```
