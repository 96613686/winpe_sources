# HTTP_HANDLER::IoCompletionCallback(_TP_CALLBACK_INSTANCE *,void *,void *,ulong,unsigned __int64,_TP_IO *)

- ea: `0x18005b540`
- end: `0x18005b638`
- name: `?IoCompletionCallback@HTTP_HANDLER@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z`
- size: `248`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PVOID Overlapped, ULONG IoResult, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001274`
- `0x18005b540`
- `0x18005b640`
- `0x18005ba74`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b5b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005b5b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b592`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b616`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b592`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005b616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b584`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b5a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b608`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b584`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b5a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005b608`
- `HTTPAPI!HttpCancelHttpRequest` at `0x18005b5f1`
- `HTTPAPI!HttpCancelHttpRequest` at `0x18005b5f1`

## pseudocode

```c

```
