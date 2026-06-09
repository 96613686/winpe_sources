# ComputeService::Resources::DuplicateHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void *,ushort const *)

- ea: `0x180012d8c`
- end: `0x180012e2b`
- name: `??$DuplicateHandle@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Resources@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAXPEBG@Z`
- size: `159`
- prototype: `__int64 __fastcall(LPHANDLE lpTargetHandle, HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800126a8`

## callees

- `0x180015638`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012dba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012dc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012dba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012dc3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180012ded`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180012ded`

## string_xrefs

- `0x180012e0c`: `onecore\vm\compute\shared\computesystem\ServerResources.h`

## pseudocode

```c

```
