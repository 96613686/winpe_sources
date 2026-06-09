# Windows::ChangeTracking::SQLiteChangeTrackingTable::TryFind(sqlite3 *,Windows::ChangeTracking::change_record_key)

- ea: `0x180083f64`
- end: `0x180084206`
- name: `?TryFind@SQLiteChangeTrackingTable@ChangeTracking@Windows@@CA?AV?$optional@Uchange_record_key@ChangeTracking@Windows@@@std@@PEAUsqlite3@@Uchange_record_key@23@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180087a40`

## callees

- `0x18001be0c`
- `0x180082cf0`
- `0x180082d58`
- `0x180083e54`
- `0x180083e78`
- `0x180083f64`
- `0x1800846e8`
- `0x180085cc4`
- `0x180085d58`
- `0x180085ea0`
- `0x1800865e8`
- `0x180086654`
- `0x180087364`
- `0x1800decbc`
- `0x1800fdb00`
- `0x1801244c0`
- `0x18012541a`

## import_xrefs

- `SearchIndexerCore!sqlite3_column_int64` at `0x1800840c4`
- `SearchIndexerCore!sqlite3_column_int64` at `0x1800840d7`
- `SearchIndexerCore!sqlite3_column_int64` at `0x1800840c4`
- `SearchIndexerCore!sqlite3_column_int64` at `0x1800840d7`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x18008400f`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180084035`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180084083`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x18008400f`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180084035`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180084083`

## string_xrefs

- `0x180083fbd`: `SELECT Client, Batch, Path FROM ChangeTracking WHERE Client = :Client AND Batch = :Batch AND Path = :Path;`
- `0x180084079`: `:Path`

## pseudocode

```c

```
