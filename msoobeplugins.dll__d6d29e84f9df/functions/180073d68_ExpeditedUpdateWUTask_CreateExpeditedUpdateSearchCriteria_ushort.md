# ExpeditedUpdateWUTask::CreateExpeditedUpdateSearchCriteria(ushort * *)

- ea: `0x180073d68`
- end: `0x180073e9b`
- name: `?CreateExpeditedUpdateSearchCriteria@ExpeditedUpdateWUTask@@AEAAJPEAPEAG@Z`
- size: `307`
- prototype: `__int64 __fastcall(ExpeditedUpdateWUTask *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073adc`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180008544`
- `0x180073d68`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073dde`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180073dde`
- `OLEAUT32!__imp_SysAllocString` at `0x180073e5c`
- `OLEAUT32!__imp_SysAllocString` at `0x180073e5c`

## string_xrefs

- `0x180073dcb`: `UUPUpdateCriteria`
- `0x180073e4b`: `ExpeditedUpdateWUTask search criteria: [%s]`
- `0x180073e10`: `IsInstalled=0 AND DeploymentAction=*`
- `0x180073e17`: `IsInstalled=0 AND DeploymentAction=*`
- `0x180073e35`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`

## pseudocode

```c

```
