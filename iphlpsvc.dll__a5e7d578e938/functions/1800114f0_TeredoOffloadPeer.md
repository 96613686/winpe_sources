# TeredoOffloadPeer

- ea: `0x1800114f0`
- end: `0x1800119a7`
- name: `TeredoOffloadPeer`
- size: `1207`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000fd90`

## callees

- `0x18000d7c0`
- `0x1800114f0`
- `0x1800153d0`
- `0x1800190f0`
- `0x18004b5f0`
- `0x18004c188`
- `0x180051b40`
- `0x180083010`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180011744`
- `ntdll!RtlIpv6AddressToStringW` at `0x18001175b`
- `ntdll!RtlIpv6AddressToStringW` at `0x180011744`
- `ntdll!RtlIpv6AddressToStringW` at `0x18001175b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116fa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011874`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011925`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011874`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011925`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800116ea`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800116ea`
- `WS2_32!__imp_ntohl` at `0x18001162c`
- `WS2_32!__imp_ntohl` at `0x180011648`
- `WS2_32!__imp_ntohl` at `0x18001162c`
- `WS2_32!__imp_ntohl` at `0x180011648`
- `WS2_32!__imp_ntohs` at `0x180011663`
- `WS2_32!__imp_ntohs` at `0x18001167f`
- `WS2_32!__imp_ntohs` at `0x180011663`
- `WS2_32!__imp_ntohs` at `0x18001167f`

## string_xrefs

- `0x180011576`: `Attempting to offload peer 0x%p.`
- `0x1800115db`: `Re-offloading peer 0x%p on timeout (was %i, last attempt at 0x%016I64x, time 0x%016I64x).`
- `0x1800118e5`: `Max offload attempts exceeded for peer.`
- `0x1800118ad`: `Not re-offloading peer 0x%p yet (last attempt at 0x%016I64x, time 0x%016I64x).`

## pseudocode

```c

```
