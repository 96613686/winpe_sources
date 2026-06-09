# GetProcessingInterval(int,HKEY__ *,int,ulong &)

- ea: `0x180089de0`
- end: `0x180089ffa`
- name: `?GetProcessingInterval@@YAJHPEAUHKEY__@@HAEAK@Z`
- size: `538`
- prototype: `int(int, HKEY, int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180012540`
- `0x18002f880`

## callees

- `0x180075ec0`
- `0x180089de0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089f0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089e60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089e60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180089ea1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180089ed4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180089f02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180089ea1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180089ed4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180089f02`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180089f4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180089f4e`

## string_xrefs

- `0x180089f9b`: `GPOThread(%s): dwOffset=%d., dwTimeout=%d.`
- `0x180089fd9`: `GPOThread(%s): dwOffset=%d., dwTimeout=%d.`

## pseudocode

```c

```
