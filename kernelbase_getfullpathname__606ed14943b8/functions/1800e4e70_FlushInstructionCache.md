# FlushInstructionCache

- ea: `0x1800e4e70`
- end: `0x1800e4efb`
- name: `FlushInstructionCache`
- size: `139`
- prototype: `BOOL __stdcall(HANDLE hProcess, LPCVOID lpBaseAddress, SIZE_T dwSize)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800e4e70`

## import_xrefs

- `ntdll!NtClose` at `0x1801a0f45`
- `ntdll!NtClose` at `0x1801a0f45`
- `ntdll!NtUnmapViewOfSection` at `0x1801a0f34`
- `ntdll!NtUnmapViewOfSection` at `0x1801a0f34`
- `ntdll!RtlOpenCrossProcessEmulatorWorkConnection` at `0x1800e4e9c`
- `ntdll!RtlOpenCrossProcessEmulatorWorkConnection` at `0x1800e4e9c`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e4ed0`
- `ntdll!RtlWow64PopCrossProcessWorkFromFreeList` at `0x1800e4ed0`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e4ee9`
- `ntdll!RtlWow64RequestCrossProcessHeavyFlush` at `0x1800e4ee9`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a0f03`
- `ntdll!RtlWow64PushCrossProcessWorkOntoWorkList` at `0x1801a0f03`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a0f1c`
- `ntdll!RtlWow64PushCrossProcessWorkOntoFreeList` at `0x1801a0f1c`

## pseudocode

```c

```
