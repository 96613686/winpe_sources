# BCryptHashData

- ea: `0x180010600`
- end: `0x1800106c8`
- name: `BCryptHashData`
- size: `200`
- prototype: `NTSTATUS __stdcall(BCRYPT_HASH_HANDLE hHash, PUCHAR pbInput, ULONG cbInput, ULONG dwFlags)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b9b0`
- `0x18000bbd0`
- `0x180053184`
- `0x180062240`
- `0x180072064`
- `0x1800726a0`
- `0x180072958`
- `0x180072f38`
- `0x18008ca78`
- `0x18008cc30`
- `0x18008d914`
- `0x18008dc2c`

## callees

- `0x180010600`
- `0x18001155c`
- `0x18005200c`
- `0x1800a4300`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18001064c`
- `ntoskrnl!KeGetCurrentIrql` at `0x18001064c`

## string_xrefs

- `0x180010686`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c

```
