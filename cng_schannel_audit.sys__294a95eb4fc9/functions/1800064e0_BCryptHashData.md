# BCryptHashData

- ea: `0x1800064e0`
- end: `0x1800065a8`
- name: `BCryptHashData`
- size: `200`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x180001ab0`
- `0x180049084`
- `0x180058070`
- `0x180067ec4`
- `0x180068500`
- `0x1800687b8`
- `0x180068d98`
- `0x180082888`
- `0x180082a40`
- `0x180083724`
- `0x180083a3c`

## callees

- `0x1800064e0`
- `0x18000743c`
- `0x180047f1c`
- `0x18009d860`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000652c`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000652c`

## string_xrefs

- `0x180006566`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c

```
