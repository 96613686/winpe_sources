# CZDPTask::_BeginAsyncInstall(IUpdateInstaller *,IUpdateCollection *,void *,IInstallationJob * *)

- ea: `0x180056f68`
- end: `0x1800570ff`
- name: `?_BeginAsyncInstall@CZDPTask@@AEAAJPEAUIUpdateInstaller@@PEAUIUpdateCollection@@PEAXPEAPEAUIInstallationJob@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(CZDPTask *__hidden this, struct IUpdateInstaller *, struct IUpdateCollection *, void *, struct IInstallationJob **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180057830`

## callees

- `0x180007bbc`
- `0x180055818`
- `0x180055a98`
- `0x180056f68`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180057058`
- `OLEAUT32!__imp_VariantInit` at `0x180057058`
- `OLEAUT32!__imp_VariantClear` at `0x1800570b8`
- `OLEAUT32!__imp_VariantClear` at `0x1800570b8`

## string_xrefs

- `0x1800570a3`: `Failed to begin WU ZDP Install [hr=0x%08X]`
- `0x180056ffe`: `CZDPTask setting OOBE_GLOBAL_SETTING_ZDPSTATUS ZDP_Installing.`
- `0x1800570d7`: `Failed to put updates into IUpdateInstaller [hr=0x%08X]`

## pseudocode

```c

```
