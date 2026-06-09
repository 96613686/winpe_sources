# KerbGetAuthProxy(_KDC_PROXY_CACHE_ENTRY *)

- ea: `0x180098158`
- end: `0x1800984ce`
- name: `?KerbGetAuthProxy@@YAJPEAU_KDC_PROXY_CACHE_ENTRY@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(struct _KDC_PROXY_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005228c`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18000b300`
- `0x18006637c`
- `0x180070680`
- `0x18007108c`
- `0x1800736a4`
- `0x18008b70c`
- `0x180097f54`
- `0x180098158`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800981e9`
- `ntdll!RtlInitUnicodeString` at `0x180098367`
- `ntdll!RtlInitUnicodeString` at `0x180098376`
- `ntdll!RtlInitUnicodeString` at `0x1800981e9`
- `ntdll!RtlInitUnicodeString` at `0x180098367`
- `ntdll!RtlInitUnicodeString` at `0x180098376`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientUninitialize` at `0x180098491`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientUninitialize` at `0x180098491`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientDisconnectFromServer` at `0x180098486`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientDisconnectFromServer` at `0x180098486`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientInitialize` at `0x1800982cc`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientInitialize` at `0x1800982cc`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientGetProxyForUrl` at `0x180098344`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientGetProxyForUrl` at `0x180098344`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180098466`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180098476`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180098466`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180098476`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientConnectToServer` at `0x18009830a`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientConnectToServer` at `0x18009830a`

## string_xrefs

- `0x180098411`: `KerbGetAuthProxy: CacheEntry %p, Proxy %wZ, ProxyBypass %wZ, PorxyEpoch %d\n`

## pseudocode

```c

```
