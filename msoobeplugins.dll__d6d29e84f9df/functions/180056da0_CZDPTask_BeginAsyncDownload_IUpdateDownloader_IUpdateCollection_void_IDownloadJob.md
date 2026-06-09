# CZDPTask::_BeginAsyncDownload(IUpdateDownloader *,IUpdateCollection *,void *,IDownloadJob * *)

- ea: `0x180056da0`
- end: `0x180056f60`
- name: `?_BeginAsyncDownload@CZDPTask@@AEAAJPEAUIUpdateDownloader@@PEAUIUpdateCollection@@PEAXPEAPEAUIDownloadJob@@@Z`
- size: `448`
- prototype: `int(CZDPTask *__hidden this, struct IUpdateDownloader *, struct IUpdateCollection *, void *, struct IDownloadJob **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x180057478`

## callees

- `0x180007bbc`
- `0x180055730`
- `0x1800559e8`
- `0x180056da0`
- `0x180058200`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180056eb3`
- `OLEAUT32!__imp_VariantInit` at `0x180056eb3`
- `OLEAUT32!__imp_VariantClear` at `0x180056f10`
- `OLEAUT32!__imp_VariantClear` at `0x180056f10`

## string_xrefs

- `0x180056f2c`: `Failed to put Priority into IUpdateDownloader [hr=0x%08X]`
- `0x180056e59`: `CZDPTask setting OOBE_GLOBAL_SETTING_ZDPSTATUS ZDP_Downloading.`
- `0x180056f35`: `Failed to put updates into IUpdateDownloader [hr=0x%08X]`

## pseudocode

```c

```
