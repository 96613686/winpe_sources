# util_GetPackageResourcesInstance(ushort const *,_GUID const &,bool,HINSTANCE__ * *,ulong *)

- ea: `0x14002fbd8`
- end: `0x14002fe0f`
- name: `?util_GetPackageResourcesInstance@@YAHPEBGAEBU_GUID@@_NPEAPEAUHINSTANCE__@@PEAK@Z`
- size: `567`
- prototype: `__int64 __fastcall(const unsigned __int16 *, GUID *rguid, bool, HINSTANCE *, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000b4a0`
- `0x140012440`
- `0x14003ff70`

## callees

- `0x140001020`
- `0x140004a0c`
- `0x140004a98`
- `0x14002fbd8`
- `0x14002fe10`
- `0x140032720`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002fd61`
- `ADVAPI32!RegCloseKey` at `0x14002fd91`
- `ADVAPI32!RegCloseKey` at `0x14002fd61`
- `ADVAPI32!RegCloseKey` at `0x14002fd91`
- `ole32!StringFromGUID2` at `0x14002fc6c`
- `ole32!StringFromGUID2` at `0x14002fc6c`
- `OLEAUT32!__imp_SysAllocString` at `0x14002fc39`
- `OLEAUT32!__imp_SysAllocString` at `0x14002fc39`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd6b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd74`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd7d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd9b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fda4`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fdad`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd6b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd74`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd7d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd9b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fda4`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fdad`

## string_xrefs

- `0x14002fcc1`: `\SatelliteDll`
- `0x14002fd04`: `DllName`

## pseudocode

```c

```
