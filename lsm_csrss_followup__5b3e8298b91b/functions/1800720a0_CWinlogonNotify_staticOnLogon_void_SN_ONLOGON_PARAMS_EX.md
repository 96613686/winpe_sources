# CWinlogonNotify::staticOnLogon(void *,_SN_ONLOGON_PARAMS_EX *)

- ea: `0x1800720a0`
- end: `0x1800722c6`
- name: `?staticOnLogon@CWinlogonNotify@@CAKPEAXPEAU_SN_ONLOGON_PARAMS_EX@@@Z`
- size: `550`
- prototype: `unsigned int __fastcall(void *, struct _SN_ONLOGON_PARAMS_EX *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x18000a6f0`
- `0x180015ef8`
- `0x180017a50`
- `0x18001ed10`
- `0x180028bbc`
- `0x18002bf6c`
- `0x18004b460`
- `0x1800720a0`
- `0x180097010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180072160`
- `ntdll!EtwEventActivityIdControl` at `0x180072160`
- `ntdll!RtlNtStatusToDosError` at `0x18007225c`
- `ntdll!RtlNtStatusToDosError` at `0x18007225c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072213`

## string_xrefs

- `0x180072194`: `CRpcUtils::GetClientToken failed: 0x%x in %s`

## pseudocode

```c

```
