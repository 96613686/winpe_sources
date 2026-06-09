# CGroupPolicySession::DeleteSession(ulong)

- ea: `0x180056624`
- end: `0x180056859`
- name: `?DeleteSession@CGroupPolicySession@@QEAAXK@Z`
- size: `565`
- prototype: `void __fastcall(CGroupPolicySession *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d2c`

## callees

- `0x18004df78`
- `0x180056624`
- `0x180075ec0`
- `0x18007d304`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056665`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056665`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800566e1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800566e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005673e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005673e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800566bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800566bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056794`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005682f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005682f`

## string_xrefs

- `0x180056701`: `CGroupPolicySession::DeleteSession: Beginning WaitForSingleObject.`
- `0x180056725`: `CGroupPolicySession::DeleteSession: Beginning WaitForSingleObject.`
- `0x1800567c5`: `CGroupPolicySession::DeleteSession: Completed WaitForSingleObject.`
- `0x1800567e9`: `CGroupPolicySession::DeleteSession: Completed WaitForSingleObject.`

## pseudocode

```c

```
