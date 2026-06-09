# CQueryCallback::OnQueryResultUpdate(_DEV_QUERY_RESULT_ACTION,ushort const *,ulong,_DEVPROPERTY * const)

- ea: `0x180008ba0`
- end: `0x180009164`
- name: `?OnQueryResultUpdate@CQueryCallback@@UEAAJW4_DEV_QUERY_RESULT_ACTION@@PEBGKQEAU_DEVPROPERTY@@@Z`
- size: `1476`
- prototype: `int __high(enum _DEV_QUERY_RESULT_ACTION, const unsigned __int16 *, unsigned int, struct _DEVPROPERTY *const)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800634a0`
- `0x1800634b0`

## callees

- `0x180007500`
- `0x18000759c`
- `0x180008ba0`
- `0x180009170`
- `0x180009220`
- `0x180009250`
- `0x180009434`
- `0x180009800`
- `0x1800359c0`
- `0x18007e9cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008dc1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008dc1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008e4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008d7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008d8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008e64`

## pseudocode

```c

```
