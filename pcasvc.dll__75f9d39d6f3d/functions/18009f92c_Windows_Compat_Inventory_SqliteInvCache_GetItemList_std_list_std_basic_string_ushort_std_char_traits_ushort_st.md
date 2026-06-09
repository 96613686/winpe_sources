# Windows::Compat::Inventory::SqliteInvCache::GetItemList(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,unsigned __int64)

- ea: `0x18009f92c`
- end: `0x18009fba2`
- name: `?GetItemList@SqliteInvCache@Inventory@Compat@Windows@@QEBAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_K@Z`
- size: `630`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18009f690`
- `0x1800a2650`

## callees

- `0x180012920`
- `0x1800182e0`
- `0x180018470`
- `0x180018768`
- `0x18009c764`
- `0x18009ca08`
- `0x18009d058`
- `0x18009f92c`
- `0x1800a1110`
- `0x1800a6e3c`
- `0x1800f1f10`

## import_xrefs

- `winsqlite3!sqlite3_bind_int64` at `0x18009fa9c`
- `winsqlite3!sqlite3_bind_int64` at `0x18009fa9c`
- `winsqlite3!sqlite3_errmsg` at `0x18009fa58`
- `winsqlite3!sqlite3_errmsg` at `0x18009fabd`
- `winsqlite3!sqlite3_errmsg` at `0x18009fb25`
- `winsqlite3!sqlite3_errmsg` at `0x18009fa58`
- `winsqlite3!sqlite3_errmsg` at `0x18009fabd`
- `winsqlite3!sqlite3_errmsg` at `0x18009fb25`
- `winsqlite3!sqlite3_prepare16_v2` at `0x18009fa37`
- `winsqlite3!sqlite3_prepare16_v2` at `0x18009fa37`
- `winsqlite3!sqlite3_column_text16` at `0x18009fadd`
- `winsqlite3!sqlite3_column_text16` at `0x18009fadd`

## string_xrefs

- `0x18009fa74`: `Windows::Compat::Inventory::SqliteInvCache::GetItemList`
- `0x18009fb53`: `Windows::Compat::Inventory::SqliteInvCache::GetItemList`

## pseudocode

```c

```
