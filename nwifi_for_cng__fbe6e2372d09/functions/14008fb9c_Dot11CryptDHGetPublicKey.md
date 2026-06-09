# Dot11CryptDHGetPublicKey

- ea: `0x14008fb9c`
- end: `0x14008fcaa`
- name: `Dot11CryptDHGetPublicKey`
- size: `270`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140039998`

## callees

- `0x14000599c`
- `0x14008fb9c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008fc77`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008fc77`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fc88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fc88`
- `ksecdd!BCryptExportKey` at `0x14008fbf0`
- `ksecdd!BCryptExportKey` at `0x14008fc47`
- `ksecdd!BCryptExportKey` at `0x14008fbf0`
- `ksecdd!BCryptExportKey` at `0x14008fc47`

## pseudocode

```c

```
