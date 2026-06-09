# DnsFwQueryCompletionRoutine(void *,_DNS_QUERY_RAW_RESULT *)

- ea: `0x18006f980`
- end: `0x18006fae7`
- name: `?DnsFwQueryCompletionRoutine@@YAXPEAXPEAU_DNS_QUERY_RAW_RESULT@@@Z`
- size: `359`
- prototype: `void __fastcall(struct _DNS_FORWARD_CONTEXT *lpMem, struct _DNS_QUERY_RAW_RESULT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180008b00`
- `0x18004368c`
- `0x18006f980`
- `0x180086700`
- `0x180086b1c`
- `0x180086f78`

## import_xrefs

- `DNSAPI!DnsQueryRawResultFree` at `0x18006fab2`
- `DNSAPI!DnsQueryRawResultFree` at `0x18006fab2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006fa8a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006fa8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fa7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fa7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa4c`

## pseudocode

```c

```
