# ClusterKeyValueStoreUpdateKeyImpl(_HKEYVALUESTORE *,wchar_t const *,wchar_t const *,void *,ulong,ulong,ulong)

- ea: `0x18008a644`
- end: `0x18008ab9b`
- name: `?ClusterKeyValueStoreUpdateKeyImpl@@YAKPEAU_HKEYVALUESTORE@@PEB_W1PEAXKKK@Z`
- size: `1367`
- prototype: `unsigned int __usercall@<eax>(struct _HKEYVALUESTORE *@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, void *@<r9>, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x18008c8c0`

## callees

- `0x180002f50`
- `0x18001cc2c`
- `0x180029410`
- `0x180029578`
- `0x180052d30`
- `0x1800888e8`
- `0x180088934`
- `0x180088b10`
- `0x18008a644`
- `0x18008af20`
- `0x180094ab4`
- `0x180094ce8`
- `0x180095144`
- `0x180096894`
- `0x180096b88`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18008a759`
- `RPCRT4!NdrClientCall3` at `0x18008a759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008a68d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008a68d`

## string_xrefs

- `0x18008a7d2`: `KeyValueStoreName`

## pseudocode

```c

```
