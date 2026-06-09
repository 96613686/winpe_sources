# NlDnsWriteBinaryLog(void)

- ea: `0x1800237b4`
- end: `0x180023b4f`
- name: `?NlDnsWriteBinaryLog@@YAXXZ`
- size: `923`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180023b58`

## callees

- `0x18000d710`
- `0x18000ed34`
- `0x18001606c`
- `0x1800160a0`
- `0x1800237b4`
- `0x180024074`
- `0x18003f648`
- `0x1800850b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180023a05`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180023a23`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180023a05`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180023a23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023872`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023b38`
- `ntdll!RtlLeaveCriticalSection` at `0x180023887`
- `ntdll!RtlLeaveCriticalSection` at `0x180023aee`
- `ntdll!RtlLeaveCriticalSection` at `0x180023887`
- `ntdll!RtlLeaveCriticalSection` at `0x180023aee`
- `ntdll!RtlEnterCriticalSection` at `0x1800237f1`
- `ntdll!RtlEnterCriticalSection` at `0x1800237f1`

## string_xrefs

- `0x180023a5c`: `onecore\ds\netapi\svcdlls\logonsrv\server\dns.cxx`
- `0x180023a7f`: `onecore\ds\netapi\svcdlls\logonsrv\server\dns.cxx`
- `0x180023aa9`: `NlDnsWriteBinaryLog: not written to binary log file.`
- `0x180023acf`: `\system32\config\netlogon.dnb`

## pseudocode

```c

```
