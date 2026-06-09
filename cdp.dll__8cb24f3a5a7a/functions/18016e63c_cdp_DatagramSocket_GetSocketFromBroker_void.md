# cdp::DatagramSocket::GetSocketFromBroker(void)

- ea: `0x18016e63c`
- end: `0x18016e6f4`
- name: `?GetSocketFromBroker@DatagramSocket@cdp@@AEAA_NXZ`
- size: `184`
- prototype: `bool __fastcall(cdp::DatagramSocket *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008b670`

## callees

- `0x18000f8d0`
- `0x1800113bc`
- `0x180030190`
- `0x18016e63c`
- `0x18016e6fc`
- `0x1801f6fb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016e698`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18016e698`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016e6a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18016e6a6`
- `sbservicetrigger!ServiceTriggerEnumerateTransferredSockets` at `0x18016e66e`
- `sbservicetrigger!ServiceTriggerEnumerateTransferredSockets` at `0x18016e66e`

## string_xrefs

- `0x18016e6b1`: `{"text":"Could not enumerate sockets from socket broker (return value = %u), will create our own"}`

## pseudocode

```c

```
