# CGroupPolicySession::ExecuteLogonScriptsAsync(void *)

- ea: `0x1800230c0`
- end: `0x1800234de`
- name: `?ExecuteLogonScriptsAsync@CGroupPolicySession@@CAKPEAX@Z`
- size: `1054`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800230c0`
- `0x1800234e4`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002332d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18002332d`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18002311c`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18002311c`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800231b6`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800231b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002317f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002340e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002345d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002348e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023143`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002317f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800231d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002340e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002345d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002348e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800234c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800234c3`

## string_xrefs

- `0x180023149`: `CGroupPolicySession::ExecuteLogonScriptsAsync - CreateWaitableTimer failed with error %d.`
- `0x180023185`: `CGroupPolicySession::ExecuteLogonScriptsAsync - CreateWaitableTimer failed with error %d.`
- `0x180023352`: `CGroupPolicySession::ExecuteLogonScriptsAsync: Completed script delay.`
- `0x18002337f`: `CGroupPolicySession::ExecuteLogonScriptsAsync: Completed script delay.`

## pseudocode

```c

```
