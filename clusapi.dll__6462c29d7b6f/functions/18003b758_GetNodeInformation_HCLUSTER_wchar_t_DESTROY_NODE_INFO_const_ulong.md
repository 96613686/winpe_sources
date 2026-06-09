# GetNodeInformation(_HCLUSTER *,wchar_t *,_DESTROY_NODE_INFO * * const,ulong *)

- ea: `0x18003b758`
- end: `0x18003baef`
- name: `?GetNodeInformation@@YAXPEAU_HCLUSTER@@PEA_WQEAPEAU_DESTROY_NODE_INFO@@PEAK@Z`
- size: `919`
- prototype: `void __fastcall(HCLUSTER hCluster, wchar_t *, struct _DESTROY_NODE_INFO **const, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1800441a0`

## callees

- `0x180002f50`
- `0x180003510`
- `0x180003c14`
- `0x180003c44`
- `0x18001236c`
- `0x18001feac`
- `0x18002acc0`
- `0x18002adc0`
- `0x18002c220`
- `0x18003180c`
- `0x18003b758`
- `0x180057c9c`
- `0x180057f5c`
- `0x180058ad0`
- `0x180059580`
- `0x18006f910`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003b98d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003b98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b7fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b948`

## string_xrefs

- `0x18003b950`: `Failed to open cluster node`
- `0x18003ba63`: `Failed to copy hosting node name`

## pseudocode

```c

```
