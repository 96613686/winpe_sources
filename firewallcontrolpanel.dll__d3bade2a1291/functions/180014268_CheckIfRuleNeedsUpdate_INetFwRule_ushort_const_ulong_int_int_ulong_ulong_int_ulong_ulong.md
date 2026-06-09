# CheckIfRuleNeedsUpdate(INetFwRule *,ushort const *,ulong,int,int,ulong,ulong,int &,ulong *,ulong *)

- ea: `0x180014268`
- end: `0x180014427`
- name: `?CheckIfRuleNeedsUpdate@@YAJPEAUINetFwRule@@PEBGKHHKKAEAHPEAK3@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct INetFwRule *, const unsigned __int16 *, unsigned int, int, int, unsigned int, unsigned int, int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180013e3c`

## callees

- `0x180008b30`
- `0x180014268`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800142e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800142e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180014407`
- `OLEAUT32!__imp_SysFreeString` at `0x180014407`

## pseudocode

```c

```
