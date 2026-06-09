# ValidateQueuedOps(PROGRESS_CONTEXT *)

- ea: `0x1801f53c4`
- end: `0x1801f561f`
- name: `?ValidateQueuedOps@@YAJPEAUPROGRESS_CONTEXT@@@Z`
- size: `603`
- prototype: `__int64 __fastcall(struct PROGRESS_CONTEXT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1801f5628`

## callees

- `0x180070398`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1801f309c`
- `0x1801f3d54`
- `0x1801f3e2c`
- `0x1801f461c`
- `0x1801f53c4`

## import_xrefs

- `ntdll!NtClose` at `0x1801f554a`
- `ntdll!NtClose` at `0x1801f5588`
- `ntdll!NtClose` at `0x1801f55e8`
- `ntdll!NtClose` at `0x1801f554a`
- `ntdll!NtClose` at `0x1801f5588`
- `ntdll!NtClose` at `0x1801f55e8`
- `ntdll!NtSetCachedSigningLevel` at `0x1801f5507`
- `ntdll!NtSetCachedSigningLevel` at `0x1801f5507`
- `ntdll!NtCreateFile` at `0x1801f54d4`
- `ntdll!NtCreateFile` at `0x1801f54d4`

## string_xrefs

- `0x1801f5568`: `Failed to open file (status=0x%x):  %wZ\n`

## pseudocode

```c

```
