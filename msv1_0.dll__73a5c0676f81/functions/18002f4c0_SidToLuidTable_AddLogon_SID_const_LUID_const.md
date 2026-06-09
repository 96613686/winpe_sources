# SidToLuidTable::AddLogon(_SID const *,_LUID const *)

- ea: `0x18002f4c0`
- end: `0x18002f607`
- name: `?AddLogon@SidToLuidTable@@QEAAJPEBU_SID@@PEBU_LUID@@@Z`
- size: `327`
- prototype: `int(SidToLuidTable *__hidden this, const struct _SID *, const struct _LUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800427d0`

## callees

- `0x18002f4c0`
- `0x18002f610`
- `0x18002ffec`
- `0x180056218`
- `0x18006bd74`

## import_xrefs

- `ntdll!RtlAvlInsertNodeEx` at `0x18002f593`
- `ntdll!RtlAvlInsertNodeEx` at `0x18002f593`

## pseudocode

```c

```
