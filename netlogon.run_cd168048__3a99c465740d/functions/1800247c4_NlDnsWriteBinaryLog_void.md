# NlDnsWriteBinaryLog(void)

- ea: `0x1800247c4`
- end: `0x180024b8a`
- name: `?NlDnsWriteBinaryLog@@YAXXZ`
- size: `966`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180024b90`

## callees

- `0x18000dd00`
- `0x18000f3e4`
- `0x180016a70`
- `0x180016aa4`
- `0x1800247c4`
- `0x180025114`
- `0x180041f80`
- `0x18008b2c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180024a27`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180024a4b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180024a27`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180024a4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024888`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024888`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b6c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800248a3`
- `ntdll!RtlLeaveCriticalSection` at `0x180024b1c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800248a3`
- `ntdll!RtlLeaveCriticalSection` at `0x180024b1c`
- `ntdll!RtlEnterCriticalSection` at `0x180024801`
- `ntdll!RtlEnterCriticalSection` at `0x180024801`

## string_xrefs

- `0x180024a8a`: `onecore\ds\netapi\svcdlls\logonsrv\server\dns.cxx`
- `0x180024aad`: `onecore\ds\netapi\svcdlls\logonsrv\server\dns.cxx`
- `0x180024ad7`: `NlDnsWriteBinaryLog: not written to binary log file.`
- `0x180024afd`: `\system32\config\netlogon.dnb`

## pseudocode

```c

```
