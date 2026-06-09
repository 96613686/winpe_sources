# util_SearchRegistryForSwitch(ushort const *,ushort const *,REGISTRY_ARG_TYPE *)

- ea: `0x1400376ac`
- end: `0x1400378fe`
- name: `?util_SearchRegistryForSwitch@@YAJPEBG0PEAW4REGISTRY_ARG_TYPE@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(const unsigned __int16 *, OLECHAR *psz, enum REGISTRY_ARG_TYPE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140021048`

## callees

- `0x140001020`
- `0x140004a0c`
- `0x140004a98`
- `0x14001fa6c`
- `0x14002fe10`
- `0x140033ab0`
- `0x1400376ac`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140037881`
- `ADVAPI32!RegCloseKey` at `0x140037881`
- `OLEAUT32!__imp_SysAllocString` at `0x1400376fb`
- `OLEAUT32!__imp_SysAllocString` at `0x1400377b6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400376fb`
- `OLEAUT32!__imp_SysAllocString` at `0x1400377b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1400377ad`
- `OLEAUT32!__imp_SysFreeString` at `0x14003784c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003788b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400377ad`
- `OLEAUT32!__imp_SysFreeString` at `0x14003784c`
- `OLEAUT32!__imp_SysFreeString` at `0x14003788b`

## string_xrefs

- `0x14003771a`: `\AppCommandLine\`
- `0x1400377cf`: `\AppCommandLine`

## pseudocode

```c

```
