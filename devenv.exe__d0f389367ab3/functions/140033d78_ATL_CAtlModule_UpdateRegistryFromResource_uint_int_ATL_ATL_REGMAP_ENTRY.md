# ATL::CAtlModule::UpdateRegistryFromResource(uint,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x140033d78`
- end: `0x1400340b3`
- name: `?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `827`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, unsigned int, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x1400340c0`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002140`
- `0x140033d78`
- `0x1400341ec`
- `0x140034294`
- `0x1400344fc`
- `0x1400361c0`
- `0x1400638f8`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x140033df3`
- `KERNEL32!InitializeCriticalSectionEx` at `0x140033df3`
- `KERNEL32!GetModuleFileNameW` at `0x140033e8f`
- `KERNEL32!GetModuleFileNameW` at `0x140033e8f`
- `KERNEL32!GetModuleHandleW` at `0x140033f09`
- `KERNEL32!GetModuleHandleW` at `0x140033f09`
- `KERNEL32!GetLastError` at `0x140033dfd`
- `KERNEL32!GetLastError` at `0x140033dfd`
- `KERNEL32!EnterCriticalSection` at `0x140033e33`
- `KERNEL32!EnterCriticalSection` at `0x140033f19`
- `KERNEL32!EnterCriticalSection` at `0x140033fa6`
- `KERNEL32!EnterCriticalSection` at `0x140033fe4`
- `KERNEL32!EnterCriticalSection` at `0x140033e33`
- `KERNEL32!EnterCriticalSection` at `0x140033f19`
- `KERNEL32!EnterCriticalSection` at `0x140033fa6`
- `KERNEL32!EnterCriticalSection` at `0x140033fe4`
- `KERNEL32!LeaveCriticalSection` at `0x140033e4e`
- `KERNEL32!LeaveCriticalSection` at `0x140033fc8`
- `KERNEL32!LeaveCriticalSection` at `0x140034009`
- `KERNEL32!LeaveCriticalSection` at `0x140033e4e`
- `KERNEL32!LeaveCriticalSection` at `0x140033fc8`
- `KERNEL32!LeaveCriticalSection` at `0x140034009`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14003406a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14003406a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140034062`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140034062`

## string_xrefs

- `0x140034088`: `REGISTRY`

## pseudocode

```c

```
