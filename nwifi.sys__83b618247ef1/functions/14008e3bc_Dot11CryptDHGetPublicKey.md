# Dot11CryptDHGetPublicKey

- ea: `0x14008e3bc`
- end: `0x14008e4ca`
- name: `Dot11CryptDHGetPublicKey`
- size: `270`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140039778`

## callees

- `0x14000599c`
- `0x14008e3bc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008e497`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14008e497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e4a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008e4a8`
- `ksecdd!BCryptExportKey` at `0x14008e410`
- `ksecdd!BCryptExportKey` at `0x14008e467`
- `ksecdd!BCryptExportKey` at `0x14008e410`
- `ksecdd!BCryptExportKey` at `0x14008e467`

## pseudocode

```c

```
