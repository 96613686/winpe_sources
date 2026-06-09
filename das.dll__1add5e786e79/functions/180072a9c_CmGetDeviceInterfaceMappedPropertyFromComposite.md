# _CmGetDeviceInterfaceMappedPropertyFromComposite

- ea: `0x180072a9c`
- end: `0x180072e27`
- name: `_CmGetDeviceInterfaceMappedPropertyFromComposite`
- size: `907`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, GUID *Guid, int, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180072954`
- `0x1800731cc`

## callees

- `0x180017210`
- `0x18001e010`
- `0x18003bc80`
- `0x18006b4a0`
- `0x18006b4ec`
- `0x180072a9c`

## import_xrefs

- `ntdll!RtlGUIDFromString` at `0x180072c24`
- `ntdll!RtlGUIDFromString` at `0x180072c24`
- `ntdll!RtlFreeHeap` at `0x180072de5`
- `ntdll!RtlFreeHeap` at `0x180072de5`
- `ntdll!RtlAllocateHeap` at `0x180072d06`
- `ntdll!RtlAllocateHeap` at `0x180072d06`
- `ntdll!RtlInitUnicodeStringEx` at `0x180072c0d`
- `ntdll!RtlInitUnicodeStringEx` at `0x180072c0d`

## pseudocode

```c

```
