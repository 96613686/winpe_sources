# LOCATION_TABLE::FindTable(ushort const *,CONFIG_ELEMENT_TABLE * *,ulong *)

- ea: `0x1800156d0`
- end: `0x1800158b1`
- name: `?FindTable@LOCATION_TABLE@@QEAAJPEBGPEAPEAVCONFIG_ELEMENT_TABLE@@PEAK@Z`
- size: `481`
- prototype: `int(LOCATION_TABLE *__hidden this, const unsigned __int16 *, struct CONFIG_ELEMENT_TABLE **, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180024130`
- `0x180026250`
- `0x180026938`
- `0x180045458`
- `0x180054d3c`

## callees

- `0x1800156d0`
- `0x18005b010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001586b`
- `msvcrt!_wcsicmp` at `0x18001586b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800157f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800157f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015805`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015805`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800157a4`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800157a4`

## pseudocode

```c

```
