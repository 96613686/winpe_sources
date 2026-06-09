# CWinlogonNotify::staticOnLogon(void *,_SN_ONLOGON_PARAMS_EX *)

- ea: `0x180076200`
- end: `0x180076439`
- name: `?staticOnLogon@CWinlogonNotify@@CAKPEAXPEAU_SN_ONLOGON_PARAMS_EX@@@Z`
- size: `569`
- prototype: `unsigned int __fastcall(void *, struct _SN_ONLOGON_PARAMS_EX *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x1800077a0`
- `0x18000b978`
- `0x18000c684`
- `0x18000da1c`
- `0x1800125d0`
- `0x180020290`
- `0x18002ae18`
- `0x18002dfb0`
- `0x18004e850`
- `0x180076200`
- `0x18009c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800762c0`
- `ntdll!EtwEventActivityIdControl` at `0x1800762c0`
- `ntdll!RtlNtStatusToDosError` at `0x1800763c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800763c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076379`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076379`

## string_xrefs

- `0x1800762fa`: `CRpcUtils::GetClientToken failed: 0x%x in %s`

## pseudocode

```c

```
