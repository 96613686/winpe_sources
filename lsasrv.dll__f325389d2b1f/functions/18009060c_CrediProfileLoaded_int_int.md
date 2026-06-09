# CrediProfileLoaded(int,int)

- ea: `0x18009060c`
- end: `0x180090aca`
- name: `?CrediProfileLoaded@@YAJHH@Z`
- size: `1214`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800905f0`
- `0x1800f4470`

## callees

- `0x18000111c`
- `0x180011278`
- `0x18003a68c`
- `0x18003ff10`
- `0x18004091c`
- `0x180041e80`
- `0x180044860`
- `0x180061df8`
- `0x18007b0bc`
- `0x18007b1c8`
- `0x18007b49c`
- `0x18009060c`
- `0x180095014`
- `0x1800b86d0`
- `0x1800c6f18`
- `0x1800c6fc4`
- `0x1800c7068`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090888`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x180090821`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x180090821`
- `ntdll!NtClose` at `0x1800909b5`
- `ntdll!NtClose` at `0x1800909b5`
- `ntdll!RtlLeaveCriticalSection` at `0x1800909ca`
- `ntdll!RtlLeaveCriticalSection` at `0x1800909ca`
- `ntdll!RtlEnterCriticalSection` at `0x180090778`
- `ntdll!RtlEnterCriticalSection` at `0x180090788`
- `ntdll!RtlEnterCriticalSection` at `0x180090778`
- `ntdll!RtlEnterCriticalSection` at `0x180090788`
- `ntdll!NtOpenThreadToken` at `0x1800907dd`
- `ntdll!NtOpenThreadToken` at `0x1800907dd`
- `RPCRT4!RpcRevertToSelf` at `0x1800909ed`
- `RPCRT4!RpcRevertToSelf` at `0x1800909ed`
- `USERENV!GetProfileType` at `0x18009085b`
- `USERENV!GetProfileType` at `0x18009085b`

## pseudocode

```c

```
