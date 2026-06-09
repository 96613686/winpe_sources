# ClRtlGetIADsSecurityDescriptor(IADs *,IADsSecurityDescriptor * *,ProvideSpecialPermissionsErrorStep *)

- ea: `0x1800a0250`
- end: `0x1800a0314`
- name: `?ClRtlGetIADsSecurityDescriptor@@YAJPEAUIADs@@PEAPEAUIADsSecurityDescriptor@@PEAW4ProvideSpecialPermissionsErrorStep@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(struct IADs *, struct IADsSecurityDescriptor **, enum ProvideSpecialPermissionsErrorStep *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a0940`

## callees

- `0x1800a0250`
- `0x1800b5010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800a027f`
- `OLEAUT32!__imp_VariantInit` at `0x1800a027f`
- `OLEAUT32!__imp_VariantClear` at `0x1800a02e8`
- `OLEAUT32!__imp_VariantClear` at `0x1800a02e8`

## string_xrefs

- `0x1800a0293`: `nTSecurityDescriptor`

## pseudocode

```c

```
