# util_GetPackageRegistryStrings(ATL::CComBSTR const &,ATL::CComBSTR const &,_GUID const &,ATL::CComBSTR &,ushort * *,ulong *,ushort * *)

- ea: `0x140039248`
- end: `0x14003949d`
- name: `?util_GetPackageRegistryStrings@@YA?AW4GetPackageRegistryStringResult@@AEBVCComBSTR@ATL@@0AEBU_GUID@@AEAV23@PEAPEAGPEAK3@Z`
- size: `597`
- prototype: `enum GetPackageRegistryStringResult __high(const struct ATL::CComBSTR *, const struct ATL::CComBSTR *, const struct _GUID *, struct ATL::CComBSTR *, unsigned __int16 **, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003fe5c`

## callees

- `0x140001020`
- `0x140004a0c`
- `0x140004a98`
- `0x140004f28`
- `0x14000b118`
- `0x14002fe10`
- `0x140033ab0`
- `0x140039084`
- `0x140039248`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140039451`
- `ADVAPI32!RegCloseKey` at `0x140039451`
- `ole32!StringFromGUID2` at `0x140039300`
- `ole32!StringFromGUID2` at `0x140039300`
- `OLEAUT32!__imp_SysFreeString` at `0x14003945d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003945d`

## string_xrefs

- `0x1400392d7`: `CompanyName`

## pseudocode

```c

```
