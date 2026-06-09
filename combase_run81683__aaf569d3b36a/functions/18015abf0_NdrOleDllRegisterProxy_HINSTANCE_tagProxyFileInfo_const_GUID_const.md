# NdrOleDllRegisterProxy(HINSTANCE__ *,tagProxyFileInfo const * *,_GUID const *)

- ea: `0x18015abf0`
- end: `0x18015b0c0`
- name: `?NdrOleDllRegisterProxy@@YAJPEAUHINSTANCE__@@PEAPEBUtagProxyFileInfo@@PEBU_GUID@@@Z`
- size: `1232`
- prototype: `__int64 __fastcall(HMODULE hDll, const tagProxyFileInfo **pProxyFileList, const _GUID *pclsid)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180101e4c`
- `0x18015abf0`
- `0x18015b0c8`
- `0x1801999b0`
- `0x1801f64c4`
- `0x1801f6548`
- `0x180255010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18015ad95`
- `ntdll!DbgPrint` at `0x18015ada2`
- `ntdll!DbgPrint` at `0x18015add1`
- `ntdll!DbgPrint` at `0x18015adde`
- `ntdll!DbgPrint` at `0x18015ae03`
- `ntdll!DbgPrint` at `0x18015af90`
- `ntdll!DbgPrint` at `0x18015af9d`
- `ntdll!DbgPrint` at `0x18015afcc`
- `ntdll!DbgPrint` at `0x18015afd9`
- `ntdll!DbgPrint` at `0x18015affe`
- `ntdll!DbgPrint` at `0x18015ad95`
- `ntdll!DbgPrint` at `0x18015ada2`
- `ntdll!DbgPrint` at `0x18015add1`
- `ntdll!DbgPrint` at `0x18015adde`
- `ntdll!DbgPrint` at `0x18015ae03`
- `ntdll!DbgPrint` at `0x18015af90`
- `ntdll!DbgPrint` at `0x18015af9d`
- `ntdll!DbgPrint` at `0x18015afcc`
- `ntdll!DbgPrint` at `0x18015afd9`
- `ntdll!DbgPrint` at `0x18015affe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ac66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015ac66`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18015ac48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18015ac48`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015acf0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015acf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b079`

## string_xrefs

- `0x18015ad87`: `Possible security threat: Server registers an interface compiled without /robust option`
- `0x18015af82`: `Possible security threat: Server registers an interface compiled without /robust option`
- `0x18015adfc`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`
- `0x18015aff7`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`

## pseudocode

```c

```
