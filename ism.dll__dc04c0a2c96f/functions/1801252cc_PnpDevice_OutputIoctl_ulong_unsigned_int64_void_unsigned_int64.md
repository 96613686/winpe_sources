# PnpDevice::OutputIoctl(ulong,unsigned __int64,void *,unsigned __int64 *)

- ea: `0x1801252cc`
- end: `0x1801253c5`
- name: `?OutputIoctl@PnpDevice@@QEAAJK_KPEAXPEA_K@Z`
- size: `249`
- prototype: `__int64 __usercall@<rax>(PnpDevice *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18012628c`

## callees

- `0x18008daac`
- `0x180124cc0`
- `0x1801252cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012536d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012536d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801252fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801252fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801253ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801253ad`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180125363`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180125363`

## pseudocode

```c

```
