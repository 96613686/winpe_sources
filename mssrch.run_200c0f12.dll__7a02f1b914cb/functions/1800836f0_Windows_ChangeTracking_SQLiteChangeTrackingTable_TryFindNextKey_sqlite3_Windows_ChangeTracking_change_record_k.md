# Windows::ChangeTracking::SQLiteChangeTrackingTable::TryFindNextKey(sqlite3 *,Windows::ChangeTracking::change_record_key,Windows::ChangeTracking::change_record_key)

- ea: `0x1800836f0`
- end: `0x180083a3b`
- name: `?TryFindNextKey@SQLiteChangeTrackingTable@ChangeTracking@Windows@@CA?AV?$optional@Uchange_record_key@ChangeTracking@Windows@@@std@@PEAUsqlite3@@Uchange_record_key@23@1@Z`
- size: `843`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180088760`

## callees

- `0x18001be0c`
- `0x180082cf0`
- `0x180082d58`
- `0x1800836f0`
- `0x180083e24`
- `0x180083e78`
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

- `SearchIndexerCore!sqlite3_column_int64` at `0x1800838de`
- `SearchIndexerCore!sqlite3_column_int64` at `0x1800838f1`
- `SearchIndexerCore!sqlite3_column_int64` at `0x1800838de`
- `SearchIndexerCore!sqlite3_column_int64` at `0x1800838f1`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x1800837a4`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x1800837ca`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180083805`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x18008383b`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180083862`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x18008389d`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x1800837a4`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x1800837ca`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180083805`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x18008383b`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x180083862`
- `SearchIndexerCore!sqlite3_bind_parameter_index` at `0x18008389d`

## string_xrefs

- `0x180083752`: `SELECT Client, Batch, Path FROM ChangeTracking WHERE (Client, Batch, Path) > (:BeforeFirstClient, :BeforeFirstBatch, :BeforeFirstPath) AND (Client, Batch, Path) < (:AfterLastClient, :AfterLastBatch, :AfterLastPath) ORDER BY Client, Batch, Path LIMIT 1;`
- `0x1800837fb`: `:BeforeFirstPath`
- `0x180083893`: `:AfterLastPath`

## pseudocode

```c

```
