# CRdpUdpPortRedirectorEndpoint::Receive(uchar *,unsigned __int64,ulong *,sockaddr_storage *,in6_addr *)

- ea: `0x180145b30`
- end: `0x180145d7c`
- name: `?Receive@CRdpUdpPortRedirectorEndpoint@@MEAAJPEAE_KPEAKPEAUsockaddr_storage@@PEAUin6_addr@@@Z`
- size: `588`
- prototype: `int(CRdpUdpPortRedirectorEndpoint *__hidden this, unsigned __int8 *, unsigned __int64, unsigned int *, struct sockaddr_storage *, struct in6_addr *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180016ad0`
- `0x1800506ac`
- `0x180078820`
- `0x180079624`
- `0x180125aa0`
- `0x180125db0`
- `0x180145b30`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180145bec`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180145bec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180145b8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180145b8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145d57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180145d57`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180145d4c`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180145d4c`

## string_xrefs

- `0x180145baa`: `No read buffer available in CRdpUdpPortRedirectorEndpoint::Receive. Ignoring the event.`

## pseudocode

```c

```
