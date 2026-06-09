# GetPropertyBStr(IConfigNode *,_GUID const &,tagVARIANT *)

- ea: `0x18005a960`
- end: `0x18005abcd`
- name: `?GetPropertyBStr@@YAJPEAUIConfigNode@@AEBU_GUID@@PEAUtagVARIANT@@@Z`
- size: `621`
- prototype: `int(struct IConfigNode *, const struct _GUID *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18005a724`

## callees

- `0x180008de0`
- `0x18005a960`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005aace`
- `OLEAUT32!__imp_SysAllocString` at `0x18005aace`
- `OLEAUT32!__imp_VariantInit` at `0x18005a9b5`
- `OLEAUT32!__imp_VariantInit` at `0x18005a9c5`
- `OLEAUT32!__imp_VariantInit` at `0x18005a9b5`
- `OLEAUT32!__imp_VariantInit` at `0x18005a9c5`
- `OLEAUT32!__imp_VariantClear` at `0x18005aba7`
- `OLEAUT32!__imp_VariantClear` at `0x18005aba7`
- `OLEAUT32!__imp_VariantCopy` at `0x18005ab78`
- `OLEAUT32!__imp_VariantCopy` at `0x18005ab78`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005aa72`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005ab18`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005ab5f`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005aa72`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005ab18`
- `OLEAUT32!__imp_VariantChangeType` at `0x18005ab5f`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18005aa91`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18005aa91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ab8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005ab8f`
- `dmiso8601utils!SystemTimeToISO8601String` at `0x18005aab4`
- `dmiso8601utils!SystemTimeToISO8601String` at `0x18005aab4`

## pseudocode

```c

```
