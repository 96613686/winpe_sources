# Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *,IErrorInfo * *)

- ea: `0x18002b488`
- end: `0x18002b5b6`
- name: `?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@PEAPEAUIErrorInfo@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(struct IAppHostAdminManager *, const unsigned __int16 *, const unsigned __int16 *, struct IAppHostElement **, struct IErrorInfo **)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800026b4`
- `0x18000cb74`
- `0x18000d7e0`
- `0x18000d8e0`
- `0x180014c6c`
- `0x1800150d0`
- `0x18001ea20`
- `0x180029b4c`
- `0x18003e17c`
- `0x180043f78`

## callees

- `0x18002b488`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b4ad`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b4c8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b4ad`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b4c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b57d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b58b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b57d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b58b`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002b544`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002b544`
- `iisutil!PuDbgPrintError` at `0x18002b537`
- `iisutil!PuDbgPrintError` at `0x18002b537`

## string_xrefs

- `0x18002b51a`: `Config_GetSection`

## pseudocode

```c

```
