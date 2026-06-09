# SdbResolveDatabaseEx

- ea: `0x18007597c`
- end: `0x180075cdd`
- name: `SdbResolveDatabaseEx`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180075148`

## callees

- `0x18001d348`
- `0x180021144`
- `0x1800212e4`
- `0x1800250d0`
- `0x18003acd8`
- `0x180070e54`
- `0x180071034`
- `0x180074fa0`
- `0x1800758ac`
- `0x18007597c`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180075b3e`
- `ntdll!RtlAppendUnicodeToString` at `0x180075b4f`
- `ntdll!RtlAppendUnicodeToString` at `0x180075b3e`
- `ntdll!RtlAppendUnicodeToString` at `0x180075b4f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180075b5d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180075b5d`
- `ntdll!ZwClose` at `0x180075c92`
- `ntdll!ZwClose` at `0x180075c92`
- `ntdll!RtlAllocateHeap` at `0x180075aeb`
- `ntdll!RtlAllocateHeap` at `0x180075aeb`

## string_xrefs

- `0x180075a42`: `SdbGetPathSystemSdb failed.`
- `0x180075b7e`: `Failed to open Key "%ws" [%x]`
- `0x180075af9`: `Failed to allocate %ld bytes for key path`
- `0x180075b27`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\InstalledSDB`
- `0x180075c5d`: `SdbGetPathCustomSdb failed to get the database path.`

## pseudocode

```c

```
