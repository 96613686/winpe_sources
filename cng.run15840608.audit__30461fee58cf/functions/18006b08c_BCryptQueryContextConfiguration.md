# BCryptQueryContextConfiguration

- ea: `0x18006b08c`
- end: `0x18006b1dc`
- name: `BCryptQueryContextConfiguration`
- size: `336`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG *pcbBuffer, PCRYPT_CONTEXT_CONFIG *ppBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x18001be80`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800289e0`
- `0x180029710`
- `0x18006b08c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18006b1a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x18006b1a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b1ae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18006b1ae`

## pseudocode

```c

```
