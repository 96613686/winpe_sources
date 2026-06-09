# CWebPlatformTridentHost::AggregatedNavigation2(ulong,IBindCtx *,IBindStatusCallback *,ushort const *,IUri *,ushort const *)

- ea: `0x1809f6ca0`
- end: `0x1809f7199`
- name: `?AggregatedNavigation2@CWebPlatformTridentHost@@UEAAJKPEAUIBindCtx@@PEAUIBindStatusCallback@@PEBGPEAUIUri@@2@Z`
- size: `1273`
- prototype: `__int64 __fastcall(CWebPlatformTridentHost *this, unsigned int, struct IBindCtx *, struct IBindStatusCallback *, unsigned __int16 *, struct IUri *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1809fbaf0`

## callees

- `0x180013efc`
- `0x1800c5000`
- `0x1804e4c1c`
- `0x1809f6ca0`
- `0x1809fe64c`
- `0x1809fe970`
- `0x181096e88`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1809f6f65`
- `KERNEL32!LocalFree` at `0x1809f7113`
- `KERNEL32!LocalFree` at `0x1809f6f65`
- `KERNEL32!LocalFree` at `0x1809f7113`
- `KERNEL32!LocalAlloc` at `0x1809f6f15`
- `KERNEL32!LocalAlloc` at `0x1809f6f15`
- `iertutil!CreateUriWithFragment` at `0x1809f6d76`
- `iertutil!CreateUriWithFragment` at `0x1809f6d76`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809f7138`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809f7148`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809f7138`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1809f7148`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809f6f54`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809f6f86`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809f6f54`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x1809f6f86`
- `ole32!ReleaseStgMedium` at `0x1809f7128`
- `ole32!ReleaseStgMedium` at `0x1809f7128`
- `OLEAUT32!__imp_SysAllocString` at `0x1809f6e87`
- `OLEAUT32!__imp_SysAllocString` at `0x1809f6e87`
- `OLEAUT32!__imp_SysFreeString` at `0x1809f70f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1809f7158`
- `OLEAUT32!__imp_SysFreeString` at `0x1809f7167`
- `OLEAUT32!__imp_SysFreeString` at `0x1809f70f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1809f7158`
- `OLEAUT32!__imp_SysFreeString` at `0x1809f7167`

## pseudocode

```c

```
