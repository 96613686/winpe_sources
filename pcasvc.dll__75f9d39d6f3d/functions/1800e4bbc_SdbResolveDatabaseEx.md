# SdbResolveDatabaseEx

- ea: `0x1800e4bbc`
- end: `0x1800e4f1d`
- name: `SdbResolveDatabaseEx`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800e47a0`

## callees

- `0x180012920`
- `0x18001961c`
- `0x180019c84`
- `0x180033fa8`
- `0x1800347fc`
- `0x18003b5c0`
- `0x180080a84`
- `0x1800e4174`
- `0x1800e4aec`
- `0x1800e4bbc`

## import_xrefs

- `ntdll!ZwClose` at `0x1800e4ed2`
- `ntdll!ZwClose` at `0x1800e4ed2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800e4d7e`
- `ntdll!RtlAppendUnicodeToString` at `0x1800e4d8f`
- `ntdll!RtlAppendUnicodeToString` at `0x1800e4d7e`
- `ntdll!RtlAppendUnicodeToString` at `0x1800e4d8f`
- `ntdll!RtlAllocateHeap` at `0x1800e4d2b`
- `ntdll!RtlAllocateHeap` at `0x1800e4d2b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800e4d9d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800e4d9d`

## string_xrefs

- `0x1800e4d67`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x1800e4dbe`: `Failed to open Key "%ws" [%x]`
- `0x1800e4e9d`: `SdbGetPathCustomSdb failed to get the database path.`
- `0x1800e4c82`: `SdbGetPathSystemSdb failed.`
- `0x1800e4d39`: `Failed to allocate %ld bytes for key path`

## pseudocode

```c

```
