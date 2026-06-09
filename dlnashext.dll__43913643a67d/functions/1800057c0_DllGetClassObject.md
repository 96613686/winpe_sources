# DllGetClassObject

- ea: `0x1800057c0`
- end: `0x1800059f2`
- name: `DllGetClassObject`
- size: `562`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800057c0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800057ed`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800057ed`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800058e8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800058e8`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005959`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800059a4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180005959`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800059a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005947`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005947`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005985`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005999`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005985`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005999`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800058ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800058fd`

## pseudocode

```c

```
