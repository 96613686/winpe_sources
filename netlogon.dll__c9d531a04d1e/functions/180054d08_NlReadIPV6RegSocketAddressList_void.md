# NlReadIPV6RegSocketAddressList(void)

- ea: `0x180054d08`
- end: `0x180054f57`
- name: `?NlReadIPV6RegSocketAddressList@@YAXXZ`
- size: `591`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180055c9c`

## callees

- `0x180007278`
- `0x18000d710`
- `0x180023eb0`
- `0x180054d08`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054d8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180054d8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054f40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054d75`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054dbe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054d75`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180054dbe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054f49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054f49`
- `ntdll!RtlLeaveCriticalSection` at `0x180054f1f`
- `ntdll!RtlLeaveCriticalSection` at `0x180054f1f`
- `ntdll!RtlEnterCriticalSection` at `0x180054ed5`
- `ntdll!RtlEnterCriticalSection` at `0x180054ed5`

## string_xrefs

- `0x180054d13`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x180054d35`: `Cannot NlOpenNetlogonKey to get socket address list.\n`
- `0x180054eeb`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`

## pseudocode

```c

```
