# LDAP_REQUEST::Authenticate(_SecHandle *,SslSecurityState *)

- ea: `0x18035f110`
- end: `0x180360363`
- name: `?Authenticate@LDAP_REQUEST@@QEAA?AW4DecryptReturnValues@@PEAU_SecHandle@@PEAW4SslSecurityState@@@Z`
- size: `4691`
- prototype: `__int64 __fastcall(__int64, struct _SecHandle *, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1803604e0`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001ea60`
- `0x180030af8`
- `0x180030b60`
- `0x18003e2e0`
- `0x18007cf4c`
- `0x180180c50`
- `0x180181ae0`
- `0x180181bf0`
- `0x180207b4c`
- `0x180325718`
- `0x180352428`
- `0x180352568`
- `0x18035acb8`
- `0x18035f110`
- `0x180362e44`
- `0x180364d5c`
- `0x180366940`
- `0x18036ad58`
- `0x1804533b8`

## import_xrefs

- `NTDSATQ!AtqWriteSocket` at `0x18035fcc7`
- `NTDSATQ!AtqWriteSocket` at `0x18035fcc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035f519`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804736fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18035f519`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1804736fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18035f4a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18035f4a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18035f534`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180473718`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18035f534`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180473718`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18035f358`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18035f358`
- `SspiCli!AcceptSecurityContext` at `0x18035f501`
- `SspiCli!AcceptSecurityContext` at `0x18035f501`
- `Secur32!SeciAllocateAndSetIPAddress` at `0x18035f382`
- `Secur32!SeciAllocateAndSetIPAddress` at `0x18035f382`
- `Secur32!SeciFreeCallContext` at `0x18035f526`
- `Secur32!SeciFreeCallContext` at `0x18035f526`

## pseudocode

```c

```
