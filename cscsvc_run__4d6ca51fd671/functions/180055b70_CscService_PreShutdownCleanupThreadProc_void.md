# CscService_PreShutdownCleanupThreadProc(void *)

- ea: `0x180055b70`
- end: `0x180055e1e`
- name: `?CscService_PreShutdownCleanupThreadProc@@YAKPEAX@Z`
- size: `686`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180055970`

## callees

- `0x18000c3f0`
- `0x180025e4c`
- `0x18003c460`
- `0x18003c964`
- `0x1800541ec`
- `0x180055b70`
- `0x1800561b0`
- `0x180056214`
- `0x180056264`
- `0x18005628c`
- `0x1800562f4`
- `0x1800567cc`
- `0x18005e754`
- `0x1800828a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055dfa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180055dfa`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180055d0a`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180055d44`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180055d0a`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180055d44`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055d56`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180055d56`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180055c86`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180055c86`

## pseudocode

```c

```
