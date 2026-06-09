# ATL::CAtlModule::UpdateRegistryFromResource(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x14003639c`
- end: `0x140036771`
- name: `?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `981`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140036780`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002140`
- `0x1400341ec`
- `0x140034294`
- `0x1400344fc`
- `0x1400361c0`
- `0x14003639c`
- `0x1400638f8`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x140036417`
- `KERNEL32!InitializeCriticalSectionEx` at `0x140036417`
- `KERNEL32!GetModuleFileNameW` at `0x1400364ba`
- `KERNEL32!GetModuleFileNameW` at `0x1400364ba`
- `KERNEL32!GetModuleHandleW` at `0x140036531`
- `KERNEL32!GetModuleHandleW` at `0x140036531`
- `KERNEL32!GetLastError` at `0x140036421`
- `KERNEL32!GetLastError` at `0x140036421`
- `KERNEL32!EnterCriticalSection` at `0x140036452`
- `KERNEL32!EnterCriticalSection` at `0x140036541`
- `KERNEL32!EnterCriticalSection` at `0x140036610`
- `KERNEL32!EnterCriticalSection` at `0x1400366af`
- `KERNEL32!EnterCriticalSection` at `0x140036452`
- `KERNEL32!EnterCriticalSection` at `0x140036541`
- `KERNEL32!EnterCriticalSection` at `0x140036610`
- `KERNEL32!EnterCriticalSection` at `0x1400366af`
- `KERNEL32!LeaveCriticalSection` at `0x140036471`
- `KERNEL32!LeaveCriticalSection` at `0x14003656b`
- `KERNEL32!LeaveCriticalSection` at `0x14003663a`
- `KERNEL32!LeaveCriticalSection` at `0x1400366d9`
- `KERNEL32!LeaveCriticalSection` at `0x140036471`
- `KERNEL32!LeaveCriticalSection` at `0x14003656b`
- `KERNEL32!LeaveCriticalSection` at `0x14003663a`
- `KERNEL32!LeaveCriticalSection` at `0x1400366d9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14003666b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14003666b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140036663`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140036663`

## string_xrefs

- `0x140036717`: `REGISTRY`
- `0x140036742`: `REGISTRY`

## pseudocode

```c

```
