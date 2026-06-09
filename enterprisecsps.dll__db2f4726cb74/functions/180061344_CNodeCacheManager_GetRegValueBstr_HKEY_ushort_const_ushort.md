# CNodeCacheManager::GetRegValueBstr(HKEY__ *,ushort const *,ushort * *)

- ea: `0x180061344`
- end: `0x18006146b`
- name: `?GetRegValueBstr@CNodeCacheManager@@AEAAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `295`
- prototype: `int(CNodeCacheManager *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800607f8`
- `0x180060a78`
- `0x180060af0`
- `0x1800611c8`

## callees

- `0x180061344`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800613dc`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800613dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180061442`
- `OLEAUT32!__imp_SysFreeString` at `0x180061442`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800613ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800613ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061414`

## pseudocode

```c

```
