# IcmDeleteLocalDC

- ea: `0x1800383a0`
- end: `0x1800384e0`
- name: `IcmDeleteLocalDC`
- size: `320`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180031940`
- `0x1800764f0`
- `0x180078938`

## callees

- `0x1800383a0`
- `0x1800384e8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800384c8`
- `ntdll!RtlFreeHeap` at `0x1800384c8`
- `ntdll!RtlEnterCriticalSection` at `0x180038462`
- `ntdll!RtlEnterCriticalSection` at `0x180038462`
- `ntdll!RtlLeaveCriticalSection` at `0x1800384aa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800384aa`
- `win32u!NtGdiSetIcmMode` at `0x1800383df`
- `win32u!NtGdiSetIcmMode` at `0x18003840b`
- `win32u!NtGdiSetIcmMode` at `0x18003844d`
- `win32u!NtGdiSetIcmMode` at `0x1800383df`
- `win32u!NtGdiSetIcmMode` at `0x18003840b`
- `win32u!NtGdiSetIcmMode` at `0x18003844d`

## pseudocode

```c

```
