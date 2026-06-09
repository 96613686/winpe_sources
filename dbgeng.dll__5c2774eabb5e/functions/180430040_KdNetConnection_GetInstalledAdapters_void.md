# KdNetConnection::GetInstalledAdapters(void)

- ea: `0x180430040`
- end: `0x1804300f9`
- name: `?GetInstalledAdapters@KdNetConnection@@QEAAPEAU_IP_ADAPTER_ADDRESSES_LH@@XZ`
- size: `185`
- prototype: `struct _IP_ADAPTER_ADDRESSES_LH *__fastcall(KdNetConnection *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180431c58`
- `0x180431cec`

## callees

- `0x180430040`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180430080`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1804300cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180430080`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1804300cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1804300e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1804300e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180430094`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180430094`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180430065`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1804300bd`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180430065`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1804300bd`

## pseudocode

```c

```
