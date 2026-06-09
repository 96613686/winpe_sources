# BCryptQueryContextConfiguration

- ea: `0x18007522c`
- end: `0x18007537c`
- name: `BCryptQueryContextConfiguration`
- size: `336`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG *pcbBuffer, PCRYPT_CONTEXT_CONFIG *ppBuffer)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002f7f8`

## callees

- `0x180025b70`
- `0x180025fb0`
- `0x18002ee00`
- `0x18002effc`
- `0x180032b10`
- `0x180033840`
- `0x18007522c`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180075342`
- `ntoskrnl!ExReleaseResourceLite` at `0x180075342`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007534e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007534e`

## pseudocode

```c

```
