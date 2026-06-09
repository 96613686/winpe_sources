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
- `0x180049b14`
- `0x180058960`
- `0x1800688c4`
- `0x180068f00`
- `0x1800691b8`
- `0x180069798`
- `0x180083878`
- `0x180083a30`
- `0x180084714`
- `0x180084a2c`

## callees

- `0x1800064e0`
- `0x18000743c`
- `0x1800489ac`
- `0x18009f6d0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18000652c`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000652c`

## string_xrefs

- `0x180006566`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c

```
