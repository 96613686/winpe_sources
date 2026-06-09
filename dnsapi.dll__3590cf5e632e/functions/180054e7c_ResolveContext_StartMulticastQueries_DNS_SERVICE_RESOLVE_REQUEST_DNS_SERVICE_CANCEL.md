# ResolveContext::StartMulticastQueries(_DNS_SERVICE_RESOLVE_REQUEST *,_DNS_SERVICE_CANCEL *)

- ea: `0x180054e7c`
- end: `0x1800550ce`
- name: `?StartMulticastQueries@ResolveContext@@SAJPEAU_DNS_SERVICE_RESOLVE_REQUEST@@PEAU_DNS_SERVICE_CANCEL@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct _DNS_SERVICE_RESOLVE_REQUEST *, struct _DNS_SERVICE_CANCEL *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180054050`

## callees

- `0x18005464c`
- `0x180054e7c`
- `0x1800550d4`
- `0x18005536c`
- `0x18008bf98`
- `0x1800dbc44`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800dfdc8`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054f60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054f60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054fbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180054fbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055056`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055079`

## pseudocode

```c

```
