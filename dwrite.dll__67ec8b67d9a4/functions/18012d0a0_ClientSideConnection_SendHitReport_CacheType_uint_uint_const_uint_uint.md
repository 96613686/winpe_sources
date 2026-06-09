# ClientSideConnection::SendHitReport(CacheType,uint,uint const *,uint,uint)

- ea: `0x18012d0a0`
- end: `0x18012d16d`
- name: `?SendHitReport@ClientSideConnection@@QEAAJW4CacheType@@IPEBIII@Z`
- size: `205`
- prototype: `int __high(enum CacheType, unsigned int, const unsigned int *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18012c130`
- `0x18012c958`

## callees

- `0x18012d0a0`
- `0x18012d1d4`
- `0x18012d230`
- `0x18012d284`
- `0x1801f37b0`
- `0x1801fa81c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012d0ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012d0ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012d14e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012d14e`

## pseudocode

```c

```
