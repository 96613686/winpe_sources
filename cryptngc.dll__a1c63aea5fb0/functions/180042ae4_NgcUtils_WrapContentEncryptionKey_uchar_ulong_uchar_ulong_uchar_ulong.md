# NgcUtils::WrapContentEncryptionKey(uchar *,ulong,uchar *,ulong,uchar *,ulong)

- ea: `0x180042ae4`
- end: `0x180042bbc`
- name: `?WrapContentEncryptionKey@NgcUtils@@YAJPEAEK0K0K@Z`
- size: `216`
- prototype: `int(NgcUtils *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003c2ec`
- `0x18003c7d8`

## callees

- `0x180028380`
- `0x18002d08c`
- `0x180042ae4`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x180042b25`
- `bcrypt!BCryptImportKeyPair` at `0x180042b25`
- `bcrypt!BCryptEncrypt` at `0x180042b7c`
- `bcrypt!BCryptEncrypt` at `0x180042b7c`

## string_xrefs

- `0x180042b90`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c

```
