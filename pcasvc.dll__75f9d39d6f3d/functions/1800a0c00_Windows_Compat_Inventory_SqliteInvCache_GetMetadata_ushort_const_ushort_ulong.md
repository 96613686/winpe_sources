# Windows::Compat::Inventory::SqliteInvCache::GetMetadata(ushort const *,ushort *,ulong &)

- ea: `0x1800a0c00`
- end: `0x1800a0e63`
- name: `?GetMetadata@SqliteInvCache@Inventory@Compat@Windows@@UEBAJPEBGPEAGAEAK@Z`
- size: `611`
- prototype: `int(Windows::Compat::Inventory::SqliteInvCache *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000c018`
- `0x180012920`
- `0x1800182e0`
- `0x18009c764`
- `0x18009c798`
- `0x18009d058`
- `0x1800a0c00`
- `0x1800a6e3c`
- `0x1800f1f10`

## import_xrefs

- `winsqlite3!sqlite3_errmsg` at `0x1800a0cb5`
- `winsqlite3!sqlite3_errmsg` at `0x1800a0d4d`
- `winsqlite3!sqlite3_errmsg` at `0x1800a0d99`
- `winsqlite3!sqlite3_errmsg` at `0x1800a0cb5`
- `winsqlite3!sqlite3_errmsg` at `0x1800a0d4d`
- `winsqlite3!sqlite3_errmsg` at `0x1800a0d99`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1800a0c94`
- `winsqlite3!sqlite3_prepare16_v2` at `0x1800a0c94`
- `winsqlite3!sqlite3_bind_text16` at `0x1800a0d2c`
- `winsqlite3!sqlite3_bind_text16` at `0x1800a0d2c`
- `winsqlite3!sqlite3_column_text16` at `0x1800a0db7`
- `winsqlite3!sqlite3_column_text16` at `0x1800a0db7`

## string_xrefs

- `0x1800a0e07`: `StringCchCopyW failed [%#x]`
- `0x1800a0cd1`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`
- `0x1800a0d06`: `Windows::Compat::Inventory::SqliteInvCache::GetMetadata`

## pseudocode

```c

```
