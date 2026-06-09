# RegistryDetouring::InitializeRegRootHive(bool,ushort const *)

- ea: `0x14002ae80`
- end: `0x14002b0db`
- name: `?InitializeRegRootHive@RegistryDetouring@@YAJ_NPEBG@Z`
- size: `603`
- prototype: `__int64 __fastcall(RegistryDetouring *__hidden this, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140016668`

## callees

- `0x140001020`
- `0x1400013a0`
- `0x140003160`
- `0x140004950`
- `0x140015150`
- `0x1400152a4`
- `0x140021710`
- `0x1400249e0`
- `0x140029000`
- `0x14002ae80`
- `0x14002b0dc`
- `0x140031e3c`
- `0x140033ab0`
- `0x140061fe0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14002af4e`
- `KERNEL32!WaitForSingleObject` at `0x14002af8e`
- `KERNEL32!WaitForSingleObject` at `0x14002af4e`
- `KERNEL32!WaitForSingleObject` at `0x14002af8e`
- `KERNEL32!ReleaseMutex` at `0x14002af7e`
- `KERNEL32!ReleaseMutex` at `0x14002b069`
- `KERNEL32!ReleaseMutex` at `0x14002af7e`
- `KERNEL32!ReleaseMutex` at `0x14002b069`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14002aef3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14002aef3`

## pseudocode

```c

```
