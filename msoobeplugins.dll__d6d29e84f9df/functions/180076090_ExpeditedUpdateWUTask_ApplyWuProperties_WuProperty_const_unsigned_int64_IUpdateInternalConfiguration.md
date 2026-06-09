# ExpeditedUpdateWUTask::_ApplyWuProperties(WuProperty const *,unsigned __int64,IUpdateInternalConfiguration *)

- ea: `0x180076090`
- end: `0x1800761e9`
- name: `?_ApplyWuProperties@ExpeditedUpdateWUTask@@AEAAJPEBUWuProperty@@_KPEAUIUpdateInternalConfiguration@@@Z`
- size: `345`
- prototype: `__int64 __fastcall(ExpeditedUpdateWUTask *__hidden this, const struct WuProperty *, unsigned __int64, struct IUpdateInternalConfiguration *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180075f28`
- `0x180075fdc`

## callees

- `0x180008544`
- `0x180076090`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800760ed`
- `OLEAUT32!__imp_VariantInit` at `0x1800760f8`
- `OLEAUT32!__imp_VariantInit` at `0x1800760ed`
- `OLEAUT32!__imp_VariantInit` at `0x1800760f8`
- `OLEAUT32!__imp_VariantClear` at `0x180076186`
- `OLEAUT32!__imp_VariantClear` at `0x180076191`
- `OLEAUT32!__imp_VariantClear` at `0x1800761de`
- `OLEAUT32!__imp_VariantClear` at `0x180076186`
- `OLEAUT32!__imp_VariantClear` at `0x180076191`
- `OLEAUT32!__imp_VariantClear` at `0x1800761de`

## string_xrefs

- `0x1800760b8`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x1800761c9`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076146`: `Applying WU configuration property [0x%08X] of type [%d] with values [%d] | [%d]`

## pseudocode

```c

```
