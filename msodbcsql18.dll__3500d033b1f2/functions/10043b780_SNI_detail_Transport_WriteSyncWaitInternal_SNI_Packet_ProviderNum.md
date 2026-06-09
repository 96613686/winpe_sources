# SNI::detail::Transport::WriteSyncWaitInternal(SNI_Packet *,ProviderNum)

- ea: `0x10043b780`
- end: `0x10043ba28`
- name: `?WriteSyncWaitInternal@Transport@detail@SNI@@IEAAKPEAVSNI_Packet@@W4ProviderNum@@@Z`
- size: `680`
- prototype: `unsigned int __high(struct SNI_Packet *, enum ProviderNum)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1004245e0`
- `0x10044ade0`

## callees

- `0x10043a7c4`
- `0x10043a930`
- `0x10043b780`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546b88`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x10043b8b4`
- `KERNEL32!GetOverlappedResult` at `0x10043b8b4`
- `KERNEL32!WaitForSingleObject` at `0x10043b7e8`
- `KERNEL32!WaitForSingleObject` at `0x10043b7e8`
- `KERNEL32!GetLastError` at `0x10043b807`
- `KERNEL32!GetLastError` at `0x10043b8c2`
- `KERNEL32!GetLastError` at `0x10043b807`
- `KERNEL32!GetLastError` at `0x10043b8c2`

## pseudocode

```c

```
