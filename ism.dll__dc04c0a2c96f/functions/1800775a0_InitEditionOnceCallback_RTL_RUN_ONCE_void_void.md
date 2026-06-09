# InitEditionOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800775a0`
- end: `0x1800776ac`
- name: `?InitEditionOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `268`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800775a0`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800775b5`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800775b5`
- `ntdll!RtlIsMultiSessionSku` at `0x1800775bb`
- `ntdll!RtlIsMultiSessionSku` at `0x1800775bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800775f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800775f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077636`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077667`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077636`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180077667`

## pseudocode

```c

```
