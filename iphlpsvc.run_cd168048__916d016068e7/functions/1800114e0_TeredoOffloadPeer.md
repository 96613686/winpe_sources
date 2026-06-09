# TeredoOffloadPeer

- ea: `0x1800114e0`
- end: `0x180011997`
- name: `TeredoOffloadPeer`
- size: `1207`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000fd80`

## callees

- `0x18000d7b0`
- `0x1800114e0`
- `0x1800153c0`
- `0x1800190e0`
- `0x18004b630`
- `0x18004c1c8`
- `0x180051b80`
- `0x180083010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180011734`
- `ntdll!RtlIpv6AddressToStringW` at `0x18001174b`
- `ntdll!RtlIpv6AddressToStringW` at `0x180011734`
- `ntdll!RtlIpv6AddressToStringW` at `0x18001174b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116ea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011864`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011915`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011864`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011915`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800116da`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800116da`
- `WS2_32!__imp_ntohl` at `0x18001161c`
- `WS2_32!__imp_ntohl` at `0x180011638`
- `WS2_32!__imp_ntohl` at `0x18001161c`
- `WS2_32!__imp_ntohl` at `0x180011638`
- `WS2_32!__imp_ntohs` at `0x180011653`
- `WS2_32!__imp_ntohs` at `0x18001166f`
- `WS2_32!__imp_ntohs` at `0x180011653`
- `WS2_32!__imp_ntohs` at `0x18001166f`

## string_xrefs

- `0x180011566`: `Attempting to offload peer 0x%p.`
- `0x1800115cb`: `Re-offloading peer 0x%p on timeout (was %i, last attempt at 0x%016I64x, time 0x%016I64x).`
- `0x1800118d5`: `Max offload attempts exceeded for peer.`
- `0x18001189d`: `Not re-offloading peer 0x%p yet (last attempt at 0x%016I64x, time 0x%016I64x).`

## pseudocode

```c

```
