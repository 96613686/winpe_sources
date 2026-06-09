# NlReadIPV6RegSocketAddressList(void)

- ea: `0x180058824`
- end: `0x180058a9e`
- name: `?NlReadIPV6RegSocketAddressList@@YAXXZ`
- size: `634`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800599a4`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x180024f38`
- `0x180058824`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800588af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800588af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058a7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058a7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058891`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800588e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058891`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800588e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058a89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058a89`
- `ntdll!RtlLeaveCriticalSection` at `0x180058a53`
- `ntdll!RtlLeaveCriticalSection` at `0x180058a53`
- `ntdll!RtlEnterCriticalSection` at `0x180058a03`
- `ntdll!RtlEnterCriticalSection` at `0x180058a03`

## string_xrefs

- `0x18005882f`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x180058851`: `Cannot NlOpenNetlogonKey to get socket address list.\n`
- `0x180058a1f`: `onecore\ds\netapi\svcdlls\logonsrv\server\srvsess.cxx`

## pseudocode

```c

```
